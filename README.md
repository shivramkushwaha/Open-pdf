# Open PDF

A free, open-source, browser-based PDF reader and learning workspace built with HTML, CSS and JavaScript.

## Features in this starter

- Open a local PDF in the browser
- Render pages with Mozilla PDF.js
- Page navigation and zoom
- Search extracted PDF text
- Save page bookmarks
- Save page-based personal notes
- Collect question text manually
- Local browser storage for notes, bookmarks and question collections

## Run locally

PDF.js uses a CDN in this starter. You need an internet connection the first time you load the reader.

1. Extract this folder.
2. Open a terminal in the project folder.
3. Start a local static server, for example:

   ```bash
   python -m http.server 8000
   ```

4. Open `http://localhost:8000` in your browser.
5. Choose a PDF.

You can also use a static hosting service such as GitHub Pages. Do not open `reader.html` directly with a `file://` URL; browsers restrict some PDF worker features in that mode.

## Dependencies and licenses

- [PDF.js](https://github.com/mozilla/pdf.js) — Apache License 2.0; loaded from cdnjs in `reader.html`.
- The application source in this repository — MIT License.

The CDN version is convenient for development but is not fully offline. For an offline deployment, download a matching PDF.js release and host `pdf.min.js` and `pdf.worker.min.js` locally, then update the script paths in `reader.html`.

## Privacy

The selected PDF is read by the browser and is not uploaded by this application. Notes, bookmarks and question collections are stored in the browser's `localStorage`, on the device and browser profile being used. Clearing browser site data may erase them. Avoid using shared/public devices for private documents.

## Current limitations

- Search works on selectable text; scanned/image-only PDFs need OCR.
- Highlighting is not yet persisted as PDF annotations.
- Questions are added manually; automatic AI question generation is not included.
- No cloud sync, accounts, or server backend.
- Password-protected and unusually structured PDFs may not render.

## Project structure

```text
open-pdf/
├── index.html
├── reader.html
├── assets/
│   ├── css/
│   │   ├── style.css
│   │   └── reader.css
│   └── js/
│       ├── app.js
│       ├── reader.js
│       ├── search.js
│       ├── annotations.js
│       ├── bookmarks.js
│       └── questions.js
├── data/
│   └── documents.json
├── LICENSE
└── README.md
```
