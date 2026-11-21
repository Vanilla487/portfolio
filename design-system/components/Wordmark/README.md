# Wordmark

The type-only logo: "lwc" in lowercase DM Sans 500 at 22px, which unfolds into "lewis william christie" on hover.

- Each initial is a two-column grid (`auto 0fr`) holding the letter and the rest of the name. On hover the column opens to `1fr` over `1.1s cubic-bezier(0.4, 0, 0.2, 1)`.
- In the site, an invisible copy of the full name reserves the width so nothing reflows. Place it top-left at `space-36` / `space-40`.
- There is no graphic mark. Don't substitute an icon, a monogram badge or a different face. The preview shows the closed and open states.
