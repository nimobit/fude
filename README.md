# 筆 Fude — Kanji stroke-order board

A local-first web whiteboard to record and replay the stroke order of kanji.
Built for Japanese study: draw a character stroke by stroke, and the app records
the order, coordinates and timing of each stroke, then replays the sequence as an
animation and exports a video or image you can keep on your phone.

## Features

- Canvas with pointer events (mouse, touch, stylus) and smooth, gap-free strokes
- Variable-width brush that reacts to drawing speed (and real pressure on a stylus)
- Faithful animated replay with stroke-order numbers, like a practice manual
- Adjustable replay speed (0.5×–3×)
- Three sheet formats: square with practice grid, A4 portrait, 16:9 whiteboard
- Video export via MediaRecorder: native MP4 where supported, WebM fallback
- On iOS/Android: save straight to the photo gallery via the Web Share API
- Still-image export as PNG or JPG
- Persistent kanji library in localStorage — no backend, data stays on the device
- Library import/export as JSON to move characters between devices
- Light / dark theme, following the system preference
- Single HTML file, zero dependencies, no build step, fully offline-capable

## Run locally

Serve `index.html` with any static server:

```bash
python -m http.server 8480
```

On an iPad with no network, serve it with the WorldWideWeb app (The Iconfactory)
and open `localhost` in Safari.

## Deploy with Docker

```bash
docker compose up -d
```

The app is served on `http://<host>:8480`. For external access without opening
ports, put a Cloudflare Tunnel in front, pointing to `http://localhost:8480`.

## Privacy

Everything stays on the device: strokes, library and theme live in the browser's
local storage and are never sent anywhere. The app makes no external requests and
works offline.

## License

MIT — see [LICENSE](LICENSE).
