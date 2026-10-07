# Project rules for agents

This repo is a single static page, `index.html`, served by GitHub Pages from `main`. Pushing to `main` publishes to the public immediately, so treat every commit as a release.

For any change, follow `.claude/skills/maintain-rescue-site/SKILL.md`.

Hard rules:
- Never change, add or remove a helpline number without a source you actually opened (the organisation's own site or a news report from the last 2 years). Put the source URL in `CHANGELOG.md`. If you can't verify, leave the number alone and tell the user.
- Keep everything in `index.html`. No frameworks, build tools, trackers, analytics or external scripts. The only external resource allowed is the Google Fonts stylesheet, with system font fallbacks.
- The emergency card (helplines, four steps, "no milk" warning) stays first and short. New content goes into a `<details>` section.
- Never add advice that encourages keeping a squirrel as a pet or long-term home care.
- Colours are CSS variables in `:root`, with matching dark-mode values. Don't hard-code colours elsewhere.
- Ask the user before deleting a section or changing the page's overall structure.
