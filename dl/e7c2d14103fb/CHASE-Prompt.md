# CHASE: find who owes you and draft the chase emails with Claude Code

Free · Cut The Code · checked 26 Nov 2026

**What this is:** the exact prompt from the video, a CSV template for your invoices, and 3 follow-up emails (friendly, firm, final) for the clients who still haven't paid. Claude writes **drafts only**. You read them and you press send.

**Our run:** a made-up ledger of 40 invoices for a small design studio. One prompt, about 37 seconds: **16 overdue invoices, 10 clients, £7,020**, the total checked 3 different ways, and one polite email per client in chase-emails.md. It also caught a trap in the file (Windows line endings) that made a simple check find no overdue invoices at all.

## 1. Export your invoices

Save them as a CSV with these columns (any order is fine, Claude will read the headers):

```
invoice,client,issued,due,amount_gbp,paid_on
INV-1001,Example Ltd,2026-10-01,2026-10-31,450,
INV-1002,Another Co,2026-10-05,2026-11-04,300,2026-11-02
```

Leave `paid_on` empty for unpaid invoices. Most accounting tools (Xero, QuickBooks, FreeAgent, a spreadsheet) can export this.

## 2. The prompt (from the video)

> invoices.csv is my sales ledger. Today is <today's date>. List every unpaid invoice that is past its due date, total what I'm owed, and check that total a second way. Then draft one short, polite chase email per client in chase-emails.md. Don't send anything.

## 3. Follow-up 1: friendly (7 days after the first email)

> For every client in chase-emails.md who still shows as unpaid in invoices.csv, draft a short, friendly follow-up in follow-up-1.md. Mention the invoice numbers and amounts, ask if anything is stopping payment, and offer to resend the invoice. Don't send anything.

## 4. Follow-up 2: firm (14 days)

> For clients still unpaid, draft a firmer follow-up in follow-up-2.md: state the total, the original due dates and how many days overdue each invoice is, and ask for payment or a date by which they will pay. Stay polite and factual. Don't send anything.

## 5. Follow-up 3: final notice (30 days)

> For clients still unpaid after the second follow-up, draft a final notice in follow-up-3.md. Give a clear deadline 7 days from today, offer a payment plan, and say what happens next under my terms (for example, late-payment interest if my terms allow it). Keep it calm and professional. Don't send anything.

## The honest catch

- **Check the "paid" column first.** If a client paid yesterday and your export doesn't know, the email will be wrong. Claude can only see what's in the file.
- **Read every draft before you send it.** You know the relationship; Claude doesn't.
- In the UK, businesses can claim statutory interest and compensation on late payments from other businesses (the Late Payment of Commercial Debts Act). Check it applies to you before you mention it.
- Our ledger was made up. Your numbers will differ.

More free Claude Code guides: cutthecode.co.uk
