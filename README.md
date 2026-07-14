# FREERUN

A single-file third-person parkour game in a hand-drawn ink-and-paper city.
You play an ink-drawn runner — chibi proportions, long black box braids, red
sash, gloves and shoe stripes — with full procedural animation for running,
vaulting, wall-run leans, climbing, mantling, sliding and landing rolls.
Everything — engine glue, world generation, movement, audio, HUD, and an
embedded copy of three.js — lives in [`index.html`](index.html). No build
step, no server, no network: download the file, open it in a browser, run.

![genre] free-roam rooftop district · momentum parkour · time trials · collectibles

## Play

Open `index.html` in any modern desktop browser (Chrome, Edge, Firefox,
Safari) and click **RUN**. The game uses pointer lock, so click the canvas to
recapture the mouse after pausing.

## Controls

| Input | Action |
| --- | --- |
| `WASD` | move (camera-relative) |
| mouse | orbit the camera |
| `Shift` (hold) | sprint — speed builds up over a second |
| `Space` | jump / wall-jump / kick off a climb / mantle |
| `C` or `Ctrl` | slide at speed · **timed roll** as you land to negate fall damage |
| push into a wall (airborne) | wall-climb (drains grip) |
| jump alongside a wall | wall-run (Space to kick off) |
| `E` | start a time trial at a red pad |
| `R` | back to checkpoint / restart trial |
| `Esc` | pause |

## Systems

- **Momentum movement** — sprint builds speed; chaining vaults, wall-runs,
  wall-jumps, mantles, slides and rolls without stopping fills the red
  **flow** meter, which makes you faster. Stop moving and it drains.
- **Grip meter** — wall-climbs, wall-runs and ledge hangs share a stamina
  pool that regenerates on the ground.
- **Fall damage** — hard landings splatter ink on the screen and hurt.
  Tap `C` just before impact to roll and keep your momentum instead.
- **Forgiving feel** — coyote time, jump buffering, generous ledge
  detection, auto-vault over low obstacles, capped delta time.
- **Time trials** — three red-ink checkpoint courses (INK RUN, ALLEY CAT,
  SKYLINE) with bronze / silver / gold medals; best times persist in
  `localStorage`.
- **Collectibles** — 10 red pages hidden in hard-to-reach spots.
- **Procedural audio** — Web Audio footsteps that change with the surface,
  wind that rises with height and speed, whooshes on jumps and wall-runs.
- **Third-person camera** — smooth mouse orbit, pulls back with speed and
  flow, banks into wall-runs, landing springs — and never clips through
  walls (exact ray-vs-world clamping with snap-in / ease-out distance).
- **Character animation** — fully procedural: run cycle scaled by speed,
  vault and mantle tucks, wall-run lean with a hand on the wall, climbing
  reaches, ledge-hang dangle, slide lean-back, mid-air somersault rolls,
  plus physics-y braids and scarf that trail, lift in falls and whip on
  turns. An ink-blob shadow keeps the runner grounded visually.

## Notes

three.js r160 (MIT) is embedded as a base64 `data:` URL in the import map so
the file stays fully self-contained.
