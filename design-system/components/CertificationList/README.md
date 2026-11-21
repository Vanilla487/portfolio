# CertificationList

A ruled list of credentials: name, a hairline that stretches to the right, and the year in an aligned column. A pending one shows a status word and the pulsing dot.

- Each row is a grid `auto 1fr 4.4em`, so every year starts at the same x whatever the name's length. The dot is allowed to overhang (the list keeps `1.6em` right padding for it).
- Type is DM Sans 400, `clamp(18px, 2.4vw, 30px)`, line height 1.2, with `.22em` row padding. The rule is 1px `text` at 85% opacity, vertically centred.
- **Pending:** replace the year with the status word ("Pending" / "Ausstehend") followed by a PulseDot. Only one row should pulse at a time.
- Use a `<ul>`. Rules and dots are `aria-hidden`. Official titles stay in English in both languages. Under `bp-phone` names may wrap.
