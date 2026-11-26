# SPEED: 10 prompts that make a slow app fast with Claude Code

Free · Cut The Code · checked 26 Nov 2026

**What this is:** the exact prompt from the video, plus 9 more for the usual reasons an app is slow. Paste each one into Claude Code inside your project. Every prompt asks Claude to **measure first** and **show the before and after**, so you can see it worked instead of taking its word for it.

**Our run:** a made-up sample shop app (100 customers, 2,000 orders; each database call waits 20 ms, like a hosted database). The report took **2.32 s and made 101 database calls**. Claude Code found the cause (one extra query per customer, the "N+1" problem), rewrote it as one query, and timed it again: **0.02 s and 1 database call**, about 100× faster, with the same top five customers line for line.

## 1. The one from the video

> report.py is slow. Profile it, find out why, fix it, and show me the timing before and after.

(Swap report.py for your slow file or page. Run it inside your project folder in Claude Code.)

## 2. Find the slow part before touching anything

> Profile this app's slowest page or command. Show me where the time goes (top 5 functions or queries, with timings) before you change anything.

## 3. Too many database calls (N+1)

> Count the database queries this page makes. If it runs one query per item in a loop, rewrite it as a single query or a join, then show the query count and the timing before and after.

## 4. Missing index

> Look at the queries this app runs most. For each one, check whether the columns it filters or joins on have an index. Add only the indexes that help, and show the timing of each query before and after.

## 5. Work done on every request that could be cached

> Find work this app repeats on every request (the same lookup, the same file read, the same calculation). Cache what is safe to cache, tell me how it gets refreshed, and time it before and after.

## 6. Slow page load in the browser

> Open the site's home page and measure what makes it slow to load (image sizes, scripts, fonts). Fix the top 3 and show the load numbers before and after.

## 7. Images that are far too big

> List every image on the site larger than 300 KB. Resize and compress them for the size they are shown at, keep the originals, and show the total page weight before and after.

## 8. Calls that could run at the same time

> Find places where this code waits for one slow call to finish before starting the next, when the calls don't depend on each other. Run them together where it is safe, and show the timing before and after.

## 9. Loading everything when you need a little

> Find places where this app loads a whole table or file into memory and then uses a small part of it. Change them to fetch only what's needed, and show the memory and timing before and after.

## 10. Keep it fast

> Write a small benchmark script for the 3 slowest things we fixed, so I can run it later and see if anything got slow again. Put the current timings at the top of the file.

## The honest catch

- **Check the answer is still right.** Faster code that gives a different result is broken code. Ask Claude to compare the output before and after (it did in our run).
- **Work on a copy or a branch,** not on your live site, and test before you deploy.
- Your numbers will differ from ours: our sample app was made up and its database delay was simulated.

More free Claude Code guides: cutthecode.co.uk
