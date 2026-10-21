# Repository instructions

## Project shape

Orbit is a self-contained browser quiz in `index.html`. The document contains the markup, all CSS, the question data, and the quiz state/rendering logic in one file; it uses no framework, external assets, dependencies, or server-side code. Keep the quiz usable by opening that file directly in a browser.

The stylesheet owns the visual system through CSS custom properties in `:root`, with dark-theme overrides under `prefers-color-scheme: dark`. Responsive layout and reduced-motion behavior are also CSS media queries. The inline script defines the ten question records, caches DOM references, and manages answer selection, progress, scoring, results, and replay.

## Behavior and UI conventions

- Keep question records aligned with the quiz flow: each has a prompt, four answer strings, a zero-based `correct` index, and a short explanatory `fact`. The progress track and result score use the question-array length.
- Render answer choices as native buttons. Preserve keyboard focus movement between answers, the next action, and the next question/results heading.
- Keep progress exposed through the progress bar's ARIA values and announce answer feedback through the status region. Treat decorative marks as hidden from assistive technology.
- Use the existing theme variables for colors so updates work in both color schemes. Any new animation must be disabled or made static under `prefers-reduced-motion`.
- Keep content self-contained and offline-capable; do not add a build step or runtime dependency for ordinary quiz changes.

## Validation

There are no configured build, test, or lint commands. Open `index.html` directly in a browser and smoke-test the affected quiz path. For quiz logic or interaction changes, check both correct and incorrect answers, score and progress updates, completion/results, replay, and keyboard-only operation. Check both color schemes and reduced motion when changing presentation or animation.
