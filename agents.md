# AGENTS.md

## What this project is

A single static HTML page teaching Python basics ("A Field Guide to Python"), with an embedded
third-party online compiler so visitors can run Python in-browser. There is no backend, no build
step, and no database &mdash; the whole project is three files at the repo root plus config.

## Architecture

- `index.html` &mdash; all markup and content, in document order: header/nav, hero, intro paragraph,
  five `.specimen` articles (one per Python concept), the live lab (`#lab`, containing the OneCompiler
  `<iframe>`), a further-reading grid, and the footer.
- `styles.css` &mdash; single stylesheet, organized with section comments matching the HTML sections
  top to bottom. Uses CSS custom properties (defined in `:root`) for the color palette and fonts;
  change the palette by editing those variables rather than hunting for hex codes throughout the file.
- `script.js` &mdash; vanilla JS, no dependencies: mobile nav toggle, an `IntersectionObserver` that
  adds `.is-visible` to `[data-reveal]` elements as they scroll into view, clipboard copy buttons on
  code blocks, and a call into `hljs` (loaded via CDN in `index.html`) for syntax highlighting.
- `netlify.toml` &mdash; `publish = "."` since this is a static site with no build output directory.

## Conventions

- No framework, no bundler, no package.json. Keep it that way unless the scope of the project
  actually grows to need one &mdash; this was intentionally built as a single self-contained page.
- Fonts and the highlight.js library are loaded from CDNs (Google Fonts, cdnjs) directly in
  `index.html`'s `<head>`; there's no local asset pipeline.
- Each of the five teaching sections is a `.specimen` article with a consistent internal structure
  (number, heading + Latin-style tag, prose, a `.code-block` with a copy button, a `.field-note`
  callout). Follow that structure when adding a sixth specimen.
- The live compiler is a plain `<iframe>` pointed at `https://onecompiler.com/embed/python`
  &mdash; no API key or account is involved. If swapping providers, keep it a no-auth embeddable
  widget so the page stays fully static.

## Non-obvious decisions

- Body copy uses a monospace font (IBM Plex Mono) throughout, not just in code samples &mdash; a
  deliberate aesthetic choice ("field guide meets terminal"), not an oversight.
- There is no PLAN.md: this project was scoped and built as a single complete deliverable rather
  than staged across milestones.
