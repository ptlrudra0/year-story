# Personal photo editor principles
1. Process photos locally. No accounts, sync, upload, analytics or remote processing.
2. Preserve the five-tab recorded shell. New controls must not replace it with a dashboard.
3. Use original code and licensed data. Recreated effects and display typography are not proprietary matches.
4. Never fabricate metadata. Dates and places are blank until entered by the person editing.
5. Every visible control must work, including cancel, confirm, reset and failure paths.
6. Preserve the earlier editor. Ship this editor separately.
7. Check rendered output and actual PNG pixels, not merely code or DOM existence.


# Personal photo editor: approved first release
## Status
Scope approved 16 November 2026 following one consolidated scope interview and readable plan. Development follows github/spec-kit specification, planning, task and verification stages. Its upstream templates are retained beside this specification.
## User stories
- Import an ordinary SDR JPEG or PNG, edit in Presets, Recipe, Analog, Polaroid and Tune, and export a PNG.
- Use current-photo thumbnails, category strips, gold selection and warm ruler sheets with live preview and transactional cancel.
- Use the eight licensed DAEDAL 33-point creative Rec.709 looks at adjustable strength. They are not Log conversion.
- Use None/B1/P1/P3/P4/PT1/PT2/PT3/S1/E1/E2/E3 with portrait and landscape fitting, editable border, colour, typography, year and metadata.
- Save local drafts, reopen, delete, back up/import full projects manually. Save named recipes and templates and exchange settings as JSON or QR.
- Save personal palettes and typography locally without adding a navigation tab.
## Limits
No camera, pack store, community service, payments, posting, music, Log/RAW/HDR processing, exact proprietary filter formula or font-file claim. Native library and sharing UI are browser adaptations. Export, Tune detail, metadata, border/text, QR and draft-reopen flows are designed adaptations of unrecorded screens.
## Acceptance
Check all tabs and tool changes, sheet commit/cancel, reset, twelve templates with portrait and landscape, local storage failure, draft round trip, project backup round trip, recipes and QR round trip, all eight LUT parse/identity/strength tests, PNG pixel dimensions, preview/export consistency, network-upload absence, mobile/tablet/desktop layouts. Actual Apple-device tests remain distinct from browser simulation.


# Implementation plan
- Static self-contained HTML on existing GitHub Pages, at a separate file, with no third-party runtime calls.
- Canvas 2D CPU pipeline, trilinear 33-cube LUT interpolation, consistent composition for preview and export, deterministic procedural analog effects.
- Browser-decoded SDR JPEG/PNG only. Explicit colour-format gate and unsupported metadata checks; no false automatic HDR detection claim.
- IndexedDB for original source and project settings; localStorage for small preferences and recipes with visible error handling.
- Warm modal sheets and five-tab shell. Matching visible spacing is prioritized over invented screens.
- Vendored MIT QR generation and decoding. QR contains settings only, never photos.
- Bound canvas size to 12 megapixels / 4096 side for source output. Imported source bytes preserved in local drafts and backups. Preview uses bounded resolution.
- Verify on Chromium and WebKit where available, with synthetic non-personal portrait/landscape fixtures. No private reference content in public artifacts.


# Implementation tasks
- [ ] Five-tab responsive editor, import, selection preview and local library.
- [ ] Rendering pipeline, LUTs, tune and analog effects.
- [ ] Twelve Polaroid layouts and editable brand/metadata controls.
- [ ] Transactional ruler, recipes, QR, project persistence, import/export.
- [ ] Automated functional, pixel, privacy and visual checks.
- [ ] Preserve old editor, deploy separately and verify the live build.


## Verification completed before deployment
Chromium with mobile 390x844, tablet 768x1024, desktop 1440x1000. All eight LUTs parse; 33³ trilinear identity and zero-strength checks pass, 50% blend within one byte; ruler cancel/commit; nine Tune and four Analog tools; twelve template families in portrait and landscape; recipes and QR round-trip; draft reopen and project backup import; storage-error paths; SDR format and HDR marker rejection; PNG story/feed/square/source dimensions and bounded canvas; no photo network requests. Original sample illustration plus public-domain NASA test photo were used only for tests. NASA test image is not bundled in this website.

Limitations: no physical iPhone/iPad validation; WebKit test could not launch in the test environment because browser libraries were unavailable. Browser colour decoding, OS photo picker/share and old-iPad memory behavior remain device checks. This is a recreation of the shell and documented scope, not a claim that proprietary font/filter/texture algorithms or every unrecorded detail matches Binsoo exactly.
