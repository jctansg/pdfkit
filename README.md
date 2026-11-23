# PDF Toolkit

Free, private, browser-based PDF tools. All processing happens locally.

## Tools

| Tool | Description |
|------|-------------|
| [PDF Merge](merge.html) | Merge multiple PDFs into one file, reorder and rotate pages, and remove unwanted pages. |
| [PDF Convert](convert.html) | Convert, compress, flatten and export PDFs — change PDF version, rasterize pages, and edit document metadata. |
| [PDF Metadata Inspector](meta.html) | Inspect document properties, XMP metadata, page geometry and file integrity. |

## Features

- 100% client-side — files are never uploaded anywhere
- Page-level editing: reorder, rotate, delete
- Rasterize/flatten and version conversion via pdf-lib + pdf.js + jsPDF
- Installable PWA — `manifest.webmanifest` + `sw.js` for offline use

## Run locally

```bash
cd pdf
python3 -m http.server 8000
```

Open http://localhost:8000/merge.html (or convert.html / meta.html).

## Deploy to GitHub Pages

1. Push this folder to a new repository.
2. Enable **Pages** (Deploy from branch → `main` / root).
3. Available at `https://<user>.github.io/<repo>/merge.html`, `.../convert.html`, `.../meta.html`.

Any static host works — no build step. Libraries load from CDN (jsDelivr / cdnjs), so an internet connection is needed on first load.

## Dependencies

Loaded from CDN at runtime:

- `pdf-lib` — PDF creation/manipulation
- `pdfjs-dist` / `pdf.js` — PDF rendering and parsing
- `jspdf` — PDF export (convert.html)
- `jszip` — batch ZIP export (convert.html)

## Structure

```
pdf/
├── merge.html            # Merge / reorder / rotate pages
├── convert.html          # Convert, compress, flatten, metadata
├── meta.html             # Metadata & integrity inspector
├── manifest.webmanifest  # PWA manifest
├── sw.js                 # Service worker (offline support)
└── icon.svg              # App icon
```

## License

MIT
