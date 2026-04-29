# Component cookbook

Thirty-six component archetypes you can compose into any macrostructure. Every entry: a *shape*, a one-line "use when", a one-line "don't confuse with", and a short structural sketch (DOM + minimal CSS). Pick from this file when you're building a section and don't know which shape to reach for.

The same macrostructure (e.g., Bento Grid) can be built from many different combinations of these archetypes. The macrostructure picks the *page shape*; this file picks the *components inside it*.

**Diversification rule:** within a single page, no two sections should use the same archetype. A Bento Grid might pair *Bento feature block* with *Inline form CTA* with *Logo wall (hairline)*. The next page Hallmark builds should pick different archetypes from the same categories.

---

## Within-archetype variation knobs

Picking an archetype is the first axis of variety. The second is *how you build it*. Two pages built with the same archetype should not be identical — each archetype below has 2–3 *variation knobs*. Pick one value per knob per output. This prevents "every Bento I build looks like the same Bento."

When you pick an archetype, **state the knob values you chose** in the macrostructure stamp comment, e.g.:

```css
/* Hallmark · macrostructure: Bento Grid · F1 Bento knobs: tiles=6, spans=irregular, accent=corner-only · ... */
```

| Archetype | Knob A | Knob B | Knob C |
| --- | --- | --- | --- |
| **H1 Marquee** | Display size: `xxl` (clamp 4–12rem) · `xl` (clamp 3–8rem) | Alignment: left-bias · centred · right-bias | Underlay: none · single rule above · single rule below |
| **H2 Split Diptych** | Ratio: 7/5 · 6/6 · 5/7 | Right side: photo · proof column · pull-quote | Divider: hairline · negative space · vertical rule |
| **H3 Quote-Led** | Quote weight: italic display · roman display · roman body large | Attribution position: under quote · margin-aligned · right-flush | Length: ≤80 chars · 80–160 chars |
| **H4 Stat-Led** | Number style: tabular display · italic display · monospace | Qualifier position: below · inline-right · stacked-above | Secondary stats: none · two below · row of four |
| **H5 Letter** | Salutation: greeting · "Dear X," · time-stamp | Body length: 1 paragraph · 2 paragraphs · 3 paragraphs | Signoff: typed name · drawn signature SVG · initials |
| **H6 Photographic** | Image area: full-bleed · 16/7 · 4/3 · 1/1 square | Caption position: lower-left · upper-right · margin | Text below or overlaid |
| **H7 Demo Video Clipped-Edge** | Clip side: right · left · both | Aspect ratio: 16/10 · 16/9 · 4/3 | Frame: hairline · browser chrome · none |
| **H8 Mockup Split** | Frame style: browser chrome · macOS toolbar · minimal hairline · floating no-frame | Tilt: 0° · 1.5° · 3° | Screenshot count: 1 · stack-of-3 · orbit-of-3 |
| **H9 Custom Illustration** | Build method: Tier-A pure-CSS · Tier-B hand-SVG · Tier-C generated · Tier-D library | Animation: none · loop · scroll-linked | Scale: small accent · dominant |
| **F1 Bento (feature)** | Tiles: 4 · 6 · 7 · 9 | Spans: regular · irregular · mosaic | Border: hairline all · accent corners · none |
| **F2 Sticky-scroll stack** | Pinned side: left · right | Right pane content: code · screenshot · diagram | Pin steps: 3 · 4 · 5 |
| **F3 Tabular spec sheet** | Columns: 2 (key/val) · 3 (key/val/unit) · 4 (with footnote) | Rule density: every row · groups of 3 · headers only | Numbers: tabular · proportional |
| **F4 Step sequence** | Numbering: I/II/III · 01/02/03 · 1.0/2.0/3.0 | Layout: vertical stack · horizontal flow · diagonal | Connector: line · arrow · none |
| **F5 Annotated screenshot** | Callouts: numbered pins · margin labels · inline arrows | Frame: device · plain · floating | Anchor: image-led or text-led |
| **F6 Product card grid** | Card ratio: 3/4 portrait · 1/1 square · 4/3 landscape | Density: 3-up · 4-up · 5-up | Micro-action: Add · Save · View → · none |
| **C1 Outlined chip** | Shape: rectangular · pill (only allowed for tactile/playful tones) · slab | Density: spacious · compact | Adornment: arrow · plus · none |
| **C2 Inline form-as-CTA** | Field count: 1 · 2 · 3 | Submit position: end-of-row · separate line · embedded button | Helper: above · below · none |
| **C3 Typographic link CTA** | Underline: solid · dashed · double · none | Hover behaviour: thicken · slide · colour shift | Arrow: → · ↗ · none |
| **C4 Sticky bottom bar** | Reveal: always · scroll-up · after fold | Anchored: viewport bottom · viewport top · inline at bottom | Shadow: hairline · none · subtle |
| **T1 Pull quote w/ marginalia** | Quote treatment: italic display · roman large · serif italic | Attribution: signed · stamped · timestamped | Marginalia: none · timeline · 1 footnote |
| **T2 Logo wall (hairline)** | Layout: single row · 2 rows · grid 3×N | Logo treatment: monochrome ink · brand colour · ghosted | Divider: hairline cells · none |
| **T3 Single huge quote** | Quote face: serif italic · roman display · italic mono | Width: full-bleed · 60ch · 40ch | Attribution position: same line · separate band |
| **T4 Numbered stat strip** | Layout: 3-up · 4-up · 5-up · 6-up | Number weight: display · body large | Qualifier position: under · inline · above |
| **Ft1 Mast-headed** | Wordmark size: display 3xl · display 2xl · xl | Tagline: italic serif · roman body · none | Links row: inline · 2-line stack |
| **Ft2 Inline single line** | Order: wordmark/links/credit · credit/wordmark/links | Separator: middot · pipe · em-dash · vertical rule | Density: dense · spaced |
| **Ft3 Index columns** | Columns: 3 · 4 · 5 | Heading style: small caps · italic · monospace | Bullet: hairline · none |
| **Ft4 Dense colophon** | Family: monospace · serif · sans | Layout: single block · paragraphs · log-style | Includes: build hash · date · attribution |
| **N1 Wordmark + 2 links** | Position: left/right split · centred · right-flush | Links: text · text+icon · pill | Sticky: yes · no |
| **N2 Floating chip** | Anchor: top · bottom · top-right · bottom-left | Content: theme picker · search · navigation | Backdrop: blur · solid · none |
| **N3 Side-rail** | Side: left · right | Width: 12ch · 16ch · 20ch | Indicator: filled bar · text-only · numbered |
| **N4 Hidden behind ⌘K** | Trigger: button · keyboard only · both | Surface: modal · sheet · spotlight | Recents: shown · hidden |

