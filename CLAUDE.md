# vocab-quiz

## Project Overview
Two standalone static HTML quiz apps — no build system, no package manager, no framework.

- **index.html** — Vocabulary Matcher: loads word/definition pairs from a Google Sheets CSV, user clicks words to match definitions; supports multiple vocab sets via a dropdown (each set = a separate sheet tab)
- **states.html** — US States & Capitals Quiz: interactive D3.js map, user types state names and capitals
- **vocab.md** — source vocabulary word list (16 words, Shakespeare-era)

## Architecture
- Pure vanilla JavaScript embedded in `<script>` tags inside each HTML file
- No separate JS/CSS files — everything is inline in the HTML
- CDN dependencies only: D3.js v7, TopoJSON v3, US Atlas (jsDelivr)
- Google Sheets CSV export URL as the data backend for index.html; multiple sets supported via `VOCAB_SETS` array and `&gid=` tab parameter

## Key Conventions
- No TypeScript, no linting, no formatting config
- CSS uses custom properties (variables) for theming
- Mobile-first responsive design with media queries
- No build step — files are served as-is (GitHub Pages compatible)

## Deployment
Hosted on **GitHub Pages** from the `thatchrisharper/vocab-quiz` repository.
Live URL: https://thatchrisharper.github.io/vocab-quiz/
Remote: https://github.com/thatchrisharper/vocab-quiz.git

Changes pushed to the default branch deploy automatically.

**GitHub account:** Use the `thatchrisharper` account for pushes/PRs (`gh auth switch --user thatchrisharper`). The `arborcompany` account does not have write access.

## Development
Open HTML files directly in browser or use a simple static server:
```
npx serve .
# or
python3 -m http.server
```
