# SECRETS: check a project for leaked keys before you push it, with Claude Code

Free · Cut The Code · checked 26 Nov 2026

**What this is:** the exact prompt from the video, plus 5 checks to run before any repo goes public. Claude finds the keys, moves them out of the code, cleans the git history and tells you what to rotate.

**Our run:** a made-up repo with 4 fake keys planted the way people really leak them. One prompt, 37 seconds: it found **all 4**: a payment key hard-coded in the code, a mailer key in a committed .env, an API key left in history by an "ignore config" commit, and a database password that a "tidy env" commit replaced with CHANGE_ME but left in history. It made a backup, fixed the files, rewrote the history and listed every key to rotate.

## 1. The prompt (from the video)

> I'm about to push this project to a public GitHub repo. Check it for leaked secrets first: hard-coded keys, committed .env files, and keys in the git history. Fix what you can safely fix, and tell me exactly which keys I must rotate.

## 2. The 5 checks to run first

1. **Is there a remote already?** If the repo was ever pushed or shared, assume every key in its history is leaked. Rotate first, clean second.
2. **Does .gitignore cover .env and .env.*?** Keep a .env.example with names but no values.
3. **Search the history, not just today's files:**
> Search every commit in this repo's history for anything that looks like a key, token or password, and list the commit, file and line for each.
4. **Check config files and notebooks:** keys hide in config.txt, settings.json, docker-compose files and notebook outputs.
5. **After a history rewrite:** delete old clones and backups that still hold the keys, and only push the cleaned repo.

## 3. Follow-up

> Add a pre-commit check that blocks commits containing anything that looks like a secret, and show me it catching a fake key.

## The honest catch

- **Our keys were fake,** made up for this demo. With real keys, rewriting history doesn't un-leak a key that someone already copied: rotate it at the provider.
- A history rewrite changes every commit hash. If others work on the repo, agree it with them first.
- Claude made a local backup of the old history before rewriting. That backup still contains the secrets: delete it once you've checked the result.

More free Claude Code guides: cutthecode.co.uk
