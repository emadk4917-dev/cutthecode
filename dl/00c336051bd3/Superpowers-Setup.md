# Superpowers setup (1 page)
*Cut The Code · free · checked 25 Nov 2026*

**What it is:** Superpowers is a free plugin for Claude Code (it also works in Codex, Cursor, Gemini CLI and others) by Jesse Vincent and Prime Radiant. It's a set of skills that switch on by themselves. Instead of jumping straight into code, Claude asks what you want, agrees a design with you, writes a plan of small tasks, then builds it test-first.
**Official repo (always install from here):** https://github.com/obra/superpowers · MIT licence · 326,182 GitHub stars on 25 Nov 2026 · last commit 24 Nov 2026.

## 1. Install (2 minutes)
Inside Claude Code, type:
```
/plugin install superpowers@claude-plugins-official
```
That's Anthropic's official plugin marketplace. Or use the author's own marketplace:
```
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```
Then start a new session. **Check it works:** type `Let's make a react todo list`. If it's installed, Claude starts asking you questions (the brainstorming skill) before it writes any code.

## 2. Three first prompts
```
I want to build [your thing]. Before any code, ask me questions one at a time until you understand what I want and why, then show me the design in short chunks.
```
```
Write the implementation plan for the design we agreed: tasks of 2-5 minutes each, exact files, and how to check each one.
```
```
Something's broken: [what you see]. Find the root cause before you change anything, then prove the fix works.
```

## 3. The 7-step flow it runs (from the README)
1. **brainstorming**: questions first, then a design you approve
2. **using-git-worktrees**: a separate branch, so your main code stays safe
3. **writing-plans**: bite-sized tasks (2-5 minutes each) with exact files and checks
4. **subagent-driven-development** or **executing-plans**: works through the plan, with reviews
5. **test-driven-development**: write a failing test, then the code that passes it
6. **requesting-code-review**: reviews between tasks; critical issues block progress
7. **finishing-a-development-branch**: tests, then merge / PR / keep / discard

15 skills in all, including systematic-debugging and verification-before-completion.

## 4. The honest catch
- **It uses more of your Claude limit.** Questions, a written plan, tests and reviews all cost tokens, and it can run for a long time on a big plan. For a one-line fix or a typo, it isn't worth it: say "small change, no plan needed", or do it without Superpowers.
- **It's slower to start.** You answer questions before you see code. That's the point, but it can feel slow.
- **Optional telemetry:** the brainstorming "visual companion" loads the Prime Radiant logo from their site (version number only, says the README). Turn it off with the environment variable `SUPERPOWERS_DISABLE_TELEMETRY=1`.
- Claude Code needs a paid Claude plan (Pro and up). The plugin itself is free.

Sources: github.com/obra/superpowers (README, LICENSE) · GitHub API, 25 Nov 2026.
*Cut The Code isn't affiliated with the author or Anthropic. We get nothing for recommending it.*
