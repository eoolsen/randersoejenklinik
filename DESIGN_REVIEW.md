# Design Review — Randers Øjenklinik

_Senior visual/UX designer review, healthcare/specialist-practice lens._
_Date: 2026-06-30._

## Overall verdict

A competent, cohesive site (≈ B+). The design system is real — defined radius
scale, tinted shadow scale, consistent Feather-style iconography, restrained
motion. It reads more "modern clinic" than most Danish specialist-practice
templates. What holds it back from an A is **audience-fit and trust-craft**,
not aesthetics.

**Framing fact:** the audience is disproportionately elderly and visually
impaired — it is an *eye* clinic. Contrast, type size, tap targets and focus
states are therefore core brief, not polish.

---

## Findings by area

### 1. Color
- **Strength:** steel-blue + ochre-gold is a textbook complementary scheme;
  token system is disciplined.
- **Blue-heavy page:** header, hero, stats band and footer are all blue. The
  white/gray sections rescue it, but the frame feels cool/clinical-cold.
  Worth pressure-testing a **lighter, near-white header** — in this sector a
  clean white header often reads more premium/medical-grade and avoids
  competing with the hero directly beneath it.
- **Gold-on-steel-blue fails as text:** `--gold #c9963a` on `#a7c4de` ≈ 2.3:1,
  under the 4.5:1 floor. Used in top-bar/footer link **hover** states. Darken
  the hover gold or switch hover to a `--blue-deep` underline.

### 2. Typography
- **One typeface everywhere** (Source Sans 3) — safe but a little generic.
  Industry move: **pair it** (humanist serif or distinct display sans for
  headings) for warmth + differentiation.
- **Heading weight 800** with tight tracking is slightly aggressive for a
  care brand; test 700 on H2s.
- **Body too small for the audience:** service-card copy `0.9rem` (~15px) and
  nav `0.8rem` uppercase are risky for older eyes. Bump component body toward
  `1rem`. The 17px base is good — extend that generosity to components.

### 3. Layout, spacing, rhythm
- Good. 6rem section padding, 1140px container, generous subtitles — breathes
  well. Grids are sensible and degrade cleanly.
- Alternating white / `--gray-light` sections are **very** subtle; consider a
  hair more separation so sections read as distinct.

### 4. Components
| Component | Read |
|---|---|
| Hero | On-trend (pill eyebrow, glow orbs, floating eye, dual CTA). Gradient-only — no photography. |
| Nav | Glassy blur sticky + animated underline = nicely crafted. Uppercase 0.8rem is small. |
| Service cards | Best component — gradient icon tile, top-accent reveal, lift. Polished. |
| Stats | Good trust signals + gold-underline detail, but **percentages are unsourced** — add a source line or they read as marketing. |
| Team | Real faces = strongest trust asset. Keep. |
| Footer | Clean, well-structured; bookend weighting works. |

### 5. Motion
Tasteful, and **`prefers-reduced-motion` is respected** — exactly right for a
medical audience (vestibular sensitivity). No changes.

### 6. Imagery & content design — biggest opportunity
Site leans on gradients/SVG. In healthcare, **authentic photography is the #1
trust lever** — clinic interior, equipment, candid staff/practitioner shots.
A real, warm hero photograph would out-convert any styling change here.
**Status: deferred — real professional clinic photography to be added later
by the owner.** When photos land: replace/augment the gradient hero, add an
"about the clinic" band, and extend the authenticity of the team grid.

### 7. Accessibility (core brief here)
- **No visible focus states** — no `:focus-visible` styling; keyboard/low-vision
  users get only suppressed browser defaults on custom buttons/cards. Add clear
  focus rings. **High priority.**
- **No skip-to-content link.**
- **Hamburger:** static `aria-label="Åbn menu"`, no `aria-expanded` toggle, no
  animate-to-X.
- Contrast: gold hover (see §1); verify `--gray-text` body clears 4.5:1 at small
  sizes.
- Good marks: `lang="da"`, alt text on team photos, semantic sections,
  reduced-motion.

### 8. Conversion / UX (clinic-specific)
- **"Book tid →" doesn't book** — it anchors to a phone number. Either wire up
  online booking or relabel honestly ("Ring og book") and make the phone CTA
  unmissable. Older patients will call — make the number large and tap-friendly
  on mobile.
- **Surface credentials/accreditation higher** (DDKM, 30 years' experience,
  speciallæge status) — currently low/footer. Authority above the fold converts
  in medical.
- **Missing favicon / apple-touch-icon** — small polish tell.

---

## Prioritized punch-list

### P1 — do first (audience-critical)
- [x] Add visible `:focus-visible` states + skip-to-content link + hamburger
      `aria-expanded` _(done — PR #9)_
- [ ] Contrast fixes (gold hover) and bump component body text toward `1rem`
- [ ] _(deferred)_ Replace/augment gradient hero with authentic clinic +
      practitioner photography — **owner to supply photos**
- [x] Make booking CTA real or honestly labeled; prominent phone CTA on mobile
      _(done — PR #9: relabelled "Ring og book tid" + mobile sticky call bar)_

### P2 — elevate
- [ ] Pressure-test a lighter/white header vs. the current heavy steel-blue
- [ ] Introduce a type pairing (serif or display for headings)
- [x] Add favicon set _(done — PR #11: SVG + 32px PNG + apple-touch-icon,
      theme-color)_
- [ ] Source the stat percentages

### P3 — refine
- [x] Drop heading weight to 700 _(done — PR #10: section titles 800 → 700)_
- [x] Slightly stronger section-background contrast _(done — PR #10:
      `.section-alt` now uses a deeper blue-tinted `--gray-alt`)_
- [x] Custom logo mark _(done — PR #10: white almond, gold iris, dark pupil)_

---

**Bottom line:** the craft is here; the gaps are **trust and accessibility**,
which for an eye clinic are the whole game.
