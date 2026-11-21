# PhotoCaption

The row under the About photo, with external links on the left and the current photo's `place · country` on the right.

- It sits `space-10` under the photo, with `space-between` alignment. Links are 12px `text-dim` (hover `text`) and `space-16` apart.
- The location is 12px: place in `text` at weight 500, then a middle dot and the country in `text-dim`. If the country matches the place, it's left out (for example Mauritius).
- It updates with the gallery (every 6s, or when the photo is clicked) and is `aria-live="polite"`. Places and countries need German forms (Jordanien, Schweiz, Black-River-Gorges-Nationalpark).
- Use country names, not coordinates.
