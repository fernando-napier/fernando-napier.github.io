# fernando-napier.github.io

A collection of games I built for my kids (and myself).

---

## Siren Head

**[Play it here](https://fernando-napier.github.io/sirenhead.html)**

A first-person survival game where you roam a dark procedural city, collect scattered notes, and escape — all while avoiding the towering Siren Head monster(s).

### Mechanics
- **Detection meter** — Siren Head tracks you by proximity and line of sight. The meter fills as you're spotted; reach 100% and it's over.
- **Blink** — hold the blink button to freeze Siren Head in place (inspired by Weeping Angels). Times out and goes on cooldown.
- **Paralyze gems** — collectible gems that freeze all Siren Heads temporarily.
- **Notes** — find all the hidden notes to trigger the escape sequence.
- **Sprint** — hold run to move faster at the cost of more noise.
- **Win sequence** — escape triggers a disco dance celebration with the Siren Heads, complete with jumping, swaying, floor tiles, and disco lights.

### How it was built
Everything lives in a single `sirenhead.html` file — no build step, no dependencies beyond Three.js (loaded from CDN). The 3D scene, all character meshes, audio, and game logic are hand-coded in vanilla JS:

- **Three.js** for the 3D renderer, scene graph, and raycasting (collision + line-of-sight checks)
- **Web Audio API** for the siren oscillators, ambient drone, and wind noise — all synthesized in-browser, no audio files
- **Canvas 2D** for the minimap overlay
- **Touch controls** built from scratch: virtual joystick (left side), look drag (right side), and on-screen sprint/blink buttons
- Landscape-only layout enforced via CSS `transform: rotate(90deg)` on portrait devices
- Siren Head AI uses steering + separation to handle multiple heads without them stacking

