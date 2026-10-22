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

- Tilted 3D board built with CSS transforms: thick edges, stacked-disc pieces, a soft
  ground shadow, and a gentle parallax as the mouse moves across it. A slider sets the
  tilt from flat to steep.
- Full American checkers rules: diagonal moves on the pink squares, mandatory captures,
  chained multi-jumps, and kings that move in every direction. The game ends when a side
  has no legal move, or is drawn after forty moves without a capture or a soldier advancing.
- Computer opponent with three strengths, driven by an alpha-beta search.
- Two-player mode, undo (also Ctrl/Cmd+Z), legal-move highlights, last-move tinting, and
  animated captures and crownings.
- Responsive layout that stacks the panel beneath the board on phones.

## Deployment

The site is published with GitHub Pages at https://checkers.clayson.io.
Every push to the default branch runs `.github/workflows/pages.yml`, which enables Pages
on first run, sets the custom domain, and deploys the repository root. DNS for
`checkers.clayson.io` is a CNAME record pointing at `claysonio.github.io`.

## Files

- `index.html` contains the whole app: markup, styles, game rules, and the AI.
