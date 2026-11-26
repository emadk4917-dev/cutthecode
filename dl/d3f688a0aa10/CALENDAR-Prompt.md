# CALENDAR: the Claude Code prompt that finds the hours in your week

Free · Cut The Code · checked 26 Nov 2026

**What this is:** the exact prompt we gave Claude Code, the plan it wrote for a made-up week of 25 meetings, and the 3 messages it drafted to free the time.

**Our run:** a made-up sample week, 25 meetings, 23.5 hours booked. Claude found **9.0 hours back**: merge three status calls into one (2.5 h), keep one weekly sync instead of three (2.0 h; it spotted the sync had moved and the old copies stayed), shrink a 2-hour review to 30 minutes because only 2 pages changed (1.5 h), move a brainstorm to a shared doc (1 h), decline a demo already seen in October (1 h) and skip an optional lunch & learn (1 h).

## 1. Export your week

Google Calendar: Settings → Import & export → Export (or export one calendar). Outlook: File → Save calendar. Save it as week.ics in an empty folder.

## 2. The prompt (from the video)

Open Claude Code in that folder and paste:

> Read week.ics, my calendar for next week. Find the meetings I could cut, shorten or merge, show the hours I'd get back for each, and write the 3 short messages I'd send to free that time, in plan.md.

## 3. Follow-ups

> Which of these changes need someone else to agree? Put them in order of how easy they'll be.

> Block the freed time as focus time and tell me which two blocks to protect first.

## The honest catch

- **It only drafts.** It reads the file and writes a plan. Nothing is declined or sent until you do it.
- The week in the video is a made-up sample. Your export holds real names and details, and Claude Code sends what it reads to Claude: remove anything you would rather not share first.
- It only knows what's in the invites. A meeting with no agenda might still matter to someone; ask before you cut it.

More free Claude Code guides: cutthecode.co.uk