**Anti-pattern:** picking the same knob values across two different outputs is the same kind of templating as picking the same archetype. If your last Bento was `tiles=6, spans=irregular, accent=corner-only`, the next one must change at least one knob.

---

## Heroes

### H1 · Marquee
A single statement fills the fold. No subhead, no CTA in view.
*Use when:* the brand or person *is* the message.
*Don't confuse with:* H4 Stat-Led (which is a number, not a statement).

```html
<section class="hero-marquee">
  <h1 class="display-xxl">A statement.</h1>
</section>
```
```css
.hero-marquee { min-height: 80dvh; display: grid; align-content: end; padding: 0 var(--page-gutter) var(--space-2xl); }
.display-xxl { font-size: clamp(4rem, 12vw, 12rem); line-height: 0.92; }
```

### H2 · Split Diptych
Headline + lede on one side, image or product capture on the other. 6/6 or 7/5 columns.
*Use when:* you can pair every claim with a visual proof.
*Don't confuse with:* H6 Photographic (which puts the image full-bleed, not paired).

```html
<section class="hero-split">
  <div><h1>…</h1><p>…</p><a class="cta-outline">…</a></div>
  <figure><img src="" /></figure>
</section>
```
```css
.hero-split { display: grid; grid-template-columns: 7fr 5fr; gap: var(--space-2xl); align-items: center; }
@media (max-width: 56rem) { .hero-split { grid-template-columns: 1fr; } }
```

