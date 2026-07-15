---
name: humane-minimalism
description: Design or refine interfaces in the humane-minimalist tradition — calm typographic surfaces with deep, tactile behavior. Use when designing or polishing UI, choosing typography or type scales, adding or auditing motion and transitions, making a site or app feel warmer and more crafted, or deciding where playfulness and delight belong.
---

# Humane Minimalism

This skill distills the working judgment of a school of design whose common trait is a specific structure rather than a minimal style: **a simple surface with unusually deep behavior**. Surfaces in this tradition are calm, typographic, almost plain. The personality lives in how things move, respond, and connect, and every expressive move is rationed. When you design under this skill, you are aiming for software that feels clearer, livelier, and more inevitable, never merely decorated. Companion craft: `REFERENCE.md` holds specific values and techniques; reach for it when you need numbers.

## The ground comes first, and the ground is text

Start with body text before layout. A reliable procedure: set the paragraph in a 320px column and find the size giving five or six words per line; widen to ~700px, add a point or two of size and 5 to 10% of line-height, aiming for ten to fourteen words per line; put the breakpoint where both settings feel slightly wrong. Keep the measure near 34 to 42rem. Keep the whole system to a handful of sizes (four is workable; if you need more than seven, you're misusing the other tools). Build hierarchy by exhausting **spacing, then weight, then color, before size**: a heading that is body-sized, semibold, one shade darker, with generous space above, outranks a big one. Ink is never pure black on pure white: one proven recipe sets body text at a custom 440 weight in a tinted slate (#4a515b on #fcfcfc) and derives every gray from one hue ramp. One accent color does all interactive signaling. Structure comes from whitespace and hairlines (~1px at ~12% opacity), not boxes. Round line-heights and spacing to a 4px rhythm, then trust the eye over the numbers.

## Motion is information, budgeted by frequency

Every animation must say something: that a thing appeared, left, changed, or is connected to what came before. The test: does this transition explain the path from A to B? Treat the app as having unbreakable physical rules: elements move, morph, or persist, and they never teleport (static transitions feel like digital whiplash). But the budget is governed by frequency, a law this school arrived at independently more than once. A launcher like Raycast, opened hundreds of times a day, would be maddening if it animated on every open. Spectacle belongs to rare moments (onboarding, completion, recovery), while daily actions get only easing quality and haptics. Never animate keyboard-driven or high-frequency actions at all.

When motion does run: enter with ease-out, 150–250ms for standard UI (drawers up to 300–500ms); exits ~20% faster than entrances; scale in from 0.95, never 0; set transform-origin to the trigger so motion emanates from where the user acted; animate only transform and opacity; prefer interruptible transitions over keyframes; always honor prefers-reduced-motion. When unsure, remember the school's verdict: sometimes the best animation is no animation.

## Depth is behavior, not decoration

What makes these interfaces feel alive is that they respond like material. The rule: if a behavior can be demonstrated, prose about it is a fallback. Show the thing, live, and let the reader poke it; enlarge hit targets invisibly so interaction costs nothing. The purest case in this tradition is a personal site with zero JavaScript and plain semantic HTML, plus one SVG turbulence filter through which the whole page shimmers. **One expressive move per surface, played against a conventional ground.** That is why the play never reads as frivolous: the jokes are content-level, the markup stays boring, and the single effect gets all the attention. Call the underlying discipline the grain: work with what the medium wants to do (fluid, vertical, edgeless) and reject bear-on-a-bicycle stunts that are impressive precisely because they fight it. Before adopting machinery to manage complexity, change the design so the complexity disappears.

## Craft is judgment, frozen into constants

This school tunes by feel, then commits the result as a number and defends it: one shipped swipe-dismiss gate is 45px or 0.11px/ms of velocity, found by trial and error and then frozen; the open source drawer library Vaul runs the iOS curve cubic-bezier(0.32, 0.72, 0, 1) at 500ms. Do the same: when something finally feels right, extract the values, name them, and reuse them. A token earns its name by recurring: name what you need this week, and skip what you might need someday. And keep scope itself as a design material: single-purpose tools, one verb apiece, named small, shipped real and early. The maker who walks every edge case before handoff is where quality comes from.

## The refusals

What this school does not do is most of the style. No hero images, carousels, or portfolio theater. No decoration that carries no information. No animation on frequent paths. No entrance from scale(0), no bounce, no motion that fights or fakes physics. No pure black on pure white, no second accent color, no type scale sprawl. No configuration panels where a better default or one real escape hatch would do. No complexity-management tooling where a simpler plan removes the complexity. No shipping the fancy version without a plain fallback beneath it. When in doubt, delete — and if fluent users then name a workflow they lost, that deletion was wrong; restore it.

## Checks to run before calling it done

1. **Squint test** — does the page read as even, calm type-color with one focal point?
2. **Frequency audit** — is anything animated that a user triggers many times a day?
3. **A→B test** — does every transition explain where things came from or went?
4. **Grain test** — is anything here impressive because it fights the medium?
5. **One-move test** — is there exactly one expressive gesture on this surface, on a calm ground?
6. **Deletion pass** — remove the least defensible element; did anything break? Repeat.
