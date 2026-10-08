# Fate's Calling

An offline-ready, Baldur's Gate-inspired classroom D20 roller. It randomly selects each student number once per round, with a 3D animated die, adjustable materials, generated roll audio, Theater Mode, and a persistent developer panel.

Live site: https://reiiigns.github.io/fates-calling/

## Features

- Random, cryptographically backed selection without repeats until the pool resets
- Canvas-rendered 3D D20 with gemstone and metallic materials
- Touch, keyboard, and iPad-responsive controls
- Generated in-browser roll and landing sounds; no external audio assets
- Local developer settings persistence plus JSON export/import
- Offline support after the initial online load

## Install on iPad

1. Open https://reiiigns.github.io/fates-calling/ in Safari.
2. Tap **Share**.
3. Choose **Add to Home Screen**.
4. Tap **Add**.
5. Open Fate's Calling from the Home Screen.
6. After the first online launch completes, test it with Wi-Fi disabled.

The app is configured for standalone display. iPad Safari does not expose normal web fullscreen consistently, so **Fullscreen** uses Theater Mode as its reliable fallback.

## Developer panel

Tap **DEV** to adjust die material, timing, audio, sizing, copy, colors, and font. Changes save in the browser. Use **Export settings** to save a JSON backup or **Import settings** to restore one.

## Updating

Edit the static files in the repository root, commit, and push to `main`. GitHub Pages publishes from that branch/root. The service worker uses network-first caching: an online reload refreshes app resources and records them for the next offline launch. If changing the precached file list, update `ASSETS` in `sw.js` and bump its `CACHE` version.

## Troubleshooting

- **No sound:** iPad/browser audio starts only after a user interaction. Roll once with Sound enabled.
- **Old version appears:** reload while online, then close and reopen the Home Screen app.
- **Offline does not work:** open the app online once and wait for it to finish loading before testing offline.
