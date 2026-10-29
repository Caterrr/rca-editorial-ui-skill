# Implementation defaults

Use these defaults for this skill, adjusting to the user's material and explicit requests. Historical measurements remain in [source-observations.md](source-observations.md).

## Tokens and type

An accent substitution changes the accent, not the whole palette.

```css
:root {
  --ed-black: #000;
  --ed-white: #fff;
  --ed-secondary-light: #676767;
  --ed-secondary-dark: #bbb;
  --ed-accent: #ff5d1c;
  --ed-type-scale: .9;
  --ed-ease: cubic-bezier(.24,.26,.2,1);
}
[data-accent="blue"] { --ed-accent: #0070f0; }
```

Opaque blue `#0070f0` has about 4.59:1 contrast against white and 4.58:1 against black. Recheck if opacity, blending or an image changes the background. Do not assume the source orange passes small-text contrast on white; a neutral action label with an orange rule or arrow is an appropriate adaptation.

Apply a single multiplier to each final font size:

```css
.ed-body { font-size: calc(18px * var(--ed-type-scale)); }
.ed-title { font-size: calc(44px * var(--ed-type-scale)); }
@media (min-width: 599px) {
  .ed-title { font-size: calc(78px * var(--ed-type-scale)); }
}
@media (min-width: 1023px) {
  .ed-title { font-size: calc(90px * var(--ed-type-scale)); }
}
```

This gives a 16.2px body and a 39.6 / 70.2 / 81px display title. Smaller title roles use the corresponding source role before scaling; not every section needs display type. A scale of 1 is available when explicitly requested. If “original sizes” refers to an existing site, restore that site’s pre-scale role values; do not silently replace them with the historical RCA table.

Quote `"Source Sans 3"` in CSS, including `@font-face`. Use 400/600 and `font-display:swap`; keep the upstream OFL license when self-hosting. The skill contains no font binaries. For Chinese, add a suitable system sans-serif fallback.

Controls should inherit type. Do not multiply unitless line-height, inherited text or `em`-relative icons again. Scale every term of a fluid clamp together. Do not repeatedly shrink body text to solve dense content.

## One coordinate system

An independently written recipe, not a copied site stylesheet:

```css
.ed-grid {
  box-sizing: border-box;
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  max-width: 1440px;
  padding-inline: 20px;
  margin-inline: auto;
}
@media (min-width: 599px) {
  .ed-grid { padding-inline: 60px; }
}
@media (min-width: 1023px) {
  .ed-grid {
    grid-template-columns: 16.74% repeat(3, minmax(0, 1fr)) 16.74%;
  }
}
```

Use the same container and tracks for decorative rules. Do not add a gap to one grid but not the other. Put breathing room within spans. Rule layers are non-interactive and hidden from the accessibility tree.

| Desktop content | Start column | Span |
|---|---:|---:|
| Small section label | 1 | 1 |
| Editorial heading | 2 | 2–3 |
| Readable passage | 3 | 2 |
| Ordinary landscape work image | 2 | 3 |
| Alternate landscape image | 1 | 3 |

Choose spans rather than filling every cell. Mobile prose and main media can span both columns. Three desktop tracks are an image default, not a cap on every kind of media. For detailed storyboards, keep that default and offer enlargement first. Widen only for a demonstrated legibility need or an explicit request, not merely because the asset is called a storyboard.

## Section geometry and imagery

Treat a step as part of the adjoining section's background. Reserve its height in the preceding section's bottom spacing so the entering fill cannot cover copy or controls.

- Start with heights 36 / 80 / 100px across the three viewport ranges, adapting when the composition calls for less.
- Place the vertical turn on a real grid line. At 1440px, a turn near 574px is the start of column 3. A guessed `40vw` does not stay aligned beyond the container cap.
- Continue the fill to the correct viewport edge. Change sides when the next image, title or empty track gives it a purpose.
- On phones, a midpoint step is often enough. Return overlapping desktop media to normal flow when absolute positioning would crowd the content.
- Keep screenshots and diagrams intact. Atmospheric full-bleed imagery is a separate mode, not the default treatment of every work image.

The desktop position of the start of column 3 can be understood as:

```text
containerWidth = min(viewportWidth, 1440)
outerMargin = (viewportWidth - containerWidth) / 2
contentWidth = containerWidth - 120
column3Start = outerMargin + 60 + contentWidth × (0.1674 + 0.2217333333)
```

Prefer equivalent grid placement where possible; this relationship does not require JavaScript layout calculations.

For text on imagery, place a separate **neutral black** overlay behind the text. Do not apply opacity to the entire section. Select strength from the actual image areas behind the copy, retaining faces, focal objects and useful detail. The source's 65% overlay was measured on one component only.

## Pace and interaction

Keep one dominant idea per stage. Avoid repeating the same premise in a hero, card, heading and paragraph. Move detail to a separate page or accessible disclosure when useful, preserving access to the evidence.

Prefer native controls where sufficient. A gallery needs clear labels, position, keyboard-operable previous/next controls and appropriate touch behavior. Preserve useful content or links when JavaScript fails. Modal menus/viewers should close with Escape, contain focus while open and return it on closure.

Use short 250ms feedback with the shared easing. A slower reveal is optional, not part of the source contract. Do not add autoplay or scroll parallax just to appear animated. Reduced motion should remove decorative transforms, reveals and smooth scrolling while preserving intentional user-controlled navigation.

## Focused verification

For new implementations, inspect phone, tablet, desktop and both sides of 599px / 1023px. For small revisions, check the changed behavior without rerunning unrelated tests.

Verify actual grid positions, image spans, overflow, font loading, step clearance and focus visibility. Exercise included interactions. Distinguish local browser results, source inspection, successful publication and authenticated live behavior; one does not prove the others.
