# Source observations

Observed on the RCA homepage on **28 October 2026**. These historical implementation measurements are not an official brand specification or a claim about the current live site. Recheck the source when exact present-day fidelity matters. The tested adaptation is in [implementation.md](implementation.md).

## Type

The source uses Source Sans 3, body 18px / 1.4, principally weights 400 and 600. Heading weight is 400, line-height 1.22; links commonly use 600. RCA's SVG wordmark is separate artwork.

| Source role | Below 599px | 599–1022px | From 1023px |
|---|---:|---:|---:|
| display-one |44|78|90|
| display-two |38|68|76|
| one |32|52|64|
| two |28|38|46|
| three |24|28|32|
| four |22|26|30|
| five |18|20|24|
| body |18|18|18|

Values are CSS pixels **before** the adaptation's 0.9 scale. The original uses `font-display:block`; `swap` is an adaptation for resilient loading. The Latin subset does not contain Chinese glyphs; use an appropriate fallback for Chinese text.

## Grid

- Border-box container, maximum 1440px including padding, centered.
- Gutters: 20px each below 599px; 60px at and above 599px.
- Two equal tracks below 1023px; `16.74% 1fr 1fr 1fr 16.74%` from 1023px.
- At 1440px the content width is 1320px; internal boundaries are approximately x = 281, 574, 866 and 1159px.
- Above 1440px, the entire capped container centers rather than stretching the tracks.
- The fixed decorative rule layer uses 1px black/white lines with multiply/screen blending, `pointer-events:none` and hidden accessibility semantics. Inspect `.grid` and `.grid__lines`.

## Palette

| Role | Observed value |
|---|---|
| Black / white | `#000` / `#fff` |
| Action accent | `#ff5d1c` |
| Secondary on white | `#676767` |
| Secondary on black | `#bbb` |
| Dark / light rules | `#0000001f` / `#ffffff1f` |
| Focus indicator | `#009bde` |

Artwork supplies most additional colour. Observing a source colour is not evidence that every small-text pairing passes a contrast threshold.

## Three boundary mechanisms

1. **Grid-aligned fill:** `.section__notch-fill` changes the edge over one, two or three columns. `--opposite` reverses the filled side. Pseudo-elements continue the fill beyond the container to the screen edge. Observed heights: 36px phone, 80px tablet, 100px desktop.
2. **Crossing media:** in the inspected desktop `.promo-banner__media-container` variant, media starts at column 4, spans 2, has width 116.74% and a negative bottom margin of 70px. Its image extends upward with height `calc(100% + 280px)`. On narrow screens it returns to normal flow before the copy. These are one component's measurements, not universal overlap settings.
3. **Full-bleed image with partial pane:** the hero image remains visible beside the entering white action pane. The statistics section uses a cover image under `#000000a6` (about 65% black), with text staggered across columns. That opacity belongs to one source component, not every photograph.

Explanations about rhythm, continuity and reading pauses are design analysis. The research did not establish the designers' stated intentions.

## Motion and responsive behavior

| Behavior | Observed implementation |
|---|---|
| Shared easing | `cubic-bezier(.24,.26,.2,1)` |
| Drawer / header transform | 250ms |
| Link underline | 250ms, background-size 0 → 100% |
| CTA top rule | 250ms ease-out, 6px extension in the inspected variant |
| Arrow movement | 3–5px, usually 250ms |
| Carousel | 400ms, `cubic-bezier(.165,.840,.440,1)`, no autoplay |
| Parallax | General Rellax speed −3; homepage pane override −1 |
| Scroll-aware header | Headroom tolerance: 10px up / 20px down |

Some phone CTA rules cancel transforms. Selected components and smooth scrolling have reduced-motion handling, but complete parallax coverage was not established. New implementations should cover all decorative motion they introduce.

The hero uses viewport-specific crops. Promotional media can change order and span; carousel peeks also vary. Responsive composition is a deliberate reflow rather than only a smaller desktop.

## Source links

- [RCA homepage](https://www.rca.ac.uk/)
- [CSS bundle observed on 28 October 2026](https://www.rca.ac.uk/static2/css/main.d458428a8498.css): search `heading--display-one`, `grid__lines`, `section__notch-fill`, `promo-banner__media-container`, `stat-block-bg-image`.
- [JavaScript bundle observed that day](https://www.rca.ac.uk/static2/js/main.28fe610445f5.js): search `createSlideshow`, `data-parallax`, `animationDuration`, `Headroom`.
- [Source Sans upstream](https://github.com/adobe-fonts/source-sans) and [OFL license](https://github.com/adobe-fonts/source-sans/blob/release/LICENSE.md).

Hashed site URLs may change or disappear. This repository links to the source for attribution; it does not redistribute its bundles or assets.
