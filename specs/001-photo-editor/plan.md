# Implementation plan
- Static self-contained HTML on existing GitHub Pages, at a separate file, with no third-party runtime calls.
- Canvas 2D CPU pipeline, trilinear 33-cube LUT interpolation, consistent composition for preview and export, deterministic procedural analog effects.
- Browser-decoded SDR JPEG/PNG only. Explicit colour-format gate and unsupported metadata checks; no false automatic HDR detection claim.
- IndexedDB for original source and project settings; localStorage for small preferences and recipes with visible error handling.
- Warm modal sheets and five-tab shell. Matching visible spacing is prioritized over invented screens.
- Vendored MIT QR generation and decoding. QR contains settings only, never photos.
- Bound canvas size to 12 megapixels / 4096 side for source output. Imported source bytes preserved in local drafts and backups. Preview uses bounded resolution.
- Verify on Chromium and WebKit where available, with synthetic non-personal portrait/landscape fixtures. No private reference content in public artifacts.
