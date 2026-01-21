<!-- copilot-instructions.md: Guidance for AI coding agents working on this repo -->
# Copilot / AI Agent Instructions

Purpose
- Short and focused guidance to help an AI agent be productive on this small static site.

Big picture
- This is a simple static marketing/landing page: primary files are `index.html` and `style.css` at the repository root.
- Layout relies on Bootstrap (CDN) plus custom CSS in `style.css`. Visual assets (images) are referenced by filename in the project root (e.g. `ipadair.png`, `iphones.jpg`).

Where to start
- Open and edit: `index.html` and `style.css` to make layout or visual changes.
- To preview locally, serve the folder as static files and open `index.html` in a browser. Example quick server (if available):
- Python: `python -m http.server 8000` from the project root and browse `http://localhost:8000`.

Key patterns & conventions (project-specific)
- Class naming: UI sections and cards use numbered names (e.g. `.sectioniphone`, `.sectiongift`, `.article1`..`.article6`). Keep these names when making incremental changes.
- Buttons: `.btn1`, `.btn2`, `.btn3`, `.btn4` are styled in `style.css`. Update sizes/colors here rather than replacing HTML unless adjusting semantics.
- Images are referenced by filename (no subfolders). If adding assets, place them in the project root and reference by the same filename, or update `index.html` paths.
- Fixed-layout approach: many styles use fixed pixel widths/heights (e.g. `width: 1920px;`, `height: 692px;`). Be cautious: changes that assume responsiveness may break intended pixel-perfect layouts.

Files to inspect for examples
- `index.html` — overall structure and Bootstrap grid usage (container-fluid, row, col-*).
- `style.css` — custom visual rules (background-image usage, `.article*` classes, `.btn*` classes).

Typical agent tasks and safe behaviours
- Small visual tweaks: modify CSS rules (colors, paddings, background-image) and verify in browser.
- Responsive improvements: prefer adding media queries at the bottom of `style.css` and avoid renaming classes unless requested.
- Images: when updating an image reference, ensure the file exists in the project root and update both CSS `background-image` urls and any `<img src>` usages.
- Avoid large refactors: this repo is a simple static page — do not introduce build tools, transpilers, or package managers without explicit instruction.

Examples (copy-paste edits)
- Change hero background: edit `.sectioniphone { background-image: url('iphones.jpg'); }` in `style.css`.
- Make small responsive rule (add at end of `style.css`):
  ```css
  @media (max-width: 768px) {
    .packarticle { width: 100%; }
    .ipadair { width: 80%; margin-left: auto; margin-right: auto; }
  }
  ```

What not to do
- Do not add or assume a build/test system (there's none present).
- Do not move assets to a different directory without updating all references in both HTML and CSS.
- Avoid renaming many numbered classes in a single change — it increases risk of visual regressions.

# Copilot / AI Agent Instructions

Purpose
- Short, focused guidance to help an AI agent be productive on this small static landing site.

Big picture
- This is a static marketing page: the primary files are `index.html` and `style.css` at the repo root.
- Layout uses Bootstrap (CDN) + custom CSS. Images live in the project root and are referenced by filename (e.g. `ipadair.png`, `iphones.jpg`).

Where to start
- Edit `index.html` and `style.css` for layout or styling changes.
- Quick local preview: run `python -m http.server 8000` in the project root and open `http://localhost:8000`.

Project-specific conventions
- Class naming: numbered section/article classes are authoritative — e.g. `.sectioniphone`, `.sectiongift`, `.packarticle`, `.article1`..`.article6`.
- Buttons: use the existing button classes `.btn1`, `.btn2`, `.btn3`, `.btn4` for consistent styles.
- Images: keep image files in the repo root; update both `<img src>` and CSS `background-image` URLs when renaming.
- Fixed-layout: many rules use fixed pixel widths/heights (e.g. `width: 1920px`). Assume pixel‑perfect layout; add responsiveness only via targeted media queries.

Common tasks & examples
- Change hero background: update `.sectioniphone { background-image: url('iphones.jpg'); }` in `style.css`.
- Add mobile rules: append a media query at the end of `style.css` (do not rename classes):
  ```css
  @media (max-width: 768px) {
    .packarticle { width: 100%; }
    .ipadair { width: 80%; margin: 0 auto; }
  }
  ```
- Prefer CSS-only tweaks for visuals; change HTML structure only when necessary for semantics or content.

Files to inspect
- `index.html` — Bootstrap grid usage and the HTML structure for each `.article*` block.
- `style.css` — where background images, fixed sizes, and `.btn*` styles live.

Do not
- Add build tools, package managers, or test frameworks without approval.
- Move image assets to new folders unless you update all references.
- Renaming many numbered classes in one change — it causes visual regressions.

Commit guidance
- Keep commits small and focused. Example messages:
  - `css: tweak .btn2 border color`
  - `fix: correct background-image path for .article1`

If uncertain
- Ask the repo owner before structural changes.

Please review — tell me any missing details or examples to add.
