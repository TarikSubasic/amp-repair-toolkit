# Amp Repair Toolkit

An offline-first diagnostic assistant for **12 V car-audio amplifiers**. The MVP guides a technician through safe intake, symptom-specific measurements, likely fault areas, repair notes, and final verification.

## Run it

Open `index.html` in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8080
```

Then visit <http://localhost:8080>.

No packages, server, account, or internet connection are required. Cases are stored in the browser's local storage. Use **Export case** to make a portable JSON backup.

## Included workflows

- No power / no LEDs
- Stuck in protect mode
- Fuse blows
- No or distorted output
- Beginner “How to check safely” procedures covering supply voltage, voltage drop, resistance/short checks, output DC, internal rails, gate drive, and signal tracing
- An expandable visual-guide system for adding verified procedure diagrams

The tool deliberately gives measurement-driven suggestions rather than declaring a component defective. It assumes a current-limited bench supply and a qualified user familiar with electronic repair.

## Technical references

The workflows use original wording and rules informed by public educational material from:

- [BCAE1 Amplifier Repair Basics](https://bcae1.com/repairbasicsforbcae1/repairbasics.htm)
- [BCAE1 Protect Mode Troubleshooting](https://www.bcae1.com/repairbasicsforbcae1/troubleshootingbasicsampinprotect.htm)

BCAE1's separately sold repair tutorial is linked for further study but is not copied or bundled with this project. Model-specific service manuals should take priority over general screening thresholds.

## Important safety limits

Car amplifiers contain high-current circuits and internal rails that may remain charged. Do not connect speakers during initial diagnosis. Never bypass fuses or protection circuits. Disconnect power before resistance/continuity tests, observe polarity, and use current limiting for every first power-up after a repair.

## Project files

- `index.html` — application structure
- `styles.css` — responsive UI
- `app.js` — workflows, diagnostic rules, persistence, and exports