### H3 · Quote-Led
A pull-quote with attribution is the hero. Your headline is borrowed credibility.
*Use when:* you have a real testimonial that earns the front page.
*Don't confuse with:* T3 Single huge quote (which lives mid-page, not in the hero slot).

```html
<section class="hero-quote">
  <blockquote class="display-italic">"…"</blockquote>
  <p class="attribution">— Name, Role, Company</p>
</section>
```

### H4 · Stat-Led
A giant number or metric is the hero. A small qualifier line below.
*Use when:* you have one defensible, externally-verifiable number.
*Don't confuse with:* T4 Numbered stat strip (which is several stats in a row, not one focal).

```html
<section class="hero-stat">
  <p class="figure tnum">99.97<span class="unit">%</span></p>
  <p class="qualifier">…</p>
</section>
```
```css
.figure { font-size: clamp(6rem, 18vw, 16rem); font-variant-numeric: tabular-nums; line-height: 0.85; }
```

### H5 · Letter Hero
First-person opening — "Dear reader,". No buttons in fold. Reads as personal correspondence.
*Use when:* the founder's voice is the brand.
*Don't confuse with:* H1 Marquee (which is impersonal declaration).

```html
<section class="hero-letter">
  <p class="salutation"><em>Dear reader,</em></p>
  <p class="lede">…</p>
</section>
```

### H6 · Photographic Fold
Single full-bleed image fills the viewport. Caption sits in a corner.
*Use when:* you have real photography that earns full-bleed.
*Don't confuse with:* H2 Split (which pairs image with text in a grid).

```html
<section class="hero-photo">
  <img class="bleed" src="" alt="" />
  <p class="caption">Spring, 2026.</p>
</section>
```
```css
.hero-photo { position: relative; height: 80dvh; }
.hero-photo .bleed { width: 100%; height: 100%; object-fit: cover; }
.hero-photo .caption { position: absolute; bottom: var(--space-md); right: var(--space-md); }
```

### H7 · Demo Video — Clipped-by-viewport-edge
Display headline left, demo video right, the rightmost ~10–20 % extending past the viewport so it's intentionally cut off. The clip *is* the design — implies "there's more product than fits the screen". Pioneered by Linear, refined by Vercel / Resend / Cursor.
*Use when:* the brief is SaaS / dev-tool / dashboard / platform AND you have real footage of the product (or a hand-built CSS-art mockup of it).
*Don't confuse with:* H4 Stat-Led (number-led, no video) or H8 Mockup Split (still screenshot, not video).

See [`hero-enrichment.md`](hero-enrichment.md) for the full E1 recipe (codec chain, autoplay rules, `prefers-reduced-motion` fallback, mobile collapse). The cookbook entry below is the structural sketch.

```html
<section class="hero hero--clipped">
  <div class="hero__copy">
    <h1>Plan, build, ship.</h1>
    <p>The project tracker your engineering team won't ignore.</p>
  </div>
  <figure class="hero__media">
    <video autoplay muted loop playsinline preload="metadata"
           poster="/hero-poster.webp" fetchpriority="high">
      <source src="/hero.av1.mp4" type='video/mp4; codecs="av01.0.05M.08"'>
      <source src="/hero.h264.mp4" type="video/mp4">
    </video>
  </figure>
</section>
```
```css
.hero--clipped { display: grid; grid-template-columns: 1fr 1.4fr; gap: var(--space-2xl); overflow: visible; }
.hero__media   { width: calc(100% + 12vw); aspect-ratio: 16 / 10; border-radius: 12px; overflow: hidden; }
@media (max-width: 60rem) { .hero--clipped { grid-template-columns: 1fr; } .hero__media { width: 100%; } }
```

