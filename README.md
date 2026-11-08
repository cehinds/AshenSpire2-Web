# AshenSpire II — The Hollow March

[Play in your browser](https://cehinds.github.io/AshenSpire2-Web/)

Unity Web player v0.1.3: M05 battle clarity. An original FFII-inspired game using AshenSpire assets and procedural content. This repository contains the compiled public player and credits.

## Play

Desktop browser with WebGL 2. WASD/arrows walk; E interacts; M opens the map. In battle: F1–F4 select the acting hero, 1–5 select cards, Shift+1–4 target allies, 6–9 target enemies, Tab cycles targets, Enter plays, Space ends the selected turn. Escape closes/back/pauses. Mouse controls expose all battle actions and inspectors.

Campaigns save in this browser on this site. Use Export Campaign to keep a portable backup or Import Campaign File to bring a local-preview campaign here. Imports stay in your browser. Browser storage is separate from localhost and other sites.

## Build and credits

Unity 6000.6.7f1 / IL2CPP. Ordinary player; no QA fixture or state-snapshot hooks. M05 passed 21 battle, 17 save-slot and 11 portable browser scenarios plus 118 battle-domain assertions. These are development checks, not a production release certification.

[Art credits](Credits/CREDITS.md) · [Import provenance](Credits/IMPORT-MANIFEST.json) · [Audio provenance](Credits/AUDIO-PROVENANCE.md)

GitHub Pages serves the root of `main`; `.nojekyll` preserves the prebuilt Unity files. Future deployments should use verified builds and preserve this site URL for browser-save continuity.
