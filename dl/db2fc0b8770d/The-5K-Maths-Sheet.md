# The **$5K Maths Sheet**

What it actually takes to make $5,000 with Claude Code: 5 routes, each with a real price, the number of sales you'd need, the hours, the first message to send and the exact first prompt. From the Cut The Code video "What It Actually Takes to Make $5,000 With Claude Code".

**Honest note:** this is not income advice and nothing here is guaranteed. Results vary, and you may earn nothing. The maths is an illustration: $5,000 ÷ your price = the number of sales you need. Every market price has its source and the date we checked it. Anything marked **example** is our suggested price or our estimate, not a measured figure. None of these routes is passive.

## The one-line plan

**$5,000 ÷ your price = the number of yeses you need.**

| Route | Price per sale | Where the price comes from | Sales for $5,000 | Hours (example) |
|---|---|---|---|---|
| 1. Local-business websites | $500 + $50/month | example; market $1,000–$30,000+ (WebFX), from £499 + VAT (DotGO) | **10 sites** | ~4 h a site |
| 2. Automations (retainers) | $300 setup + $100/month | example; market $79/month (BeepBack) | **10 clients, by month 2** | ~3 h setup, ~1 h/month each |
| 3. Digital products | $29 | $29 Claude Code kit (Selar); $4.99 median prompt listing (Getly) | **173 sales** | ~10 h to make, then posting |
| 4. Your own app | $19/month | example | **264 paying users in one month** | weekends for months |
| 5. Clipping | $1.00 per 1,000 views, or $150/month a streamer | Content Rewards campaign; $150 is example | **5,000,000 paid views, or 34 streamers** | ~2 h a day posting |

Prices were checked on 26 Nov 2026 unless another date is shown. Pound prices are converted at the Wise mid-market rate on 26 Nov 2026: £1 = $1.3104.

**What you need:** Claude Pro, which includes Claude Code: $20 a month billed monthly, or $17 a month billed yearly (claude.com/pricing, 26 Nov 2026). A laptop, an empty folder for each build, and a free place to host what you build.

**Which route first?** If you want your first dollar this week, start with route 1. Routes 1 and 2 pay fastest but you have to talk to businesses. Route 3 needs an audience. Route 4 takes months and customers can cancel. Route 5 pays per view, and most clips get few views.

## Route 1: websites for local businesses

**Who pays:** local service businesses that live on calls and bookings: plumbers, barbers, dentists, dog groomers.

**Real prices:** WebFX (US agency), 2026 pricing guide from 250 US marketing professionals: web design $1,000 to $30,000+ (webfx.com/web-design/pricing, 26 Nov 2026). DotGO (UK): from £499 + VAT one-off (≈ $654 before VAT), then £45 a month for support; the same page puts freelancers at £500 to £3,000 and agencies at £3,000 to £10,000+ (dotgo.uk, 26 Nov 2026).

**The maths (illustration):** **example** price $500 a site + $50 a month. $5,000 ÷ $500 = **10 websites**. Those 10 clients at $50 a month = $500 coming back every month.

**Hours (example):** about 4 hours a site including edits and the call, plus about an hour to research 10 businesses. Your first one will take longer. Claude's part is minutes: in our run it built the demo site in under 2 minutes.

**Steps**
1. **Pick** one trade in one town ("plumbers in Tampa"). That's your whole market for now.
2. **Build** a demo with the prompt below, in an empty folder.
3. **Position:** sell "more calls from people searching on their phone", not "a website". Say "I build websites for plumbers in Tampa".
4. **Find them:** Google Maps, your trade + your town. List 10 businesses with no website, or one that breaks on a phone: name, phone, what's wrong.
5. **Build first, ask second:** make the first business its own homepage before you message them.
6. **Get paid, then go live:** send a Stripe payment link. When it's paid, publish on a free host. The business pays for its own domain.

**The exact first prompt** (open Claude Code in an empty folder with `claude`, then paste):

> Build a one-page website for a local business. Client: [business name], a [trade] in [town]. Mobile first. Sections: hero with a big tap-to-call button, services with prices "from", service area, a quote request form, and opening hours. Do NOT invent reviews, awards or certifications. One index.html file, fast, no frameworks. When it's done, open it in a headless browser, check it at phone and desktop width, and tell me the page weight.

**First-client script:**

> Hi [name]. I build websites for [trade] in [town]. I noticed you don't have one, so I made you a homepage. Here's the link: [link]. If you want it live, it's $500, then $50 a month and I keep it updated.

**Our run:** 26 Nov 2026, a made-up plumber in Tampa. Claude Code wrote the page, opened it in a headless browser, checked it at phone and desktop width and reported the page weight, in under 2 minutes.

## Route 2: automations (monthly retainers)

**Who pays:** the same local businesses. An enquiry at 9pm that waits until morning often books with whoever answered first.