### H8 · Mockup Split (browser-framed)
Headline left, browser-frame mockup right, the mockup tilted 1–3° for life. Frame can be browser chrome, macOS toolbar, minimal hairline, or floating no-frame.
*Use when:* you're selling a web app and you have a clean, well-lit screenshot.
*Don't confuse with:* H7 Clipped-Edge (which extends past the viewport) or H2 Split Diptych (which uses photography or proof column, not a product mockup).

```html
<section class="hero-mock">
  <div>
    <h1>The studio's new mute button.</h1>
    <p>Press <kbd>⌘ M</kbd> from anywhere.</p>
  </div>
  <figure class="mock">
    <header class="mock__chrome"><span></span><span></span><span></span></header>
    <div class="mock__body"><!-- screenshot or CSS-art mockup --></div>
  </figure>
</section>
```
```css
.hero-mock  { display: grid; grid-template-columns: 1fr 1.2fr; gap: var(--space-2xl); align-items: center; }
.mock       { transform: rotate(1.5deg); border-radius: 12px; overflow: hidden; box-shadow: 0 24px 60px -20px oklch(20% 0.02 60 / 0.18); }
.mock__chrome { display: flex; gap: 6px; padding: 10px 12px; background: var(--color-paper-2); border-block-end: var(--rule-hair) solid var(--color-rule); }
.mock__chrome span { width: 10px; height: 10px; border-radius: 50%; background: var(--color-rule-2); }
```

### H9 · Custom Illustration Centerpiece
A single hand-built SVG (Tier B in the enrichment hierarchy — or pure CSS at Tier A for simpler shapes) sitting on the hero as one illustrative element. The bakery loaf, the studio's mascot, the workflow diagram.
*Use when:* the brand has a *thing* that benefits from being drawn — a craft, a character, a process.
*Don't confuse with:* H6 Photographic (real photography) or H8 Mockup (a product screenshot, not artwork).

The illustration itself is *built*, not picked from Storyset / Humaaans / unDraw / Lottie. See [`custom-craft.md`](custom-craft.md) for full recipes (CSS art, hand-built SVG, declarative animation). The cookbook entry below is the page-level structural sketch.

```html
<section class="hero-art">
  <div>
    <p class="eyebrow">Maple Street Bread · est. 2026</p>
    <h1>Sourdough, every morning.</h1>
    <p>Slow-fermented overnight, baked on stone, before you wake.</p>
  </div>
  <svg viewBox="0 0 200 100" class="loaf" aria-label="A loaf of bread">
    <path class="loaf__body" d="M 20 70 Q 100 10 180 70 L 180 90 L 20 90 Z" />
    <path class="loaf__score" d="M 60 50 L 90 30 M 100 45 L 130 25 M 140 50 L 165 35" />
  </svg>
</section>
```
```css
.hero-art   { display: grid; grid-template-columns: 1fr 1fr; gap: var(--space-2xl); align-items: center; }
.loaf__body { fill: oklch(72% 0.14 50); }
.loaf__score{ stroke: oklch(38% 0.10 35); stroke-width: 2; fill: none; stroke-linecap: round; }
```

---

## Section heads

### S1 · Left-margin numbered
A narrow left column holds `01 — LABEL.`; the wide right column holds the heading and content.
*Use when:* the page is editorial / specimen.
*Don't confuse with:* S5 Bottom-anchored (which puts the label *under* the section).

```html
<header class="head-margin">
  <p class="num-label">01 — Foundations</p>
  <h2>…</h2>
</header>
```
```css
.head-margin { display: grid; grid-template-columns: 10rem 1fr; gap: var(--space-xl); align-items: baseline; }
```

### S2 · Hanging
Heading floats above the section in negative space; no border, no rule.
*Use when:* the content has a quiet, room-to-breathe energy.
*Don't confuse with:* S3 Sticky-pinned (which moves with scroll).

```html
<header class="head-hang">
  <h2>…</h2>
</header>
```
```css
.head-hang { padding-block: var(--space-3xl) var(--space-xl); }
```

