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
| [**AEGIS**](aegis/index.html) | Bullet-parry arena | **No gun** — your rotating shield is your only weapon. Parry incoming bullets to fire them back into the turrets that shot them; chain parries to charge an AEGIS Burst that reflects every bullet at once. |
| [**TEMPO**](tempo/index.html) | Time-bending arena shooter | **Time moves only when you do** — enemies, their bullets, and spawns all run at the speed *you* move. Stand still and the world nearly freezes; your own shots always fly at full speed. Freeze time, aim, fire, then dance through the gaps. Clear 12 waves to win. |
| [**ENCORE**](encore/index.html) | Echo / replay arena shooter | **Every life replays beside you** — the instant you die, your whole run is recorded and returns from the next take on as an intangible *echo* that moves and fires exactly as you did. Enemies only chase the live you, so your echoes pour uninterrupted fire into the CORE. Stack enough past selves to burst it in one take before your 7 takes run out. |
| [**EMBER**](ember/index.html) | Brick-breaker (Breakout) | **Keep the ball hot** — breaking bricks and rallying off the paddle add heat; heat decays over time. A *cold* ball just clinks off bricks without breaking them; a *molten* ball pierces straight through whole rows. Chain bricks and rally to stay lethal. Clear all 5 levels. |
| [**LUMEN**](lumen/index.html) | Top-down survival in the dark | **Light is life** — a single meter is your sight, your ammo, *and* your health. It drains every second and every bolt you fire spends it; killing shades drops *motes* that refuel you. Keep feeding the light that keeps the dark out, or it goes out for good. |

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
aegis/            # AEGIS      — bullet-parry / shield-reflect arena
tempo/            # TEMPO      — time-moves-when-you-move arena shooter
encore/           # ENCORE     — echo / replay "fight beside your past lives" arena
ember/            # EMBER      — molten breakout / brick-breaker with a heat twist
lumen/            # LUMEN      — light-is-life survival in the dark
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
