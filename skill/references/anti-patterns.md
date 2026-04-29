# Anti-patterns — the named tells

The `hallmark audit` verb flags these by name. Every one of these is a signature of AI-generated UI. Seeing one is a problem; seeing two in the same view is a confirmation.

Each entry: the tell, why it reads as AI-generated, and the fix.

---

## Critical (ships as slop)

### The purple-gradient hero

A hero section with a background gradient from purple to blue or purple to pink, often with white centred text. This is the single most-recognised AI aesthetic.

**Fix.** Pick a single anchor hue. One accent. No gradient backgrounds on heroes. If you want warmth, tint the neutrals.

### Inter-everywhere

Inter (or Roboto, or Open Sans) used as both display and body, with no pairing face. A one-font page is a template page.

**Fix.** Pair a distinctive display face with a refined body face. See [`typography.md`](typography.md).

### The 3-column feature grid

Three equal columns, each with an icon above a two-line heading above a three-line body. Usually spanned full-width with 24px gap. Every LLM emits this.

**Fix.** Break the grid. Vary column widths. Mix card heights. Remove one card and use negative space. Move the icons inline, not above. Or drop the cards entirely and use typographic rhythm.

### Card-in-card

A bordered container with cards inside it. Or: a card containing another card containing a small "micro-card". Visual nesting with no semantic reason.

**Fix.** Pick one containment layer. Usually the outer one is the wrong one.

### The gradient headline

A headline with `background-clip: text` fill set to a linear gradient (usually purple-to-pink or blue-to-cyan). Signals "AI generated" faster than almost anything else.

**Fix.** Solid ink. If you want the headline to feel alive, use weight or italic or a display face — not a gradient fill.

### The side-stripe card

A card with a thick coloured border on one edge (usually left, 4–6px, purple or green). Very recognisable; very 2018-SaaS-AI.

**Fix.** Use a hairline border all around, or no border, or a small accent square beside the heading. Never an asymmetric thick stripe.

### Full-viewport centred hero

`min-height: 100vh` (or `100dvh`), everything centred, one short sentence, one big CTA. The default LLM landing page.

**Fix.** Let the hero be the height of its content. Bias left or right. Put more than a sentence in it.

### Pure black, pure white

`#000000` background or `#ffffff` surface. Both read as flat and synthetic.

**Fix.** Tint toward your anchor hue. See [`color.md`](color.md).

### Default-attractor sameness

Two consecutive Hallmark outputs in the same project use the same macrostructure. The first emitted left-margin numbered labels + huge serif + asymmetric spans (Specimen); the second did exactly the same. The page looks redesigned only because copy changed.

**Why it fails.** Hallmark's whole point is that two pages for two briefs feel like *different sites*, not colour-swaps of one template. Repeating a macrostructure across outputs is the structural fingerprint of templating, which is the AI tell Hallmark exists to defeat.

**Fix.** Before writing code, look in the project's CSS for a `/* Hallmark · macrostructure: <name> · ... */` stamp. If one exists, your pick must be a different macrostructure — categorically different where possible (a serif-led editorial macrostructure paired with a sans-led grid one, not two editorial variants). See [`macrostructures.md`](macrostructures.md) for the twenty-one named choices.

### Specimen fall-through

Producing the Specimen macrostructure (numbered left-margin labels like `01 — HELLO.` + huge serif display + asymmetric spans + hairline rules + typographic-only CTA + sometimes a hand-drawn SVG accent) when the brief did not explicitly request editorial / foundry / specimen energy. This is the single most-repeated Hallmark output, and it's the reason the skill felt like it had one shape.

**Why it fails.** Specimen is a beautiful pattern when the brief is editorial. Applied to a SaaS pricing page, a developer tool, an e-commerce site, or a personal app, it looks like the AI defaulted — because it did.

**Fix.** The Specimen macrostructure is one of twenty-one in [`macrostructures.md`](macrostructures.md), not a default. If the brief is vague, pick from the first ten in that file (Bento Grid, Long Document, Marquee Hero, Stat-Led, Workbench, Conversational FAQ, Manifesto, Photographic, Quote-Led, then Specimen). Reach for Specimen only when the brief explicitly says "editorial", "specimen sheet", "type foundry", or names the Specimen theme.

### Aurora-blob background

Flowing organic mesh blobs in purple-to-pink-to-cyan, layered behind hero text. Looks "premium" until you've seen it on every Dribbble shot since 2022.

**Why it fails.** It's the 2022–2023 generated-design default. Audiences pattern-match this in milliseconds: AI template.

**Fix.** Solid surface. Or a subtle two-stop CSS gradient + SVG `<feTurbulence>` grain at < 0.1 opacity. See [`hero-enrichment.md`](hero-enrichment.md) E7 for the recipe.

### Floating-orb decoration

Ambient generic 3D spheres or blurred coloured circles drifting behind the hero, often added "for depth". They have no semantic role.

