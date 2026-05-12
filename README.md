# Puyo Puyo Demo

Single-file HTML/JS demo of the Puyo Puyo falling-block puzzle game.
Same terminal-green aesthetic as [x1-tetris](https://github.com/jacklevin74/x1-tetris).

## Play

Open `index.html` in a browser, or any static host:

```bash
python3 -m http.server -d . 8000
# → http://localhost:8000
```

## Controls

| Key | Action |
|---|---|
| ← → | Move pair |
| ↑ | Rotate (with wall-kicks) |
| ↓ | Soft drop (+1 point per cell) |
| Space | Hard drop (+2 points per cell) |
| R | Restart |

## Mechanics

- 6×12 board, 5 puyo colors.
- Pairs spawn as a pivot + follower; 4 rotations supported.
- On lock, gravity compacts each column, then a flood-fill finds
  same-color groups of 4+ and pops them.
- After a pop, gravity reapplies and the chain detection runs again —
  recursive cascades count as one combo with an exponential score
  multiplier (Puyo chain bonus table).
- Game over when the spawn cell is occupied.

## Roadmap (towards PPT2-style PVP)

- Side-by-side dual board
- Garbage exchange (nuisance puyos sent on chain pops)
- Mode switch — Tetris or Puyo per side, hybrid play