### S3 · Sticky pinned
Heading remains in viewport while content scrolls beneath. Orientation aid.
*Use when:* the section is dense and the user benefits from always seeing where they are.
*Don't confuse with:* S1 Left-margin (which doesn't move).

```html
<header class="head-sticky">
  <p class="num-label">02</p>
  <h2>…</h2>
</header>
```
```css
.head-sticky { position: sticky; top: 0; background: var(--color-paper); padding-block: var(--space-sm); border-bottom: 1px solid var(--color-ink); z-index: 10; }
```

### S4 · Inline (no break)
The heading is a small caps phrase that emerges *inside* the body flow; no spatial break.
*Use when:* the page is prose-led; reading should be continuous.
*Don't confuse with:* S2 Hanging (which separates with negative space).

```html
<p>… <span class="head-inline">A small heading.</span> …</p>
```
```css
.head-inline { font-variant-caps: all-small-caps; letter-spacing: 0.06em; font-weight: 500; }
```

### S5 · Bottom-anchored
The label or heading sits *below* the section's content. Inverts hierarchy.
*Use when:* the content is the primary act and the label is a footer to it.
*Don't confuse with:* S1 Left-margin (which leads with the label).

```html
<section>
  <div class="content">…</div>
  <p class="num-label">— end of 02</p>
</section>
```

---

## Feature blocks

### F1 · Bento grid
Asymmetric grid of 8–15 tiles in mixed spans (1×1, 2×1, 1×2, 2×2). Visual rhythm via size.
*Use when:* multiple equally-valid entry points; SaaS feature page.
*Don't confuse with:* F2 Sticky-scroll (which stacks vertically with sticky pacing).

```html
<section class="bento">
  <article class="cell span-2x2">…</article>
  <article class="cell span-1x1">…</article>
  <article class="cell span-2x1">…</article>
</section>
```
```css
.bento { display: grid; grid-template-columns: repeat(4, 1fr); grid-auto-rows: 12rem; gap: var(--space-md); }
.span-2x2 { grid-column: span 2; grid-row: span 2; }
.span-2x1 { grid-column: span 2; }
.span-1x2 { grid-row: span 2; }
@media (max-width: 56rem) { .bento { grid-template-columns: repeat(2, 1fr); } }
```

### F2 · Sticky-scroll stack
Sticky left pane, scrolling right pane that cycles through related screenshots.
*Use when:* feature has multiple sub-states worth showing in sequence.
*Don't confuse with:* F4 Step sequence (which is linearly numbered, not synced).

```html
<section class="sticky-stack">
  <div class="pane-sticky"><h3>…</h3><p>…</p></div>
  <div class="pane-scroll">
    <figure>1</figure><figure>2</figure><figure>3</figure>
  </div>
</section>
```
```css
.sticky-stack { display: grid; grid-template-columns: 1fr 1fr; gap: var(--space-2xl); }
.pane-sticky { position: sticky; top: var(--space-xl); align-self: start; }
```

### F3 · Tabular spec sheet
Each row is a feature; columns hold name, value, footnote. Hairline rules between rows. Tabular numerics.
*Use when:* features compare quantitatively.
*Don't confuse with:* F1 Bento (which is non-tabular and visually rhythmic).

```html
<table class="spec-sheet tnum">
  <tr><th>Latency</th><td>p99 &lt; 50 ms</td><td class="muted">measured externally</td></tr>
  <tr>…</tr>
</table>
```

### F4 · Step sequence
Numbered stages (`1.0 → 2.0 → 3.0`) flow vertically. Each stage has a heading, a paragraph, sometimes a small visual.
*Use when:* the product is a workflow, not a single moment.
*Don't confuse with:* F2 Sticky-scroll (which doesn't number stages).

```html
<ol class="steps">
  <li><span class="stage">1.0</span><h3>Intake.</h3><p>…</p></li>
  <li><span class="stage">2.0</span><h3>Plan.</h3><p>…</p></li>
</ol>
```

