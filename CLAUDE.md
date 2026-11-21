# Working on this repo

Personal portfolio for Lewis William Christie. Static site: `index.html` (markup, EN/DE translations, scripts), `main.css` (styles), `assets/` (images). No build step.

## Source of truth

- This repo's `main` branch on GitHub (`Vanilla487/portfolio`) is the only real copy of the site. Always pull the latest `main` before changing anything.
- Never edit copies of `index.html` or `main.css` saved elsewhere (claude.ai Project files, old downloads, chat attachments). If one turns up, treat it as out of date.

## Design system

The lwc design system lives in `design-system/`. Read it before any visual change and follow it:

- `design-system/README.md`: voice, casing, colour, type, layout, motion, iconography and accessibility rules.
- `design-system/tokens.css` and `design-system/api/tokens.md`: colours, type styles, spacing, radius, sizes and breakpoints.
- `design-system/components/<Name>/README.md`: per-component rules (SideNav, PillButton, Wordmark, JobEntry, CertificationList, ProjectItem, PhotoCaption, PulseDot, GroupLabel).

Rules that are easy to break:

- Only use spacing values from the spacing tokens (2, 8, 10, 14, 16, 22, 24, 26, 28, 36, 40, 60, 70). Sections keep 70px vertical padding.
- No cards, borders or shadows. Structure comes from size, alpha and whitespace.
- `text-dim` for anything people need to read. `text-dimmer` only for inactive nav links and the footer.
- `focus` (orange) is the only hue: focus rings, selection and live status. One orange thing per view.
- Two type families only: DM Sans for headlines and list items, Inter for small text (14px body, 12px captions).
- Interface words are lowercase. Every visible string needs English and German versions in the `i18n` object in `index.html`.
- Under 780px (`bp-tablet`) the top bar stacks: wordmark and toggles on one row, nav links as a wrapping row below.

If a change needs something the design system doesn't cover, say so instead of inventing a new value. If the design itself changes, update `design-system/` in the same commit (or flag that it needs regenerating; it was generated from `main@973fe26`).

## Checking changes

- Look at the page at phone width (360–390px) and desktop width (about 1440px), in dark and light theme, and in English and German.
- Make sure nothing scrolls sideways on phones.

## Git

- Ask before committing or pushing, and say whether it's going to `main` or a separate branch.
