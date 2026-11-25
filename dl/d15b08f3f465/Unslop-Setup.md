# unslop setup (1 page)
*Cut The Code · free · checked 25 Nov 2026.*

**What it is:** unslop is a free skill for Claude Code (also Codex and Google Antigravity) by Damir Sokolovsky. It turns vibecoded, AI-looking UI into a designed interface. It lists the slop first (purple gradients, glows, emoji labels, shouty copy, uneven spacing), proposes a direction from your product, then fixes the screen pass by pass.
**Official repo (always install from here):** https://github.com/heydamir/unslop  · licence CC BY 4.0 · 21,298 stars on 25 Nov 2026 (created 29 Oct 2026).
**Heads-up:** several other skills are also called "unslop" and do different things (some edit text). Make sure it's the heydamir one.

## 1. Install (2 minutes)
In a terminal, with Claude Code installed:
```
claude plugin install unslop --marketplace heydamir/unslop
```
Older Claude Code without `--marketplace`? Do it in two steps:
```
claude plugin marketplace add heydamir/unslop
claude plugin install unslop@heydamir
```
Then start a new Claude Code session (or run `/reload-plugins`).
Only want it in one project? Run the install from that project's folder and add `--scope local`.

## 2. First run
Open your project in Claude Code and type one of these:
```
/unslop this dashboard
/unslop the hero of https://your-site.com
/unslop my landing page and make the story video so I can post it
```
If another skill already uses the name, type `/unslop:unslop`.
It audits the screen and proposes a direction **before** it edits anything, so steer it early ("keep our green", "less playful"). If your screen is already good, it says so and only suggests small tweaks.

## 3. The passes it works through
Spacing → colour → icons → copy → type → layout → details → visuals → motion.
Tip: do one screen at a time, and commit before you run it, so you can compare before and after.

## 4. The honest catch
- **Hero images cost money.** When a hero needs a new scene or object, it can generate one through a paid image service (fal, Replicate, OpenAI images or Higgsfield). It shows the prompt and **asks before every paid generation**, so say no if you don't want to pay. Dashboards and apps rarely need one.
- **Live-site snapshots and the story video** need Playwright (`npm install -D playwright` then `npx playwright install chromium`); the video also needs ffmpeg.
- **Credit if you share it.** CC BY 4.0 means you can use and change it, even commercially, as long as you credit Damir Sokolovsky and link the repo.

## 5. Bonus: 3 lines that stop slop before it starts
Add this to your build prompt (from our own test, based on Anthropic's prompting best-practices page):
> Design rules: don't make it look AI-made. No purple gradients on white, no Inter, Roboto or Arial, and no cookie-cutter hero with three icon cards. Pick one distinctive font pairing from Google Fonts and one bold accent colour that suits [your business], and commit to it.

Sources: github.com/heydamir/unslop (README, LICENSE) · platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices
*Cut The Code isn't affiliated with the author. We get nothing for recommending it.*