### F5 · Annotated screenshot
A product capture sits centre-stage with arrows or short labels pointing to UI details.
*Use when:* the product UI itself is the explanation.
*Don't confuse with:* F2 Sticky-scroll (which uses multiple screenshots in sequence).

```html
<figure class="annotated">
  <img src="" />
  <span class="callout" style="--x:60%; --y:30%;">→ assigns automatically.</span>
</figure>
```

### F6 · Product card grid
Each card is a product, not a feature. Image · name · price · one micro-action. Reads like a shop floor, not a marketing site.
*Use when:* the brief is commerce, catalogue, lookbook, marketplace — anything where the page sells *things*, not *features*.
*Don't confuse with:* F1 Bento (which sells *features*; tiles vary in size and span). Product cards are uniform on purpose — the rhythm comes from the products, not the layout.

**Variation knobs:** card ratio (3/4 portrait · 1/1 square · 4/3 landscape) · density (3-up · 4-up · 5-up) · price treatment (under name · over image · hover-reveal) · micro-action (Add · Save · View → · none).

```html
<section class="product-grid">
  <article class="product">
    <a class="product__media" href=""><img src="" alt="" loading="lazy" /></a>
    <div class="product__meta">
      <h3 class="product__name">Linen Apron · Indigo</h3>
      <p class="product__price tabular-nums">¥ 6,400</p>
    </div>
    <button class="product__add" aria-label="Add Linen Apron to bag">+</button>
  </article>
  <!-- ... more products, uniform shape ... -->
</section>
```
```css
.product-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: var(--space-xl) var(--space-lg); }
@media (max-width: 60rem) { .product-grid { grid-template-columns: repeat(2, 1fr); } }
.product { display: grid; gap: var(--space-sm); position: relative; }
.product__media { display: block; aspect-ratio: 3 / 4; background: var(--color-paper-2); overflow: hidden; }
.product__media img { width: 100%; height: 100%; object-fit: cover; transition: transform var(--dur-long) var(--ease-out); }
.product__media:hover img { transform: scale(1.02); }
.product__name { font-family: var(--font-body); font-size: var(--text-md); margin: 0; }
.product__price { font-family: var(--font-mono); font-size: var(--text-sm); color: var(--color-ink-2); }
.product__add { position: absolute; top: var(--space-sm); right: var(--space-sm); width: 32px; height: 32px; background: var(--color-paper); border: var(--rule-hair) solid var(--color-rule-2); cursor: pointer; opacity: 0; transition: opacity var(--dur-short) var(--ease-out); }
.product:hover .product__add, .product:focus-within .product__add { opacity: 1; }
@media (pointer: coarse) { .product__add { opacity: 1; } }
```

**Anti-patterns to avoid in product grids:**
- Don't borrow Bento's irregular spans — products want uniform rhythm.
- Don't put feature-style two-line descriptions under product names. The price *is* the description.
- Don't auto-scale the image on idle — only on hover, and only by 1.02× max.
- Don't use cards with shadow + radius + border + tile + ribbon. Pick one container signal.

---

## CTAs / signups

### C1 · Outlined chip
A bordered, transparent button with a typographic verb ("Save changes").
*Use when:* the page has one primary action; you want it visible but quiet.
*Don't confuse with:* C2 Oversized solid (which is statement-loud).

```html
<a class="cta-outline">Open your studio →</a>
```
```css
.cta-outline { display: inline-flex; align-items: center; gap: 0.4em; padding: 0.7rem 1.2rem; border: 1px solid var(--color-ink); min-height: 44px; }
```

### C2 · Inline form-as-CTA
The CTA *is* the form — a single email input with a "Submit →" beside it. No separate landing for sign-up.
*Use when:* the action is collecting an email.
*Don't confuse with:* C1 Outlined chip (which navigates, not submits).

```html
<form class="cta-form">
  <label for="email" class="visually-hidden">Email</label>
  <input id="email" type="email" placeholder="you@example.com" />
  <button type="submit">Send →</button>
</form>
```
```css
.cta-form { display: grid; grid-template-columns: 1fr auto; border-bottom: 1px solid var(--color-ink); }
.cta-form input { background: none; border: 0; padding: 0.7rem 0; min-height: 44px; }
```

