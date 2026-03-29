# pdf-reader

A lightweight PDF.js widget optimized for embedding (including Element.io widgets).

## Features

- Load PDFs from local files or remote HTTPS URLs.
- Single-page reader mode with page controls and keyboard navigation.
- Continuous-scroll mode for full-document browsing.
- Zoom slider + fit-width action.
- Renderer improvements:
  - high-DPI canvas rendering
  - render task cancellation to avoid stale draws
  - resize re-rendering
- Element.io-friendly auto-update bridge via `postMessage`:
  - emits `pdf-widget:update`
  - accepts `pdf-widget:set-pdf-url` and `pdf-widget:set-page`
- Startup source loading via either `?pdf=<url>` or `#pdf=<encoded-url>`.

## Run

Open `index.html` in a browser.

## Widget messaging

### Outbound

```json
{
  "type": "pdf-widget:update",
  "page": 1,
  "totalPages": 10,
  "mode": "single",
  "zoom": 1.1,
  "height": 1400
}
```

### Inbound

- Set URL
```json
{ "type": "pdf-widget:set-pdf-url", "url": "https://example.com/doc.pdf" }
```
- Set page
```json
{ "type": "pdf-widget:set-page", "page": 4 }
```
