# Hero enrichment — when, what, and how much

This file is loaded after the macrostructure pick (Step 3 in the design flow), when you reach Step 4: "Decide on hero enrichment." It tells you whether to enrich the hero with media at all, and if so, which archetype and how to build it.

**The promise.** Enrichment is an option, not a default. A typographic-only hero is *always* an acceptable answer. Visual enrichment — demo video, illustration, mockup, animated loop, abstract background, photography — has to *earn its place*. If the hero can be deleted of its enrichment and still works, the enrichment earned its place. If the hero collapses without the enrichment, you propped weak typography on a crutch.

**The bar.** Better nothing than bad something. A page that ships a quiet, well-set typographic hero is always better than a page that ships a stock illustration, a Lottie checkmark, an aurora-blob background, or a generic centred demo video block.

---

## The enrichment hierarchy

Reach for the highest tier the brief lets you ship in the time you have. Skipping tiers is the new tell.

| Tier | What | When |
| --- | --- | --- |
| **0 · Typography only** | No enrichment. Display, lede, optional CTA. | Always acceptable. The strongest fail-state. |
| **A · Custom-built CSS art** | Pure-CSS shapes, gradients, clip-paths, no asset, zero dependency. | Geometric shapes, gradient compositions, glyph-style decoration. |
| **B · Hand-built SVG** | Designed in Figma, optimised, animated declaratively. | Illustrations more complex than CSS handles cleanly — a loaf, a mascot, a workflow diagram. |
| **C · Generated illustration** | Nanobanana / Recraft V4 / Midjourney, with provenance + post-processing. | Characters or specific scenes that hand-build can't economically reach. Always post-processed. |
| **D · Library illustration** | Storyset / Humaaans / unDraw, customised with brand colours. | When budget and timeline force a shortcut — and even then, never unmodified. |
| **E · Lottie animation** | LAST RESORT. Only when complex character motion can't be hand-built. | Articulated figures, multi-frame mascot loops. Never for "spinning logo" or "checkmark draw" — those are CSS. |

**The discipline.** If you can do it in tier A, do it in tier A. If A can't reach it, try B. Only drop to C when characters demand it. Only D when the brief is explicit about "fast and cheap". Only E when E is genuinely the only option. Reaching for E because it's familiar — and many AI tools do — is the signature of a templated page.

See [`custom-craft.md`](custom-craft.md) for *how* to build at tiers A and B. See [`assets.md`](assets.md) for the catalogue of sources at tiers C, D, and E.

---

## Eyeball or ask — the decision protocol

Two paths to picking enrichment:

```
If the brief contains explicit visual cues, pick from this map:

  • "demo", "show how it works", "product tour"           → E1 / E2 demo video
  • "platform", "tool", "infra", "dashboard", "developer" → E3 / E4 mockup
  • "shop", "store", "menu", "products", "items"          → E8 photography (or F6 product grid)
  • "bakery", "kitchen", "café", "atelier" + craft brief  → E5 custom illustration (Tier B SVG)
  • "agency", "studio", "portfolio"                       → E8 photography or no enrichment
  • "manifesto", "essay", "book", "letter"                → no enrichment (typography only)
  • Quiet theme picked                                    → no enrichment (the theme IS restraint)

Else if the brief is genuinely ambiguous, ask one question:
  "Want me to add a demo video, an illustration, or keep it
   typography-only? I default to typography-only because it's
   the strongest fail-state."

Else default to no enrichment. State the inference in one sentence
in your reply, alongside the macrostructure inference.
```

When in doubt: don't enrich. The hero will be fine. Most great landing pages are typographic.

---

## Eight enrichment archetypes

Each archetype has a one-line definition, "use when", "avoid when", a short code sketch, and 2–3 within-archetype variation knobs (consistent with [`component-cookbook.md`](component-cookbook.md)).

### E1 · Demo Video — Clipped-by-viewport-edge

