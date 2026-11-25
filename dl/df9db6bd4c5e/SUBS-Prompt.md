# SUBS: find every subscription in your bank statement

**One Claude Code prompt. About a minute. A page with every subscription, biggest first.**

## What you need
- Claude Code (it comes with Claude's paid plans, Pro and up)
- 3 months of your bank statement as a CSV (most UK banking apps have "Export" or "Download statement")

## Steps
1. In your banking app, export the last 3 months as a CSV. **Delete any column with your account number, sort code or name** before you go on.
2. Make an empty folder, put the file in it and name it `statement.csv`.
3. Open a terminal in that folder, type `claude` and press Enter.
4. Paste this prompt:

> statement.csv is 3 months of my bank statement. Find every subscription. Build subscriptions.html: one page, biggest first, monthly and yearly cost for each, total at the top. Flag any price rises and anything charged twice.

5. Open `subscriptions.html` in your browser.

**Our run:** on a made-up 3-month statement (142 rows), Claude Code found all 10 subscriptions, £1,318.68 a year in total, in 36 seconds. It flagged a gym that charged twice and a price rise of £1, and it correctly left out rent, energy and two same-day takeaway orders.

## Make it better (optional follow-ups)
> Add a "cancel first" list: the 3 subscriptions I could cancel with the least pain, and how much I'd save a year.

> Add a column with the date each one renews next, based on the statement.

## The catch
- Claude reads the file to do this, so **remove personal details first**.
- Check every line against your statement before you cancel anything. Claude can misread a merchant name.
- This isn't financial advice. It just reads your statement.

Free from Cut The Code · cutthecode.co.uk
