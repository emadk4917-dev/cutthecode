# EMAILS: the free Claude Code skill that writes your welcome emails

Free · Cut The Code · checked 26 Nov 2026

**What this is:** the one command that installs 53 free marketing skills into Claude Code (Marketing Skills by coreyhaines31, MIT licence), and the exact prompt we used to run the `emails` skill on our own sign-up page. Plus the file it wrote, word for word.

**Our run:** we gave it a copy of our free download page. It wrote **3 welcome emails** (send now, day 2, day 4) with subject lines, preview lines and one button each. It caught a mistake we'd have made: our form only collects an email address, so it left out the first-name greeting. And it matched every claim in the emails to a line on the page, leaving out prices and results the page doesn't state.

## 1. Install the skills (one line, in your project folder)

```
npx skills add coreyhaines31/marketingskills -a claude-code
```

Restart Claude Code. Skills run with Claude's permissions, so skim the ones you use first.

## 2. The prompt (from the video)

> Use the emails skill. setup.html is our real free download page. Write the 3 welcome emails someone should get after downloading it: subject lines, the emails, and when to send each. Keep every claim to what the page says. Save it to welcome-emails.md. Don't ask me questions.

Swap setup.html for your own sign-up page.

## 3. Follow-ups

> Add a 4th email for day 7 that introduces our paid offer, using only what's on the pricing page.

> Rewrite email 1 for someone who signed up from a YouTube Short, in under 80 words.

## The honest catch

- **It writes the emails. It doesn't send them.** You paste them into your email tool and switch the sequence on yourself.
- Check every link from a real inbox before you turn it on. It assumed one PDF address and told us to confirm it.
- It only knows what's on the page. If your page doesn't say it, the emails won't either.

More free Claude Code guides: cutthecode.co.uk
