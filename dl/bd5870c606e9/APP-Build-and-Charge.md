# APP: **build-and-charge prompts**: spec → build → Stripe/Whop

The 4 prompts we pasted into Claude Code to go from an idea to an app with a $19 a month "Start your plan" button: write the spec, build and test it, connect a Stripe or Whop payment link, and get the first 10 customers. Plus what Claude said, honestly, about what still isn't ready.

**Why this pack:** Cut The Code's founder built an app with Claude Code that he charges for every month. Its real dashboard on 26 Nov 2026 showed monthly recurring revenue of £9,734.41 (≈ $12,756 at £1 = $1.3104), up from £0 in May. That's his own business, it took months of work and support, and **it is not a typical result**. This pack is the method in small: one boring problem, one type of customer, one price.

We ran every prompt here in Claude Code on 26 Nov 2026 on a made-up app (an invoice chaser for tradespeople). Test mode only: no real card was charged, no real email was sent. Results vary run to run.

## Before you start

- **Claude Code** (it comes with Claude's paid plans; Pro is $20 a month billed monthly, claude.com/pricing, 26 Nov 2026) and **Node.js**.
- An empty folder. Open a terminal in it and type `claude`.
- A Stripe account (free to open; fees per payment) or a Whop seller account, for step 3.
- **Pick a boring problem someone already pays to fix.** Chasing late invoices, missed calls, booking no-shows. Swap our idea for yours in prompt 1 and keep the rest.

## 1. Spec: what are we building, and what will people pay for?

> I want to build a small web app that people pay for, and charge for it. The idea: an invoice chaser for tradespeople (plumbers, electricians, cleaners) who lose money to late payers. Write SPEC.md, one page: 1) who it's for and the one job it does, in two lines; 2) the screens, one line each; 3) 5 to 8 "must work" checks I could pass or fail in a browser; 4) pricing: one $19 a month plan, and what's free versus paid; 5) what to leave out of version 1. Don't invent market prices or statistics: where a number would help, write "CHECK:" and what I should look up. Don't write any code yet.

**Our run:** 39 seconds. 7 screens, 8 "must work" checks, a free-versus-paid table (free: 3 invoices chased at once; paid: unlimited, custom schedule, editable wording), and **5 "CHECK:" lines instead of made-up numbers**, for example "what existing invoice-chasing tools charge per month, to confirm $19 is in a sensible range". It also left SMS, invoice design, taking payments and accounting integrations out of version 1.

**Do this before prompt 2:** answer the CHECK lines yourself. Ten minutes of looking up competitors' prices beats any guess.

## 2. Build it, then test every "must work" check

> Build exactly what SPEC.md says. Node + one HTML page, no frameworks, data stays in the browser. Make sample-invoices.csv with 8 obviously made-up clients so I can see it working. Then open it in a headless browser at phone width, check every "must work" item, fix anything that fails, and write TEST-REPORT.md with PASS or FAIL for each.

**Our run:** about 9 minutes. **8 of 8 checks passed** at 375px wide, 16 screenshots, and it fixed 2 real bugs on the way (a message that vanished after a CSV import, a missing icon). Two checks only passed in local test mode, because there were no email or Stripe keys, and it said so.

**The best part was the warning.** Claude told us that "keeping data in the browser conflicts with charging for this": reminders only send while the app is open in a tab, the paid plan is stored in the browser where a user could edit it, and clearing the browser deletes the account. That's exactly what you need to hear before someone pays you.

## 3. Charge: a Stripe or Whop payment link, no secret keys

> Now make it something people can pay for, with no secret keys in the code. 1) Add a pricing section with the $19 a month plan and a "Start your plan" button that opens the payment link stored in config.json (PAYMENT_LINK), so I can paste in either a Stripe Payment Link or a Whop checkout link. 2) Make welcome.html, the page people land on after paying. 3) Write GET-PAID.md: the exact steps to create a $19 a month Payment Link in Stripe in test mode and send buyers to welcome.html afterwards, the same for a Whop plan, how to test it with Stripe's test card, and what to check before switching to live mode. Don't state fees or rules you're not sure of; say where to check them. Also say honestly what this setup doesn't do yet (for example, knowing who has paid). Then test that the button opens the link in config.json.

