# HobbyX Multi-Grader — static export

Open `index.html` directly (double-click) or host the folder on any static server. No build step, no network needed at runtime.

```
index.html     page shell
styles.css     static CSS: @font-face + compiled Tailwind 3.4.17 + app tokens/animations + grade-reveal
script.js      app code, JSX precompiled to plain JS (load order: data, i18n, icons, ui, grading, auth, tweaks-panel, root)
assets/        images, vendored React 18.3.1 production UMD, <image-slot> element, fonts/ (Nunito + Noto Sans HK slices, woff2)
```

- No Babel / Tailwind CDN / Google Fonts / unpkg at runtime, no blob: URLs, no script injection.
- `assets/image-slots-data.js` + `assets/cards/` hold the two card images that were dropped into `<image-slot>`s in the prototype (now real files).
- The design-time controls above the phone (Samples 1–5, Auth/Grading/Empty/Only Grading/Loading, Light/Dark, Online/Offline) are kept as in the prototype. For production, delete `GraderPicker`, the phase pills and the offline toggle in `root.jsx` (compiled into `script.js`).

## Known external dependency
Mock card art in the sample data (`PKM(n)` / `YGO(id)` in `data.jsx`) hotlinks `images.pokemontcg.io` and `images.ygoprodeck.com`. Those are prototype placeholders; real cards come from the API. Replace with local files if the export must work fully offline.
