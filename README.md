# IBC Map Painter

2D top-down map editor for the Imaginarium Living World map. A companion tool to the isometric Phaser editor — designed for fast, efficient terrain painting with mouse, touch, or Apple Pencil.

## Quick Start

**Option A — GitHub Pages:**
Visit [https://imaginebc.github.io/IBCMapEditor/](https://imaginebc.github.io/IBCMapEditor/)

**Option B — Local:**
Open `index.html` in any browser. No build step, no server required.

## Features

- **2D top-down view** — simple rectangular grid, no isometric projection
- **Touch + Apple Pencil support** — Pointer Events API for natural drawing on iPad
- **Pinch-to-zoom + two-finger pan** — standard tablet navigation
- **Ground + Overlay layers** — paint terrain separately from trees/props
- **Flood fill** — fill connected regions with one click
- **Eyedropper** — Alt+Click to pick any tile from the canvas
- **Variable brush size** — 1–10 tiles, keyboard `[` and `]` to adjust
- **Undo/Redo** — Ctrl+Z / Ctrl+Y, 80-step history
- **Building + entry point visualization** — buildings shown as labeled rectangles

## Data Sharing with IBC3React

The painter uses the same localStorage key (`imaginarium-map-editor`) as the IBC3React Phaser editor. Changes made here appear in the app editor and vice versa.

**Workflow:**
1. Export map from IBC3React editor (or generate with `node Scripts/generate-town-map.cjs`)
2. Load the JSON into the painter (Load → Browse or paste)
3. Paint in 2D top-down view
4. Save to browser storage (syncs with IBC3React editor automatically)
5. Or export JSON and copy to `IBC3React/public/maps/imaginarium-map.json`

## Controls

| Action | Mouse | Touch/Stylus |
|--------|-------|-------------|
| Paint | Left-click drag | Draw |
| Pan | Middle-click drag | Two-finger drag |
| Zoom | Scroll wheel | Pinch |
| Eyedropper | Alt+Click | — |
| Undo | Ctrl+Z | — |
| Redo | Ctrl+Y | — |
| Brush size | `[` / `]` keys | Slider |

## Color Legend

| Color | Terrain |
|-------|---------|
| Greens | Grass variants |
| Blue | Water |
| Tan/Brown | Dirt paths |
| Gray | Cobblestone |
| Warm Gray | Warm cobblestone (plazas) |
| Gold | Entry points |
| Dark green dots | Trees |
| Gray dots | Rocks/stones |
| Red rectangles | Buildings |

## Tech

Zero dependencies. Single HTML file with inline CSS + JS. Uses Canvas2D for rendering. Works offline after first load.

---

*Built by Atlas (Claude) for the Imaginarium project*
