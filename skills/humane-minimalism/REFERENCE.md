# Humane Minimalism Reference

Topic-by-topic specifics: verified values, techniques, and judgment tests. All values were extracted from shipped source code or verbatim published writing (July 2026). Use these as starting points, then tune by eye.

## Editorial typography

- Body-size procedure: 320px column → 5–6 words/line; ~700px column → 10–14 words/line, +1–2px size, +5–10% line-height; breakpoint where both settings feel slightly wrong. One shipped result: 18/24 until 600px, then 20/28, 700px max width.
- A live production system: ONE typeface (Familjen Grotesk variable, self-hosted), four sizes (0.875 / 1 / 1.125 / 1.25rem), "bold" is weight 500, h1 is body-sized. Measure 34rem. Dark-only: #000 page, #151515 panel, #ddd text, #fff headings, hairlines rgba(255,255,255,0.12), one accent rgb(200,150,100) used only for link underlines/hover.
- Hierarchy order: spacing → weight → color → size → typeface switch → accent. Lowest heading resembles body text; each level up gets one more step of distinction plus more surrounding space.
- Typeface-pairing smoke test: set both candidates as body text at the same narrow measure; if line breaks frequently match, their horizontal rhythms are compatible.
- Line-height/spacing in multiples of 4. Trust the eye over numbers; skip modular scales.
- Grain test: fluid, vertical, edgeless is what the web wants; reject techniques that are impressive because they fight this.
- Complexity rule: instead of changing tools or workflow, change the design.

## Motion constants

- Durations: micro-interactions 100–150ms; tooltips/dropdowns 150–250ms; modals/drawers 200–300ms; exits ~20% faster than entrances. Nothing above 500ms; 500ms reserved for full-screen gesture surfaces.
- Easing: enter/exit viewport → ease-out; on-screen move/morph → ease-in-out; hover color → ease; constant motion → linear; default → ease-out. Built-in CSS curves are weak; use custom beziers. A proven hover/press curve: cubic-bezier(.165,.84,.44,1) (easeOutQuart) at 200ms. iOS sheet curve: cubic-bezier(0.32, 0.72, 0, 1) at 500ms (Vaul).
- Sonner constants: 3 visible toasts, 356px wide, 14px gap, 4000ms lifetime, swipe-dismiss at ≥45px OR velocity >0.11px/ms, exit keyframe 200ms ease-out, rear toasts scale 1−0.05n.
- Vaul constants: velocity threshold 0.4 (flick-close), close below 25% travel, 100ms scroll-lock timeout between inner-scroll-top and drag-start, logarithmic overdrag damping 8·(ln(v+1)−2), background scales down + gains radius proportional to drag.
- Micro-rules: scale(0.97) on :active; enter from scale(0.93–0.95), never 0; transform-origin at the trigger; ~2px blur to mask crossfade seams; transform/opacity only; 44px minimum hit area via pseudo-element; extend hit areas during gestures (::before at ±100% width); zero-duration for subsequent tooltips; disable hover-lift on touch devices.
- Never animate keyboard-initiated or hundreds-of-times-daily actions.

## Typographic ink and restraint

- Body ink: variable font at custom weight 440 ('wght' 440), color #4a515b (a tinted slate rather than black) on #fcfcfc; every gray from one hue-consistent "ink" ramp; tinted ::selection.
- Hierarchy without size: headings body-sized, weight 600, one shade darker, mt-14/mb-7, text-balance. One vertical rhythm unit (1.75rem) for all prose spacing.
- Emphasis voice: an italic serif (Lora Italic used upright) for em/blockquote/nav instead of bolding.
- Links: decoration-from-font underlines in a lighter shade than text, darkening on hover.
- Justified prose stack: text-align justify + hanging-punctuation first allow-end last + hyphens auto + hyphenate-limit-chars 10 6 6 (+ text-spacing-trim for CJK).
- Fonts: self-hosted, font-display: block with metric-matched fallbacks (ascent-override/size-adjust); prefer an invisible flash over layout shift.
- Transitions: ~200ms ease; page transitions are blur-crossfade only (out 0.4s to blur(4px); in 0.6s with 0.2s delay), guarded by @supports and prefers-reduced-motion. Nav hover: color only, transform-none.
- Budget-first design: set the byte/perf budget before designing (COBE: 5kB globe, 1kB texture); degrade assets until they stop looking almost the same, ship one step before that.
- Animation tests: does it inform (appeared/left/changed/interactive)? does it pull attention from content? does it slow the site? Any yes on the last two → remove.

## Motion architecture and delight