**Real price:** BeepBack, a missed-call text-back tool for US local service businesses, lists a starting price of $79 a month, flat rate (GetApp listing, 26 Nov 2026).

**The maths (illustration):** **example** price $300 setup + $100 a month. 10 clients = $3,000 up front + $1,000 a month. **By the end of month two: $5,000.**

**Hours (example):** about 3 hours to set up and test each client, then about an hour a month each to check it's still working. Claude's part is minutes: our test build took under a minute.

**Steps**
1. **Build** the demo with the prompt below. Test mode first: nothing is really sent.
2. **Position:** "every enquiry answered in under a minute, even at midnight".
3. **Who to ask:** your website clients first. You already built their form.
4. **Send the message** below.
5. **Go live safely:** connect a real email service, send the first test to yourself, and read every reply it writes for a week.
6. **Charge a setup fee and a monthly fee:** it has to keep running, and someone has to watch it.

**The exact first prompt:**

> Build an instant enquiry reply automation for a small business (demo: [business type]). A tiny Node server with a POST /enquiry webhook. For every enquiry: save it to leads.csv, write a friendly reply email that uses their name and the service they asked about, and put it in an outbox folder (TEST MODE: nothing is really sent). Then send it 3 test enquiries with curl and show me leads.csv and one reply.

**First-client script:**

> How many enquiries came in after 6pm last week? I can make sure every one gets a reply within a minute, and you see them all in one sheet. Want me to set it up on your site form?

**Our run:** 26 Nov 2026, a made-up dog groomer. Claude Code built the server, fired 3 test enquiries at it, saved them to leads.csv and wrote 3 replies that used each customer's name and their dog's name, in under a minute.

## Route 3: digital products

**Who pays:** people who want a shortcut you've already taken.

