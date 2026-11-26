# COPY: the free Claude Code skill that rewrites your homepage headline

Free · Cut The Code · checked 26 Nov 2026

**What this is:** the one command that installs 53 free marketing skills into Claude Code (Marketing Skills by coreyhaines31, MIT licence), and the exact prompt we used to run the `copywriting` skill on our own homepage hero. Plus the file it wrote, word for word.

**Our run:** we gave it a copy of our homepage. It kept our strongest line, cut the second line from **9 words to 4** ("Build yours with Claude."), and caught a mismatch we had missed: the headline sells AI employees, but the button offered a website prompt pack. It rewrote the button to say what you actually get, wrote 3 headline options with the reasons, and refused to add any claim it couldn't back up.

## 1. Install the skills (one line, in your project folder)

```
npx skills add coreyhaines31/marketingskills -a claude-code
```

Restart Claude Code. Skills run with Claude's permissions, so skim the ones you use first.

## 2. The prompt (from the video)

> Use the copywriting skill on index.html, our real homepage. Rewrite the hero: headline, subheadline and button. Give me 3 headline options and why each works, pick one, save it to hero-copy.md, then make index-v2.html with your pick in place. Don't ask me questions; use what's on the page.

Swap index.html for your own page. It only writes new files; your page stays as it is.

## 3. Follow-ups

> Do the same for the next section down, and keep every claim to what the page already proves.

> Write 2 versions of the button text and tell me how to A/B test them for a week.

## The honest catch

- **It won't invent proof.** If your page has no numbers, testimonials or results, it leaves a [NEED: ...] note instead of making them up. Add your real ones.
- It works from what's on the page. If the page is vague about who it's for, tell it in the prompt.
- Read the rewrite out loud before you publish it. You know your customers; it doesn't.

More free Claude Code guides: cutthecode.co.uk
