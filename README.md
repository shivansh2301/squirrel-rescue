# Baby Squirrel Rescue Kit

A one-page site for people in Bengaluru who find a baby palm squirrel. It walks them through four steps in order (look, give mum a chance, keep it warm, call a rescuer), with a shortcut to the helplines for emergencies. Care, volunteering, donating and group-running details are in fold-out sections below.

**Live site:** `https://<your-username>.github.io/squirrel-rescue/`

## What's in this repo

| File | What it is |
|---|---|
| `index.html` | The whole site: one self-contained HTML file, no build step |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |
| `CLAUDE.md` | Short project rules for AI coding agents |
| `.claude/skills/maintain-rescue-site/SKILL.md` | Step-by-step maintenance procedure for agents (and humans) |
| `CHANGELOG.md` | Dated log of content changes, especially helpline numbers |

## How it's hosted

GitHub Pages, deploying from the `main` branch, root folder. Every push to `main` goes live within a minute or two. There's no server, database or build to maintain.

## Making changes

**By hand:** edit `index.html` on GitHub (pencil icon), commit to `main`, done.

**With an agent (Claude Code or similar):** open the repo and ask in plain words, for example:

- "Check the helpline numbers are still correct"
- "Add Wildlife SOS as a fourth helpline"
- "Translate the emergency section into Kannada"
- "Run the monthly check"

The agent reads `CLAUDE.md` and the `maintain-rescue-site` skill, makes the change, checks it, updates `CHANGELOG.md`, and commits.

## Rules that matter

1. **Helpline numbers must be correct.** A wrong number is the worst bug this site can have. Only change one after confirming it from the organisation's own website or a recent news report, and note the source in `CHANGELOG.md`.
2. **The four steps stay first and short**, with the helplines in step 4 and a shortcut to them in the header. Everything else goes in a fold-out section.
3. **Keep it one file** that works offline once loaded and opens quickly on a cheap phone over mobile data.
4. **Never encourage people to keep or raise a squirrel themselves.** The care steps are for the first few hours, before handover to a licensed centre.

## Monthly check (5 minutes)

- [ ] Call or verify each helpline number
- [ ] Open the live site on a phone; check the numbers are visible without scrolling
- [ ] Update the "Numbers from … [month year]" line in the footer
- [ ] Add a line to `CHANGELOG.md`

## Custom domain (optional)

Buy a domain (for example `squirrelhelp.in`), add a `CNAME` file containing just the domain, set it under **Settings → Pages → Custom domain**, and point the domain's DNS to GitHub Pages as GitHub's instructions describe. Tick **Enforce HTTPS**.

## Content sources

- PfA Wildlife Hospital: https://www.pfawildlifehospital.org/
- ARRC Bangalore: https://wildarrc.org/
- BBMP 1533 helpline: https://www.deccanherald.com/india/karnataka/bengaluru/helpline-to-rescue-wildlife-1134454.html
- Care guidance: https://www.squirrelrefuge.org/treating-dehydration-in-squirrels, https://www.squirrel-rehab.org/faq.html
- Wildlife SOS: https://news.wildlifesos.org/you-found-a-baby-squirrel-what-do-you-do/

This site is for first-response guidance only and doesn't replace a vet or licensed rehabilitator.
