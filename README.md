# Rosé & Gold Checkers

A 3D checkers game for the browser, played on a board of golden and pink squares.
Pearl pieces face Onyx pieces; play a friend on one screen or take on the computer.

## Play

Open `index.html` in any modern browser. There is no build step and no dependencies
beyond the Google Fonts stylesheet, which falls back to system fonts when offline.

To serve it locally instead:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Features

- Made for a phone lying flat between two players: Pearl sits at the bottom edge and
  Onyx at the top. The board fills the screen, each player has a status bar at their own
  end (the far one turned to face them), and when the turn passes the view swings around
  the table so the board leans toward whoever is to move.
- Full screen: phones drop the browser toolbars on the first touch, lock to portrait and
  keep the screen awake. Adding the page to the home screen launches it full screen too.
- Sound effects for moves, captures, crownings and wins, synthesised with Web Audio.
- Tilted 3D board built with CSS transforms: thick edges, stacked-disc pieces, a soft
  ground shadow, and a gentle parallax as the mouse moves across it.
- Full American checkers rules: diagonal moves on the pink squares, mandatory captures,
  chained multi-jumps, and kings that move in every direction. The game ends when a side
  has no legal move, or is drawn after forty moves without a capture or a soldier advancing.
- Two players by default; a computer opponent with three strengths, driven by an
  alpha-beta search, is available from the menu.
- A menu button in each status bar opens the settings: opponent, strength, board tilt,
  sound, whether the board turns to each player, full screen, undo (also Ctrl/Cmd+Z) and
  new game. Settings are remembered on the device.

## Deployment

The site is published with GitHub Pages at https://checkers.clayson.io.
Every push to the default branch runs `.github/workflows/pages.yml`, which enables Pages
on first run and deploys the repository root.

One-time setup for the domain:

1. DNS: add a CNAME record for `checkers` pointing at `claysonio.github.io`.
2. GitHub: Settings → Pages → Custom domain, enter `checkers.clayson.io`, save, and tick
   "Enforce HTTPS" once the certificate has been issued.

## Files

- `index.html` contains the whole app: markup, styles, game rules, sounds, and the AI.
- `manifest.webmanifest` and `icon.svg` let the game be installed to a home screen.
