---
name: rca-editorial-ui
description: Build or refine an RCA-inspired editorial website using Source Sans 3, a shared unequal five-column desktop and two-column mobile grid, monochrome sections, stepped transitions, spacious media, and restrained motion. Use for this specific visual language or an explicit RCA-style request.
---

# RCA-inspired editorial UI

An independent design-study skill, not an official RCA system. Apply its composition principles to the user's own identity and material. Source observations and tested adaptations are distinct.

## Read the content first

Read the supplied page, project or content before composing. Preserve project facts, credits, dates, draft status and destinations. Do not infer a completed film or product from a placeholder page. State source-access gaps instead of inventing content.

Use the existing stack and requested deliverable. This skill describes visual implementation; it does not independently authorize publishing, creating accounts, modifying other sites, or installing itself.

Read [implementation.md](references/implementation.md) before selecting tokens, spans or section geometry. Consult [source-observations.md](references/source-observations.md) when explaining what was actually observed on RCA or comparing source values.

## Visual grammar

- **One shared grid.** Content and decorative rules use the same centered, border-box 1440px container. Gutters are 20px below 599px and 60px thereafter. Use two equal tracks below 1023px; at 1023px and above, use `16.74% repeat(3, minmax(0, 1fr)) 16.74%`. Five equal viewport strips are a different design.
- **Measured type, modest scale.** Use Source Sans 3, principally 400 for titles/body and 600 for actions. Choose a type role, then apply the tested `0.9` scale once. This compact adaptation is not RCA's source value. Keep body text readable; do not rescale inherited or `em`-relative sizes. Honor explicit scale overrides.
- **Black and white first.** Surfaces are `#000` / `#fff`, with neutral secondary grays. The default action accent is `#ff5d1c`. The tested blue variant changes only the accent to `#0070f0`. An accent substitution does not imply tinted surfaces, teal grays, coloured overlays or recoloured artwork.
- **Deliberate image scale.** Ordinary landscape project images default to three desktop tracks, often columns 2–4. Keep detail images uncropped. Use full-bleed imagery selectively for atmosphere, with a separate neutral-black overlay when text needs it. Main mobile images and prose can span both columns.
- **Transitions belong to sections.** A stepped edge changes where adjoining regions meet. Align its vertical turn to a grid line, continue the fill to the viewport edge, and reserve space so it cannot cover content. A small tab pasted onto an image is not equivalent. Vary the side or use an actual media overlap when the material supports it; do not stamp an identical notch onto every section.
- **Reduce competition.** Give each stage one dominant image or thought. Remove duplicate summaries before adding padding. Leave empty tracks deliberately. Detailed evidence can move to a named disclosure or case-study page, but stays reachable. If the user asks to keep the wording, reduce competition through layout rather than deleting copy.
- **Short, purposeful motion.** Prefer 250ms underline, arrow, opacity and drawer feedback. Use a manual gallery only when it improves the content experience. Keep useful content available if JavaScript fails; remove decorative movement and smooth scrolling for reduced motion.

These are the tested defaults of this skill, not universal requirements for every website. Explicit user requirements and the material's accessibility needs take priority.

## Produce and check

Use appropriate project assets and an original identity. Do not package RCA's wordmark, site bundles, photographs, videos or site-extracted font files. When self-hosting Source Sans 3, obtain it from an upstream distribution and retain its OFL license.

Check phone, tablet and desktop composition and both sides of a changed breakpoint. Verify actual rule/content alignment, image spans, text wrapping, contrast and section-step clearance. Exercise the menu, gallery and disclosures actually included, including keyboard closure and focus. A screenshot alone does not establish full responsive or media verification.

Report the useful result and material verification limits. Keep implementation measurements out of visitor-facing copy unless they help that visitor.
