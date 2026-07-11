# networkplanning
Network Planning
# Network Planning — Design System

**networkplanning.co** · A WFWorks Company

---

## Brand in one sentence

Deeply researched, design-led travel guides — aviation in the bones, warmth in the body.

---

## Aesthetic foundation

- **Graphic modernism leads** — Brazilian 1960s–70s poster and airline livery tradition: bold geometry, flat color, confident form. Niemeyer curves as a signature motif; Bo Bardi rawness as occasional texture.
- **Aviation industrial structure** — flip-clock Solari boards, tight grids, sharp 1px rules, IBM Plex Mono for all technical metadata. The structural layer of the brand.
- **Tropical pop** — coral (WFWorks family thread) breaks the cool structure. Saffron and viridian appear as destination-specific accents.
- **Jetsonian nostalgia** — Space Age retrofuturism meets the modern web. Of its era and not.

---

## Color palette

| Token               | Hex       | Use                                      |
| ------------------- | --------- | ---------------------------------------- |
| `--color-void`      | `#10171C` | Primary dark — the main structural color |
| `--color-charcoal`  | `#263642` | Dark panels, section headers             |
| `--color-graphite`  | `#47606E` | Secondary text, muted elements           |
| `--color-parchment` | `#EAEDEB` | Primary base — greige, steely blue-green  |
| `--color-coral`     | `#E25E3A` | **WFWorks family accent** — primary pop  |
| `--color-saffron`   | `#E9A224` | Tropical warm — Rio, warm destinations   |
| `--color-viridian`  | `#2D7D64` | Tropical depth — Siem Reap, jungle       |
| `--color-sky`       | `#7292AA` | Aviation / map blue-grey                 |

---

## Typography

Three typefaces. Clear roles. No exceptions.

**F37 Holborn Cyrillic** — all headlines and body copy
- Display type, h1/h2, section intros, planner voice, field notes
- Weight range Thin–Black, plus italics — lean into the geometric weight for display, lighter weights for running body text
- Licensed desktop font, not on Google Fonts — the site references it by name via `--f-disp`/`--f-body`, but actually showing it to visitors needs it self-hosted as a webfont (check the license covers web embedding first)

**Courier New** — all technical / metadata text
- Section tabs: `DESK 04 // OAXACA`
- Day headers, coordinates, codes, booking references
- Navigation links, labels, captions
- Tracking: 0.10–0.18em | Weight: 400 / 500 | Case: UPPERCASE
- `--f-mono` prefers IBM Plex Mono (the actual Google Font loaded here) with Courier New as fallback — the two read as the same family

**Times New Roman Italic** — rare emphasis only, applied by hand, never a running voice

---

## Logo mark

The NP mark: a navigation hub ring (circle, stroke-only) with a subtle crosshair, a center origin dot, a departure route line, and a coral destination dot at the terminus.

Reads as: *a route network departing from a hub toward a destination.*

**Usage rules:**
- Always show the mark with wordmark in formal contexts
- Standalone mark works for favicon, social avatar, guide corner stamp
- Destination dot is always coral `#E25E3A` — even in monochrome contexts, use a coral dot
- On dark backgrounds: circle and line in `#EAEDEB`. On light: `#10171C`.
- Minimum size: 20px (mark alone); 80px (full lockup)

---

## Flip-board (Solari) animation

The brand's signature interactive element on the web.

- Implementation: see `components/core/FlipBoard.jsx` (React) and `website/index.html` (vanilla JS)
- Tile: near-black background (`#0E0E10`), IBM Plex Mono 500, parchment text
- Center split line: `rgba(0,0,0,0.5)` — the mechanical feel
- Animation: characters scramble through 1–4 random glyphs before settling
- Cascade delay: 42ms per tile left-to-right
- Pause between destinations: 3500–4000ms
- Used on: homepage hero, destination index page header, booking-window component

---

## Graphic system rules

**Section tabs** — every major content block opens with one:
- `[1px coral tick] TAB LABEL TEXT // SECTION`
- IBM Plex Mono 500, 10–11px, letter-spacing 0.13em, UPPERCASE
- On dark: `rgba(243,239,231,0.38)`. On light: `#47606E`.

**Rules and grids:**
- 1px `#C0C7C3` — standard content divider
- 2px `#10171C` — heavy structural rule
- 2px `#E25E3A` — coral accent rule (hero left edge, product card header)
- Grid: 12 columns, 8px base, 24px gutter (desktop), 20px (mobile)

**Border radius:** Near-zero. `2px` maximum. This is not a rounded brand.

---

## Product components (guide templates)

### Day Header
Dark panel with left coral border. Day number (IBM Plex Mono 32px), vertical rule, location name + IATA/coordinate metadata.

### Planner Note
Ivory background, 2px coral left border. IBM Plex Mono label + F37 Holborn Cyrillic italic body. The personal voice of the planner.

### Fun Fact
Near-black box. IBM Plex Mono label in saffron or coral. F37 Holborn Cyrillic 300 body in muted parchment.

### Section Tab (guide)
Same as web tab. Aviation strip energy in the printed page.

---

## Destination flex range

The system flexes across three registers:

| Destination    | Temperature        | Accent          | Feel                    |
| -------------- | ------------------ | --------------- | ----------------------- |
| Rio de Janeiro | Warm, vibrant      | Coral + Saffron | Energetic, lush         |
| Siem Reap      | Cultural, textural | Viridian        | Ancient, deliberate     |
| Austin         | Cool, younger      | Sky             | Minimal, design-forward |

The mark, type, and structure stay constant. Color accent and photography warmth shift.

---

## File structure

	Network Planning/
	├── _ds_manifest.json       ← Claude Design manifest
	├── styles.css              ← Global styles + utility classes
	├── tokens/
	│   ├── colors.css
	│   ├── typography.css
	│   ├── spacing.css
	│   └── shadows.css
	├── guidelines/             ← Brand guideline cards
	│   ├── brand-voice.card.html
	│   ├── logo.card.html
	│   ├── graphic-system.card.html
	│   ├── colors-brand.card.html
	│   ├── colors-neutrals.card.html
	│   ├── colors-pairings.card.html
	│   ├── type-display.card.html
	│   ├── type-body.card.html
	│   └── type-scale.card.html
	├── components/
	│   ├── core/
	│   │   ├── Button.jsx
	│   │   ├── Tag.jsx
	│   │   ├── SectionTab.jsx
	│   │   ├── FlipBoard.jsx
	│   │   └── core.card.html
	│   └── guide/
	│       ├── PlannerNote.jsx
	│       ├── FunFact.jsx
	│       └── DayHeader.jsx
	├── logo/
	│   └── render.html         ← All logo lockups + icon sizes
	└── website/
	    └── index.html          ← Full homepage prototype (Solari animation live)

---

*Network Planning · A WFWorks Company · networkplanning.co*
