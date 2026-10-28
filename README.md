# Lakshmi Puja · লক্ষ্মী পূজা

A cinematic devotional site for Lakshmi Puja — written in Assamese, with interactive 3D graphics, a generative music engine and a rendered short film.

**Live:** https://suman876-ops.github.io/lakshmi-puja/

## Highlights

- **Darshan** — an interactive Three.js golden lotus mandala: extruded petals, bead rings and drifting particles. Drag to rotate, scroll to zoom, with auto-rotate and fullscreen.
- **Cinema** — a 26-second film rendered frame by frame from the artwork, with drifting embers, a warm grade and Assamese captions, carrying its own ambient soundtrack.
- **Music** — a generative score on the Web Audio API: a tanpura drone, a bansuri line in Raga Bhairavi and temple bells on their own schedule. It never repeats. One-shot bell, conch and ululation sounds sit alongside.
- **Puja Vidhi** — the eight ritual steps as a scroll-animated timeline.
- **Mantras** — four mantras in Devanagari with transliteration, meaning and audio.
- **Gallery**, a dhyana timer that rings a bell, a clickable diya, a blessing-card generator that exports a PNG, and an FAQ.

## Structure

```
index.html              the whole site — HTML, CSS, JS and every image embedded
media/puja-video.mp4    the 26-second film with its soundtrack
```

Everything but the video is embedded in `index.html`, so the page makes no image requests. The video streams as a normal file so the page paints quickly.

## Author

Suman Mahata

## License

MIT
