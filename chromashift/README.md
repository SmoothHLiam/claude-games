# CHROMASHIFT

A single-file HTML5 Canvas **arena survivor** with a color-polarity twist.

**Genre:** Top-down arena survival shooter (auto-aim twin-stick-lite).
**Twist:** You are **CYAN** or **MAGENTA**. Your shots only destroy enemies that
*match your current color* — the opposite color is immune to your fire and must be
dodged until you **flip**. The whole game is reading the incoming wave and flipping
your polarity in time. A combo meter rewards staying on a roll (it only breaks when
you take a hit), so holding one color is a pure risk/reward gamble.
**Controls:** Move = `WASD` / Arrows / touch-drag · Flip = `Space` / Click / Tap ·
Pause = `Esc` / `P` · Mute = `M`. Shooting is automatic and auto-aims the nearest
enemy of your color.
**Goal:** Survive escalating waves, build combos, chase a high score. You lose when
your shield reaches zero.

## Run it

It's one self-contained file with **no dependencies and no build step**:

> **Open `index.html` directly in any modern browser** (double-click it, or drag it
> into a browser tab). That's it — no server needed.

## Notes

- 100% procedural: all art is drawn to canvas, all SFX are synthesized with the Web
  Audio API. No external assets, no CDN, nothing to 404.
- High score is kept in memory for the session (no `localStorage`), so it resets on
  reload.
- Colors are paired with distinct **shapes** (cyan = square, magenta = diamond) so the
  polarity reads even for color-vision-deficient players.
- Verified headless (Chromium) for a clean boot, working state machine
  (menu → play → pause → game over), and zero console errors. Audio autoplay,
  touch input, and exact visual feel are best confirmed by opening it yourself.