- Three principles: simplicity (fundamentals at your fingertips, everything else appears when relevant), fluidity (you float rather than walk), delight (selective emphasis).
- Motion tests: every animation must explain A→B; the app has unbreakable physical rules; persisting elements stay visually continuous (shared-element rule); no redundant animation.
- Delight-Impact Curve: delight potential rises as usage frequency falls. Rare flows (onboarding, backup, recovery) get spectacle (confetti, sound, skeuomorphism); daily flows get easing quality and haptics only.
- Techniques: tray/sheet system whose height changes per step (progress felt without a progress bar); directional motion mapped to IA (tab order → slide direction); text/icon morphs instead of swaps (Continue→Confirm); status indicators migrate to where the result will live; selective skeuomorphism + sound for destructive actions.
- Atmosphere formula: custom or characterful typeface + warm off-whites (#fbfaf9, #f3f5f7) + one saturated brand color (#1A88F8); gradients only as loading shimmer. Mood comes from type, warmth, and motion rather than ornament.
- Evidence habit: publish rationale with screen recordings at 1x and 0.5x.

## Systems discipline

- A value earns a token name by recurring; name what you need this week (most of the difference between 20 tokens and 487).
- Names carry purpose rather than scale: Toast/Background/Default over Neutral/400; the name becomes the instructions for every tool that touches it.
- First taxonomy split: non-interactive (environment) vs interactive (behavior). Primitives are options, semantics are choices; expose only choices; alias every primitive.
- Divergence test: could these two elements ever differ? Yes → component token; no → shared semantic token. Alpha convention: Blue/500-A50.
- Write the why in one sentence where the name lives. Renames are maintenance rather than surgery.

## Tactile explanation

- Show-the-thing: if a behavior can be demonstrated live, prose is a fallback. Open with a sandbox + live event log before teaching.
- Scrollytelling mechanics: prose blocks are scroll listeners; the explained artifact (code panel, diagram) stays pinned while highlights change with reading position; clicking prose scrolls the artifact.
- Ease-begets-use: enlarge hover/hit targets with invisible overlay elements (hovering anywhere triggers the tooltip); duplicate hover reveals with click/scroll paths.
- Same data in synchronized multiple views; edits round-trip.
- Pacing: one idea per screen for openers (picture-book cadence), then 20px serif at ~1.9 line-height for connective prose, 1–3 sentences between demos, jump-linked headings.
- Progressive-enhancement showmanship: plain fallback declared first, fancy rendering (oklch gradients, SVG-clipped text) layered after. Playfulness never carries information alone.
- Control tests: is the human still in control of the outcome, or a machine operator? Keep friction that carries meaning; cut friction that breaks flow.

## Material play

- One expressive move on a calm ground: the purest shipped case is whole-page SVG feTurbulence + feDisplacementMap backdrop-filter over plain semantic HTML, zero JavaScript. Personality in one global filter; content stays a boring document.
- Content-level jokes over interaction-level jokes (a redacted-block employer, a decorative game-tile divider, self-deprecating alt text): humor that costs no usability.
- Feedback-loop test: does this activity shorten idea→reaction-to-the-real-thing? If code is faster than a design tool for the question, skip the design tool.
- Edge-case ownership: the designer walks every edge case by building it; if engineers discover the edge cases after handoff, that is too late.
- Mood boards should contain technologies: understand the material (GPU, CRDT, DOM) until it suggests ideas.
- Cap the room: hard-limit social/spatial software (one shipped example: 8 people, no accounts); expose one real escape hatch (user-editable CSS) instead of settings panels.
- Demo the material on its own marketing page ("Try it with your face" + inline privacy reassurance at the point of ask).

## Scope as personality

- Smallness test: can it be named in one or two lowercase words and explained in one line? The name is the spec.
- One verb per shipped unit; personality via naming, microcopy, and easter-egg conventions, never via configuration surface.
- AI as amplifier rather than replacement: package AI as a few named, bounded capabilities (like Diagram's Magic Icon and Magic Copy) grounded in the user's own components instead of one open prompt box.
- Real-thing test: people using the actual artifact beats internal polish.
- Meet users inside their existing tool (plugins over destination apps); defer infrastructure (an Airtable backend) with written swap-out conditions.
- Dogfood identity: one practitioner's homepage is an iframe of their own smallest product.

## Triangulated laws (reached independently across the school)

1. **Frequency law** (stated independently at least twice): expressiveness budget is inversely proportional to usage frequency.
2. **Calm ground, one move**: one expressive gesture per surface against conventional structure.
3. **Motion = spatial information**: animation exists to explain appearance, departure, change, or connection; otherwise it doesn't exist.
4. **Judgment freezes into constants**: tune by eye, then commit numbers/tokens and reuse.
5. **Typography is the surface**: type + spacing + one accent carries the entire visual identity; hierarchy from spacing/weight/color before size.
6. **Depth from behavior**: direct manipulation and live demonstration over decoration and description.
7. **Maker-designer unity**: quality comes from the same brain designing and building: edge cases, materials, constraints.
