# Grace Notes with Andy

A personal website for music, faith, and daily Christian reflection — built as a single-page static site and deployed via Cloudflare Pages.

---

## Overview

**Grace Notes with Andy** is a personal bio page featuring:

- An introduction and bio alongside a profile photo
- A personal statement of faith (*Gratia et Cantus Firmus*) in an interactive accordion format
- Links to the author's Substack and YouTube channel
- A daily Christian devotional that automatically rotates each day using JavaScript — no server or database required

---

## File Structure

```
/
├── index.html        # The entire site — markup, styles, and script in one file
└── andy-profile.png  # Profile photo displayed in the bio section
```

The site is intentionally kept as a self-contained single file with no build tools, no dependencies, and no frameworks. All CSS and JavaScript live inside `index.html`.

---

## Features

### Daily Devotional
A curated set of Scripture passages and reflections rotates automatically based on the day of the year. No API or backend is needed — the rotation is handled entirely in client-side JavaScript. To add more devotional entries, edit the `devotionals` array in the `<script>` block at the bottom of `index.html`.

### Credo Accordion
The *Gratia et Cantus Firmus* statement of faith uses native HTML `<details>` and `<summary>` elements — no JavaScript required. Each of the eleven articles is collapsed by default and expands on click, working correctly on all modern browsers and screen readers.

### Responsive Layout
The bio section stacks vertically on mobile. The credo grid collapses from multi-column to a single column on smaller screens. All layout is handled with CSS Flexbox and Grid.

---

## Deployment (Cloudflare Pages)

This site is deployed via [Cloudflare Pages](https://pages.cloudflare.com/).

**To deploy or update:**

1. Push changes to the `main` branch of this repository
2. Cloudflare Pages will automatically detect the push and rebuild the site
3. No build command or output directory configuration is needed — Cloudflare serves the repository root directly

**Initial setup (one-time):**

1. In the Cloudflare dashboard, go to **Workers & Pages → Create → Pages → Connect to Git**
2. Select this repository
3. Set **Build command** to *(leave blank)*
4. Set **Build output directory** to `/` or leave blank
5. Click **Save and Deploy**

---

## Customization Notes

| What to change | Where to find it |
|---|---|
| Bio text | `index.html` — `.bio-text` section |
| Profile photo | Replace `andy-profile.png` (keep the same filename) |
| Substack / YouTube URLs | `index.html` — `.links-grid` section |
| Devotional entries | `index.html` — `devotionals` array in `<script>` |
| Credo content | `index.html` — `.credo-grid` section |
| Colors and fonts | `index.html` — `:root` CSS variables at the top of `<style>` |

---

## Tech Stack

- **HTML5** — semantic markup
- **CSS3** — custom properties, Flexbox, Grid, keyframe animations
- **Vanilla JavaScript** — devotional rotation only (no libraries)
- **Google Fonts** — Cormorant Garamond, Josefin Sans
- **Cloudflare Pages** — hosting and CDN

---

*Made with music and faith.*
