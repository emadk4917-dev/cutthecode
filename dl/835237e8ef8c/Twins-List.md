# TWINS: 10 paid apps with free open-source twins

**From Cut The Code** · checked 25 Nov 2026

Ten apps people pay for every month, each with a free, open-source "twin" on GitHub. Part 1 is five twins that mostly run on a small server. Part 2 is five that run on your own computer. There's a setup prompt for each one that you can paste into Claude Code.

Star counts and last-commit dates come from the GitHub API (25 Nov 2026: part 1 at 02:29 UTC, part 2 at 06:11 UTC). Prices come from each company's own pricing page and can change, so check before you cancel anything.

| # | You pay for | Price | Free twin | GitHub repo | Stars | Licence | Needs a server? |
|---|---|---|---|---|---|---|---|
| 01 | Miro (whiteboard) | $8/member/mo (Starter, billed yearly; $10 monthly) | **Excalidraw** | github.com/excalidraw/excalidraw | 136k | MIT | No: excalidraw.com is free in your browser |
| 02 | DocuSign (e-signatures) | £8/mo (Personal, UK, £96 billed yearly) | **Documenso** | github.com/documenso/documenso | 15.9k | AGPL-3.0 | Yes |
| 03 | Buffer (post scheduler) | $6/channel/mo (Essentials, monthly billing) | **Postiz** | github.com/gitroomhq/postiz-app | 42.3k | AGPL-3.0 | Yes |
| 04 | Fathom (website analytics) | from $15/mo | **Umami** | github.com/umami-software/umami | 40.3k | MIT | Yes |
| 05 | iCloud Photos (iCloud+ 200 GB) | £2.99/mo (UK) | **Immich** | github.com/immich-app/immich | 120k | AGPL-3.0 | Yes, plus disk space |

## The honest catch

- **Four of the five run on your own server.** A small cloud server (VPS) costs a few pounds a month. Immich also needs enough disk space for your whole photo library.
- **You do the updates.** Nobody patches it for you. Claude Code can run the updates, but you have to ask it to.
- **Backups are your job.** This matters most for Immich. Immich's own docs recommend a 3-2-1 backup (3 copies, 2 kinds of storage, 1 off-site) of both your photos and its database.
- **Some of them need extra setup.** Postiz needs a developer app (API keys) for each social network you connect. Documenso needs an email (SMTP) account to send signing requests.
- **What the licences mean:** MIT and AGPL-3.0 both let you run these free for yourself or your business. Under AGPL, if you change the code and offer it to other people as a service, you have to share your changes.
- Most of these companies also sell a hosted version (Excalidraw+, Documenso cloud, Postiz cloud, Umami Cloud). That's how they pay for the free code. If you'd rather not run a server, that's the option.

## Before you start (servers 02–05)

1. A small Linux VPS (Ubuntu) with at least 2 GB of RAM. Immich needs more: its docs say 6 GB of RAM minimum (8 GB recommended), plus disk for your photos. A spare computer at home works too.
2. A domain or subdomain pointed at the server (e.g. `sign.yourdomain.com`).
3. Claude Code on your computer, with SSH access to the server.
4. Read each prompt before you paste it. Every prompt asks Claude Code to show you each command before running it.

## Setup prompts for Claude Code

### 01 · Excalidraw (no server needed)

Use it free at excalidraw.com. If you want your own copy on your server:

```
Set up a self-hosted Excalidraw on my server (ssh user@MY_SERVER) using the official Docker image from github.com/excalidraw/excalidraw.
Serve it on https://draw.MYDOMAIN with an automatic HTTPS certificate (Caddy is fine).
Explain each command and wait for my OK before you run it. At the end, open the URL and confirm it loads.
```

### 02 · Documenso (instead of DocuSign)

```
Set up Documenso on my server (ssh user@MY_SERVER) with Docker, following the official self-hosting guide in github.com/documenso/documenso.
Use https://sign.MYDOMAIN with automatic HTTPS. Set up PostgreSQL, my SMTP email details (ask me for them, never print them back) and a signing certificate the way the docs describe.
Show me each command and wait for my OK. At the end, send a test document to my email and confirm I can sign it.
```

### 03 · Postiz (instead of Buffer)

```
Set up Postiz on my server (ssh user@MY_SERVER) with Docker Compose, following the official docs linked from github.com/gitroomhq/postiz-app.
Use https://social.MYDOMAIN with automatic HTTPS.
Then walk me through creating the developer app and API keys for these networks, one at a time: [list your networks].
Show me each command and wait for my OK. At the end, schedule a test post to one account and confirm it went out.
```

### 04 · Umami (instead of Fathom)

```
Set up Umami on my server (ssh user@MY_SERVER) with Docker, following the official install guide in github.com/umami-software/umami.
Use PostgreSQL and https://stats.MYDOMAIN with automatic HTTPS. Change the default admin password straight away.
Show me each command and wait for my OK. Then add my website, give me the tracking script, add it to my site's <head> if I tell you where the site's code is, and check a visit shows up.
```

