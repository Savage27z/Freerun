# FREERUN

A single-file first-person parkour game in a hand-drawn ink-and-paper city.
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
| `WASD` | move |
| `Shift` (hold) | sprint — speed builds up over a second |
| `Space` | jump / wall-jump / kick off a climb / mantle |
| `C` or `Ctrl` | slide at speed · **timed roll** as you land to negate fall damage |
| hold `W` into a wall | wall-climb (drains grip) |
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
- **Camera feel** — FOV widens with speed, the camera banks into wall-runs,
  landing springs, hand-drawn boil on the HUD.

## Notes

three.js r160 (MIT) is embedded as a base64 `data:` URL in the import map so
the file stays fully self-contained.
