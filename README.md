# Pixel Forge

A self-contained pixel art editor that runs entirely in your browser. No install, no server, no accounts — open the HTML file and start drawing. Nothing you create ever leaves your machine.

## Features

- **Drawing tools** — pencil, eraser, fill bucket, and eyedropper
- **Adjustable brush size** — 1px to 4px
- **Horizontal mirror mode** — for symmetrical sprites and characters
- **Color picker** — hex input, native color picker, a 16-color retro palette, and a recently-used swatch row
- **Resizable grid** — up to 128 × 128, with linked or independent width/height, quick presets (8², 16², 32², 64²), and resizing that preserves existing artwork instead of wiping it
- **Zoom and view controls** — zoom slider, toggleable grid lines, and a transparency checkerboard
- **Undo / redo** — up to 60 steps of history
- **Isometric conversion** — turn your flat artwork into an isometric projection, either as tilted flat tiles or extruded 3D/voxel blocks, with adjustable tile size, block height, and shading
- **PNG export** — choose a pixel scale (1×–32×) and export with a transparent or solid-color background; the isometric view exports separately at full resolution
- **Keyboard shortcuts** — for a faster workflow (see below)

## Getting started

1. Open `pixel-forge.html` in any modern web browser (Chrome, Firefox, Safari, Edge).
2. Pick a color from the palette, the picker, or a hex code.
3. Choose a tool and start drawing on the grid.
4. Use **Export PNG** in the header, or the **Export** panel on the right, to download your art.

That's it — no build step, no dependencies to install.

## Tools

| Tool | Shortcut | Description |
|---|---|---|
| Pencil | `B` | Paints the current color onto the grid |
| Eraser | `E` | Clears pixels back to transparent |
| Fill bucket | `F` | Flood-fills a contiguous area of matching color |
| Eyedropper | `I` | Picks the color of the pixel you click |
| Mirror X | `M` | Mirrors every stroke across the vertical center line |

## Keyboard shortcuts

| Action | Shortcut |
|---|---|
| Pencil / Eraser | `B` / `E` |
| Fill / Eyedropper | `F` / `I` |
| Mirror X | `M` |
| Decrease / increase brush size | `[` / `]` |
| Undo / Redo | `Ctrl+Z` / `Ctrl+Shift+Z` |
| Clear canvas | `Delete` or `Backspace` |
| Close isometric preview | `Esc` |

Shortcuts are disabled while typing in a text field, and while the isometric preview is open (only `Esc` is active there).

## Canvas grid

- Set width and height independently, or keep them linked to stay square.
- Use the presets (8×8, 16×16, 32×32, 64×64) for common sprite sizes.
- Click **Apply Grid Size** to resize. Growing the grid pads new space with transparency; shrinking it crops from the bottom-right, with a confirmation if you have existing artwork.

## Exporting

### Standard PNG
Pick a **pixel scale** (how many output pixels represent one grid cell — e.g. 8× turns a 16×16 grid into a 128×128 image) and choose whether the background should be transparent or a solid fill color. Click **Download PNG**.

### Isometric PNG
Open **Convert to Isometric** in the right panel to preview your art as an isometric projection:

- **Flat tiles** — projects the artwork onto a tilted 2:1 isometric grid, like a game floor tile
- **3D blocks** — extrudes every non-transparent pixel into a shaded cube for a voxel-style look

Adjust tile size, block height (3D blocks mode only), and side-shading strength, then use **Download Isometric PNG** to export the projection at full resolution — independent of the standard export.

## Tips

- Turn off **Checkerboard** if the transparency pattern is distracting while you work — it's a display aid only and never appears in exports unless you choose a solid background.
- The eyedropper won't pick up transparent pixels; clicking an empty cell leaves your current color unchanged.
- Undo/redo history resets when you resize the grid, since the canvas dimensions themselves change.
- For pixel-perfect exports, keep pixel scale at whole-number values (already enforced by the scale dropdown).

## Browser support

Works in any modern browser with support for the HTML5 Canvas API and Pointer Events (Chrome, Firefox, Safari, Edge — desktop and mobile). Touch input is supported for drawing on tablets and phones.

## Privacy

Pixel Forge does no networking beyond loading its two Google Fonts on first load. Your artwork is held only in memory for the current browser tab and is never saved, uploaded, or transmitted anywhere. Closing or refreshing the tab discards your work, so export before you're done.