### 05 · Immich (instead of iCloud Photos)

```
Set up Immich on my server (ssh user@MY_SERVER) with Docker Compose, following the official install guide in github.com/immich-app/immich.
Put the photo library on [the disk/path I'll tell you] and serve it on https://photos.MYDOMAIN with automatic HTTPS.
Also set up a nightly backup of the photo library AND the database to [a second location], following Immich's backup-and-restore docs (3-2-1 rule).
Show me each command and wait for my OK. At the end, tell me how to connect the Immich phone app and check the first backup ran.
```

### Keep them updated (all servers)

```
On my server (ssh user@MY_SERVER), check which of these Docker apps have new releases: Documenso, Postiz, Umami, Immich.
For each one, read its release notes for breaking changes, back up its database first, then update it.
Show me each command and wait for my OK.
```

---

# Part 2: 5 more twins that run on your own computer

*Added 25 Nov 2026 for the Fri 27 Nov video. Stars, licences and last commits from the GitHub API (25 Nov 2026, 06:11 UTC).*

These five don't need a server. They're apps (or a small tool) that run on your own laptop or desktop.

| # | You pay for | Price | Free twin | GitHub repo | Stars | Licence | Runs on |
|---|---|---|---|---|---|---|---|
| 06 | Otter.ai (transcription) | $16.99/mo (Pro, billed monthly; ~$8.33/mo billed yearly) | **Buzz** | github.com/chidiwilliams/buzz | 23.1k | MIT | Your computer, offline (uses OpenAI's open Whisper models) |
| 07 | remove.bg (background remover) | from $9/mo (40 credits) | **rembg** | github.com/danielgatis/rembg | 25.7k | MIT | Your computer (command line, Claude Code runs it for you) |
| 08 | Adobe Lightroom (photo editor) | £11.99/mo (1TB plan, UK) | **darktable** | github.com/darktable-org/darktable | 13.5k | GPL-3.0 | Desktop app (Windows, Mac, Linux) |
| 09 | YNAB (budgeting) | $14.99/mo ($109/yr) | **Actual** | github.com/actualbudget/actual | 30.4k | MIT | Desktop app, local-first |
| 10 | Adobe Premiere Pro (video editor) | £21.98/mo (annual, billed monthly, UK) | **Shotcut** | github.com/mltframework/shotcut | 15.8k | GPL-3.0 | Desktop app (Windows, Mac, Linux) |

## The honest catch (part 2)

- **Your computer does the work.** Transcribing an hour of audio with Buzz, or removing 500 backgrounds with rembg, is slow on an old laptop. A newer machine (or a graphics card) makes a big difference.
- **No cloud sync like the paid apps.** darktable, Shotcut and Buzz keep everything on the one computer. Actual can sync between devices, but only if you run its sync server yourself.
- **They're not identical.** darktable has no phone app like Lightroom. Shotcut has fewer built-in effects than Premiere Pro. Actual's bank sync needs extra setup (and its sync server), so the simple way is to import a CSV export from your bank.
- **Get them from the official repo.** Some of these have look-alike paid versions in app stores. Download from the GitHub releases page (or the project's own site, linked from the repo).

## Setup prompts for Claude Code (part 2)

Read each prompt before you paste it. Each one asks Claude Code to show you every command before it runs it.

### 06 · Buzz (instead of Otter)

```
Install Buzz on this computer from the official releases page linked from github.com/chidiwilliams/buzz (not an app-store copy).
Tell me which download matches my operating system, then walk me through installing it.
Then show me how to transcribe [path to my audio file] with the "small" Whisper model and export it as a .txt and an .srt file.
Show me each command before you run it.
```

### 07 · rembg (instead of remove.bg)

```
Install rembg on this computer, following the README at github.com/danielgatis/rembg. Use a Python virtual environment so it doesn't touch the rest of my system.
Then remove the background from every photo in [./products] and save the results as PNGs in [./products-cutout].
Show me each command before you run it, and open two of the results so I can check them.
```

### 08 · darktable (instead of Lightroom)

```
Help me install darktable on this computer from the official download linked from github.com/darktable-org/darktable.
Then give me a 5-step beginner workflow: import a folder, crop, exposure, colour, export as JPEG. Use the real menu names from darktable's manual.
```

### 09 · Actual (instead of YNAB)

```
Help me install the Actual desktop app from the official releases linked from github.com/actualbudget/actual.
Then set up a budget for me with these categories: [rent, food, transport, bills, fun, savings].
Show me how to import a CSV export from my bank, and how to back up the budget file.
```

### 10 · Shotcut (instead of Premiere Pro)

```
Help me install Shotcut on this computer from the official download linked from github.com/mltframework/shotcut.
Then give me the exact steps to make a 9:16 vertical video: new project at 1080x1920, import my clips from [folder], cut them, add a music track, add text, and export an MP4 for TikTok.
```


## One rule for next time

Before you pay for any app, search GitHub for its name plus "open source alternative". Then check three things: the stars, the licence, and the date of the last commit.

*Not sponsored. We don't get anything from any of these projects or companies.*