**Real prices:** on Selar, a "Claude Code Starter Kit" is listed at $29 (selar.com, 26 Nov 2026). On Getly, the median price of 60 Claude and Cursor prompt listings was $4.99 (Getly's own count, measured 6 Nov 2026).

**The maths (illustration):** $5,000 ÷ $29 = **173 sales**. At $4.99 it's **1,003 sales**. That's why you don't race to the bottom.

**Hours (example):** about 10 hours to write down what you know and turn it into a product, then most of your time goes on posting about it. Claude's part: our run turned a notes file into a 10-page PDF and a sales page in a few minutes.

**Steps**
1. **Pick** what you actually know. Built 5 plumber sites? That's "the plumber website kit".
2. **Build:** put your notes in notes.md and paste the prompt below.
3. **Get paid:** Whop or Gumroad hosts the file and takes the payment.
4. **First sale:** post the process as short videos, show the real result, one link in your bio.
5. **Price** like the market, then add what only you have: your templates, your checklist, your real examples.

**The exact first prompt:**

> Turn notes.md into a digital product I can sell: a clean 8 to 10 page PDF guide with a cover, a contents page and a checklist at the end, plus a one-page sales page (sales.html) with the price, what's inside and a buy button. Use HTML and a headless browser to print the PDF. Keep every fact from the notes; add no claims that aren't in them. Show me the page count when done.

**First-sale script** (the caption on the short video that shows your real result):

> I built [number] websites for [trade] with Claude Code. Here's the exact kit I use: the prompts, the checklist and the message I send. It's $29, link in bio. If you'd rather do it yourself, the first prompt is in this video.

**Our run:** 26 Nov 2026. We gave Claude Code the notes for this sheet. It made a 10-page PDF guide with a cover, contents and checklist, plus a sales page.

## Route 4: your own app

**Proof (the founder's own business, not typical):** Cut The Code's founder built an app with Claude Code. Its real dashboard on 26 Nov 2026 showed monthly recurring revenue of £9,734.41 (≈ $12,756), 1,258 new customers in the last 12 months and 615 paying members, from £0 in May. We blur the app's name and its customers; the numbers are untouched. **This is his app's revenue, not Cut The Code's**, it took months of work, and it is not a typical result.

**The maths (illustration):** **example** price $19 a month. $5,000 in a single month = **264 paying customers**. 100 customers = $1,900 every month, for as long as they stay.

**Getting paid:** a Stripe Payment Link sells the monthly plan. Stripe in the US charges 2.9% + 30¢ per successful domestic card payment, with no monthly fee (stripe.com/pricing, 26 Nov 2026). Whop is the other option: it hosts the checkout and the membership.

**Hours (example):** a first version in a weekend or two, then ongoing hours every week on support and fixes. Our demo build took Claude under 3 minutes; a product people pay for monthly takes far longer.

**Steps**
1. **Pick** a boring problem someone already pays to fix. Not a cool idea, a boring, expensive one (for example, chasing unpaid invoices).
2. **Build** a first version with the prompt below.
3. **Get paid:** a Stripe Payment Link or a Whop checkout for the monthly plan.
4. **Position:** don't launch to the whole internet. Launch to the 10 businesses you already know from routes 1 and 2.
5. **First 10 customers:** load their own overdue invoices into the app in front of them, and give them the first month free.
6. **Keep them:** answer every support email fast, and build what they ask for.

**The exact first prompt:**

> Build a small paid web app for tradespeople: an invoice chaser. They paste or upload a CSV of unpaid invoices (client, email, amount, due date), the app shows a dashboard of what's overdue and by how many days, and writes a polite reminder email for each one, firmer the later it is. Node + one HTML page, data stays local. Add a pricing section with a $19 a month plan and a Stripe Payment Link placeholder (no real keys). Load sample-invoices.csv, run it, and screenshot the dashboard to dashboard.png.

**First-client script:**

> Hi [name], quick one. How much are you owed right now from late invoices? I've built a little tool that shows who owes what and writes the reminder for you. Can I load yours in for 15 minutes this week? First month's free.

**Our run:** 26 Nov 2026. Claude Code built the dashboard, the reminders and a $19 pricing section, and checked it in a browser in under 3 minutes. Want the full spec → build → charge prompts? Comment APP, or get them at cutthecode.co.uk/app.

## Route 5: clipping

**Who pays:** brands and streamers who pay per view on campaigns, or creators who pay someone to make their clips.

**Real prices:** the Content Rewards campaign "Boeshi GTA 6 Clipping" paid $1.00 per 1,000 views, $3 minimum and $300 maximum per clip, with $278 of a $1,750 budget used (screenshot 26 Nov 2026, 14:18 UTC). Content Rewards' own article says the median rate across 710 live campaigns on 16 Nov 2026 was $1.00 per 1,000 views. For comparison, Castos sells 4 short clips per podcast episode for $990 a month (castos.com, 26 Nov 2026).

**The maths (illustration):** campaigns: $5,000 at $1 per 1,000 views = **5,000,000 paid views**, which is at least 17 clips that hit the $300 cap, and a clip under 3,000 views pays nothing. Clips as a service: **example** price $150 a month for 20 clips, so **34 streamers**.

**Hours (example):** about 2 hours a day picking, posting and tracking clips. Claude's part in our run: 5 vertical clips cut in under 12 minutes.

**Steps**
1. **Set up:** check you have ffmpeg, Python and faster-whisper (Claude can check and install them).
2. **Build** the clipper skill with the prompt below.
3. **Pick** an open campaign, or one small streamer, and read the rules: captions, credit, banned content.
4. **Clip** a stream the creator allows you to clip. Credit them on every clip.
5. **Post and track:** submit each link and keep a tracker of views and pay.
6. **Or sell it as a service** with the message below.

**The exact first prompt:**

> Build me a clipper skill in .claude/skills/clipper. Given a stream video: 1) transcribe it with faster-whisper (small.en, word timestamps), 2) find the spikes: the loudest seconds plus wild words like no way, bro, oh my god, 3) then YOU read the transcript around each spike and pick the 5 best 20 to 45 second moments that make sense on their own, 4) cut each one to a 1080x1920 vertical clip with ffmpeg: streamer's face cam on top, gameplay below, big burned-in word captions, and a credit line with the streamer's channel. Save clips/ plus clips.csv (start, end, hook, why). Test it on 10 seconds of video first, then tell me how to use it.

**First-client script** (Claude wrote this one in our run):

> Hey [name], love your streams. I make vertical clips for TikTok, Reels and Shorts, with your face cam, captions and your channel credited. I'll cut 5 from a recent stream for free so you can see if you like them. If you do, it's 20 clips a month for $150. Want me to send the free ones?

**Our run:** 26 Nov 2026, 20 minutes of a streamer's GTA 6 stream from an open clipping campaign. Claude Code built and tested the skill in about 3.5 minutes, then cut 5 vertical clips in under 12 minutes. Only clip videos you have permission to use.

## Start today (checklist)

- [ ] Pick one route. If unsure: route 1.
- [ ] Pick one trade in one town (or one streamer, or one problem).
- [ ] Write your price and your number: $5,000 ÷ price = ___ yeses.
- [ ] Find 10 people who'd pay. Name, contact, what's wrong.
- [ ] Build the first one something real with the prompt above.
- [ ] Send the first-client script.
- [ ] When they say yes, send a Stripe payment link.
- [ ] Write down what you learned. That's your first digital product.

**Income disclaimer:** results vary. These are examples and illustrations, not promises or typical results. What you earn depends on your work, skills, market and time, and you may earn nothing. The app revenue shown is the founder's own business, anonymised; it is not Cut The Code's revenue and it is not typical. Market prices are from the named pages on the dates shown and can change.

*Small print:* Cut The Code is independent and not affiliated with Anthropic, Stripe, Whop, Content Rewards or any business named here; none has reviewed or endorsed this sheet. Claude is a trademark of Anthropic. The businesses in our runs (the Tampa plumber, the dog groomer) are made up. cutthecode.co.uk/fivek
