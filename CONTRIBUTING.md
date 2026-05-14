# Contributing to Voynich Quest 6

## Before You Start

Check the existing project notes in `progress.md` and review the current behavior in `index.html`. For large gameplay, architecture, accessibility, or visual changes, open an issue or discussion first so the intended direction is clear.

## Local Setup

No install step is required. Open `index.html` directly, or serve the folder locally:

```powershell
python -m http.server 5173
```

Then visit `http://127.0.0.1:5173/index.html`.

## Development Guidelines

- Keep the game usable as a standalone offline-first HTML file.
- Do not add required external network services for core gameplay.
- Keep optional APIs behind feature detection and user-triggered controls.
- Preserve the canvas dimensions and responsive layout unless the change is intentional and tested.
- Keep keyboard controls, visible focus, live status text, high contrast, and reduced motion support working.
- Avoid storing sensitive data. Local notes and state should remain local browser data.
- Keep generated validation files in `output/` only when they are useful for reviewing the change.
- Prefer clear, small changes over broad rewrites.

## Code Style

- Use plain JavaScript, CSS, and HTML that match the existing single-file style.
- Keep names descriptive and consistent with existing game systems.
- Add comments only where they clarify non-obvious logic.
- Guard access to browser APIs such as camera, speech, WebXR, WebGPU, MIDI, HID, fullscreen, and `localStorage`.
- Keep deterministic test hooks intact:
  - `window.render_game_to_text()`
  - `window.advanceTime(ms)`

## Testing Checklist

Before submitting a change, verify:

- The game starts, pauses, resets, and reaches game-over state cleanly.
- Submitting correct and incorrect answers behaves as expected.
- Canvas interactions work with mouse, pointer, and keyboard focus.
- Folio navigation does not break puzzle state.
- Codex, Lab, XR Vault, Hypotheses, Spectrometer, Timeline, and Forge dialogs open and close.
- Optional API probes fail gracefully when unsupported or denied.
- High contrast and reduced motion modes remain usable.
- Browser console shows no unexpected errors.
- `window.render_game_to_text()` returns valid JSON.
- `window.advanceTime(1000)` runs without throwing.

## Pull Requests

Pull requests should include:

- A short summary of the user-facing change.
- Any relevant screenshots for visual or canvas changes.
- Notes about manual testing performed.
- Any known limitations or follow-up work.

Keep pull requests focused. Separate unrelated gameplay, visual, documentation, and tooling changes when practical.

## Bug Reports

Good bug reports include:

- Browser and operating system.
- Steps to reproduce.
- Expected result.
- Actual result.
- Console errors, if any.
- Screenshot or `window.render_game_to_text()` output when useful.

## Feature Requests

Feature requests should explain the player experience, the research or gameplay idea behind it, and how it fits the offline-first single-file project model.
