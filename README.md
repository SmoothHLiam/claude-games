# Claude Games — Arcade

A growing collection of small, **complete**, single-file browser games. Every
game is built to the same contract (see [`GAME_AGENT.md`](GAME_AGENT.md)): it
boots into a real **main menu**, has a working **pause menu**, ships synthesized
**sound effects**, and carries **at least one signature twist**. No installs, no
external assets, no build step.

## Play

Open **`index.html`** at the repo root for the arcade hub, then pick a game —
or jump straight into any game's folder.

| Game | Genre | The twist |
|---|---|---|
| [**FLIPSIDE**](flipside/index.html) | One-button gravity runner | **Graze combo** — the *later* you flip before a spike sweeps past, the bigger the score and the higher your multiplier climbs. Safe play barely scores. |
| [**CHROMASHIFT**](chromashift/index.html) | Top-down arena survivor | **Color polarity** — you're cyan or magenta and your shots only destroy enemies that match your current color. Flip in time or dodge. |
| [**GRAVLASSO**](gravlasso/index.html) | Asteroid arena | **No guns** — grab asteroids with a gravity lasso and fling them into enemies and each other. |
| [**GEMINI**](gemini/index.html) | Mirror snake | **Mirror control** — steer two snakes with one set of controls; Left/Right are flipped, so the amber twin reflects the cyan one across the seam. Feed both, crash neither. |

Each game is a single self-contained `index.html` — **open it directly in any
modern browser** (double-click, or drag it into a tab). No server needed.

## Structure

```
index.html        # arcade hub (links to every game)
GAME_AGENT.md     # the build contract every game follows
flipside/         # FLIPSIDE   — gravity-flip runner
chromashift/      # CHROMASHIFT — color-polarity arena survivor
gravlasso/        # GRAVLASSO  — gravity-lasso asteroid arena
gemini/           # GEMINI     — mirror twin-snake
```

## Notes

- **100% procedural.** All art is drawn to canvas; all SFX are synthesized with
  the Web Audio API. Nothing to download, nothing to 404.
- High scores are kept in memory for the session (no `localStorage`), so they
  reset on reload — safe for sandboxed/artifact environments.
- Games are verified headless (Chromium) for a clean boot, a working state
  machine (menu → play → pause → game over), and zero console errors. Exact
  visual feel, audio autoplay, and touch input are best confirmed by opening
  them yourself.
