# Patent Demos — Copilot Instructions

## What this project is
A YouTube series: "Build the History of Machine Guidance."
Expired patents implemented as working student demos — browser webapps and cheap hardware.
Each episode = one patent = one demo. Solo creator, day job constraint, monthly cadence.

## Goal
Teach students to:
1. Read an expired patent
2. Implement it with a phone or ~$20 hardware
3. Discover *why* it was superseded

## Audience
College students. Resume output: "I implemented a 1993 Caterpillar patent."

## Hardware budget: ~$20 per episode max
- Phone (GPS, tilt/roll via DeviceOrientation API, barometer, camera) — free
- NEO-6M GPS x2 (~$10), Arduino Nano (~$5), OLED (~$3), breadboard + wires (~$2)

## Content constraints
- Anonymous creator. No name/face/network.
- No paid tools. No content treadmill. Monthly cadence only.
- Narration tone: Palki Sharma (Gravitas). Short declaratives. No hedging.
  - Drop into the moment: "In 1993, Caterpillar filed a patent. GPS wasn't even public yet."
  - Connect past to present: "That expired patent is why every machine on every construction site today looks the same."

## Episode structure (per month)
- Week 1: Research + patent deep dive + script draft
- Week 2: Build working demo (webapp or hardware)
- Week 3: Film + edit (screen record, narration, DaVinci Resolve)
- Week 4: Buffer → publish

## Demo file conventions
- Browser demos: `demos/{patent-number}-{slug}.html` — single self-contained HTML file, no build step
- Hardware sketches: `demos/arduino/{slug}.ino`
- Patent notes: `docs/patents/{patent-number}-simple.html` — plain language summary

## Year 1 Episode Queue (Machine Guidance)
| Ep | Patent | Segment | Topic | Status |
|----|--------|---------|-------|--------|
| 1 | EP0682786 (1993 CAT) | Earthmoving | First guidance workscreen — GPS cross-section + plan view | TO BUILD |
| 2 | US5519620 (expired 2014) | Earthmoving | RTK GPS centimetre accuracy | PLANNED |
| 3 | US6127968 (expired 2018) | Earthmoving | OTF ambiguity resolution | PLANNED |
| 4 | US7119741 (expired ~2023) | Earthmoving | Network RTK / VRS | PLANNED |
| 5 | US6701239 (2002 CAT) | Earthmoving | Colour-coded cut/fill display | PLANNED |
| 6 | US7139662 (2004 Trimble) | Earthmoving | Dual-antenna blade tilt (~expired 2024) | PLANNED |
| 7 | US8145391 (2008 Trimble) | Earthmoving | Automatic blade control PID | PLANNED |
| 8 | US9493929 (Komatsu) | Construction Industries | Excavator bucket vs design | PLANNED |
| 9 | US11761173 (active, own) | Earthmoving | In-field pad design | PLANNED |

## Episode 1 — EP0682786 — Target file
`demos/ep0682786-guidance-demo.html`
- Pure browser, ~200 lines HTML/JS, no dependencies
- APIs: navigator.geolocation + HTML canvas
- Output: cross-section view + plan view, real-time GPS position as you walk
- Phone-ready (works in mobile browser)
