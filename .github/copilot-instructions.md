# AI Coding Agent Instructions

## Project Overview

This is a personal portfolio website called "白シ透明" (shirosuki-toumeei), built as a static HTML site with a unified CSS theme. The site consists of multiple thematic pages where the author (paserinnn) shares personal content including diary entries, photos, book reviews, music recommendations, and travel memories.

## Architecture & Key Patterns

### Page Structure
- **Hub**: `index.html` - Main landing page with navigation menu
- **Content Pages**: 
  - `01-diary.html` - Daily diary entries (生活キ録)
  - `1-photos.html` - Photo gallery (写真) using `<figure>` elements
  - `2-book.html` - Book reviews (本)
  - `3-music.html` - Music recommendations (音楽)
  - `4-outside.html` - Travel memories (外出懐コ) with commented-out JavaScript
  - `6-iina.html` - Favorites gallery (いいな) - currently hidden from nav

### Styling Convention
- **Single CSS file**: `0-style.css` (numbered prefix for ordering)
- **CSS Variables (Custom Properties)**: 
  - `--accent-color: #135389` (blue)
  - `--base-color: #FBFEFF` (off-white)
  - `--text-color: #30343A` (dark gray)
  - `--entry-background-color: white`
  - `--entry-title-background-color: #ffddcc` (warm peach)
- **Font**: Google Fonts "Yomogi" (Japanese calligraphy style) via CDN link in every page `<head>`
- **Typography Classes**:
  - `.yomogi-regular` - Page titles (44px, font-weight: 600)
  - `.subtittle` - Page subtitles (18px, font-weight: 100)

### HTML Patterns
- **Content Wrapper**: All pages use `<div class="container">` for responsive layout
- **Entry Structure**: Each page wraps content in `<article class="entry">` > `<div class="entry-content">`
- **Date Headers**: Use `<h3 class="current-date">` for timestamps (format: YYYY/MM/DD)
- **Images**: Stored in `gazouu/` folder, use `<figure>` + `<img>` + `<figcaption>` pattern with `style="max-width:70%; height:auto;"`
- **Navigation**: List-based nav in `<header>` linking to content pages

### Responsive Design
- Mobile breakpoint: `@media (max-width: 768px)` adjusts `.container` width from 70% to 90%
- Base styling uses `max-width` for desktop optimization

## Development Notes

### File Organization
- Number-prefixed files for CSS organization (e.g., `0-style.css`)
- HTML files use short numerical prefixes for grouping (e.g., `01-diary.html`, `1-photos.html`)
- Image assets in `gazouu/` directory (Japanese slang for "image/photo")

### CSS Customization
- Modify color scheme by updating `:root` CSS variables
- Font size hierarchy: headings (44px/34px) → body text (18px) → footer (default)
- Margins/padding follow pattern: `.container` max-width 70%, internal margin/padding adjusted via body margin (80px)

### Common Edits
1. **Adding New Page**: Copy template structure from `01-diary.html`, update `<title>` and `<h1>` class="yomogi-regular"
2. **Changing Colors**: Edit `:root` variables in `0-style.css`
3. **Adding Images**: Place in `gazouu/` folder, use `<figure>` pattern with 70% max-width
4. **Navigation Update**: Modify `<ul>` in `index.html` `<nav>` (note: `6-iina.html` currently commented out)

### Known Issues/Quirks
- `index.html` line 17: Syntax error in `<li>` tag (`<a href="2-book.html"</a>本` - missing opening `>`)
- `4-outside.html` contains commented JavaScript for date auto-population (not currently used)
- Date format inconsistencies exist (e.g., "2025/0/21" typo, "2024/??/??" placeholders)

## Content Maintenance
- Diary entries use chronological order with manual date input
- Photo captions are empty (`<figcaption></figcaption>`) - consider populating
- Music/book entries follow simple `<li>` + `<p>` format
- Some entries have placeholder content ("??") awaiting author updates
