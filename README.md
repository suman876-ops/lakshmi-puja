# লক্ষ্মী পূজা · Sri Lakshmi Puja

> শ্রীময় হোক সকলের জীবন

A single-file, cinematic devotional website for **Lakshmi Puja** — built in Assamese, with interactive 3D graphics, a generative music engine, and a rendered short film. Everything (images, video, audio) is embedded in one HTML file, so it runs offline with no build step and no dependencies to install.

**Live site:** https://suman876-ops.github.io/lakshmi-puja/

---

## Features

**3D দৰ্শন (Darshan)** — an interactive Three.js golden lotus mandala: three rings of extruded petals around a glowing core, bead rings, a drifting particle field and floating petals. Drag to rotate, scroll to zoom, with auto-rotate and fullscreen controls.

**চলচ্চিত্ৰ (Cinema)** — a 26-second cinematic film rendered frame-by-frame from the artwork: slow Ken Burns moves across the lotus throne, owl, kalash, diya, offerings and pillars, with drifting embers, a warm film grade and Assamese captions. It carries its own ambient soundtrack, and has a theatre mode.

**সংগীত (Music)** — a generative ambient score written with the Web Audio API: a tanpura drone (Sa–Pa), a bansuri line in Raga Bhairavi, and temple bells on their own schedule. It never loops and never repeats. Alongside it are one-shot sounds — temple bell (ঘণ্টা), conch (শঙ্খ), ululation (উলুধ্বনি), a diya-lighting whoosh, and a chant drone on each mantra card.

**পূজাৰ নিয়ম (Puja Vidhi)** — the eight steps of the ritual as a scroll-animated timeline.

**শ্ৰী লক্ষ্মী মন্ত্ৰ (Mantras)** — four mantras (bija, dhyana, mangala, sampad) in Devanagari with transliteration and Assamese meaning; each can be heard.

**গ্যালাৰি (Gallery)** — a masonry gallery with a keyboard-navigable lightbox.

**পূজা টাইমাৰ ও দীপ (Timer & Diya)** — a dhyana timer that rings a bell when it ends, and a clickable diya that lights up and remembers your count.

**শুভেচ্ছা (Blessings)** — a generator that builds a personalised wish card from a name and exports it as a PNG.

Plus a preloader, scroll progress bar, scroll-reveal animations, a blessing marquee, an alpana rosette turning behind the hero, a marigold garland, and a fully responsive layout.

---

## Running it

No build step, no server, no package install:

```
open index.html
```

Or serve it locally:

```
python3 -m http.server
```

Then visit `http://localhost:8000`.

To publish it yourself, drop `index.html` at the root of any static host. The filename is already `index.html` so it works as a site entry point as-is.

---

## Tech

- Plain HTML, CSS and vanilla JavaScript — no framework, no bundler.
- [Three.js](https://threejs.org/) r158 (loaded from a CDN) for the 3D mandala.
- Web Audio API for all music and sound effects — every sound is synthesised at runtime, there are no audio files.
- Google Fonts: Noto Serif Bengali, Noto Serif Devanagari, Cormorant Garamond, Jost.
- The video was rendered offline with FFmpeg and the soundtrack synthesised with NumPy.

### Notes

- Three.js and the fonts load from a CDN. Offline, the 3D section falls back to a CSS-animated mandala and the text falls back to a system serif — nothing breaks.
- The page respects `prefers-reduced-motion`: the particle field, parallax and reveal animations are disabled for anyone who asks for reduced motion.
- Audio only starts after a user gesture, as browsers require.

---

## Credits

Design reference and artwork: the original Lakshmi Puja visual provided by the project owner. Typography by Google Fonts. Built with love for the puja season.
