HobbyX — Grading App · Static Production Build
Build date: 2026-07-24

HOW TO RUN
  Open index.html in Chrome (double-click), or host the folder on any static
  web server. No build step, no bundler, no internet required except:
    • Google Fonts (Nunito) — loaded from fonts.googleapis.com
    • Some trading-card thumbnail art — loaded from third-party CDNs
      (images.pokemontcg.io, images.ygoprodeck.com). These cannot be bundled
      (CORS). When offline or blocked, cards fall back to a bundled placeholder.

STRUCTURE
  index.html          entry point
  styles.css          precompiled stylesheet (Tailwind utilities + app + reveal + tokens)
  script.js           precompiled application (React, no JSX/Babel at runtime)
  assets/             images, fonts helpers, vendored React (production builds)

NOTES
  • Faithful 1:1 export of the live design, including the Auth / Grading review
    switcher, Light/Dark toggle, Online/Offline control, and the phone bezel.
  • No CDN/Babel at runtime — JSX is precompiled and React is vendored locally.
  • Custom features preserved: date-range estimates (incl. cross-year ranges),
    invoice numbers (H######) behind a biometric gate with a persistent
    Face/Touch-ID error, and the Completed-tab status filter
    (Ready for Pickup / Picked Up).
