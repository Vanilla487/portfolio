# lwc

Quiet type, warm neutrals and one orange signal. This is the design system behind Lewis William Christie's portfolio (`Vanilla487/portfolio`). It's a dark-first, typographic site where big DM Sans headlines carry the page and almost everything else steps back.

## Content fundamentals

- **Voice.** First person, plain and brief. Say what was done and for whom: "Owned a central feature for distributing letters across all case types." No buzzwords, no exclamation marks.
- **Casing.** Interface words are lowercase: nav (`intro`, `work`, `certifications`), job titles (`senior system architect`), company names (`ai4process`) and the wordmark (`lwc`). Proper titles keep their own case: certification names ("Lead System Architect"), project names ("What's For Dinner?"), places ("Black River Gorges National Park").
- **Bilingual.** Every visible string has English and German versions (`en` / `de` toggle). Write both. German labels follow the same casing (`zertifikate`, `über mich`). Place names translate where German has its own form (Jordan → Jordanien, Switzerland → Schweiz). Official certification titles stay in English.
- **Numbers and dates.** Years only, with an en dash and spaces for ranges: `2021 – current`, `2023 – 2024`. A status replaces the year when it's unknown: "Pending", followed by the pulsing dot.
- **Separators.** A middle dot with 8px either side: `Wadi Rum · Jordan`. Never a slash or a pipe.

## Visual foundations

### Colour
Neutral-first. `bg` and `text` do almost all the work. Hierarchy comes from **alpha on the ink**, not from new hues, which is why secondary text is warm grey in both themes. There are two levels below `text`, and the rule for choosing is simple:
- **`text-dim`** for anything someone needs to read: descriptions, dates, company names, labels, links.
- **`text-dimmer`** only for things that are fine to miss: inactive nav links and the footer. Never use it for content.

`focus` is the only hue. It marks focus rings, text selection and live status (the Pending dot). Allow one orange thing per view. Don't use it for decoration or headings.

Dark is the default theme. Light is a warm paper version (`bg` `#f6f4ef`), not pure white. Themes cross-fade over `.35s`.

**Contrast flags (kept from the source):** `text-dim` is about 3.8:1 (dark) and 3.4:1 (light) on `bg`. That's acceptable for type at 24px or larger, but under 4.5:1 for the 12–14px text it's used on. Raising its alpha to .5 in dark and .62 in light would clear 4.5:1 (4.9:1 in both). `text-dimmer` is about 2:1, which is why it's limited to inactive nav and the footer.

### Type
- **DM Sans** (`--font-display`) for anything that reads as a headline or list item: the hero (88px), the name block (96px), job titles (32px, bold, lowercase), certification rows (30px, regular) and the wordmark. Display letter-spacing is `-0.01em`.
- **Inter** (`--font-body`) for everything small. There are only two sizes: **14px** for paragraphs and nav, **12px** for captions, dates, labels and links. Item titles (project names) are 16px DM Sans.
- Large sizes are fluid with `clamp()`. The token values are the desktop maximums, and each usage note gives the clamp.
- Sections have no visible headings. The one label on the page is the certification group label: 12px, sentence case, `text-dim`.

Both families are Google Fonts, loaded with a single `<link>` in the page head: DM Sans at 400–800 and Inter at 400–600.

### Layout and spacing
- A single column up to `width-page` (1400px), with a 40px gutter (24px under `bp-tablet`). Every section has 70px vertical padding.
- Navigation lives on the **right edge**, vertically centred: a right-aligned stack of lowercase links, then the round toggles.
- Under `bp-tablet` About becomes a single column: name, photo, caption row, then the paragraphs.
- Content is open and borderless. There are no cards and no shadows. Structure comes from size, alpha and whitespace. Where a line connects things (certification name → year), it's a 1px rule in `text` at 85% opacity, not `rule`.
- Spacing values are the ones the code uses (2, 8, 10, 14, 16, 22, 24, 26, 28, 36, 40, 60, 70). Reuse them rather than inventing in-between steps.

### Shape
Round or square, nothing in between. Controls, logo discs and status dots use `radius-round`. Photos are square-cornered. `radius-md` (14px) is kept for image tiles but isn't on the site right now.

### Imagery
Portrait photos are **black and white first**, with grain. Colour is revealed in a soft circle under the pointer, and the circle fills the photo if the pointer rests on it. A caption row under the photo carries the links on the left and the `place · country` on the right. The photos cross-fade every 6s and pause on hover.

### Motion
Short and soft. There is no motion token family, so here are the values the code uses:
- Hover colour and fill: `.2s ease`. Pill buttons also lift by `translateY(-1px)`.
- Theme switch: `.35s ease` on background and colour.
- Photo cross-fade: `.6s ease`.
- Wordmark expand (`lwc` → `lewis william christie` on hover): `1.1s cubic-bezier(0.4, 0, 0.2, 1)`.
- Status pulse: a ring that scales from 1 to 2.6 while fading from .7 to 0, over `1.8s ease-out`, looping.
- Smooth scrolling for nav jumps.

Under `prefers-reduced-motion: reduce`, all transitions, the pulse ring, smooth scrolling and the photo autoplay are switched off.

## Iconography
- Inline SVG, stroked in `currentColor`, with round caps and joins. The stroke is 2px at 16px (UI icons) and 1.4px for wide arrows.
- The project link icon is a diagonal arrow-out (`M7 17L17 7M7 7h10v10`) at 16px and 60% opacity, sitting 4px after the name.
- Theme toggle: a sun (circle with eight rays) in dark mode and a crescent moon in light mode.
- Employer marks are single-colour SVGs filled with `currentColor`, 28px inside a 56px `pill` disc. They are third-party logos, so they aren't part of this system's assets.
- Never use emoji as icons.

## Logo
There is no graphic logo. The wordmark is **`lwc`** set in DM Sans 500 at 22px, lowercase, top-left. On hover each letter expands into the full name, *lewis william christie*. See the Wordmark component.

## Accessibility
- The focus ring is 2px solid `focus` with a 3px offset and `radius-sm` corners on every focusable element.
- Decorative parts (connecting rules, status dots) are `aria-hidden`. The photo caption is `aria-live="polite"`. The clickable photo has `role="button"` and a translated `aria-label`.
- See the contrast flags under Colour.

## Not synced
Built from `Vanilla487/portfolio` at `main@973fe26` by reading `main.css` and `index.html`.
- **Fonts:** no font files. Both faces are hosted by Google Fonts, so they're named in `type.families` only.
- **Assets:** no uploads. The site has no logo file, and the files in `assets/` are employer logos and personal photos rather than brand assets.
- **Components:** the site has no component library. The previews here are static HTML with the site's own CSS, copied into `components/bundle.css` with a `lwc-` prefix. They aren't a JavaScript bundle.
