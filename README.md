# Kaleidoscope

A **pure CSS** psychedelic kaleidoscope: no JavaScript, no build step. One source image is sliced into triangular wedges, mirrored into six “kites,” and animated with spin and drift.

## Live demo

This is viewable on https://ukslim.github.io/pure-css-kaleidoscope/

## Run locally

Open `index.html` in a modern browser, or serve the folder:

```bash
# Python
python3 -m http.server 8000

# Node (npx)
npx serve .
```

Then visit `http://localhost:8000`.

## Project layout

| File         | Role                                                            |
| ------------ | --------------------------------------------------------------- |
| `index.html` | Markup: viewport, wheel, 6 kites (12 slices).                   |
| `style.css`  | Layout, clip-path wedges, spin/drift animations, CSS variables. |
| `image.png`  | Source image used for the kaleidoscope.                         |

Tuning is done via `:root` variables in `style.css` (`--k-size`, `--spin-speed`, `--drift-speed`, `--image-url`).

## Vibe coded

I am not a CSS expert, amd this was produced largely as an exercise in vibe coding. Exercise as in "practice in order to get better".
A friend had made a similar kaleidescope in V0, but with Javascript writing to a canvas element.

Asking V0 to create a pure CSS version, produced a circle of triangles, selecting the wrong parts of the source image,
wrongly mirrored and rotated. Attempting to fix it, I soon ran out of V0 free tier messages. V0 produced the background image
itself, which I retained.

Moving to Cursor, I wrote a detailed prompt, and attempted to one-shot it. The prompt advised Cursor to use Chrome DevTools to
examine its work, but still it did the wrong thing and claimed success. Attempts to correct it, failed. Attempts to improve the
plan and one-shot again, failed.

Eventual success came from:

- extracting the plan into smaller explicit steps: draw one 60° kite comprising two properly reflected 30° wedges; draw 6 kites
  properly rotated; animate the drift of the source image; rotate the view
- creating an Agent Skill in which it takes a screenshot using Chrome DevTools, then reads individual pixel values using
  ImageMagick. Only with this in its toolkit did the agent reliably recognise when it had not achieved a criteron.

## License

This project is in the **public domain**. See [UNLICENSE](UNLICENSE).
