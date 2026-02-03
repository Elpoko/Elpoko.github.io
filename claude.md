# Claude Code Instructions

## Styling
This blog is custom styled. Do NOT change the styling unless explicitly asked to do so.

## Project Structure

### Root directory (live site)
- `index.html` - Main homepage with inline styles and Lissajous animation
- `blog-template.html` - Template for creating new blog posts
- `*.html` - Individual blog posts (e.g., `2025-note.html`, `qc-hype.html`) with inline styles
- `favicon.svg` - Site favicon
- `*.jpg`, `*.png`, `*.jpeg` - Image assets

### /test directory (development/refactoring)
- `styles.css` - Unified stylesheet for both index and blog pages (~900 lines)
- `index.html` - Test index page using external `styles.css`
- `2025-note.html` - Test blog post using external `styles.css`
- `blog-template.html` - Template for new blog posts using external CSS/JS
- `blog-scripts.js` - Extracted JavaScript (dark mode toggle, footnotes)
- `favicon.svg` - Copy of favicon for testing
- `blog-styles.css` - (deprecated, can be deleted after testing)

### Unified styles.css architecture
The `/test/styles.css` file contains all styles for both index and blog pages:

- **Page type classes**: Add `class="index-page"` or `class="blog-page"` to `<body>`
- **Shared styles**: Reset, body, dark mode, mode-toggle, header elements, typography, email form
- **Index-specific**: `.index-page .container`, `.canvas-container`, `.list-item`, etc.
- **Blog-specific**: `.blog-page .container`, `article`, `.post-title`, footnotes, tables, etc.
- **Dark mode**: Works with both page types via `body.dark-mode`

### Key architectural notes
- **Current live site**: Each HTML file has ~400-700 lines of inline CSS
- **Test refactor**: Single `styles.css` eliminates duplication
- **Index vs Blog**: Different layouts controlled by body class (`.index-page` vs `.blog-page`)
- **To migrate**: Replace inline `<style>` with `<link rel="stylesheet" href="styles.css">` and add appropriate body class
