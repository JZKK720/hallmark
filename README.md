# Hallmark

A design skill for AI coding assistants. Makes the UIs they generate look made, not generated.

**Powered by Together AI.**

---

## What it is

A single, opinionated skill that gives Claude Code, Cursor, and Codex a firm rule-set for typography, colour, layout, motion, microinteractions, copy, responsive behaviour, and structural variety. It refuses to emit the on-distribution defaults every LLM was trained into.

The differentiator: Hallmark insists on **structural variety**, not just visual variety. Two pages from two briefs should not share the same hero → 3-feature → CTA → footer rhythm. They should feel like different sites.

---

## Five verbs

| Verb | What it does |
| --- | --- |
| *(default)* | Build new UI. Asks for audience + use case + tone (skippable — the skill states what it inferred either way), picks a macrostructure, applies the rule-set, runs the slop test before handing back. |
| `hallmark audit <target>` | Score existing code against the named anti-patterns + structural sameness. Punch list, no edits. |
| `hallmark refine <target>` | Polish in place. Smallest possible diff. Preserves structure. |
| `hallmark redesign <target> [--mood <name>]` | Throw out the structure, keep copy + IA + brand, rebuild with a deliberately different fingerprint. |
| `hallmark study <screenshot>` | Extract the **DNA** from a design the user admires — macrostructure, archetypes, type-pairing role, colour anchor — and produce a diagnosis report. Optionally rebuild *the user's* content using the extracted DNA. Refuses paid templates and competitor pages. Names font roles, never font IDs. Never copies pixels. |

---

## What's inside

- **[`SKILL.md`](skill/SKILL.md)** — the routing file. Design flow, slop test (33 questions), output contract.
- **[`references/`](skill/references/)** — sixteen short, opinionated rule files: typography, colour, layout, motion, microinteractions, interaction-and-states, responsive, copy, anti-patterns, the 21 named macrostructures, the 36 component archetypes with variation knobs, the 6 primitive structure axes, the vision-extraction protocol for `study`, and three new files for hero work — `hero-enrichment.md` (when to add visuals to a hero, plus eight enrichment archetypes), `custom-craft.md` (how to hand-build CSS art, SVG, declarative animation, JS-driven motion, with Lottie demoted to last resort), and `assets.md` (sourcing canon for icons, brand logos, generated illustration via Nanobanana / Recraft, library illustration, app mockups, hero video, photography, abstract backgrounds).
- **[`site/`](site/)** — a self-demonstrating landing page. Hand-written HTML + CSS + ES module, no framework, no build step. **Sixteen themes** — Specimen, Newsprint, Atelier, Garden, Salon, Linen, Almanac, Midnight, Terminal, Brutal, Manifesto, Sport, Studio, Pastel, Riso, **Quiet** — that swap not just colour and typography but the page's hero archetype and footer archetype. Switching themes literally rebuilds the page.
- **[`ROADMAP.md`](ROADMAP.md)** — Tier 1, 2, 3 work plus an explicit "things to *not* do" list.

---

## Install

```
npx skills add hallmark
```

Or copy [`skill/`](skill/) into `~/.claude/skills/hallmark/` (Claude Code) or `.cursor/rules/hallmark.mdc` (Cursor — body of `SKILL.md`, no frontmatter).

To preview the landing page:

```
cd site && python3 -m http.server 4173    # → http://localhost:4173
```

Press `T` to cycle themes, `R` for random, `?theme=studio` for a shareable link.

---

## What's distinct

- **One skill, five verbs.** Not eighteen commands.
- **Tone is a first-class decision.** "Clean and modern" is rejected. Pick an extreme.
- **Macrostructures over axes.** Pick one of 21 named whole-page shapes wholesale; the macrostructure stamp lives in the CSS comment, so the next Hallmark run picks something different.
- **Within-archetype variation.** Two Bento Grids should not be twins; each archetype has 2–3 picked-per-output knobs.
- **Microinteractions as discipline.** Silent success over celebratory toasts. Optimistic update + Undo over confirm dialogs. Hover delay 800 ms, focus delay 0 ms.
- **A 33-gate slop test** runs before every output. One yes fails the build.
- **Hero enrichment is opt-in, not a default.** A typographic-only hero is always acceptable. When enrichment is right, the skill picks from a six-tier hierarchy: typography only → custom-built CSS art → hand-built SVG → generated illustration (Nanobanana / Recraft) → library + customise → Lottie (last resort).
- **`study` extracts DNA, not pixels.** Vision-extraction with refusal heuristics, type-role vocabulary (no font ID guessing), and a confirmation step before any code.

---

## Credits

Built on the open work of:

- Paul Bakaus' [**impeccable**](https://github.com/pbakaus/impeccable) — the named-tells canon
- tw93's [**kami**](https://github.com/tw93/kami) — the slop-test concept and 20-question scoring
- Leonxlnx's [**taste-skill**](https://github.com/Leonxlnx/taste-skill) — taste vocabulary and the audit verb
- Anthropic's [**frontend-design**](https://github.com/anthropics/skills) and [**canvas-design**](https://github.com/anthropics/skills) skills — the design-context-gate pattern
- Google Stitch's [**DESIGN.md**](https://getdesign.md) — single-source design docs
- Marie Claire Dean's [**63 design skills for Claude**](https://marieclairedean.substack.com/p/i-built-63-design-skills-for-claude) — coverage map
- Steve Barclay's [**PencilPlaybook**](https://github.com/stevembarclay/pencilplaybook) — the design-language playbook format
- The [**Slopless**](https://slopless.design) tactile-rebellion canon — the 2026 anti-AI-perfect movement (informed Studio, Pastel, Riso)
- Anthropic's [**Skill Engineering**](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills) writeup — file budgets, load-on-demand patterns, frontmatter shape

Where rules overlapped, Hallmark adopted; where they diverged, Hallmark picked.

---

## Licence

MIT. Use it, fork it, ship it.