**Our run:** about 5 minutes. The button opened exactly the Stripe-style link in config.json, then a Whop-style link after we swapped it (no restart), and stayed greyed out with no link or a non-https one. It wrote GET-PAID.md with 4 parts: Stripe test-mode Payment Link with the redirect to welcome.html, a Whop plan, an end-to-end test with Stripe's test card `4242 4242 4242 4242`, and a live-mode checklist (account activation, fees, tax, receipts, terms, refund policy, one real purchase you refund).

**What you do in Stripe (from GET-PAID.md, in short):** Test mode on → **Payment Links** → create → product "Invoice Chaser Paid", $19, **Recurring, Monthly** → **After payment**: redirect to `https://your-domain/welcome.html` → copy the link (a test link starts `https://buy.stripe.com/test_`) → paste into config.json. Do it all again in live mode before real customers.

**Stripe's fee:** in the US, 2.9% + 30¢ per successful domestic card payment, no monthly fee (stripe.com/pricing, 26 Nov 2026). On $19 that's about $0.85, so about $18.15 reaches you before tax. Check your own country's page.

**Whop:** create a product, add a recurring $19 monthly plan, set its redirect URL to your welcome page, and paste the plan's checkout link into config.json. Claude wasn't sure where Whop keeps the redirect setting and said so. For the record, Whop plans do have one: our own £27 Quickstart plan sends buyers to cutthecode.co.uk/upgrade.

**What it honestly doesn't do yet** (Claude's list, shortened): it doesn't know who has paid (anyone who opens welcome.html gets paid features), it never hears about cancellations or failed payments, paid status is per device, and reminders only send while the app is open. **Treat version 1 as an honour system** and watch your Stripe or Whop dashboard.

## 4. The first 10 customers

> Last one. Write FIRST-10.md: how I'd get the first 10 paying customers for this app if I already know a few local tradespeople. Include a message under 60 words I can send, what to do on a 15-minute call (load their own overdue invoices in front of them), and how to offer the first month free. No income claims, no fake urgency.

**Our run:** 58 seconds. A checklist before you message anyone (online at https, a real reminder reached your own inbox, a live payment link), "message 3 to 5 people at a time", one follow-up and then leave it, and a minute-by-minute 15-minute call done on *their* phone. Its rule: count someone as a customer only once they've paid for month two.

**The message Claude wrote (56 words):**

> Hi [Name], I've built a tool that emails polite reminders to customers who haven't paid an invoice, and stops when they pay. I'm looking for a few local trades to try it and tell me what's wrong with it. Could I show you in 15 minutes this week, using your own overdue invoices? First month free.

## 5. Make it real (the next prompt; we haven't run this one yet)

Before strangers pay, fix what step 2 and 3 warned about. Paste this when you're ready:

> Move accounts, invoices and the paid plan from the browser to the server, with a small database. Add a webhook endpoint for Stripe (or Whop) that marks an account paid when a payment succeeds and free when it's cancelled or fails; keep the webhook signing secret in an environment variable, never in a file. Run the reminder scheduler on the server so it works with every browser closed. Then re-run every "must work" check plus: paying unlocks the account, cancelling locks it, and opening welcome.html without paying does nothing.

## The maths (illustration)

$19 a month. $5,000 in a single month = **264 paying customers**. 10 customers = $190 a month; 100 customers = $1,900 a month, for as long as they stay. Apps are the slowest route to your first dollar and the best one for money that comes back every month. For the faster routes (websites, automations, products, clipping), see the free $5K Maths Sheet: cutthecode.co.uk/fivek.

**Honest note:** a passing test report means the listed checks passed, not that the app has no bugs. This pack's app is not ready for real customers until step 5 is done and you've tested it yourself. Agent-heavy prompts use a lot of your Claude usage; our 4 prompts took about 15 minutes of Claude's time.

**Income disclaimer:** results vary. Nothing here is a promise or a typical result: what you earn depends on your work, skills, market and time, and you may earn nothing. The app revenue above is the founder's own business, anonymised; it took months, it isn't typical, and it isn't Cut The Code's revenue.

*Small print:* Cut The Code is independent and not affiliated with Anthropic, Stripe or Whop; none has reviewed or endorsed this pack. Claude is a trademark of Anthropic. The invoice chaser, its clients and the tradespeople are made up. cutthecode.co.uk/app
