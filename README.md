# DeFormer

Listening demos for **DeFormer**, a music source separation system that separates
beyond the standard four stems.

**Demo page:** https://deformerpaper-dev.github.io/DeFormer/

Each example is a 4-second window drawn from the evaluation split. For every stem
present in the window the page plays the reference alongside the output of five
systems, with the cSDR and uSDR values reported in the paper.

Examples are ordered by mean cSDR, averaged across every stem and all five systems,
best first. Each example is identified by a content hash (`example_f0fdf9b7`), not a
sequence number, so the identifier itself carries no ranking. Audio is compressed to
mp3 320 kbps CBR so the page stays light to load on GitHub Pages.

## Layout

| Path | What it is |
| --- | --- |
| `index.html` | The demo page. All data is inlined — no build step, no network fetches. |
| `audio/` | 1,245 mp3 clips (mixtures, references, and per-system estimates). |
| `examples.json` | The same example metadata as a standalone file, for convenience. |
| `.nojekyll` | Disables Jekyll processing on GitHub Pages. |

## Running locally

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

All asset references are relative, so the page works both from a local directory
and from the project subpath on GitHub Pages.
