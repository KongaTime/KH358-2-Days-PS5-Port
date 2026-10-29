# Kingdom Hearts 358/2 Days — PS5 Native Port V1.0

Kingdom Hearts 358/2 Days is running natively on PS5 homebrew! This experimental PS5 build adapts [Yokimitsuro's PC port](https://github.com/Yokimitsuro/khdays-port) with native DualSense input, graphics options, save/load support and optional HD cutscene playback.

## Features

- Native PS5 gameplay — no Nintendo DS emulator required.
- DualSense mapping, 16:9 single-screen mode and controller-accessible settings.
- Optional HD cutscenes and audio using files prepared from your own collections.
- Combat, save/load and mission menu functionality reported working in testing.
- Local PS5-to-PC Mission Mode multiplayer reported working in both host and guest roles.

## Installation

1. Download and extract the attached V1.0 ZIP.
2. Install `PPSA99852/` into `/data/homebrew/PPSA99852/` on a compatible PS5 homebrew setup.
3. On a Windows PC with Python 3.11+, use `console-transfer/transfer-to-ps5.cmd` to send your own **already prepared** PC-port game data over FTP (default port 2121).
4. Launch the title and open settings with **L3**.

**Full guide:** see `docs/INSTALLATION.md` in the repository.

## Important

- Experimental release; **full Story Mode completion on PS5 is not yet verified**.
- Two-PS5 multiplayer has not been tested in the package notes.
- This package does **not** include ROMs, extracted game data or HD media. Users must provide files from their own copies.
- Report crashes with PS5 firmware, install method, reproduction steps and sanitized logs.

## Credits

Based on **[khdays-port](https://github.com/Yokimitsuro/khdays-port)** and **[khdays-decomp](https://github.com/Yokimitsuro/khdays-decomp)** by **Yokimitsuro and contributors**, alongside the credited PS5 homebrew and third-party dependency contributors. See the repository's credits and license notices.

Thanks for supporting my projects! 🦍🍌