### C3 · Typographic link
Just a word, an arrow, and a 1-px underline. No box, no fill.
*Use when:* the page is editorial / Long Document; CTAs should not shout.
*Don't confuse with:* C1 Outlined chip (which is bordered).

```html
<a class="link">Read the case study →</a>
```

### C4 · Sticky bottom bar
A horizontal bar pinned to the viewport bottom, holding a CTA + a brief reassurance line.
*Use when:* the page is long and the CTA needs to be reachable always.
*Don't confuse with:* anything in the fold; this is a *persistent* element, not a hero CTA.

```html
<aside class="cta-sticky">
  <span>Try it free for 14 days.</span>
  <a class="cta-outline">Start →</a>
</aside>
```
```css
.cta-sticky { position: fixed; left: 0; right: 0; bottom: 0; padding: var(--space-sm) var(--space-md); background: var(--color-paper); border-top: 1px solid var(--color-rule); display: flex; justify-content: space-between; align-items: center; }
```

---

## Testimonials / proof

### T1 · Pull-quote with marginalia
A quote sits in the wide column; the attribution and source link float in the narrow margin column.
*Use when:* the page already has a marginalia rhythm (Tufte-leaning, editorial).
*Don't confuse with:* T3 Single huge quote (which is centered and dominates).

```html
<aside class="proof-margin">
  <blockquote class="serif-italic">"…"</blockquote>
  <p class="attribution muted">— Name<br />Role, Company</p>
</aside>
```

### T2 · Logo wall (hairline)
A row of customer logos, monochromatic, separated by hairline rules. No card boxes, no shadows.
*Use when:* you have recognisable customers and want to surface them quietly.
*Don't confuse with:* the AI-default 6-logo box grid; this version refuses card boxes.

```html
<section class="logo-wall">
  <ul>
    <li><img src="" /></li>
    <li><img src="" /></li>
    <li><img src="" /></li>
  </ul>
</section>
```
```css
.logo-wall ul { display: grid; grid-template-columns: repeat(auto-fit, minmax(8rem, 1fr)); gap: 0; }
.logo-wall li { padding: var(--space-md); border-right: 1px solid var(--color-rule); display: grid; place-items: center; }
.logo-wall img { filter: grayscale(1); opacity: 0.7; }
```

### T3 · Single huge quote
One quote, set big, centered, taking a whole section. No supporting text, no attribution boxes — attribution is a small caps line beneath.
*Use when:* one quote is so good it earns the room.
*Don't confuse with:* T1 Margin pull-quote (which is the *side* mate, not the *room*).

```html
<section class="proof-room">
  <blockquote class="display-italic">"…"</blockquote>
  <p class="attribution"><span class="caps">— Name, Company</span></p>
</section>
```

### T4 · Numbered stat strip
A horizontal strip of 3–5 stats (count + qualifier) running across one row. Tabular nums.
*Use when:* you have multiple complementary metrics that work together.
*Don't confuse with:* H4 Stat-led hero (which is one focal number, not several).

```html
<section class="stat-strip tnum">
  <div><b>2.4M</b><span>users</span></div>
  <div><b>99.97%</b><span>uptime</span></div>
  <div><b>14</b><span>regions</span></div>
</section>
```

---

## Footers

### Ft1 · Mast-headed
A wordmark and tagline anchor a single horizontal band. Two or three small links beside, address or licence below.
*Use when:* the page has heavy content; the footer should be quiet and singular.
*Don't confuse with:* Ft2 Inline-rule (which is even more reduced).

```html
<footer class="foot-mast">
  <p class="wordmark">Studio Name</p>
  <p class="tagline muted">Designs that don't look generated.</p>
  <p class="links muted">Imprint · Privacy · Contact</p>
</footer>
```

