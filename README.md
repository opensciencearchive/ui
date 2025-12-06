# OSA UI System

Design system for [Open Science Archive](https://opensciencearchive.org) — an editorial specification aesthetic with monochrome foundation and sage green accents.

## Installation

```bash
pnpm add github:opensciencearchive/ui
```

## Vite Configuration

Add this alias to your Vite config to enable font loading:

```js
// vite.config.js
import { defineConfig } from 'vite';
import path from 'path';

export default defineConfig({
  resolve: {
    alias: {
      '~@opensciencearchive/ui': path.resolve(__dirname, './node_modules/@opensciencearchive/ui/ui'),
    },
  },
});
```

For Astro projects:

```js
// astro.config.mjs
import { defineConfig } from 'astro/config';
import path from 'path';

export default defineConfig({
  vite: {
    resolve: {
      alias: {
        '~@opensciencearchive/ui': path.resolve(__dirname, './node_modules/@opensciencearchive/ui/ui'),
      },
    },
  },
});
```

## Usage

Import everything:

```css
@import '@opensciencearchive/ui';
```

Or import specific parts:

```css
/* Just tokens */
@import '@opensciencearchive/ui/tokens';

/* Just prose/article styles */
@import '@opensciencearchive/ui/prose';

/* Individual token files */
@import '@opensciencearchive/ui/tokens/colors.css';
@import '@opensciencearchive/ui/tokens/typography.css';
```

## Structure

```
ui/
├── index.css           # Main entry point
├── tokens/             # Design tokens (CSS custom properties)
│   ├── colors.css      # Color palette
│   ├── typography.css  # Font stacks, sizes, line heights
│   ├── spacing.css     # Spacing scale
│   ├── layout.css      # Content widths
│   ├── motion.css      # Transitions, animations
│   └── surfaces.css    # Shadows, border radii
├── base/               # Base element styles
│   ├── reset.css       # CSS reset
│   ├── elements.css    # HTML element defaults
│   └── utilities.css   # Utility classes
├── prose/              # Long-form content
│   └── article.css     # Article/spec styling (.prose class)
├── components/         # Component styles
│   ├── callout.css     # Callout boxes
│   ├── margin-note.css # Margin notes
│   └── progress-bar.css# Scroll progress indicator
└── fonts/              # Self-hosted web fonts
    └── index.css       # @font-face declarations
```

## Fonts

This design system uses three typefaces:

- **DM Serif Display** — Display/heading font
- **Inter** — Body/UI font
- **JetBrains Mono** — Code font

You can either:

1. **Self-host** (recommended): Import `@opensciencearchive/ui/fonts`
2. **Google Fonts**: Add to your HTML `<head>`:

```html
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet" />
```

## Prose/Article Styling

For long-form content like specifications or RFCs, add the `.prose` class:

```html
<article class="prose">
  <h1>Section Title</h1>
  <p>Content here...</p>
</article>
```

Features:
- Sticky section headers (h1)
- Optimized reading typography
- Responsive sizing
- Code block styling
- Table formatting

## Customization

Override CSS custom properties to customize:

```css
:root {
  /* Change accent color */
  --color-accent: hsl(220, 60%, 50%);
  --color-accent-hover: hsl(220, 60%, 35%);

  /* Change fonts */
  --font-display: 'Your Display Font', serif;
}
```

## License

MIT
