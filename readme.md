# A Field Guide to Python

A single-page Python tutorial, presented as a five-part "field guide," with a live, in-browser
Python compiler embedded at the bottom so visitors can run real code without installing anything.

## What's here

- **`index.html`** &mdash; the entire page: hero, five numbered "specimens" (Variables, Conditionals,
  Loops, Functions, Lists), a live coding lab, and a further-reading section.
- **`styles.css`** &mdash; all styling. No CSS framework; plain CSS with custom properties.
- **`script.js`** &mdash; small interactivity: mobile nav toggle, scroll-reveal for each specimen,
  copy-to-clipboard buttons on code samples, and syntax highlighting via highlight.js.
- **`netlify.toml`** &mdash; publishes the project root as a static site and sets a few baseline
  security headers.

## Key technologies

- Plain HTML/CSS/JS &mdash; no build step, no framework.
- [highlight.js](https://highlightjs.org/) (via CDN) for Python syntax highlighting in the code samples.
- [OneCompiler](https://onecompiler.com)'s embeddable Python compiler (via `<iframe>`) for the live lab,
  so readers can run and edit Python directly on the page.
- Google Fonts: Fraunces (headings) and IBM Plex Mono (body/code).

## Running locally

This is a static site with no dependencies to install. Either:

- Open `index.html` directly in a browser, or
- Serve it with the Netlify CLI for full local parity with production:

  ```bash
  netlify dev
  ```

## Deploying

The site deploys as-is on Netlify: no build command is needed, and `netlify.toml` publishes the
project root.
