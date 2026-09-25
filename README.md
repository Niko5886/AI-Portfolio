# Ethan Vale — I See Through the Wild

A self-contained wildlife-photography portfolio: a single `index.html` with all
CSS and JavaScript inline (no frameworks, no bundler, no external CSS/JS).

## Features

- Splash screen with asset-loading progress bar
- 2× intro film with a Skip control and autoplay fallbacks
- Fibonacci photo sphere (21 stills) with drag-to-rotate and momentum
- Centered "I See Through the Wild" headline locked to the sphere origin
- 16vh scroll dolly (zoom-in) with depth shading
- Flat archive grid view
- FLIP-animated lightbox with full-resolution stills
- Full-screen menu, custom cursor, and a full responsive breakpoint set

## Run locally

Just open `index.html` in a browser, or serve the folder:

```bash
npx serve .
```

## Deploy

Static site — deploy the repository root to Vercel. No build step required.
