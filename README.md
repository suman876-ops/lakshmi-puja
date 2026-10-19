# লক্ষ্মী পূজা · Sri Lakshmi Puja

> শ্রীময় হোক সকলের জীবন

A cinematic devotional website for **Lakshmi Puja** — built in Assamese, with interactive 3D graphics, a generative music engine, and a rendered short film.

**Live site:** https://suman876-ops.github.io/lakshmi-puja/

---

## Repository layout

```
index.html              the whole site — HTML, CSS, JS and every image embedded
media/puja-video.mp4    the 26-second film, with its ambient soundtrack
```

Everything except the video is embedded directly in `index.html`, so the page has no image requests to make. The video is served as a normal file so the page paints fast and the video streams.

---

## Features

**3D দৰ্শন (Darshan)** — an interactive Three.js golden lotus mandala: three rings of extruded petals around a glowing core, bead rings, a drifting particle field and floating petals. Drag to rotate, scroll to zoom, with auto-rotate and fullscreen controls.

**চলচ্চিত্ৰ (Cinema)** — a 26-second cinematic film rendered frame-by-frame from the artwork: slow Ken Burns moves across the lotus throne, owl, kalash, diya, offerings and pillars, with drifting embers, a warm film grade and Assamese captions. It carries its own ambient soundtrack, and has a theatre mode.

**সংগীত (Music)** — a generative ambient score written with the Web Audio API: a tanpura drone (Sa–Pa), a bansuri line in Raga Bhairavi, and temple bells on their own schedule. It never loops and never repeats. Alongside it are one-shot sounds — temple bell (ঘণ্টা), conch (শঙ্খ), ululation (উলুধ্বনি), a diya-lighting whoosh, and a chant drone on each mantra card.

**পূজাৰ নিয়ম (Puja Vidhi)** — the eight steps of the ritual as a scroll-animated timeline.

**শ্ৰী লক্ষ্মী মন্ত্ৰ (Mantras)** — four mantras (bija, dhyana, mangala, sampad) in Devanagari with transliteration and Assamese meaning; each one can be heard.

**গ্যালাৰি (Gallery)** — a masonry gallery with a keyboard-navigable lightbox.

**পূজা টাইমাৰ ও দীপ (Timer & Diya)** — a dhyana timer that rings a bell when it ends, and a clickable diya that lights up and remembers your count.

**শুভেচ্ছা (Blessings)** — a generator that builds a personalised wish card from a name and exports it as a PNG.

**প্ৰশ্ন-উত্তৰ (FAQ)** — the questions people actually search for (when the puja falls, what the rules are, which mantra, what to offer), with the Kojagari Lakshmi Puja 2026 date.

Plus a preloader, scroll progress bar, scroll-reveal animations, a blessing marquee, an alpana rosette turning behind the hero, a marigold garland, and a fully responsive layout.

---

## Search & SEO

The page is built to be found and understood by search engines:

- A keyword-led `<title>` and meta description targeting লক্ষ্মী পূজা ২০২৬, কোজাগৰী লক্ষ্মী পূজা, পূজাৰ নিয়ম, মন্ত্ৰ and related queries.
- `canonical` URL, `robots` directives, and Open Graph / Twitter Card tags so links unfurl properly when shared.
- Schema.org structured data (JSON-LD): `WebSite`, `WebPage`, `ImageObject` and a `FAQPage` matching the visible FAQ section.
- `robots.txt` and `sitemap.xml` at the root.
- One `<h1>`, a clean `<h2>` hierarchy, and descriptive `alt` text on every image.
- Assamese is declared throughout (`lang="as"`, `og:locale` `as_IN`), which is where this page is most likely to rank — Assamese-language competition is thin compared with Bengali or English.

To get indexed: verify the site in [Google Search Console](https://search.google.com/search-console), submit `sitemap.xml`, then use *URL Inspection → Request indexing*. Indexing is not instant and ranking is never guaranteed — see the Search Console for what Google has actually crawled.

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

---

## Tech

- Plain HTML, CSS and vanilla JavaScript — no framework, no bundler.
- [Three.js](https://threejs.org/) r158 (loaded from a CDN) for the 3D mandala.
- Web Audio API for all music and sound effects — every sound is synthesised at runtime; there are no audio files.
- Google Fonts: Noto Serif Bengali, Noto Serif Devanagari, Cormorant Garamond, Jost.
- The film was rendered offline with FFmpeg, and its soundtrack synthesised with NumPy.

### Notes

- Three.js and the fonts load from a CDN. Offline, the 3D section falls back to a CSS-animated mandala and the text falls back to a system serif — nothing breaks.
- The page respects `prefers-reduced-motion`: the particle field, parallax and reveal animations are disabled for anyone who asks for reduced motion.
- Audio only starts after a user gesture, as browsers require.
- `index.html` can also be inlined into a single fully self-contained file by replacing the video `src` with a `data:video/mp4;base64,…` URI, for offline distribution.

---

## Credits

Design reference and artwork: the original Lakshmi Puja visual provided by the project owner. Typography by Google Fonts. Built with love for the puja season.
