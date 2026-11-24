# Padel med Magnus

A padel doubles game in the browser. You and your partner Magnus play the rivals on a court at night. The first team to win 4 games takes the match. Magnus holds the back-left corner, mostly.

**Play:** https://jbacim.github.io/padel/

## How to play

| | |
|---|---|
| **Move** | Drag anywhere on the screen. Your player follows your thumb (arrow keys or WASD on desktop). |
| **Hit** | The racket swings by itself. Hit the ball at the edge of your reach ring to angle the shot. |
| **Smash** | Get under a lob before it bounces. |
| **Glass** | The ball can come off the walls after it bounces. Keep chasing it. |
| **Serve** | Tap the screen, or press Space/Enter. |

### Power-ups

| Chip | Effect |
|---|---|
| ILD | Two rocket shots |
| MAG | Magnus wakes up |
| SLOMO | Ball in slow motion |
| STOR | Giant racket |
| USYNLIG | The rivals lose sight of the ball |
| ×2 | Next point counts double |

## Install as an app

The game is a Progressive Web App. You can install it to your home screen and play it full-screen and offline.

- **Chrome / Edge / Android:** the game asks whether you want to install it. You can also install it from the ⚙ settings menu. The menu also has a switch to turn the prompt off.
- **iPhone / iPad (Safari):** tap **Share**, then **Add to Home Screen**.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole game: canvas rendering, physics, AI, sound, UI |
| `manifest.webmanifest` | App name, icons, colours and display mode |
| `sw.js` | Service worker that caches the game for offline play |
| `icons/` | App icons (192, 512, Apple touch) |

## Development

The game needs no build step. Serve the folder over HTTP to test it locally:

```sh
python -m http.server 8000
# open http://localhost:8000
```

Installing and offline play only work over `https://` or `localhost`. They don't work from `file://`.

**When you release a change,** bump `CACHE` in `sw.js` (for example `padel-v2` → `padel-v3`). Otherwise installed copies keep serving the old version.

Deployed with GitHub Pages from the `main` branch.
