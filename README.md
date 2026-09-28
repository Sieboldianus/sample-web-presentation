# Scientific Web Presentation Template (Reveal.js + Jekyll)

A modular, reproducible template for academic presentations and conference keynotes. Built with **Jekyll**, **Reveal.js**, and the **`reveal-presentation-theme`** gem.

---

## Getting Started

### 1. Fork / Clone & Rename

1. Fork or clone this repository for your new presentation.
2. In `_config.yml`, update:
   * `title`, `firstslide-title`, `firstslide-subtitle`, and `firstslide-author`
   * `baseurl`: Set to your presentation's directory path (e.g., `/my-new-talk`)
   * `url`: Set to your web hosting domain (e.g., `https://slides.ad.ioer.info`)

### 2. Local Development

Ensure you have Ruby 3+ installed:

```bash
# Install dependencies
bundle install

# Start local preview server with auto-reload
bundle exec jekyll serve --livereload
```
Open `http://127.0.0.1:4000/<baseurl>/` in your browser.

---

## Slide Authoring Syntax

Slides reside in `_posts/` as sequential Markdown files (e.g. `0001-01-01-welcome.md`, `0002-01-01-topic.md`):

| Feature | Syntax / Example |
| :--- | :--- |
| **New Slide** | Separate sections with `---` |
| **Vertical Sub-Slide** | Separate sections with `--` (reached via Down Arrow) |
| **Fragment Animations** | Add `<fragment/>` or start list items with `+` |
| **Background Color** | `<background>#232323</background>` |
| **Background Image** | `<backgroundimage>assets/photo.webp</backgroundimage>` |
| **Background Iframe** | `<!-- .slide: data-background-iframe="https://..." data-preload -->` |
| **Speaker Notes** | Add `Note:` (all following text is private to Speaker View) |
| **Clean Header** | `<!-- .slide: data-header="clean" -->` (removes top logo) |
| **Slide ID** | `<slide-id>my-topic</slide-id>` (link via `#/my-topic`) |

---

## Slide Toolchain CLI (`bundle exec slides`)

This template includes helper utilities via the theme gem:

### 1. Asset Hygiene & Unused Media Pruner

When cloning an existing presentation, remove unreferenced images and videos:
```bash
# Inspect unused files and recoverable disk space:
bundle exec slides prune

# Safely quarantine unused files to '_unused_assets/' (gitignored):
bundle exec slides prune --move
```

### 2. Styled QR Code Generator

Generates a high-contrast QR code matching the dark slide background (`#232323` background with white glyphs):
```bash
bundle exec slides qrcode
```
Saves to `images/qr.png` automatically.

### 3. Dockerized PDF Export (DeckTape)

Exports the presentation to a pixel-perfect vector PDF:
```bash
# Export using production HTTPS URL (load-pause 3000ms, pause 5500ms):
bundle exec slides pdf

# Export from local running Jekyll server:
bundle exec slides pdf --local
```

### 4. Zenodo Archival & DOI Minting

Package the slides, generate metadata, and reserve an official DOI:
```bash
bundle exec slides zenodo
```

Securely prompts for your Zenodo API token, bundles the PDF and source files, and creates a pre-reviewed draft deposit attached to the IOER community.

---

## Presenter Guide (Conference & Dual-Screen Setups)

* **Speaker View (<kbd>S</kbd>):** Press <kbd>S</kbd> to open the two-way synchronized notes window. On a dual-screen setup (projector + laptop), put the slides in fullscreen (<kbd>F</kbd>) on the projector and keep the notes on your laptop screen.
* **2D Navigation:** 
  * <kbd>→</kbd> / <kbd>←</kbd>: Advances the main horizontal narrative.
  * <kbd>↓</kbd> / <kbd>↑</kbd>: Enters optional vertical deep-dive / appendix slides.
* **Overview Mode (<kbd>O</kbd> / <kbd>Esc</kbd>):** Toggles a zoomable grid of all slides (ideal for Q&A).
* **Keyboard Shortcuts (<kbd>?</kbd>):** Opens the Reveal.js cheat sheet.