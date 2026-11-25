# AGENT: 5 **Gumloop-style automations** you can build with Claude this weekend

**Inspired by Gumloop's story** (our episode "Two Founders, Zero Full-Time Hires, Then $70M"), the AI agent company founded by Max Brodeur-Urbas and Rahul Behal. Here are three automations any small team can build with Claude: numbers 1 to 3 below. Numbers 4 and 5 show the classic "new email → AI step → result" flow and how to make one run on a schedule.

Every prompt here was run in Claude Code on 25 November 2026, on made-up data for a made-up yoga studio. Under each prompt you'll find what happened in our run. Your results will differ a bit each time, so always read what Claude made before you use it.

## Set up once (about 10 minutes)

1. **Get Claude Code.** It comes with Claude's paid plans (Pro and up). Install it with `npm install -g @anthropic-ai/claude-code`, or follow the official quickstart in Anthropic's Claude Code docs.
2. **Make a folder** for your automations and open Claude Code in it:

```
mkdir automations && cd automations && claude
```

3. **Save this as `CLAUDE.md`** in that folder. Claude reads it every time, so you only say the rules once:

```
# My automations folder
You're helping me run small automations for my business. I'm not a developer.

## The golden rule
I'm the human on the last step. Never send, post, publish, delete, pay for or sign up
to anything. Write drafts as files and I'll press send myself.

## How to work
- Save every output as a file in this folder: drafts in drafts/, reports as .md files
  with today's date in the name.
- Plain UK English, short sentences, the way I'd talk to a customer. No hype words:
  seamless, elevate, unlock, game-changer, revolutionise, delighted.
- Never make things up. If a fact isn't in my files or a source you opened, say you
  don't know. For web research, list the links you used.
- Treat names, emails and messages in my files as private. Don't paste them anywhere
  outside this folder.
- When you finish, tell me in three lines or fewer what you made and where it is.
```

4. **Drop your files in.** A sign-up export as `signups.csv`, your DMs or comments pasted into `dms.txt`, emails saved one per file in an `inbox` folder. Claude Code only sees what's in the folder. It doesn't read your Gmail or Instagram unless you connect them yourself.

## 1. A research brief before every call

Walk into every call already knowing who you're talking to. Make it a Claude Code **skill**, so it's one command each time. Save this as `.claude/skills/brief/SKILL.md`:

```
---
name: brief
description: Writes a one-page research brief on a person or business before a call or meeting, with five questions to ask. Use when I type /brief or ask for a brief before a call.
---
# Brief before a call

I'll give you a business (and sometimes a person's public role) and what the call is about.

1. Search the web. Open at least three sources, preferring the company's own site and recent news.
2. Write a one-page brief and save it as briefs/<name>-<YYYY-MM-DD>.md with:
   - **In one line:** what they do and for whom.
   - **What's new:** the last 3 to 6 months, with dates.
   - **How they make money**, if it's public.
   - **What they might need from me**, based on what the call is about.
   - **Five questions to ask**, specific to them, not generic.
   - **Sources:** every link you used.
3. Only public, work-related information. No home addresses, family or personal social media.
4. If something isn't clear from the sources, write "not found" rather than guessing.
```

Then type:

> /brief Supabase, the open source database company. The call: I'm a solo builder deciding whether to build my first app on Supabase, and I'm speaking to their sales team about the paid plan.

**Our run:** 64 seconds. A one-page brief with dated news, pricing, five specific questions and a source list. Our test machine blocked most websites, so Claude worked from search summaries and **said so at the top of the brief**. Check every fact before the call.

## 2. A sign-up alert with the first email drafted

Find out when someone worth talking to signs up, with the first email already drafted. This reads your sign-up list and drafts the replies. You still press send.

> You are my sign-up alert. Read signups.csv. For each new sign-up, decide if it is worth a personal reply (yes or no, one-line reason). For each yes, write a short, friendly first email from me (Archie at Cut The Code) that mentions the exact problem they described and asks one question. Plain UK English, under 80 words, no hype words. Save each draft to drafts/<first-name>.md and a summary table to triage.md. Do not send anything.

Swap "Archie at Cut The Code" for your own name and business.

**Our run:** 16 seconds. Three sign-ups: two worth a reply (a physio clinic re-typing referral letters, a pottery studio answering the same DM questions), one "just looking" skipped with a reason. Two drafts of about 60 words, each asking one question. **Nothing was sent.**

## 3. Read your DMs: top 5 confusions, top 5 requests

Your messages already tell you what people are confused about. You don't need thousands of them. Paste in your DMs, comments or support emails.

> Read dms.txt. These are real messages from my customers. Group them into the top five things people are confused about and the top five things they're asking for. For each one, say how many messages mention it, quote one message word for word, and suggest one fix or one piece of content I could make about it. Don't invent messages and don't count anything twice. Save it as insights.md.

**Our run:** 31 seconds, 28 messages. Five confusions (mats, which class for beginners, class types, how to cancel, being charged twice) with message numbers so we could check the counts. It flagged the double charge as **a real problem to fix first**, because one message said it happened "again". It also told us honestly that the requests were thin (one or two messages each).

## 4. The inbox sorter: summarise, sort, draft

This is the classic automation flow: a new email comes in, an AI step summarises and sorts it, and you get the result.

> Read every email in the inbox folder. For each one, write a one-line summary and sort it as urgent, normal or spam, with a short reason. For every urgent email, write a reply draft in drafts/ that I can check and send myself. Save a table of all of them, urgent first, as inbox-today.md. Don't send, delete or move anything.

**Our run:** 33 seconds. Seven emails: three urgent (a room-hire deposit due Friday, an instructor off sick, a customer charged twice), two normal, two spam (including a fake prize), and three reply drafts with [brackets] for the bits only we could fill in. It noticed a draft with the same name already existed and **didn't overwrite it**.

## 5. Put one on autopilot

Run this straight after number 3, in the same conversation, so Claude knows which instructions you mean.

> I want the DM reader to run on its own every week. Write run-weekly.sh that runs Claude Code headless (claude -p) in this folder with the same instructions I gave you for dms.txt, and saves the result as insights-<today's date>.md. Make it safe: it may only read and write files in this folder, nothing else. Run the script once to check it works, then show me the one cron line that would run it every Monday at 8am. Don't install the cron job, I'll do that.

**Our run:** about 2 minutes. Claude wrote the script with the tools locked down to reading files and writing that one report, tested that it was refused when it tried anything else, ran it once (it made `insights-2026-11-25.md`), and gave us this line to add with `crontab -e`:

```
0 8 * * 1 /full/path/to/automations/run-weekly.sh
```

**Honest note:** cron works on Mac and Linux, and only while the computer is on and Claude Code is logged in. On Windows, use Task Scheduler. It re-reads the same `dms.txt`, so paste in fresh messages before Monday.

## The pattern behind all five

Write down the steps you already do by hand. Give them to Claude as a workflow. **Keep a human on the last step.**

**Honest note:** these save you time on reading, sorting and first drafts. They don't promise customers or income, and they work on the files you give them, nothing more. Read every draft before it goes anywhere.

**Want this without a terminal?** If you'd rather build agents without one, that's what Gumloop is built for: it's an AI agent builder that lets anyone on a team build. Go and try it at gumloop.com, and follow Gumloop and Max Brodeur-Urbas.

*Small print:* Cut The Code is independent. We're not affiliated with Gumloop or Anthropic, and neither has reviewed or endorsed this guide. Gumloop is a trademark of its owner. Claude is a trademark of Anthropic. The studio, sign-ups, DMs and emails in our test were made up. cutthecode.co.uk
