# Chrome DevTools MCP setup (1 page)
*Cut The Code · free · checked 25 Nov 2026*

**What it is:** Chrome DevTools MCP (`chrome-devtools-mcp`) lets Claude Code open and control a real Chrome browser: read the console, inspect network requests, run a Lighthouse audit or a performance trace, click through pages and take screenshots. It's made by the Chrome DevTools team.
**Official repo (always install from here):** https://github.com/ChromeDevTools/chrome-devtools-mcp · Apache-2.0 licence · 59,283 GitHub stars on 25 Nov 2026 · v1.14.0 released 24 Nov 2026.
**You need:** Node.js (LTS), npm and current Google Chrome.

## 1. Install (2 minutes)
In your terminal, with Claude Code installed (the official command):
```
claude mcp add chrome-devtools --scope user npx chrome-devtools-mcp@latest
```
**Privacy-first version** (our pick): a throwaway browser profile, and no usage stats sent to Google:
```
claude mcp add chrome-devtools --scope user -- npx chrome-devtools-mcp@latest --isolated --no-usage-statistics
```
Or install it as a plugin with its 7 built-in skills (inside Claude Code):
```
/plugin marketplace add ChromeDevTools/chrome-devtools-mcp
/plugin install chrome-devtools-mcp@chrome-devtools-plugins
```
Restart Claude Code. **Check it works:** ask `Check the performance of https://developers.chrome.com`. Chrome should open and record a trace.

## 2. Three first prompts
```
Open http://localhost:3000. List the console errors and failed network requests, find the cause in my code, fix it, reload and show me a screenshot with 0 errors.
```
```
Run a Lighthouse audit on my homepage on mobile. Fix the top 3 issues, then run it again and show me before vs after.
```
```
Fill in my contact form with test data, submit it, and tell me everything that breaks.
```

## 3. What it can do
47 tools are on by default (input, navigation, emulation, performance, network, debugging, memory), 63 in the full tool reference. The ones you'll use most: `list_console_messages`, `list_network_requests`, `lighthouse_audit`, `performance_start_trace`, `take_screenshot`, `fill_form`.

## 4. The honest catch
- **It can see everything in that browser:** pages, cookies, logged-in sessions. The README warns: avoid sharing anything you don't want the AI to see. Don't log into your bank, email or admin panels in it. `--isolated` gives a clean temporary profile each time.
- **Google collects usage statistics by default** (tool success rates, latency, environment). Opt out with `--no-usage-statistics`.
- **Performance traces can send the page URL to Google's CrUX API** for real-user data. Turn that off with `--no-performance-crux`.
- Officially supports Google Chrome and Chrome for Testing only.
- Claude Code needs a paid Claude plan (Pro and up). The tool itself is free.

Sources: github.com/ChromeDevTools/chrome-devtools-mcp (README, docs/client-configurations.md, docs/configuration.md, docs/tool-reference.md, CHANGELOG.md) · GitHub API, 25 Nov 2026.
*Cut The Code isn't affiliated with Google, the Chrome team or Anthropic. We get nothing for recommending it.*
