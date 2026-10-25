---
trigger: always_on
---

# ZengLLQ GitHub Profile Theme & SVG Rules

When creating or updating `README.md`, stats widgets, badges, or SVG assets in this repository, follow these visual and technical constraints unless explicitly instructed otherwise:

## Color Palette ("My Color Theme")

- **Primary Accent (Light Purple)**: `#bd93f9` (matches Dracula / CommitPulse activity graph, titles, rings, cursors, active states)
- **Secondary Accent (Soft Lavender)**: `#c4b5fd` (secondary stats text, dates, subtle highlights)
- **Muted Monospace / Labels**: `#9489b8`
- **Primary Text**: `#faf5ff` (headings) and `#e9e4ff` (terminal body text)
- **Backgrounds & Surfaces**:
  - Deep night-sky gradient: `#131022` -> `#1c1733` -> `#25203D`
  - Elevated mini-card surface: `#1b1630` (skeleton bars: `#2b2447`)
  - Skill badge fill: single-segment Shields.io `https://img.shields.io/badge/<Label>-25203D?style=for-the-badge&logo=<slug>&logoColor=white` (escape `&` as `&amp;` inside HTML `<img src="...">` attributes; if a brand is missing from Simple Icons, supply a minimal `#fff` `24x24` `logo=data:image/svg%2Bxml;base64,...` vector icon so 100% of badges display a white icon)
  - 1px card & divider stroke: `#322b4f`
  - External stats widgets (`streak-stats`, `github-readme-stats`): `theme=transparent&hide_border=true`

## Tech Stack & Project Pillar Taxonomy

- Maintain the **4 Main Project Pillars** architecture across `README.md` and `assets/tech-domains.svg`:
  1. **01 · Blockchain** (Smart Contracts · Zero-Knowledge · Decentralized Protocols)
  2. **02 · Cybersecurity** (Low-Level Systems · Binary Analysis · SecOps & Native Tooling)
  3. **03 · Backend** (Distributed Services · Cloud-Native Integration · Data APIs)
  4. **04 · AI & Machine Learning** (Accelerated GPU Compute · Deep Learning · Symbolic & Statistical ML)
- Keep 100% cross-reference parity between `By Project Focus — 4 Main Pillars` (`Table 1`, including `Web, Mobile & Interactive Foundations`) and `Frameworks, SDKs & Engines — Complete Classification` (`Table 2`).

## GitHub README Animated SVG Guardrails

1. **Pure SMIL Only**: Use self-contained `<animate>` elements inside `.svg` files referenced via `<img src="assets/...svg">`. Never rely on `<script>`, external stylesheets, or external web fonts.
2. **Vector Icons Over Unicode Symbols**: Draw checkboxes, checkmarks, branch icons, and stars with SVG primitives (`<path>`, `<rect>`, `<circle>`) rather than Unicode glyphs (`U+2610`, `U+2611`, `U+2387`, `U+2726`), which trigger OS-dependent emoji/symbol font fallbacks and horizontal width shifts.
3. **Crisp Pixel & Loop Geometry**:
   - Place axis-aligned `stroke-width="1"` lines and rects on `.5` coordinates with integer widths/heights.
   - Scope internal `<style>` selectors to the root SVG `#id` and keep all `<defs>` IDs globally unique across `assets/*.svg`.
   - Ensure cyclic `<animate>` timelines have matching start/end values (`values[0] == values[-1]`) and hide or smooth any progress-bar reset intervals so loops never visibly bounce or freeze.
