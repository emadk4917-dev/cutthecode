# PRICING: the free Claude Code skill that reviews your prices

Free · Cut The Code · checked 26 Nov 2026

**What this is:** the one command that installs 53 free marketing skills into Claude Code (Marketing Skills by coreyhaines31, MIT licence), and the exact prompt we used to run the `pricing` skill on our own offers. Plus the review it wrote, word for word, so you can see what you'll get.

**Our run:** we pasted the text of our live offer pages into offers.md and asked for 3 changes. In 57 seconds it wrote pricing-review.md: **sell the £49/month care plan at go-live** (a year of it, £588, beats the £497 build), give content leads their own paid next step, and raise Done-For-You from £497 to £997 for new buyers. It said to leave the £249 deposit alone. And it warned us first: no sales data, so these are judgement calls to test.

## 1. Install the skills (one line, in your project folder)

```
npx skills add coreyhaines31/marketingskills -a claude-code
```

Then restart Claude Code. Skills run with Claude's permissions, so skim the ones you use first.

## 2. Make offers.md

Paste in your prices and the words on your sales pages: what each offer is, what it costs, what's included. Add any numbers you have (sales, conversion rates, refunds). The more real numbers, the less it has to guess.

## 3. The prompt (from the video)

> Use the pricing skill on offers.md, our real offers. Give me the 3 changes most likely to raise revenue, with the reasoning, and one thing you'd leave alone. Save it to pricing-review.md.

## 4. Follow-ups

> Which of these 3 changes is cheapest to test this week, and how would I know in 2 weeks if it worked?

> Write the exact copy for change 1 on my sales page, in my tone.

## The honest catch

- **It's advice, not data.** Without sales numbers it reasons from how your offers are built. Test changes on new buyers before you commit.
- The pricing skill is written for software (SaaS). It said so and used only the parts that carry over to services and courses.
- We haven't made these changes yet. Price changes are the owner's call.

More free Claude Code guides: cutthecode.co.uk