### Ft2 · Inline-rule single line
A single horizontal line of credits, address, copyright. Hairline rule above. No columns.
*Use when:* the page is editorial and the footer is afterthought.
*Don't confuse with:* Ft4 Dense typographic (which packs more in).

```html
<footer class="foot-line">
  <p>© 2026 · 137 Marlow Street · MIT licensed</p>
</footer>
```

### Ft3 · Index-style category list
Three or four short columns, each headed by a category in small caps, holding 4–6 links each.
*Use when:* the page is a hub or a documentation root.
*Don't confuse with:* Ft4 Dense typographic (which is one big block, not columns).

```html
<footer class="foot-index">
  <div><p class="caps">Product</p><ul>…</ul></div>
  <div><p class="caps">Company</p><ul>…</ul></div>
  <div><p class="caps">Resources</p><ul>…</ul></div>
</footer>
```

### Ft4 · Dense typographic
One large block of text — credits, references, licence, address — in a small monospace font, fully justified or ragged-right. Editorial colophon energy.
*Use when:* the brand is editorial and a colophon-style sign-off fits.
*Don't confuse with:* Ft3 Index (which navigates).

```html
<footer class="foot-dense mono">
  <p>Hallmark v0.2.0. Built with The Future, Fraunces, IBM Plex Mono. MIT licensed. Powered by Together AI. 137 Marlow Street, 2026.</p>
</footer>
```

---

## Navigation

### N1 · Wordmark + 2 links
Top-of-page bar: wordmark on the left, two text links on the right ("Pricing" / "Sign in"). No logo image, no menu icon.
*Use when:* the page has very few destinations.
*Don't confuse with:* N3 Side-rail (which is vertical).

```html
<nav class="nav-min">
  <a class="wordmark">Studio</a>
  <ul><li><a>Pricing</a></li><li><a>Sign in</a></li></ul>
</nav>
```

### N2 · Floating chip
A small fixed chip in a corner — wordmark + a single action ("Try it"). Doesn't sit in document flow.
*Use when:* the page is fold-heavy and traditional nav would fight the content.
*Don't confuse with:* C4 Sticky bottom bar (which is full-width).

```html
<aside class="nav-chip">
  <a class="wordmark">Studio</a>
  <a class="cta-outline">Try →</a>
</aside>
```
```css
.nav-chip { position: fixed; top: var(--space-md); right: var(--space-md); display: inline-flex; gap: var(--space-md); padding: 0.5rem 0.75rem; background: var(--color-paper); border: 1px solid var(--color-rule); }
```

### N3 · Side-rail
A thin vertical strip on the left edge — wordmark rotated, plus 2–3 dot-indicators for sections. Editorial / portfolio energy.
*Use when:* the page is long and section-numbered.
*Don't confuse with:* N1 Top wordmark (which is horizontal).

```html
<nav class="nav-rail">
  <p class="wordmark vertical">Studio</p>
  <ul class="dots"><li></li><li></li><li></li></ul>
</nav>
```
```css
.nav-rail { position: fixed; left: 0; top: 0; bottom: 0; width: 3rem; padding: var(--space-md); writing-mode: vertical-rl; }
```

### N4 · Hidden behind ⌘K
No visible nav. The user opens a command palette via `⌘K` to get anywhere. Designed for keyboard-first audiences.
*Use when:* the page is for technical users who expect this affordance.
*Don't confuse with:* N2 Floating chip (which is visible always).

```html
<button class="kbd-hint">⌘ K</button>
<dialog class="palette">…</dialog>
```

---

## Picking from this file

When building a section:

1. Identify the section's role (hero / section-head / feature / CTA / testimonial / footer / navigation).
2. Glance at the archetypes in that category.
3. Pick the one whose "Use when" fits the brief.
4. Make sure no two sections in the same page use the same archetype.
5. If the macrostructure suggests a default (e.g., Bento Grid → F1 Bento), use it; if it doesn't suggest, vary deliberately.

The goal is composed variety — within a page, sections feel different from each other; across pages Hallmark builds, sections feel different from the last.
