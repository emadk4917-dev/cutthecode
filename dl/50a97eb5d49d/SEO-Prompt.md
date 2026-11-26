# SEO: the free Claude Code skill that audits your page for Google

Free · Cut The Code · checked 26 Nov 2026

**What this is:** the one command that installs 53 free marketing skills into Claude Code (Marketing Skills by coreyhaines31, MIT licence), and the exact prompt we used to run the `seo-audit` skill on our own homepage. Plus the fixes file it wrote, word for word.

**Our run:** we gave it a copy of our homepage. It wrote seo-fixes.md with **3 fixes and the exact line for each**: our title tag is 82 characters and Google cuts it off at about 60 (line 6), the headline doesn't name what we teach (line 195), and there's no Organization structured data (add it after line 18). It also listed what was already fine and what it couldn't check.

## 1. Install the skills (one line, in your project folder)

```
npx skills add coreyhaines31/marketingskills -a claude-code
```

Restart Claude Code. Skills run with Claude's permissions, so skim the ones you use first.

## 2. The prompt (from the video)

> Use the seo-audit skill on index.html, our real homepage. Give me the 3 fixes that matter most for Google, show the exact line in the HTML for each, and save it to seo-fixes.md.

Swap index.html for your page, or run it in your site's folder.

## 3. Follow-ups

> Make fix 1 and fix 2 in a copy of the page, and show me the before and after of each changed line.

> Check every other page in this folder for the same 3 problems and list them in one table.

## The honest catch

- **It only reads your files.** It can't see Google Search Console, your rankings or real speed data. Check Search Console first: if the page isn't indexed, none of these fixes matter yet.
- Its suggested wording is a starting point. Use the search phrases Search Console shows you already get.
- We haven't changed our homepage yet.

More free Claude Code guides: cutthecode.co.uk
