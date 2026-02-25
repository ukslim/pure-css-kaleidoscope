# Kaleidoscope

A **pure CSS** psychedelic kaleidoscope: no JavaScript, no build step. One source image is sliced into triangular wedges, mirrored into six “kites,” and animated with spin and drift.

## Live demo

When this repo is published with [GitHub Pages](https://pages.github.com/), the demo is available at:

`https://<your-username>.github.io/kaleidescope/`

(Enable it under **Settings → Pages → Source**: deploy from the default branch, root.)

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

| File        | Role |
|------------|------|
| `index.html` | Markup: viewport, wheel, 6 kites (12 slices). |
| `style.css`  | Layout, clip-path wedges, spin/drift animations, CSS variables. |
| `image.png`  | Source image used for the kaleidoscope. |

Tuning is done via `:root` variables in `style.css` (`--k-size`, `--spin-speed`, `--drift-speed`, `--image-url`).

## License

This project is in the **public domain**. See [UNLICENSE](UNLICENSE).
