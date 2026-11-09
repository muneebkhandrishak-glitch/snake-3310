# Snake 3310

A playable Nokia 3310-style Snake game in a single self-contained HTML file. No build step, no dependencies, no network calls — open `index.html` in any browser and play.

## Play

Open `index.html` directly in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Then visit <http://localhost:8000>.

## Controls

| Action | Keys |
| --- | --- |
| Steer | Arrow keys or `W` `A` `S` `D` |
| Start / Pause / Resume | `Space` or `Enter` |
| Pause | `P` |
| Restart | `R` |

**On mobile:** use the on-screen D-pad below the handset, the phone's own soft keys and nav cluster, or swipe directly on the screen.

## How it plays

- **Eat to grow.** Each pellet makes the snake one block longer and adds to your score.
- **Die on wall or self collision.** Hitting the edge of the field or your own body ends the run.
- **Game over screen** shows your score, flags a `NEW RECORD` when you beat your best, and restarts on `START`, `Enter`, or a tap.
- **Speed ramp.** 8 gears, one step every 3 pellets, from 150 ms per move down to 66 ms. The `SPD` bar at the bottom of the screen fills as you climb, so the ramp is visible and not just felt.

## Features

- Classic 3310 look — a green LCD panel with a faint dot-matrix substrate, and every character drawn from a hand-built 5×7 pixel font, so the score, menus and game-over text are blocky LCD glyphs rather than a modern web font.
- Pixel-blocky snake and food. The snake is solid blocks with eyes punched out of the head that follow the direction of travel; the food is a 5×5 pixel pellet that blinks between two frames.
- Score counter — 4-digit zero-padded score top-left, high score top-right, persisted in `localStorage` so it survives a reload.
- Square-wave beeper for eating, level-up and death. It only ever makes sound after you interact, and there is a `SOUND` toggle.
- Auto-pauses if you switch tabs.

## Tech

Plain HTML, CSS and JavaScript in one file. The game renders to a `<canvas>`; the LCD font is a hand-built 5×7 bitmap glyph set. No frameworks, no external assets, no network calls.
