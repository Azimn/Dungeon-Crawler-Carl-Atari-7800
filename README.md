# Dungeon Crawler Carl: Atari 7800 Demake

Cartridge 1, The Descent, is an Atari 7800 arcade-action demake covering Floors 1 through 9. The target configuration is a 128K ROM using 160A display mode and zoneheight 8.

## Repository contents

`package/dcc7800-project-source.zip` contains `carl_demo.bas`, the asset preflight tool, the project manifest, and all 30 required four-color PNG graphics. The GitHub Actions workflow extracts the package before validation and compilation.

## Cloud build

The workflow runs on pushes to `main`, pull requests, and manual dispatch. It installs Wasmtime, downloads the pinned 7800basic v0.40 source distribution, validates the graphics package, and compiles `carl_demo.bas`.

Every run uploads `compiler-log`, including failed builds. A successful compile also uploads `dungeon-crawler-carl-atari7800-rom`, containing the generated `.a78` or `.bin` file.

## Current status

The project is a source-level handoff package. A successful ROM build has not yet been verified. The source still contains incomplete map definitions and partial late-floor encounter logic. The cloud build is intended to expose reproducible compiler diagnostics so those issues can be repaired.

## Browser testing

After a successful Actions run, download the ROM artifact and load the `.a78` or `.bin` file into an Atari 7800 browser emulator such as JS7800.
