# AncestryTools

AncestryTools is a small collection of privacy-first, browser-based genealogy utilities. Each tool is intentionally lightweight, dependency-free and runs entirely in the visitor's browser — nothing is uploaded, logged or transmitted off the user's machine.

## Key principles

- **Privacy-first**: all processing happens locally in the browser. GEDCOM files and any derived results never leave the user's PC unless the user explicitly saves or shares them.
- **Static & simple**: the project is designed to be served as a static site (for example, via GitHub Pages), keeping hosting and maintenance trivial.
- **Extensible**: tools are modular and may be added or refactored into separate CSS/JS files as the project grows.

## Included tools

- **Timeline** — GEDCOM lifespan visualiser (`timeline.html`)
  - Interactive SVG timeline of lifespans parsed from a GEDCOM file
  - Decade histogram (10-year buckets) showing average people alive per decade
  - Historical markers (Scandinavian events by default)
  - Filters for year range, name substring and birth place substring
  - Local file input only — GEDCOM files are read in the browser and not uploaded anywhere

## Planned tools

- **Family Tree Export** — export subsets to simple CSV/JSON for local analysis (privacy preserved)
- **Overlap Matrix** — visualise temporal overlap between individuals

## Usage

1. Open `index.html` in a modern browser (or host the folder on a local/static server).
2. Click the Timeline card (or open `timeline.html` directly).
3. Choose a GEDCOM file using the file input. The file is read locally and parsed in your browser; nothing is sent to any server.

## Preview locally

Run a simple static server from the project folder and open the site in a browser. Examples:

- Python 3: `python -m http.server 8000` then visit `http://localhost:8000`
- Node (npx): `npx http-server -p 8000` then visit `http://localhost:8000`
- VS Code: use the Live Server extension

## Why privacy matters

GEDCOM files often contain sensitive personal data (names, dates, places). This project deliberately avoids any remote processing to keep that data private. If you modify the code to add remote features, you should clearly inform users and obtain consent.

## Development notes

- The GEDCOM parser included is lightweight and focuses on common tags used for timelines (`NAME`, `BIRT.DATE`, `DEAT.DATE`, `BIRT.PLAC`). It is not a full GEDCOM implementation. Improve or replace it if you need broader support.
- For large datasets consider moving heavy computations to Web Workers or implement pagination/virtualization.

## Deployment

This repository can be published to GitHub Pages or any static host. When hosting publicly, the site still performs all processing in the visitor's browser; nothing is collected by the host unless you add remote analytics or upload features.

## Contributing

Contributions are welcome. Please open issues or pull requests for bug fixes, feature suggestions or documentation improvements.

## License

MIT — see LICENSE file if present.