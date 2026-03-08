# Vitsœ 606 Configurator

An unofficial, browser-based configuration tool for the [Vitsœ 606 Universal Shelving System](https://www.vitsoe.com/us/606).

---

## Features

- **Accurate geometry** — bay widths (26¼" narrow / 35⅞" wide), e-track heights (22½"–78½"), and 32mm slot pitch are all true to the real system
- **Live SVG preview** — components snap to slots, conflict highlighting flags overlapping items, and the canvas auto-fits your screen
- **All 28 components** — shelves, deep shelves, single/double shelves, desk shelves, cabinets (1/2/3-drawer, up-and-over, fold-down, drop-flap, sliding-door), and tables in both narrow and wide widths
- **Drag and drop** — drag components from the palette onto bays, reposition them vertically, or drag them between compatible bays
- **Mixed track heights** — set each e-track independently; shorter tracks show a position slider (snapped to 32mm slot increments) so you can align them precisely
- **N/W bay labels** — bays are colour-coded and labelled with width type and dimensions, plus a total-width dimension line
- **Price summary** — running total in the header, itemised breakdown in the right panel (group by bay or by item type)
- **Export / Import** — save your configuration as JSON and reload it later
- **Bay duplication** — copy all components from one bay to another matching-width bay
- **Print quote** — opens a clean printable page with the SVG layout and full itemised quote ready for Ctrl+P / Save as PDF
- **Zero dependencies** — one `.html` file, works offline, no build step

---

## Usage

1. Download `vitsoe-configurator.html`
2. Open it in any modern browser
3. Use the **Structure** panel to add bays and set track heights
4. Drag components from the **Components** palette onto bays in the canvas
5. Use **Export** to save your configuration as JSON, **Print quote** to generate a shareable PDF

---

## How the geometry works

| Property | Value |
|---|---|
| Slot pitch | 32mm |
| Narrow bay width | 667mm (26¼") |
| Wide bay width | 912mm (35⅞") |
| Track heights | 572 / 1140 / 1711 / 1994mm |
| Cabinet height | 12 slots (384mm) |
| Shelf footprint | 1 slot — depth is from the wall, not vertical |

Components have two height values internally: `hs` (slot footprint for stacking logic) and `rh` (visual render height). Shelves occupy 1 slot in the track but render taller to reflect their physical bracket profile.

---

## Pricing

Prices are in USD and reflect current Vitsœ list prices including delivery to the contiguous US. This tool is **unofficial** — always confirm your final quote with a [Vitsœ planner](https://www.vitsoe.com/us/advice).

---

## Limitations & known gaps

- No bookend components
- No sloping shelves or hanging-rail variants
- Table depth variants (31½" / 47¼" / 63") not yet differentiated
- No room dimension constraints
- Touch/mobile drag not yet supported

---

## Contributing

Pull requests welcome. The entire app is a single HTML file — data, geometry, and UI are all clearly separated in the `<script>` block. Key areas:

- **`IT[]`** — component catalogue (add new items here)
- **`ET[]` / `BW`** — track and bay dimension data
- **`renderCanvas()`** — SVG drawing logic
- **`dc()`** — per-component SVG illustrations
- **`printQuote()`** — print/PDF generation

---

## Disclaimer

This is an independent project and is not affiliated with, endorsed by, or connected to Vitsœ in any way. Vitsœ and 606 Universal Shelving System are trademarks of Vitsœ Ltd.
