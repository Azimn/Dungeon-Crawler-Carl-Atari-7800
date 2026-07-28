# Dungeon Crawler Carl: Atari 7800 Demake

This repository is configured to use GitHub Actions as an online 7800basic compiler.

## Build online

1. Place `carl_complete.bas` in the repository root.
2. Place all referenced PNG files under `gfx/`.
3. Open **Actions**.
4. Select **Build Atari 7800 ROM**.
5. Select **Run workflow**.
6. Download the `atari-7800-build` artifact from the completed run.

The workflow installs Wasmtime, downloads the pinned 7800basic v0.40 toolchain, compiles the game, preserves the full compiler log, and uploads any generated `.a78`, `.bin`, `.asm`, `.list.txt`, and `.symbol.txt` files.

The workflow also runs `tools/generate_assets.py` when that file is present, allowing indexed PNG assets to be regenerated during the cloud build instead of storing every generated image in Git.

## Current state

The cloud compiler configuration is installed. The complete game source and graphics package still need to be committed to this repository before the build can succeed.
