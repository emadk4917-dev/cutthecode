# The plan → build → check loop for Claude Code (website builds)

Free from Cut The Code · cutthecode.co.uk

Based on Anthropic's own guide, "Best practices for Claude Code" (https://code.claude.com/docs/en/best-practices). Their advice, in short: tell Claude what it can't see (a spec), then **give Claude a check to run**, because "Claude stops when the work looks done", and if nothing tells it whether the work actually *is* done, you end up being the tester.

This file has 3 parts:
1. **CLAUDE.md**, ready to paste into your project folder
2. **The review prompt**
3. **check.js**, the check itself (screenshots the page at phone size and tests it against your spec)

---

## 1. CLAUDE.md (paste this into a file called `CLAUDE.md` in your project folder)

```markdown
# How we build websites here: plan → build → check

## 1. Plan
- If there's no SPEC.md yet, don't write code. Interview me first with
  multiple-choice questions until you could write the spec, then write it to SPEC.md:
  who it's for, every section, the real content (prices, opening hours, address),
  and what "done" means.
- Once SPEC.md exists, I'll start a fresh session to build from it.

## 2. Build
- Build only what's in SPEC.md. Phone first (390px wide).
- Real content from SPEC.md only: no lorem ipsum, no placeholder prices.

## 3. Check (don't skip this)
- Check command: node check.js index.html shot.png
- Before you say it's done: run the check, open shot.png and compare it with SPEC.md.
- Fix every FAIL, then run the check again. Repeat until it says ALL PASS.
- When you report back, paste the check output and show me the screenshot.
  "Looks good" on its own isn't evidence.
```

## 2. The review prompt (paste into Claude Code once the build passes)

```text
use a subagent to review the site against SPEC.md. check every requirement in the spec is on the page and looks right in shot.png at phone width, report gaps a customer would notice, and skip style
```

(Adapted from the "Review against your spec" prompt in Anthropic's guide. Keep the "skip style" part: a reviewer asked to find problems will always find *something*.)

## 3. The plan prompt (first message in a new project)

```text
I want a one-page website for [business]. Interview me until you could write the spec, then write it to SPEC.md.
```

## 4. check.js (save next to your index.html)

Needs Node.js. Run once in the folder: `npm i playwright && npx playwright install chromium`.
Edit `REQUIRED` so it lists the facts from your SPEC.md that must be on the page.

```js
// check.js: screenshot the page on a phone and test it against your spec.
// Usage: node check.js index.html shot.png
const REQUIRED = ['Tue', 'Mon', 'Sat', 'Sun', '14 Harbour Road'];
const { chromium } = require('playwright'), path = require('path');
(async () => {
  const [file = 'index.html', out = 'shot.png'] = process.argv.slice(2);
  const b = await chromium.launch();
  const p = await b.newPage({ viewport: { width: 390, height: 844 }, deviceScaleFactor: 2 });
  await p.goto(file.startsWith('http') ? file : 'file://' + path.resolve(file), { waitUntil: 'networkidle' });
  await p.screenshot({ path: out, fullPage: true });
  const r = await p.evaluate((req) => {
    const W = document.documentElement.clientWidth, sw = document.documentElement.scrollWidth, txt = document.body.innerText;
    const small = [...document.querySelectorAll('a.btn, button, .btn, [role=button]')]
      .filter(e => { const h = e.getBoundingClientRect().height; return h > 0 && h < 44; }).map(e => e.textContent.trim());
    const missing = req.filter(s => !txt.includes(s));
    const tiny = [...document.querySelectorAll('p, li, td, span, a')].filter(e => e.offsetParent && parseFloat(getComputedStyle(e).fontSize) < 14).length;
    return [
      ['No horizontal scroll at 390px', sw <= W, sw > W ? `page is ${sw}px wide` : ''],
      ['Buttons at least 44px tall', !small.length, small.join(', ')],
      ['Everything from the spec is on the page', !missing.length, missing.length ? 'missing: ' + missing.join(', ') : ''],
      ['No text smaller than 14px', !tiny, tiny ? tiny + ' elements' : ''],
    ];
  }, REQUIRED);
  let fail = 0;
  for (const [name, ok, why] of r) { console.log((ok ? 'PASS ' : 'FAIL ') + name + (why ? '  (' + why + ')' : '')); if (!ok) fail++; }
  console.log(fail ? `${fail} to fix` : 'ALL PASS', '· screenshot:', out);
  await b.close(); process.exit(fail ? 1 : 0);
})();
```

## What it caught on our demo bakery site (the run in the video)

First build:
```
FAIL No horizontal scroll at 390px  (page is 528px wide)
FAIL Buttons at least 44px tall  (Pre-order for collection, Get directions)
FAIL Everything from the spec is on the page  (missing: Mon)
PASS No text smaller than 14px
3 to fix
```
After one fix: `ALL PASS`.

## Tips
- `button`-style links need the class `btn` (or be a real `<button>`) for the tap-size check to see them. Change the selector if your site uses something else.
- Want it enforced every time, not just most times? Anthropic's guide shows how to make the check a `Stop` hook, so Claude can't end its turn until it passes.

Cut The Code · cutthecode.co.uk
