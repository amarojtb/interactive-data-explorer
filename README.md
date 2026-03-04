# Interactive Data Explorer

A squarified treemap visualization with drill-down navigation, tooltips, and smooth animations. Built entirely from scratch — **no charting libraries**. Pure HTML Canvas and JavaScript.

## Preview

![Explorer](https://img.shields.io/badge/status-ready-brightgreen) ![Dependencies](https://img.shields.io/badge/dependencies-none-blue) ![License](https://img.shields.io/badge/license-MIT-green)

## Features

- 🗺️ **Squarified Treemap** — Optimal rectangle-packing algorithm for readable layouts
- 🔍 **Drill-Down** — Click any category to zoom into its children
- 🧭 **Breadcrumb Navigation** — Track your position and navigate back
- 💡 **Rich Tooltips** — Hover for detailed data with percentages
- 🎬 **Smooth Animations** — Transition effects on drill-down and resize
- 🎨 **Light/Dark Theme** — Toggle with localStorage persistence
- ⚡ **Zero Dependencies** — Pure HTML Canvas and JavaScript
- 📱 **Responsive** — Canvas redraws on window resize

## Quick Start

```bash
git clone https://github.com/amarojtb/interactive-data-explorer.git
cd interactive-data-explorer
open index.html
```

No build tools needed.

## Customization

All data lives in the `TREEMAP_CONFIG` object at the top of `index.html`:

### Data Structure

```javascript
data: [
  {
    name: 'Category Name',
    icon: '🎨',
    children: [
      { name: 'Item A', value: 85 },
      { name: 'Item B', value: 72 },
      // Values determine rectangle sizes
    ]
  },
  // Add more categories...
]
```

| Property | Description |
|----------|-------------|
| `name` | Category or item name |
| `icon` | Emoji icon for the category |
| `children` | Array of child items (for categories) |
| `value` | Numeric value determining area size (for leaf items) |

### Example: File Size Explorer

```javascript
data: [
  {
    name: 'Documents',
    icon: '📄',
    children: [
      { name: 'report.pdf', value: 2400 },
      { name: 'slides.pptx', value: 1800 },
    ]
  },
  {
    name: 'Images',
    icon: '🖼️',
    children: [
      { name: 'photo.jpg', value: 4200 },
      { name: 'screenshot.png', value: 850 },
    ]
  }
]
```

## Use Cases

- **Disk Usage** — Visualize file/folder sizes
- **Budget Breakdown** — Show spending categories
- **Market Share** — Display competitive landscapes
- **Tech Stack** — Compare technology adoption
- **Portfolio Allocation** — Visualize investment distribution

## Algorithm

Uses the **squarified treemap** algorithm (Bruls, Huizing, van Wijk, 2000) which optimizes rectangle aspect ratios for readability, unlike slice-and-dice which creates thin strips.

## Architecture

```
index.html (single file)
├── CSS Custom Properties (theming)
├── HTML (canvas + breadcrumbs + legend)
└── JavaScript
    ├── TREEMAP_CONFIG (your data goes here)
    ├── Squarify Algorithm (layout computation)
    ├── Canvas Renderer (drawing + animations)
    ├── Interaction (click, hover, drill-down)
    └── Legend & Breadcrumbs (navigation)
```

## License

MIT — free to use in personal and commercial projects.
