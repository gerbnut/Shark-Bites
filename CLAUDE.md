# CLAUDE.md — Shark Bites

<!-- Imports rules from Web Design CLAUDE.md -->
@import Web Design CLAUDE.md

---

## Project: Shark Bites

Algorithmic sports trading alert service. Algorithm identifies edges on player props and other markets across NBA, MLB, NHL, NFL, and UFC. Trades are published exclusively on **Kalshi** and **Polymarket** (prediction markets — not sportsbooks). Subscribers get real-time alerts via Discord and Telegram. Fully automated "human out of loop" mode is on the roadmap.

### Brand

- **Name:** Shark Bites
- **Tagline:** The algorithm finds the edge. You place the trade.
- **Price:** $99/month (single tier, everything included)
- **Tone:** Sharp, data-driven, elite — Bloomberg Terminal meets hedge fund pitch deck. NOT a loud gambling brand.

### Color System

| Token | Hex | Role |
|---|---|---|
| void | `#020c19` | Primary background |
| deep | `#040f20` | Alternate section background |
| mid | `#071828` | Surface layer |
| elevated | `#0c2240` | Elevated cards |
| signal | `#00c8f0` | Primary accent (electric cyan) |
| bio | `#00e0a8` | Secondary accent (bioluminescent teal) |
| amber | `#e8940c` | Tertiary accent |
| text-1 | `#ddeeff` | Primary text |
| text-2 | `#7aaac8` | Secondary/muted text |
| text-3 | `#3a6080` | Subtle/disabled text |

### Typography

| Role | Font | Notes |
|---|---|---|
| Display/headings | Cormorant Garamond | Serif, editorial feel |
| Data/labels/mono | JetBrains Mono | Terminal authenticity |
| Body/UI | Outfit | Clean geometric sans |

Tight tracking (`-0.03em`) on large headings. `1.7–1.8` line-height on body.

### Visual System

- Hero: layered radial gradients + SVG grain texture + sonar ring animation
- Grid background texture: `rgba(0,200,240,0.025)` at 72px intervals
- Cards: `background: rgba(7,24,40,0.75)`, `border: 1px solid rgba(0,200,240,0.08)`, 2px border-radius
- Shadows: layered, color-tinted — never flat `shadow-md`
- Animations: only `transform` and `opacity`, spring easing

### File Structure

```
shark bites/
├── CLAUDE.md           ← this file
├── Web Design CLAUDE.md
├── index.html          ← single-file site (Tailwind CDN, all styles inline)
├── serve.mjs           ← static dev server (node serve.mjs → localhost:3000)
└── brand_assets/       ← empty — brand designed from scratch
```

### Dev Server

```bash
node serve.mjs
# → http://localhost:3000
```

### Stack

- Single `index.html`, all styles inline + `<style>` block
- Tailwind CSS via CDN for layout utilities
- Google Fonts: Cormorant Garamond, JetBrains Mono, Outfit
- No build step, no dependencies
