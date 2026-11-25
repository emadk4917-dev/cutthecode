# BOOKED: the 4 prompts Claude used to build a café site with bookings

From Cut The Code's "POV: you're Claude" video. These are the **exact prompts** from our real run (Claude Code, 25 Nov 2026, about 6 minutes from prompt 1 to a passing booking test). Moth & Marmalade is a made-up café. Swap in your own business, prices and hours. Run them in order, in one Claude Code conversation, in an empty folder with `shot.js` (below) in it.

## 1. The plan
> It's 11pm. I run Moth & Marmalade, a small independent café on a corner in Sheffield (it's a made-up café for a demo, so no real address or phone number). We open at 7am tomorrow and I want people booking tables for weekend brunch from their phones. Menu: flat white £3.40, oat latte £3.60, sourdough toast with marmalade £4.50, full brunch plate £11.50, shakshuka £9.80. Open Mon to Fri 7am to 3pm, Sat and Sun 8am to 4pm. Before you build anything, write a short plan: who the page is for, the one thing every visitor should do, and every section top to bottom in one line each. Save it as PLAN.md.

## 2. The first draft
> Build index.html from PLAN.md. One file, mobile first. It needs a working booking form (name, day, time, number of people) that shows a confirmation on the page when you press the button. No backend, keep it in the page.

## 3. Screenshot it and fix it (this is where it caught "it looked like a template" and "booking was buried")
> Run node shot.js to screenshot index.html at phone width, then open shot.png and shot-top.png and look at them like the café owner would on her phone at 11pm. List the 3 biggest problems you see, especially anything that looks generic or AI-made, or anything that makes booking a table harder. Then fix them, with these design rules: don't make it look AI-made. No purple or blue gradients, no Inter, Roboto, Arial or system fonts, and no cookie-cutter hero with three icon cards. Pick one font pairing from Google Fonts and one accent colour that suits a cosy independent café, and commit to it. The Book a table button must be on the first screen. Then run node shot.js after.png and check the fixes actually worked.

## 4. Test a booking like a customer (this is where it caught the confirmation scrolling off screen)
> Now test the booking like a real customer would. Write book.js with Playwright: open index.html at 390px wide, fill in the booking form (name Sam, Saturday, 10:30, 4 people), press the button, check the confirmation appears with those details, and screenshot it as booked.png. Run node book.js. If anything fails, fix index.html and run it again until it passes. Tell me PASS or FAIL.

## shot.js (put this in the folder first; needs Node and `npm i playwright`)
```js
// node shot.js [out.png]  -> screenshots index.html at phone width (390px): first screen + full page
const {chromium}=require('playwright');const path=require('path');
(async()=>{const b=await chromium.launch();const p=await b.newPage({viewport:{width:390,height:844},deviceScaleFactor:2});
await p.goto('file://'+path.join(__dirname,'index.html'),{waitUntil:'networkidle'});await p.waitForTimeout(1200);
const out=process.argv[2]||'shot.png';await p.screenshot({path:path.join(__dirname,out),fullPage:true});
await p.screenshot({path:path.join(__dirname,out.replace('.png','-top.png'))});console.log('saved',out);await b.close()})();
```

**Honest notes:** the booking form is front-end only, so nothing is sent anywhere until you connect it to email, WhatsApp or a booking tool. Claude Code writes `book.js` itself in prompt 4. Results vary run to run; always look at the screenshots yourself.

## Bonus: the 3 subagent files from Episode 3 (planner, builder, tester)

From our Episode 3 film on Emergent. These are the **exact files** from our real recorded run (Claude Code, 25 Nov 2026). Save each one in `.claude/agents/` inside an empty folder, open Claude Code there and send the main prompt below. The tester needs Node and `npm i playwright`.

`.claude/agents/planner.md`
```markdown
---
name: planner
description: Writes PLAN.md for a one-page website before anything is built. Use it first.
tools: Read, Write
---
You plan, you never build. Write PLAN.md: who the page is for, the one thing every visitor
should do, and every section top to bottom in one line each. Keep it under 20 lines.
```

`.claude/agents/builder.md`
```markdown
---
name: builder
description: Builds or fixes index.html from PLAN.md, or from a tester report.
tools: Read, Write, Edit, Bash
---
You build index.html from PLAN.md: one file, mobile first, a booking form (name, day, time,
people) that shows a confirmation on the page. No backend. Don't make it look AI-made: no
purple or blue gradients, no Inter/Roboto/Arial, one font pairing and one accent colour.
If you are given a tester report, fix exactly what it says and nothing else.
```

`.claude/agents/tester.md`
```markdown
---
name: tester
description: Tests the booking like a real customer. Reports PASS or FAIL. Never edits the page.
tools: Read, Write, Bash
---
You never edit index.html. Write book.js with Playwright: open index.html at 390px wide,
fill the form (Sam, Saturday, 10:30, 4 people), press the button, check the confirmation shows
those details and is visible on screen, and save booked.png. Run node book.js.
Reply with PASS, or FAIL plus the one-line reason.
```

**The main prompt** (type it in Claude Code):
> Moth & Marmalade is a made-up café in Sheffield for a demo, so no real address or phone number. Build it a one-page site where people can book a table for weekend brunch from their phones. Use the planner subagent to write PLAN.md. Then use the builder subagent to build index.html from it. Then use the tester subagent to test a booking. If the tester reports FAIL, give its report to the builder to fix, then test again. Stop when the tester reports PASS, and tell me how many rounds it took.

**In our run:** the tester passed on round 1, so the builder never had to fix anything. Unasked, Claude also noticed that a name made only of spaces still books; the test didn't check for that.

**Honest notes:** the tester only checks what its file tells it to, so add the checks you care about (an empty or spaces-only name, a full time slot) to `tester.md`. The booking form is still front-end only. Results vary run to run, so always look at `booked.png` yourself.

cutthecode.co.uk
