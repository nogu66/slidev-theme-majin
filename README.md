# Slidev Theme Majin

[![NPM version](https://img.shields.io/npm/v/slidev-theme-majin?color=3AB9D4&label=)](https://www.npmjs.com/package/slidev-theme-majin)

A professional Slidev theme with 17+ Google Slides-inspired layouts for creating stunning presentations.

## Features

- 🎨 **17+ Professional Layouts** - Comprehensive set of layouts for any presentation need
- 🎯 **Google Slides Style** - Clean, modern design inspired by Google Slides
- 🚀 **Easy to Use** - Simple prop-based configuration
- 💪 **Fully Customizable** - Modify colors, fonts, and styles
- 📱 **Responsive** - Looks great on any screen size
- ⚡ **Developer Friendly** - Built with Vue 3 and TypeScript

## Installation

Add the following frontmatter to your `slides.md`. Start Slidev then it will prompt you to install the theme automatically.

```yaml
---
theme: majin
---
```

Learn more about [how to use a theme](https://sli.dev/guide/theme-addon#use-theme).

## Available Layouts

### Basic Layouts
- **title** - Title slide with date
- **section** - Section divider with optional section number
- **content** - Content slide with 1 or 2 columns
- **closing** - Closing/thank you slide

### Comparison Layouts
- **compare** - Side-by-side comparison
- **stats-compare** - Statistical comparison with trends

### Process & Timeline
- **process** - Step-by-step process
- **timeline** - Timeline with milestones

### Card Layouts
- **cards** - Simple card grid
- **header-cards** - Cards with header sections
- **bullet-cards** - Numbered bullet point cards (max 3)

### Data Display
- **table** - Data table
- **kpi** - KPI metrics cards
- **progress** - Progress bars

### Other Layouts
- **quote** - Quotation display
- **faq** - FAQ with Q&A format

See the [example.md](./example.md) for detailed usage examples of each layout.

## Quick Start

```markdown
---
theme: majin
---

---
layout: title
date: 2025.10.25
---

# Your Presentation Title

Subtitle or description

---
layout: section
sectionNo: 1
---

# Section 1

Section description

---
layout: content
---

<template v-slot:title>
Content Slide
</template>

- Bullet point 1
- Bullet point 2
- Bullet point 3
```

## Customization

### Colors

Customize theme colors by adding styles to your slides:

```markdown
<style>
:root {
  --majin-primary: #1a73e8;
  --majin-accent: #f46524;
}
</style>
```

### Fonts

Override fonts in your frontmatter:

```yaml
---
theme: majin
fonts:
  sans: 'Roboto'
  mono: 'Fira Code'
---
```

## Development

- `npm install` - Install dependencies
- `npm run dev` - Start theme preview of `example.md`
- `npm run build` - Build the theme
- `npm run export` - Generate preview PDF
- `npm run screenshot` - Generate preview PNG

## Credits

Inspired by Google Slides design system and created for the Slidev community.

## License

MIT

## Author

Created by Yuta Noguchi

---

Learn more about [Slidev](https://sli.dev)
