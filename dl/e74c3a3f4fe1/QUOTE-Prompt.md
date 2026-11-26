# QUOTE: turn your price list into a quote page with Claude Code

Free · Cut The Code · checked 26 Nov 2026

**What this is:** the exact prompt from the video, a price-list template to fill in, and the finished quote page from our run to use as a starting point. Customers pick their options on their phone and see the price straight away.

**Our run:** a made-up cleaning business ("Bright Nest Cleaning") with a 20-line price list. One prompt, 1 minute 47 seconds: **a working quote page** (2 bedrooms, fortnightly: £63), three example quotes worked out by hand and checked against the page (4 bedrooms, 3 bathrooms, one-off, oven and windows: £204), and 4 places where the price list didn't say what to do.

## 1. Write your price list

Save it as prices.md. Plain lines are fine:

```
Regular clean: 1 bed £55, 2 bed £70, 3 bed £85, 4 bed £100
Each extra bathroom after the first: +£12
Extras: oven £35, fridge £15, interior windows £20
Weekly 15% off the clean, fortnightly 10% off, monthly no discount
One-off clean: +£25 first-visit charge. Minimum charge per visit: £60
```

Write down your rules, not just the prices: what gets discounted, what's charged once, your minimum.

## 2. The prompt (from the video)

> prices.md is my price list. Build quote.html: a one-page quote calculator my customers can use on their phone. Then work out 3 example quotes by hand from the price list, check the calculator gives the same answers, and show me the working.

## 3. Answer the gaps it flags

In our run Claude listed 4 things the price list didn't say (does the discount apply to extra bathrooms? are extras charged once? does the minimum include extras? what about 5+ bedrooms?). Answer them in one message:

> Here's how I actually price it: <your answers>. Update quote.html and re-check the 3 examples.

## 4. Put it on your site

> Make quote.html match my website's colours and font (here's my homepage: <paste your site's colours or a screenshot>). Keep it one file with nothing to install.

## The honest catch

- **Claude guesses where your price list is unclear.** Read its list of choices and correct any that aren't how you charge.
- **Check 3 quotes yourself** before customers see the page.
- A quote page is an estimate. Say so on the page if your final price can change after a visit.
- Our business and prices were made up.

More free Claude Code guides: cutthecode.co.uk
