---
name: maintain-rescue-site
description: Maintain the Baby Squirrel Rescue Kit page (index.html, GitHub Pages). Use for any edit to the site, checking or updating helpline numbers, adding content or translations, or running the monthly check.
---

# Maintaining the Baby Squirrel Rescue Kit

The whole site is `index.html`. GitHub Pages serves `main` from the repo root, so a push to `main` is live within about a minute. People in an emergency rely on this page, so accuracy beats speed.

## Page structure (keep this order)

1. Hidden SVG `<symbol>` icon set (`#i-look`, `#i-wait`, `#i-warm`, `#i-call`, `#i-leaf`, `#i-hand`, `#i-cup`). Reuse them with `<svg><use href="#i-…"/></svg>`.
2. `header.hero`: inline SVG illustration (squirrel on a branch, coloured only with CSS variables), `<h1>`, the lede, and the "Hurt or in danger? See who to call" link to `#helplines`
3. `ol.trail`: exactly four `li.step`s in this order, because it's the real order of what to do:
   1. Look before you touch (age cards)
   2. Give mum a chance (with the "Skip straight to step 3 if…" box)
   3. Keep it warm, dark and quiet (with the "Don't feed it" note)
   4. Call a rescuer: `.lines#helplines`, one `.line` per helpline (name, short note, number with a Copy button whose `data-copy` is the number in `+91XXXXXXXXXX` form)
4. `section.group` "Until help arrives": `<details>` panels
5. `section.group` "Help more": `<details>` panels
6. `footer`: leaf-vine SVG, the "Numbers from … [Month Year]" line and the disclaimer

## Look and feel

- A calm leaf-and-bark palette, all from the CSS variables in `:root` with dark-mode twins. No red or alarm styling. Warnings use `--bark-soft` boxes.
- Illustrations are hand-written inline SVG built from simple shapes, with fills from CSS variables so they work in dark mode. Don't add image files, stock photos or copyrighted characters.
- The tone is calm and reassuring: most found babies don't need rescue.

## Procedure for any change

1. **Read** `CLAUDE.md`, then the part of `index.html` you'll change.
2. **Decide where it goes.** New material belongs in a `<details>` panel. Only change the emergency card if the user explicitly asks, and keep it short.
3. **Edit** using the existing classes and CSS variables. Copy the markup of a neighbouring element rather than inventing new styles.
4. **Check**:
   - The HTML is well-formed: every tag closed, attributes double-quoted.
   - Every phone number appears the same way in the visible text and in `data-copy`.
   - Open the page in a browser at about 400px wide, in both light and dark mode. Nothing should scroll sideways, and all helpline numbers should be visible on the first screen. Use a headless browser screenshot if one is available.
   - The browser console shows no errors.
5. **Log it** at the top of `CHANGELOG.md` under today's date, with sources for any facts.
6. **Commit** with a plain message, such as `Update ARRC number` or `Add Kannada emergency steps`, and push to `main`.
7. **Confirm** the live URL shows the change (allow 1–2 minutes), then tell the user what changed.

## Changing a helpline number

- Verify it from the organisation's own website first. A news report from the last two years is the fallback. Directories and aggregator sites aren't enough on their own.
- If two sources disagree, don't guess: tell the user and keep the current number until they confirm by phone.
- Update the visible number, the `data-copy` value, `CHANGELOG.md` (with the source URL) and the footer month.

## Monthly check

Run this when the user says "monthly check", or on a schedule:

1. For each helpline, open the source in `CHANGELOG.md` and confirm the number is unchanged. Search for newer Bengaluru squirrel or wildlife rescue helplines, and report any you find without adding them yet.
2. Confirm the live site loads and shows the numbers.
3. If everything matches, only update the footer month and add a "Monthly check: no changes" changelog line.
4. Report to the user: what you verified, anything that needs a phone call, and any suggested additions.

## Translations

For a Kannada or Hindi version, add a language switcher only if the user asks. Otherwise add a `<details>` panel near the top titled in that language (for example "ಕನ್ನಡದಲ್ಲಿ") containing the four steps and the milk warning. Ask the user to have a native speaker review it before or right after publishing, and note that in the changelog.

## Don'ts

- No frameworks, build steps, analytics, cookies or extra external scripts.
- No advice on long-term home care, keeping a squirrel as a pet, or releasing one yourself.
- Don't delete sections or restructure the page without asking.
- Don't force-push or rewrite history on `main`.