A display headline left, a demo video right, and the rightmost ~10–20 % of the video extending past the viewport so it's intentionally cut off. The clip *is* the design — it implies "there's more product than fits on this screen". Pioneered by Linear; refined by Vercel, Resend, Cursor.

*Use when:* the brief is a SaaS / dev tool / dashboard / platform and you have real footage of the product.
*Avoid when:* you don't have real footage. A clipped-edge video of a stock-footage city skyline reads as filler.

**Knobs:**
- Clip side (right · left · both)
- Aspect ratio (16/10 · 16/9 · 4/3)
- Frame treatment (hairline 1 px frame · browser chrome · none)

```html
<section class="hero hero--clipped">
  <div class="hero__copy">
    <h1>Plan, build, ship.</h1>
    <p>The project tracker your engineering team won't ignore.</p>
    <a class="btn" href="/signup">Try it free</a>
  </div>
  <figure class="hero__media">
    <video autoplay muted loop playsinline preload="metadata"
           poster="/hero-poster.webp" fetchpriority="high"
           aria-label="Tour of the dashboard interface">
      <source src="/hero.av1.mp4"  type='video/mp4; codecs="av01.0.05M.08"'>
      <source src="/hero.vp9.webm" type="video/webm">
      <source src="/hero.h264.mp4" type="video/mp4">
    </video>
  </figure>
</section>
```

```css
.hero--clipped {
  display: grid;
  grid-template-columns: minmax(20rem, 1fr) 1.4fr;
  gap: var(--space-2xl);
  align-items: center;
  overflow: visible;        /* let the media spill past the page edge */
}
.hero__media {
  width: calc(100% + 12vw); /* the 12 % of viewport that sits beyond the right edge */
  aspect-ratio: 16 / 10;
  border-radius: 12px;
  border: var(--rule-hair) solid var(--color-rule);
  overflow: hidden;
}
.hero__media video { width: 100%; height: 100%; object-fit: cover; }

@media (max-width: 60rem) {
  .hero--clipped { grid-template-columns: 1fr; }
  .hero__media { width: 100%; }    /* don't try to clip on mobile — reads as broken */
}

@media (prefers-reduced-motion: reduce) {
  .hero__media video { display: none; }
  .hero__media { background: url('/hero-poster.webp') center/cover; }
}
```

**Critical:** never `loading="lazy"` on the hero video — that kills LCP. Use `preload="metadata"` and `fetchpriority="high"`. Always include a `poster=""` and a `<track kind="captions">` for accessibility.

### E2 · Demo Video — Full-bleed muted loop with ghost overlay

Video fills the fold, ghost-tinted via `mix-blend-mode: multiply` over a paper-coloured overlay so the type stays readable. The video is wallpaper, not subject.

*Use when:* the product's *feel* is the message (mood, tactility, atmosphere).
*Avoid when:* the product needs to be *seen* clearly — use E1 or E3 instead.

**Knobs:**
- Ghost opacity (0.3 / 0.5 / 0.7)
- Text alignment (left-bias / centred)
- Pause behaviour (always-loop · pause-on-hover · pause-when-out-of-viewport)

### E3 · Mock App Screenshot — Browser-framed split