**Why it fails.** Generic 3D ambience is the new corporate-stock-photo. It implies "I needed something here, so I added something here."

**Fix.** Cut them. The hero doesn't need depth; it needs a strong typographic anchor.

### Sound-on autoplay

A hero video that auto-plays with audio. Browsers block it anyway, but intent matters: a video element shipped without `muted` is a video that wanted to shout at the user.

**Why it fails.** Hostile to the audience. Accessibility fail. SEO penalty. Browser blocked.

**Fix.** `<video autoplay muted loop playsinline>` — always all four. A separate audio toggle button if sound is genuinely useful.

### Lazy-loaded LCP

`loading="lazy"` on the hero image or hero video — the LCP element. The page waits to start downloading until the user scrolls to it, except they're already looking at it, so the page just sits there blank.

**Why it fails.** Tanks Largest Contentful Paint. Real-world data: lazy-loaded LCP images show p75 of 720 ms vs. 364 ms for preloaded — 2× slower, 4× more "poor" experiences.

**Fix.** `fetchpriority="high"` and `preload="metadata"` on the LCP element. Lazy-load only below-the-fold media.

---

## Major (looks AI-generated)

### Bounce and elastic easing

Buttons that bounce in, icons that wobble on hover. These easings were trendy a decade ago.

**Fix.** Exponential ease-out. See [`motion.md`](motion.md).

### Centred everything

Headline centred, body centred, button centred, section after section of centred columns.

**Fix.** Bias the layout. Wide left margin, narrow right. Or the reverse. Breaking symmetry once is enough.

### Shadow-glow on dark

A card on a dark background with a `box-shadow` that leaves a soft coloured halo around it.

**Fix.** On dark surfaces, use elevation via *lightness* (brighter surface = higher), not shadow. If you must shadow, keep it tight and dark.

### Icon-tile feature card

Rounded rectangle, icon in a coloured square at the top-left, heading below it, two lines of copy, optional "Learn more →" link. The universal template.

**Fix.** If you need these, let them be asymmetric — vary sizes, vary alignments, pull the icon inline with the heading, or drop the icon entirely.

### Glassmorphism without purpose

Frosted-glass panels everywhere — usually layered over a gradient that you also shouldn't have.

**Fix.** Glassmorphism can work when it communicates depth (overlay over content). It cannot work as decoration.

### Hover-only affordances

Hover reveals a menu; hover shows a delete button; hover triggers a tooltip that contains crucial information. Touch users get nothing.

**Fix.** Every hover affordance has a focus state and is accessible via tap/click on coarse pointers.

### Tabular data without tabular-nums

A list of prices, dates, or metrics where the numbers don't align vertically because the font uses proportional figures.

**Fix.** `font-variant-numeric: tabular-nums;` on any container displaying columns of numbers.

### Animate-on-scroll on everything

Every section fades in when it enters the viewport. Every list staggers. The page never settles.

**Fix.** Pick one orchestrated entrance. Let the rest just *be there*.

### Mismatched icon sets

Material Icons in the navbar, Heroicons in the feature cards, Lucide in the footer, an emoji "✨" in a hero badge. Each library has its own stroke voice; mixing them is the icon-set tell.

**Why it fails.** Icons are typography. You wouldn't ship a page with three different body fonts; don't ship one with three different icon strokes.

**Fix.** Pick one library per project. Lucide is the default for SaaS, Phosphor when you need weight variants, Heroicons for Tailwind/shadcn projects. See [`assets.md`](assets.md) for the canon.

### AI-illustration look

Smooth-mesh-blob characters with no joint articulation, mid-2010s "modern flat" stock poses, unmistakably-Midjourney compositions with the symmetric default lighting.

**Why it fails.** It reads as AI in milliseconds. The 2026 audience pattern-matches this faster than any other tell.

**Fix.** Hand-build the illustration in pure CSS or SVG (Tier A or B in [`hero-enrichment.md`](hero-enrichment.md)). If you must generate, use Nanobanana 2 or Recraft V4 with reference images, asymmetric crop, and grain post-processing — never raw output. See [`custom-craft.md`](custom-craft.md) Tier E.

### Lottie shortcut

Reaching for a LottieFiles community animation — the spinning logo, the checkmark draw, the loading spinner, the "loading dots" loop — when pure CSS or hand-built SVG would have produced it stronger and lighter.

**Why it fails.** Lottie pulls were an AI-tool shortcut throughout 2023–2024; the audience now reads them as one. The 50–500 KB JSON file plus the runtime cost is a tax on a job CSS does in zero bytes.

**Fix.** Build it custom. Spinning logo → CSS `@keyframes rotate`. Checkmark → SVG `stroke-dasharray` animated. Loading dots → CSS `@property` + `animation-delay`. Lottie is Tier F in the enrichment hierarchy — last resort, only for genuinely articulated character motion.

