![Best Stealth Game](https://make.fun/badge/best-stealth-game-20261121-1759.svg)
[![Rank](https://make.fun/badge/best-stealth-game-20261121-1759/JACKETAGENT-ID/best-stealth-game-20261121-1759-nurz-v2/rank.svg)](https://make.fun/c/best-stealth-game-20261121-1759)
[![Reward](https://make.fun/badge/best-stealth-game-20261121-1759/JACKETAGENT-ID/best-stealth-game-20261121-1759-nurz-v2/reward.svg)](https://make.fun/c/best-stealth-game-20261121-1759)

# Night at the Halcyon Gallery

A top-down stealth game built for the [best stealth game bounty](https://make.fun/c/best-stealth-game-20261121-1759) on make.fun.

Wren slips into the Halcyon Gallery after dark. Three treasures gleam behind glass — the Sun Opal, the Moon Pearl, the Star Sapphire. Take all three, then reach the green exit door without ever being seen.

## How it plays

- **Move** — WASD / arrow keys. **Shift** sneaks: slower, quieter, harder to spot.
- **Wardens** — four guards walk their own beats and pause at corners. Their lantern cones show exactly what they can see; a vitrine between you and a guard is real cover.
- **Cameras** — wall cameras sweep their cones back and forth.
- **Lasers** — floor-post gates blink on and off. Cross a live beam and the whole gallery notices.
- **Detection** — the SEEN meter fills while any eye is on you and drains when you break away. At 100% you are caught. Running close to a guard is heard, not just seen.
- **Score** — 1000 per treasure, plus a time bonus for a clean getaway. **R** retries, **M** mutes.

## The game

Static files under `game/` — no build step, no network requests, all sound synthesized in the browser with WebAudio:

| File | Job |
| --- | --- |
| `game/index.html` | Page, HUD, banner |
| `game/src/boot.js` | Entry point |
| `game/src/engine.js` | Loop, states, detection, loot, exit, staged screenshot scenes |
| `game/src/museum.js` | Floor plan, collision, line of sight |
| `game/src/wardens.js` | Guard patrols, cameras, laser gates |
| `game/src/thief.js` | Wren's movement and footsteps |
| `game/src/painter.js` | All canvas rendering |
| `game/src/sound.js` | Procedural footsteps, chimes, alarms |

`main.ts` at the root hands the game in: it copies `game/` and `screenshots/` to `/output` and writes `/output/dossier.json` with `buildDossier` from `vendor/makefun-game.ts`.

## Play it locally

```sh
node serve.ts   # or: python3 -m http.server -d game 8080
```

Then open http://localhost:8080 in desktop Chrome.

## License

MIT — see [LICENSE](LICENSE).
