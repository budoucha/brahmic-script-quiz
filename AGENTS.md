# Repository Guidelines

## Project Structure & Module Organization

This is a dependency-free, static browser quiz. The complete application lives in `index.html`:

- The document structure and accessible UI are in `<body>`.
- Styles are in the embedded `<style>` block.
- Quiz data and behavior are in the embedded `<script>` block.

`README.md` describes the quiz and GitHub Pages deployment. There are currently no separate source, asset, or test directories. Keep related changes close to the existing sections in `index.html`.

## Build, Test, and Development Commands

No package manager, build step, or external library is required. Open `index.html` directly in a current browser for routine development.

For a local server when testing browser behavior, run:

```powershell
python -m http.server 8000
```

Then visit `http://127.0.0.1:8000/`. Test keyboard controls (`1`–`6`, then `N`), reset behavior, feedback, and desktop/mobile layouts.

## Coding Style & Naming Conventions

Use two-space indentation, lowercase HTML element names, and single quotes in JavaScript to match the existing file. Prefer `const`; use `let` only for state that changes. Use camelCase for JavaScript variables and functions (`newQuestion`, `currentText`), kebab-case for CSS classes (`compare-card`), and descriptive IDs for UI elements (`wrong-sample`). Keep CSS custom properties in `:root` and extend the existing color and spacing system instead of adding one-off inline styles.

All visible quiz text is Japanese. Preserve correct Unicode text for each Brahmic script; do not replace samples with escaped character sequences. Maintain semantic elements, `aria-*` attributes, and visible keyboard hints when modifying the UI.

## Testing Guidelines

There is no automated test framework or coverage target yet. Manually test each affected flow in a browser before committing. When changing quiz data, confirm every added item has a label, five usable sample texts, and a meaningful distinguishing note. Check that randomly generated answer choices contain one correct item and five distinct incorrect items.

## Commit & Pull Request Guidelines

Recent history uses short, focused messages, including Japanese descriptions such as `文言修正` and concise English imperatives such as `Add project README`. Follow that style: one coherent change per commit and an imperative summary (for example, `Improve Sinhala comparison hint`).

Pull requests should explain the user-visible change, link the relevant issue when applicable, and include screenshots for layout or visual changes. State how you tested the quiz and keep unrelated reformatting out of the diff.