### Three.js for a still object

A WebGL hero where the 3D doesn't earn its place by being interactive. A stationary spinning thing the user can't touch, can't reorient, can't customise — just a model rotating because someone wanted "3D".

**Why it fails.** The 100–300 KB Three.js bundle, the model, the textures, the GPU work — all for a thing that could be a static photograph or an SVG.

**Fix.** If the user can't manipulate it, it doesn't justify Three.js. Use a still photograph or a hand-built SVG.

---

## Microinteraction tells

These are the named tells of AI-generated *motion*. See [`microinteractions.md`](microinteractions.md) for the full catalogue and recipes.

### `transition-all`

Every property animating, including ones that should be instant (visibility, focus rings).

**Fix.** Specify the properties. `transition: background-color var(--dur-short) var(--ease-out), transform 100ms var(--ease-out)`.

### Universal `hover:scale-105`

Every card lifts on hover, with no shadow change, no easing specified, no purpose.

**Fix.** Pick one signal per element. A 1px translate, or a colour shift, or an underline thickening — never all four.

### Bouncy overshoot easings on UI

`cubic-bezier(0.34, 1.56, 0.64, 1)` and friends on buttons, modals, tooltips. Tasteless throwback.

**Fix.** Reserve overshoots for genuine physical interactions (drag-and-drop release). For UI state, use `--ease-out` from `motion.md`.

### Animated hover gradients

Background gradient slides through colour space on hover.

**Fix.** Cut. Or pick one colour shift, instant.

### Cursor follower dots

A trailing dot that lags behind the pointer.

**Fix.** Cut.

### Auto-rotating carousels with no pause

WCAG 2.2.2 failure.

**Fix.** Manual advance only, or pause-on-hover-and-focus, or autoplay disabled by default.

### Celebratory success toasts

"Done!" when the user just saved a thing they can see was saved.

**Fix.** Silent success. Toasts only for failures, async actions whose effect isn't visible, and explicit confirmations the user will need.

### Confirmation dialogs for reversible actions

"Are you sure you want to delete this?" before a one-row delete.

**Fix.** Optimistic delete + 5–10s Undo toast. Reserve the modal for irreversible destructive actions, and even then, type-the-name confirmation, not click-OK.

### Tooltips with the same delay on hover and focus

Both delay 800ms.

**Fix.** Hover delay 800–1000ms. Focus delay 0ms. Different intents, different timing.

### Focus rings that animate in

The ring fades in over 200ms — keyboard users have no indicator at the start of the transition.

**Fix.** Focus rings appear instantly. Always. Don't transition `outline` or `box-shadow` when the element gains focus.

### Toasts that shift layout

New toast pushes content down; dismissed toast lets it spring back.

**Fix.** Stack at a viewport corner, fixed positioning. Existing toasts don't move when a new one arrives.

### Universal scroll-triggered fade-up

Every section fades in on intersection. The page never settles.

**Fix.** One orchestrated entrance on first load. After that, content is just there.

### Spinners that flash

A spinner appears for 50ms while a fast action completes.

**Fix.** Either delay-show the spinner (150ms before showing) or enforce a minimum visible duration (300ms once shown). Skeletons over spinners when the layout is known.

---

## Minor (small taste issues)

### Straight quotes

`"Hello"` and `'word'` in rendered text. A sign nothing was proof-read.

**Fix.** Curly quotes: `"Hello"`, `'word'`.

### Double-hyphen dashes

`--` in body copy where an em-dash belongs.

**Fix.** `—` (U+2014).

### Three periods instead of ellipsis

`...` in body copy.

**Fix.** `…` (U+2026).

### Placeholder names

"Jane Doe", "John Smith", "Example User".

**Fix.** Plausible placeholder names reflecting the audience, or pull from a seeded faker. "Maya Okonkwo", "Sam Tan", "Elena Ruiz".

### Startup-cliché product names

"Acme", "Nexus", "Pulse", "Unleash", "Seamless", "Supercharge".

**Fix.** Name the thing concretely. If it's a demo, use a domain-specific placeholder — "Maple Weekly", "Ridgeline Inventory" — not abstract startup bingo.

### `z-index: 9999`

Arbitrary large z-values.

**Fix.** Use the six-level named scale. See [`layout-and-space.md`](layout-and-space.md).

### Every section padded the same

Top padding, bottom padding, horizontal padding — all equal across every section.

**Fix.** Vary. Tighten one, expand another.

### 100vw widths

`width: 100vw` on anything. Breaks on scrollbar-visible desktops.

**Fix.** `width: 100%` with container padding.

---

## How `hallmark audit` should report

For each finding:

```
[severity] Tell name — file:line
  why it's a tell (one line)
  → fix (one line)
```

Then:

```
Summary — N critical · M major · K minor
Verdict — [ships as slop | reads as AI-generated | close, fix the minors]
```
