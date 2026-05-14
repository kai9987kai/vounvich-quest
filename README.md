# Voynich Quest 6

Voynich Quest 6 is an offline-first, single-file browser game inspired by the Voynich Manuscript. It turns manuscript analysis ideas into playable canvas puzzles, research instruments, and evidence-based scoring systems.

The current build lives in `index.html` and has no required package install or build step.

## Features

- Standalone HTML/CSS/JavaScript game that can run locally in a browser.
- Canvas-based folio exploration with glyph sampling, structural puzzle solving, scoring, achievements, and relics.
- Research-inspired tools including the palimpsest lens, co-occurrence bridge, Ink Spectrometer, Provenance Timeline, Cipher Model Forge, Hypothesis Engine, XR Vault, and Codex notes.
- Puzzle families for autocorrelation, symbol roles, quire reconstruction, hidden-token discovery, spectrum matching, provenance ordering, and model selection.
- Optional progressive-enhancement probes for browser APIs such as Web Speech, camera access, WebXR, WebGPU, MIDI, and HID.
- Local progress persistence through `localStorage`.
- Accessibility controls for high contrast, reduced motion, keyboard play, live status text, and canvas focus.
- Test hooks for browser automation: `window.render_game_to_text()` and `window.advanceTime(ms)`.

## Running Locally

You can open `index.html` directly in a modern browser.

For a local HTTP server, run:

```powershell
python -m http.server 5173
```

Then open:

```text
http://127.0.0.1:5173/index.html
```

No network access is required for the core game.

## Controls

- `Space`: start the quest
- `Enter`: submit the current answer
- `H`: request a hint
- `N` or `ArrowRight`: next folio
- `P` or `ArrowLeft`: previous folio
- `F`: fullscreen
- `L`: toggle the lens
- `Q`: open Hypotheses
- `S`: open Spectrometer
- `T`: open Timeline
- `M`: open Forge

Most actions are also available through on-screen buttons.

## Project Structure

```text
.
├── index.html       # Standalone game source
├── progress.md      # Development notes and validation history
└── output/          # Browser validation screenshots and captured state
```

The `output/` directory contains generated validation artifacts. Keep useful screenshots when they explain a visual change; otherwise they can be regenerated during testing.

## Development

This project intentionally keeps the game in one file for portability. When changing it:

- Keep the core game offline-first.
- Avoid hard dependencies on external CDNs or services.
- Treat experimental browser APIs as optional enhancements.
- Preserve keyboard access and screen-reader status updates.
- Keep `window.render_game_to_text()` and `window.advanceTime(ms)` working for automated checks.
- Add defensive guards around browser APIs and storage access.

## Verification

At minimum, test these flows in a browser before opening a pull request:

- Start, pause, reset, submit, hint, next folio, and previous folio.
- Canvas interaction and lens pointer tracking.
- Codex, Lab, XR Vault, Hypotheses, Spectrometer, Timeline, and Forge dialogs.
- High contrast and reduced motion toggles.
- Browser console for errors.
- `window.render_game_to_text()` returns valid JSON.
- `window.advanceTime(1000)` advances game state without throwing.

## Research Basis

The game references public research and platform documentation in its in-app source list, including Yale Beinecke's Voynich overview, PLOS ONE analyses, an arXiv topic-modeling paper, MDN browser API documentation, W3C WCAG guidance, and the MediaPipe Hands paper.

## License

No license file is currently included. Add a `LICENSE` file before distributing releases or accepting substantial outside contributions.
