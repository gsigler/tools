# tools

a collection of minimalist, client-side developer utilities

## design rules

all tools must follow these rules:

1. **single-file architecture**: each tool is a single HTML file with inline CSS and JavaScript
2. **no frameworks**: vanilla JavaScript only, no React/Vue/Angular
3. **client-side only**: all processing happens in the browser, no server calls (except where absolutely necessary like RSS feeds)
4. **privacy-focused**: no data sent to external servers, no tracking, no analytics
5. **dark minimal style**:
   - background: #1a1a1a
   - text: #ccc
   - borders: #333
   - font: 'Courier New', monospace
   - lowercase text for headings and labels
   - no animations, gradients, or flourishes
6. **functional over aesthetic**: plain, boring, developer-focused design
7. **consistent UX**: all tools have "← back" link, clear buttons, status messages
8. **real-time feedback**: input changes trigger immediate updates where applicable
9. **copy to clipboard**: results should be easily copied
10. **mobile responsive**: tools should work on mobile devices

## tools

### json linter
- **path**: `/jsonlint`
- **dependencies**: none
- **apis**: native JSON.parse(), JSON.stringify()

### jwt decoder
- **path**: `/jwt`
- **dependencies**: none
- **apis**: Web Crypto API (for HS256 signature verification), native base64 decoding

### date converter
- **path**: `/date`
- **dependencies**: none
- **apis**: native Date object

### qr generator
- **path**: `/qr`
- **dependencies**:
  - QRCode.js v1.0.0 (CDN: https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js)
- **apis**: Canvas API, Clipboard API

### rss reader
- **path**: `/rss`
- **dependencies**: none
- **apis**:
  - Fetch API
  - rss2json.com API (external service for parsing RSS feeds due to CORS limitations)

### base64 encoder/decoder
- **path**: `/base64`
- **dependencies**: none
- **apis**: native btoa(), atob(), encodeURIComponent(), decodeURIComponent()

### hash generator
- **path**: `/hash`
- **dependencies**: none
- **apis**: Web Crypto API (crypto.subtle.digest for SHA-1, SHA-256, SHA-384, SHA-512)

### uuid generator
- **path**: `/uuid`
- **dependencies**: none
- **apis**: crypto.randomUUID() (native v4 UUID generation)

### url encoder/decoder
- **path**: `/url`
- **dependencies**: none
- **apis**: native encodeURI(), encodeURIComponent(), decodeURI(), decodeURIComponent(), URLSearchParams

### color converter
- **path**: `/color`
- **dependencies**: none
- **apis**: native color conversion algorithms, Clipboard API

## external dependencies summary

**total tools**: 10
**tools with zero external dependencies**: 8
**tools with external dependencies**: 2

1. **QR Generator**: requires QRCode.js library from CDN
2. **RSS Reader**: requires rss2json.com API service (necessary due to CORS restrictions on RSS feeds)

all other tools use only native browser APIs and have no external dependencies.

## original prompt

```
Create a single-file HTML tool with inline CSS and JavaScript. Use a dark, minimal, boring style like a developer who isn't trying: dark gray background (#1a1a1a), monospace font, muted colors, lowercase text, no animations or gradients. Keep it functional and plain.
```
