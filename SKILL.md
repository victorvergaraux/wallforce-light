---
name: wallforce-light
description: Light version of wallforce. Makes a simple seed-based Swiss-style wallpaper generator as one HTML file with a small panel and exact-size PNG download. Use for "make a quick wallpaper generator" or "wallforce light".
---

# wallforce-light

A taste of **wallforce**: one prompt → one HTML page where every seed gives a new Swiss-style wallpaper, downloadable as a PNG at the exact screen size.

Reply in the user's language; code and control labels stay in English.

## What it does
- One generator per request, built from `assets/template.html` (a single file, no build step).
- Seed field + Generate (Space) + Download PNG (D).
- Panel (Tweakpane 4.0.5) with Screen, Palette, Margin, Cell, Count.
- 5 screens: Full HD, Ultrawide, 4K, iPhone, Post 4:5. 4 palettes: INK, SWISS, PAPER, COBALT.
- Entrance with Expo.easeInOut.

## How to use it
1. Copy `assets/template.html`.
2. Adapt it to the request by changing only:
   - `WORDS` (headline vocabulary from the subject),
   - `PALETTES` (keep the shape `{ bg, ink, colors[4] }`, each palette fully dark or light),
   - the block drawing in `draw()` (shapes and fills for the motif).
3. Keep the rules below, publish as an artifact (`capabilities: { downloads: true }`) or hand over the file, and reply in 3–5 lines: what the seed changes and the two shortcuts.

## Rules
- Everything random comes from `rng(seed, 'name')`, never `Math.random` (except to make a new seed). Same seed = same image.
- The seed changes the composition (which cells, which word, which fills), never the Margin.
- Swiss type: Plus Jakarta Sans 800 for one large headline, Inter for text, IBM Plex Mono only for data (seed, size).
- Flat colors, one accent, generous empty space, everything aligned to the grid.
- Control labels: one English word.

## Not included in the light version
Video export, presentation mode, undo/redo, photo input and photo palettes, shader layers, the full screen catalog and custom sizes, style recipes, reference-image analysis, stack questions, React/Next/Astro/Vue/Svelte installation, automated testing. These are part of the full **wallforce** skill.

## Credits
Created by Victor Vergara — [github.com/victorvergaraux](https://github.com/victorvergaraux). Fonts: Plus Jakarta Sans, Inter, IBM Plex Mono (Google Fonts, OFL). Panel: Tweakpane (MIT).
