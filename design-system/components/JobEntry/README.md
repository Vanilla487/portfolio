# JobEntry

One role in the work history: an employer mark in a round disc, then the company, a large lowercase title, dates and place, and one sentence of description.

- Grid: a `size-logo-disc` column (56px, or 44px under `bp-tablet`) plus the text, `space-22` apart, with `space-26` vertical padding.
- **Disc:** `pill` fill. The consumer supplies the employer's single-colour SVG mark (28px, `fill="currentColor"`). The preview uses a generic placeholder mark.
- **Text:** company is 12px DM Sans in `text-dim`. Title is DM Sans 700, `clamp(22px, 3vw, 32px)`, lowercase. Meta is 12px `text-dim` with `space-14` between date and city. Description is 14px/1.6 `text-dim`, max `width-prose`.
- Dates use years with a spaced en dash (`2023 – 2024`). Title and description need EN and DE versions.
