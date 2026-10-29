# Validation and scope

Finalized 29 October 2026 after two content-driven demo implementations.

## Evidence behind the defaults

The first demo applied the visual grammar to a personal introduction and a game project. User review led to three-column ordinary images, fewer competing blocks, full-bleed atmospheric media, section-level steps and a one-time 0.9 type scale. Deeper case-study content moved to its own page.

The second demo applied it to a six-page animation archive. Its first teal/dark-ocean theme was rejected. The accepted correction restores pure black/white and neutral grays, replacing only the accent with `#0070f0`. The skill preserves that distinction rather than treating a new accent as a whole-site colour wash.

## Observed demo checks

- Browser checks covered phone/tablet/desktop and both sides of 599px and 1023px. No horizontal document overflow was observed in checked layouts.
- At 1440px, tracks measured approximately 221 / 293 / 293 / 293 / 221px after gutters. At wider viewports, the capped container stayed centered.
- Three central media tracks measured about 878px at 1440px.
- After scaling, display sizes measured 81px desktop and 39.6px phone.
- Modal menu navigation, Escape closure, image viewing, manual gallery controls and native disclosures were exercised where present.
- All six animation pages were checked at 390px for overflow and visibly failed images.
- The blue revision's computed surface/text colours were black/white/neutral; its accent measured RGB(0,112,240). Mobile overlays used neutral black.
- Static links, anchors, assets and heading structure were checked.

## Limits

These observations apply to the demos, not every future output. Reduced-motion styles were inspected; OS-level preference switching was not fully exercised. The embedded player loaded the original video and title, but full playback was not tested. Local browser checks and publication success were distinct; authenticated live interaction was not established for every deployment.

The supplied skill validator passed. All package-relative links resolve; the eight-file text package was checked for local paths, private preview URLs, personal identifiers and credential patterns.

A fresh-context evaluation used a specification-only request with a blue accent, preserved project wording and unreduced type. It selected blue-only accents, neutral surfaces, scale 1 and no external actions. Its feedback led to precise 1023px wording, explicit copy-preservation priority and a three-track-first approach to detailed storyboards. This is an instruction review, not a newly rendered application test.

These checks validate packaging and selected decisions, not automatic design quality or the rights to assets supplied in future tasks.
