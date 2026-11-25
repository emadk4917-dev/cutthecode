# MARKETING: 53 free marketing skills for Claude Code

**One command installs all 53. Then you ask for a skill by name. Below: the install, and 7 prompts to run them on your own business.**

## What you need
- Claude Code (it comes with Claude's paid plans, Pro and up)
- A folder for your project (your website files, or an empty folder)

## Install (one command)
1. Open a terminal in your project folder.
2. Paste this and press Enter:

```
npx skills add coreyhaines31/marketingskills -a claude-code
```

3. Type `claude` to start a **new** Claude Code session. Skills added during a session usually only load in the next one.
4. Check they're there: `ls .claude/skills | wc -l` should print 53.

The skills are free and open source: **Marketing Skills** by Corey Haines, github.com/coreyhaines31/marketingskills, MIT licence, 62,591 stars on 25 Nov 2026.

## 7 prompts to try on your business
**1. Landing page (cro)**

> Use the cro skill on my landing page (index.html). Find the 3 changes that would win the most enquiries, with the exact line to change for each.

**2. Headline (copywriting)**

> Use the copywriting skill to rewrite my homepage headline and the first paragraph. Give me 3 options and say who each one is for.

**3. SEO (seo-audit)**

> Use the seo-audit skill on my site. List the 5 fixes that matter most, easiest first.

**4. Prices (pricing)**

> Use the pricing skill. Here's what I sell and what I charge: [paste]. What would you change, and why?

**5. Freebie ideas (lead-magnets)**

> Use the lead-magnets skill. Suggest 5 free things I could give away that my customers would actually want, and pick the best one.

**6. Cheap ideas (marketing-ideas)**

> Use the marketing-ideas skill. I run [your business] in [your town]. Give me 10 ideas I can do this month for under £50.

**7. First email (cold-email)**

> Use the cold-email skill to draft a short first email to [type of business]. Don't send anything. Add an opt-out line.

**Our run:** on 25 Nov 2026 we installed all 53 in Claude Code (9 seconds), started a new session and ran the first prompt on a copy of our own £497 website sales page. In 1 minute 37 seconds it found that **the only way to contact us was to pay a £249 deposit** (no form, no phone, no email), that the headings use a font that's never loaded, and that the "£497 in full" link goes to a store page instead of a checkout. All three were real.

## The catch
- **Skills run with full permissions.** The installer itself says: "Review skills before use; they run with full agent permissions." Open the SKILL.md files you plan to use and read them first, especially any that run scripts or call outside services.
- They're advice, not magic. Check every suggestion against what you know about your customers.
- Cold email in the UK: check the ICO's PECR guidance first (rules differ for companies and sole traders), and never send to a list you scraped without checking it.

## Not affiliated
Cut The Code isn't connected to the Marketing Skills author or to Anthropic. Claude is a trademark of Anthropic.

Free from Cut The Code · cutthecode.co.uk
