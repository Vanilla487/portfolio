# PulseDot

A small `focus`-coloured disc with a ring that grows and fades on a loop. It signals something live or in progress.

- Sized in `em` (`.55em`) so it scales with the text beside it, and placed `.5em` after the word.
- The ring is a copy of the dot that scales from 1 to 2.6 while its opacity goes from .7 to 0, over `1.8s ease-out`, on an infinite loop. The solid core stays still.
- Under `prefers-reduced-motion` the ring is hidden and only the solid dot shows.
- Always pair it with a word ("Pending"), because colour alone doesn't carry the meaning. Mark it `aria-hidden`. Keep it to one per view.
