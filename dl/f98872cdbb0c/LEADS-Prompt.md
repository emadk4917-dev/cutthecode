# LEADS: turn a public list into a checked lead list

**One Claude Code prompt. A public web page in, a clean CSV out, with every row checked. You decide who to contact (and we sent nothing).**

## What you need
- Claude Code (it comes with Claude's paid plans, Pro and up)
- A public list of businesses (a Wikipedia list, a trade directory page you're allowed to use, your council's open data)

## Steps
1. Make an empty folder, open a terminal in it, type `claude` and press Enter.
2. Paste the prompt (swap in your own list and county):

> Use curl with a User-Agent header to fetch the wikitext of the Wikipedia page "List of breweries in England" from the Wikipedia API. Turn its table of operational breweries into breweries.csv with: name, county, has_wiki_article, newest_source_year, all_sources_dead. Then check it: remove duplicates, flag every brewery whose newest source is more than 8 years old as "check it still trades", and make kent.csv with just Kent. Print the totals. Don't contact anyone.

3. Open the CSV in Excel, Numbers or Google Sheets.

## The 5 checks it ran
1. **Duplicates** merged (it found Dow Bridge Brewery listed twice).
2. **How old is the evidence?** The newest source year for every row; anything older than 8 years is flagged "check it still trades".
3. **Dead sources:** a flag when every source link is marked dead.
4. Whether the business has its own Wikipedia article (a quick "is it well known" signal).
5. County names tidied so filters work (Northants → Northamptonshire, and so on).

**Our run:** 25 Nov 2026, 1 minute 27 seconds. 700 breweries. **562 of 700 had no source from the last 8 years** (32 of 40 in Kent). It also told us where it used its own knowledge instead of the page (merging Ramsgate Brewery into Gadd's), so we could check that by hand.

## Make it useful (optional follow-ups)
**Check they still trade**

> For each row in kent.csv without a flag, tell me where I could check it's still trading (its own site, Companies House). Don't guess a website: leave it blank if you're not sure.

**An honest first message**

> Write one short, honest first message I could send to a brewery, offering [your service]. Make it easy to say no. Don't send anything.

## The catch
- Lists like this go stale. **Check every business is still trading before you contact it.**
- UK email rules (PECR): you can email limited companies with an easy opt-out, but sole traders and partnerships usually need consent first. Check the ICO's guidance before you send anything.
- Only use pages you're allowed to use, and credit the source. Wikipedia text is CC BY-SA 4.0.
- We sent nothing. Neither should Claude: keep "Don't contact anyone" in the prompt.

Free from Cut The Code · cutthecode.co.uk
