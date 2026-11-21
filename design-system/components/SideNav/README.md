# SideNav

A right-aligned, vertically centred stack of lowercase section links that highlights the section being read.

- Fixed to the right edge (`space-40` in, `top: 50%`). Under `bp-tablet` it becomes a wrapping row.
- Links are 14px `text-dimmer`, hover `text-dim`, and active `text` at weight 500 (`is-active`).
- **Active logic:** the active section is the last one whose top has passed a line 30% down the viewport. At the page bottom, the last section is active. A click highlights its item straight away and holds it until the smooth scroll settles. Don't use a narrow IntersectionObserver band, because short sections get skipped.
- The consumer supplies the section ids and the EN/DE labels. Toggles (PillButton) sit `space-28` below.