Display headline left, a browser-frame mockup right, the mockup window slightly tilted (1–3°) for life. Frames are from [Browserframe](https://browserframe.com) or hand-built (a 1-px hairline + three macOS dots).

*Use when:* you're selling a web app and you have a clean, well-lit screenshot.
*Avoid when:* the screenshot is busy or blurry — the frame draws attention to the mess.

**Knobs:**
- Frame style (browser chrome · macOS toolbar · minimal hairline · none)
- Tilt angle (0° · 1.5° · 3°)
- Screenshot count (1 · stack-of-3 · orbit-of-3)

### E4 · Mock App Screenshot — Floating no-frame

Same composition as E3 but without browser chrome — the screenshot floats with a soft shadow and 12 px corner radius. Cleaner; demands a higher-quality screenshot since the chrome isn't there to forgive.

*Use when:* the screenshot itself is beautiful enough to stand naked.
*Avoid when:* the product needs the "this is a real web app" cue from the chrome.

**Knobs:**
- Shadow depth (subtle / medium / dramatic)
- Corner radius (0 · 8 px · 16 px)
- Background reveal (gradient / solid / none)

### E5 · Custom Illustration Centerpiece

A hand-built SVG (the default, Tier B) or a generated raster (Tier C, when characters demand it) sitting on the hero as a single illustrative element — the bakery loaf, the studio's mascot, the diagram of how the workflow flows.

*Use when:* the brand has a story or a thing-it-makes that benefits from being drawn.
*Avoid when:* the brand is "modern professional team" generic — illustrating that is the new template.

**Knobs:**
- Build method (Tier A pure-CSS / Tier B hand-SVG / Tier C generated / Tier D library)
- Animation (none · loop · scroll-linked)
- Scale (small accent · dominant)

For *how* to build a hand-drawn loaf in 60 lines of SVG and animate its breath with `@property`, see [`custom-craft.md`](custom-craft.md) — there's a full bakery worked example.

### E6 · Animated Loop — pure CSS / SVG / Motion

A small custom-built loop — an orbiting dot, a breathing rectangle, an animated gradient stop, a type-mask reveal. The point is *small*, custom, and looped *only when reduced-motion is off*.

*Use when:* the page is otherwise still and one small animated element gives it life.
*Avoid when:* the page already has movement — adding more reads as anxious.

**Knobs:**
- Medium (CSS keyframes · SVG SMIL/CSS · Motion)
- Placement (margin · inline-with-headline · corner-accent)
- Loop duration (≤ 4s — anything longer drags)

### E7 · Abstract Background — subtle gradient + grain

A two-colour CSS gradient at low chroma, overlaid with SVG `<feTurbulence>` grain at < 0.1 opacity. *Not* aurora; *not* purple-to-cyan mesh; *not* floating orbs. The point is *texture you can barely see* — paper-quality, not decoration.

*Use when:* the page would feel synthetic with a flat surface.
*Avoid when:* the theme already has a paper feel (Specimen, Linen, Riso). Doubling the grain is muddy.

**Knobs:**
- Gradient direction (45° / 135° / radial)
- Grain amount (off · subtle · textured)
- Animation (none · slow drift · scroll-linked parallax)

```html
<section class="hero hero--bg">
  <div class="hero__bg" aria-hidden="true">
    <svg width="0" height="0" style="position: absolute;">
      <filter id="grain"><feTurbulence baseFrequency="0.9" numOctaves="2"/></filter>
    </svg>
  </div>
  <div class="hero__copy"> ... </div>
</section>
```
```css
.hero { position: relative; isolation: isolate; }
.hero__bg {
  position: absolute; inset: 0; z-index: -1;
  background:
    linear-gradient(135deg,
      color-mix(in oklch, var(--color-paper) 100%, var(--color-accent) 4%),
      color-mix(in oklch, var(--color-paper) 100%, var(--color-paper-2) 50%));
}
.hero__bg::after {
  content: ""; position: absolute; inset: 0;
  filter: url(#grain);
  opacity: 0.06;
  mix-blend-mode: multiply;
  pointer-events: none;
}
```

### E8 · Hero Photography — single tightly-cropped image

Existing H6 archetype in the cookbook. Cross-referenced here for completeness. See [`component-cookbook.md`](component-cookbook.md) for variation knobs.

---

## Animation discipline (hero specifically)

Cross-references [`motion.md`](motion.md), [`microinteractions.md`](microinteractions.md), and [`custom-craft.md`](custom-craft.md). The hero is the highest-stakes animation surface on the page; the rules are tighter here than elsewhere.

**One orchestrated reveal per page.** Not eight. Not "everything fades in on scroll". One: the hero settles in 0.4–0.8 s with a single coordinated motion, then stops.

**Banned for hero entrances:**
- Bouncy elastic easing (`cubic-bezier(0.34, 1.56, ...)`) — reads as 2016 Framer demo
- Scroll-fade-everything (every section fades in when it enters the viewport)
- Mouse-follow gradients on SaaS landing pages (allowed only on portfolio / creative / agency work)
- Parallax-on-mouse (motion sickness, gimmicky)
- Particle / starfield backgrounds (2010s nostalgia, distracting)
- Auto-rotating hero carousels (WCAG 2.2.2 fail unless paused-on-hover-and-focus is implemented)

**Allowed:**
- A single image-fade-in-late after the headline lands (~0.6 s after, ~0.4 s duration)
- Type-unmask on the headline (`clip-path` opening over text)
- View Transitions API for state changes (theme switch, route change)
- Number-tick on a stat-led hero (counter from 0 to final, ≤ 1.2 s)
- A single subtle Lottie / CSS loop ≤ 4 s, with `prefers-reduced-motion` fallback

**Reduced-motion is the default in 2026.** Every animation gets a `@media (prefers-reduced-motion: reduce)` block that either disables the motion or replaces it with a static keyframe. This is non-negotiable; the slop test will catch you.

---

## Quality bar — eight pre-flight questions

Every question must answer *yes* before the enrichment ships. If any answer is *no*, ship the typographic-only hero instead.

1. Does the enrichment **communicate** something the typography can't?
2. Is it under **2 MB** total (video poster + first segment, illustration + animation JSON, image + grain)?
3. Does it have a **`prefers-reduced-motion` fallback**?
4. If video: muted, looped, `playsinline`, with a poster + `fetchpriority="high"` + caption track?
5. If illustration: built or generated with intent? **Not picked from a Lottie library as a shortcut?**
6. If background: under one accent colour at < 5 % footprint? (Aurora and mesh-gradients fail this.)
7. Does it survive being deleted? (If the hero still works without it, it earned its place. If the hero collapses without it, you propped weak typography on a crutch.)
8. Does its tone match the page's tone? (Risograph illustration on a Brutal page = wrong. Hand-drawn doodle on a Workbench developer-tool page = wrong. Three.js bloom on a Quiet page = wrong.)

The slop test ([`SKILL.md`](../SKILL.md) §5) carries four binary gates that mirror these questions; the audit verb runs them.

---

## Output stamp

When you ship enrichment, the macrostructure stamp records the choice:

```css
/* Hallmark · macrostructure: Marquee Hero · H1 hero knobs: size=xxl, alignment=left-bias
 * enrichment: E1 Clipped-Edge Video · clip=right, aspect=16/10, frame=hairline
 * craft: tier-A CSS art (no real video — pure custom-built mockup)
 * theme: Pastel · accent: indigo ~3% · studied: no
 */
```

This signals to future Hallmark runs (and to the audit verb) what was chosen and how. It also lets the user see the inferences in one place and redirect if anything's off.

---

## Common mistakes — and the fixes

- **Defaulting to E5 illustration on every brief.** Most heroes don't want an illustration. Reach for E0 (typography only) first; reach for E1–E4 when there's a *thing* to show; reach for E5 only when illustration genuinely matches the tone.
- **Using a stock Lottie checkmark as the hero animation.** That's tier E used to skip tiers A–D. Build the checkmark in pure CSS (`stroke-dasharray` animated to draw the tick); it's 8 lines.
- **Adding a grain background everywhere.** Grain is a treatment, not a default. Half the existing themes already carry texture (Riso, Linen, Specimen). Don't double up.
- **Treating the abstract background as the hero.** It isn't. The headline is. The background is paper.
- **Shipping the unmodified Storyset SVG.** That's tier D ungrounded — the library look. Customise the colour to your anchor hue at minimum; recompose if you can.
- **A clipped-edge video on mobile.** The clip reads as broken on a 375-px viewport. Always collapse to stacked at < 60 rem.
