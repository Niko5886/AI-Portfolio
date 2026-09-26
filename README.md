<div align="center">

<img src="https://d8j0ntlcm91z4.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/hf_20260923_083259_8dc6261a-61b2-473e-b6f8-73171340c69e.png" alt="Family Orbit — I See Through the Wild" width="100%" />

# 🦅 Family Orbit — I See Through the Wild

### An immersive, single-file wildlife-photography archive with a 3D photo sphere

A hand-built, dependency-free portfolio experience — a black editorial archive of 21 wildlife stills arranged on a rotating Fibonacci sphere, with a cinematic intro, a FLIP lightbox and a meticulous, motion-aware design system. One `index.html`, no frameworks, no bundler, no build step.

<br />

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/Niko5886/AI-Portfolio)

<br /><br />

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/Vanilla_JS-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)

![Build](https://img.shields.io/badge/build-none%20·%20static-success)
![Single file](https://img.shields.io/badge/single--file-index.html-informational)
![Responsive](https://img.shields.io/badge/responsive-900%20·%20768%20·%20640%20·%20380-informational)
![Accessibility](https://img.shields.io/badge/a11y-reduced--motion%20aware-brightgreen)
![Status](https://img.shields.io/badge/status-ready%20to%20deploy-C6A15B)

</div>

---

## 📖 Overview

**Family Orbit — I See Through the Wild** is a premium, editorial one-page portfolio for a fictional wildlife photographer. It is intentionally **dependency-light**: no framework, no bundler, no build step — just clean HTML, one `<style>` block and one `<script>`, so it clones and runs anywhere in seconds.

The experience is anchored by a **3D Fibonacci photo sphere** of 21 stills that you drag to rotate, a **scroll-driven zoom**, and a centered headline that stays locked to the optical centre of the ring while the photographs turn around it. Every image is decoded and down-scaled on a `<canvas>` at runtime for crisp, lightweight cards.

> Built from the MotionSites **“Nature Portfolio”** design brief and committed step by step to this repository.

## ✨ Features

| | Feature | Details |
|---|---|---|
| 🎬 | **Splash + asset loader** | Progress bar driven by real load state — 21 stills + the intro film — with a timed floor and a 9 s backstop |
| 🎞️ | **Cinematic intro** | A 2× muted film with a **Skip** control, autoplay-blocked fallbacks, and a black-veil hand-off into the sphere |
| 🌐 | **Fibonacci photo sphere** | 21 stills evenly distributed on a unit sphere; **drag to rotate** with inertial momentum |
| 🎯 | **Locked headline** | “I See Through the Wild” counter-rotates in 3D to stay dead-centre on the sphere origin on every frame |
| 🔍 | **Scroll dolly** | A 16vh scroll range dollies the camera forward with depth-based shading — it never flies through the sphere |
| 🗂️ | **Flat archive grid** | A clean responsive gallery view of all 21 frames |
| 🖼️ | **FLIP lightbox** | Frames expand from their exact on-screen rect to a centred plate, swapping in the full-resolution still + field note |
| 🍔 | **Full-screen menu** | Clip-path reveal with archive / notes / studio / contact navigation |
| 🖱️ | **Custom cursor** | Blend-mode dot that widens over interactive elements (fine pointers only) |
| 📱 | **Fully responsive** | Tuned breakpoints at **900 / 768 / 640 / 380** plus a landscape short-height layout |
| ♿ | **Motion-aware** | Honours `prefers-reduced-motion`; safe-area insets for notched devices |

## 🧰 Tech Stack

- **HTML5** — semantic, accessible single-page markup
- **CSS3** — custom-property design tokens, 3D transforms & perspective, `clamp()` fluid type, container-tuned responsive layers
- **Vanilla JavaScript (IIFE-scoped)** — `requestAnimationFrame` camera loop, Fibonacci-sphere maths, pointer-drag with momentum, FLIP animation, and on-the-fly `<canvas>` image down-scaling
- **Google Fonts** — *Playfair Display* (display serif) + *Inter* (UI sans)
- **Vercel** — static hosting & continuous deployment from `main`
- **Assets** — wildlife stills & intro film streamed from CloudFront (CDN)

## 📁 Project Structure

```
.
├── index.html      # Self-contained page: markup + all CSS (<style>) + all JS (<script>)
├── README.md       # You are here
└── .gitignore
```

Everything the site needs to run lives in **one file**. The photography and film are external CDN assets referenced by absolute URL.

## 🚀 Getting Started

No install, no build. Because the intro film and stills stream over HTTPS, the site works straight from the file system, but **serving the folder** best matches production:

```bash
# clone
git clone https://github.com/Niko5886/AI-Portfolio.git
cd AI-Portfolio

# serve on http://localhost:4321  (pick any one)
npx serve -l 4321          # Node
python -m http.server 4321 # Python 3
php -S 127.0.0.1:4321      # PHP
```

Then open **http://localhost:4321/**, wait for the splash + intro, and **drag** the sphere to explore.

> 💡 An internet connection is required — the wildlife imagery and the intro film are streamed from a CDN.

## 🎨 Design System

Design tokens are defined as CSS custom properties on `:root`:

| Token | Value | Role |
|---|---|---|
| `--bg` | `#000` | Page ink / backdrop |
| `--ink` | `#f4f2ef` | Primary text |
| `--dim` | `#8c8783` | Muted text |
| `--line` | `rgba(244,242,239,.28)` | Hairlines & rules |
| `--serif` | Playfair Display | Wordmark, headline, captions |
| `--sans` | Inter | Body & UI |
| `--ease` | `cubic-bezier(.22,.61,.36,1)` | Shared motion curve |
| `--persp` | `620–1150px` | Sphere perspective (per breakpoint) |

Convention: **warm off-white on true black**, serif for editorial voice, sans for interface.

## ♿ Accessibility

- `prefers-reduced-motion` honoured — animations and transitions collapse gracefully
- ARIA labelling on the menu toggle, grid toggle and icon buttons
- Keyboard support — **Esc** closes the lightbox, then the menu, then grid view
- `viewport-fit=cover` + `env(safe-area-inset-*)` for notched devices
- Touch drag distinguishes horizontal rotation from vertical page scroll

## 🚢 Deployment

The site is a static bundle intended for **Vercel** — no build step, so deploys are near-instant.

**Option A — Dashboard (recommended)**
1. Go to [vercel.com/new](https://vercel.com/new) and import `Niko5886/AI-Portfolio`.
2. Framework Preset: **Other** · Build Command: **none** · Output Directory: **`./`**.
3. **Deploy** — every push to `main` then redeploys automatically.

**Option B — CLI**
```bash
npm i -g vercel
vercel --prod
```

> The live URL will be added here once the first Vercel deployment is published.

## 🖼️ Assets & Credits

- **Design brief** — MotionSites *“Nature Portfolio”* template.
- **Photography & intro film** — served from the MotionSites CloudFront CDN and used for this portfolio demo.
- **Fonts** — [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) & [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts.

When deploying publicly, ensure any third-party imagery carries its required attribution.

## 📄 License

© 2026 **Niko5886**. Personal portfolio project — all rights reserved.
The design derives from the MotionSites “Nature Portfolio” template; external imagery remains the property of its respective owners.

## 👤 Author

**Designed & built by Niko5886**

<div align="center">

<sub>Crafted step by step — one commit at a time 🦉</sub>

</div>
