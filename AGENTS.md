# Repository Guidelines

## Project Structure & Module Organization
# Repository Guidelines

## Project Structure & Module Organization
`old/` contains the previous website; consult it for copy and layout cues but avoid editing it directly. Build the refreshed static site at the repository root with top-level pages (`index.html`, `projects/index.html`, `talks/index.html`) and optional shared snippets in `partials/`. Place styles in `css/` (global rules in `base.css`, page-specific sheets named after the page), scripts in `js/` with matching filenames (e.g., `nav.js`), and downloads or images inside `assets/`. Document any new directories in `README.md` so future contributors stay aligned.

## Build, Test, and Development Commands
No build tooling is required—the site ships as plain HTML, CSS, and JavaScript. To preview locally, run `python3 -m http.server 8000` from the repository root and visit `http://localhost:8000`. Use `python3 -m http.server --directory old 8000` if you need to compare against the legacy site. After edits, force-refresh the browser to clear cached assets.

## Coding Style & Naming Conventions
Match the legacy formatting: tabs for indentation, lowercase filenames, and hyphenated CSS classes. Use semantic HTML elements and keep attribute quotes single as in `old/index.html`. JavaScript should expose a single global per file (e.g., `window.siteNav`) and wrap logic in an IIFE to avoid leaking helpers. Capture broader decisions in `docs/notes.md` so front-end conventions remain discoverable.

## Testing Guidelines
Testing is manual. Before committing, open the site in at least two browsers (Safari/Chrome or Firefox/Chrome) and exercise the navigation, project listings, and external links. Resize the viewport to 320px, 768px, and 1200px to confirm layout integrity. Validate HTML with `tidy -qe index.html` (run per page) and record any known issues in `docs/qa.md` so regressions are traceable.

## Commit & Pull Request Guidelines
Use short, imperative commit messages such as `Update projects listing` or `Refine nav styling`. Keep related HTML, CSS, and assets together so diffs stay reviewable. Pull requests should describe the change, note which pages were touched, and include before/after screenshots for visual updates. Reference the legacy snippet you migrated from `old/` when applicable, and list manual checks performed (browsers, screen sizes) so reviewers know what was validated.
