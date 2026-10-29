# Kingdom Hearts 358/2 Days — Native PS5 Port

**Kingdom Hearts 358/2 Days running natively on PlayStation 5 homebrew — no Nintendo DS emulator required.**

![Status](https://img.shields.io/badge/status-experimental-orange) ![Platform](https://img.shields.io/badge/platform-PS5-blue) ![Version](https://img.shields.io/badge/package-V1.0-brightgreen)

An unofficial PS5 adaptation of the [Kingdom Hearts 358/2 Days native PC port](https://github.com/Yokimitsuro/khdays-port), which builds on the [matching decompilation](https://github.com/Yokimitsuro/khdays-decomp). This PS5 build uses SDL3 with Vulkan/RADV rendering, DualSense controls, native audio output, and a controller-accessible settings menu.

> **Experimental release.** This documentation describes the supplied **KHDays 358-2 V1.0** package, internal build `00.018.903`, title ID `PPSA99852`. Story Mode has **not** been reported as completed on PS5. Expect possible bugs or performance issues.
>
> **Game files are not included.** You must supply game data extracted from your own copy of Kingdom Hearts 358/2 Days. Optional HD cutscenes and music are prepared from your own HD collections.

## Features

- **Native PS5 gameplay** — runs as a native homebrew application, not through DS emulation.
- **DualSense controls** — Cross/Circle/Triangle/Square support, camera enhancements, and quick access to settings.
- **Widescreen and single-screen options** — 16:9 is the supplied default; screen layout and scaling can be changed.
- **Visual options** — internal resolution, antialiasing, texture smoothing, and on-screen FPS display.
- **HD movie playback** — optional HD H.264/AAC cutscenes, subtitles and music from a user-prepared HD pack.
- **Save/load and Mission Mode** — saving and combat have been tested; PS5↔PC multiplayer has been tested on a local network.
- **Mod support** — the packaged transfer tools can upload a prepared `mods/` folder.

## Download

Find the latest package in this repository's **Releases** section once a release has been uploaded. The supplied local archive was named `KHDays 358-2 V1.0.zip`.

For setup, see **[Installation guide](docs/INSTALLATION.md)**. For tested features and outstanding issues, see **[Status and limitations](docs/STATUS.md)**.

## Requirements

- PS5 capable of running native homebrew; the package's instructions reference **ShadowMount+**.
- The supplied `PPSA99852` application folder.
- Your own game data prepared using the [native PC port](https://github.com/Yokimitsuro/khdays-port).
- A PC with **Python 3.11+** for the supplied transfer helper, plus an FTP-accessible PS5 (default port **2121**).
- Optional: HD cutscenes generated from your own HD collection.

**Quick install:** copy `PPSA99852/` to `/data/homebrew/PPSA99852/` on your PS5, then use `console-transfer/transfer-to-ps5.cmd` on a Windows PC to send your own prepared game files over FTP. See the [complete guide](docs/INSTALLATION.md) before launching.

## Default controls

| DualSense | In-game action |
| --- | --- |
| Cross / Circle | A / B |
| Triangle / Square | X / Y |
| D-pad / left stick | Movement / directions |
| Options | Start |
| Touchpad click | Select |
| L1 / R1 | DS L / DS R (R1 also defaults to lock-on) |
| R2 | Change target |
| L3 | Port settings menu |

The included settings file lets users customize the mapping. See [Controls and settings](docs/CONTROLS.md) for details.

## Project status

The included package documentation reports successful tests of gameplay, combat, mission menus, saves, HD movie playback, and PS5-hosted / PS5-guest multiplayer sessions with the PC port. **A full PS5 playthrough and two-PS5 multiplayer session have not been verified in those notes.** See [Status and limitations](docs/STATUS.md).

## Help and reporting issues

For reproducible issues, provide your PS5 firmware, homebrew launch method, package build, whether you installed the required game data, steps to reproduce, and the relevant log excerpt. Do **not** share copyrighted game files, ROMs, keys, or private data.

## Credits

- **[Yokimitsuro and contributors](https://github.com/Yokimitsuro/khdays-port)** — original native PC port, tooling and MIT-licensed project components.
- **[khdays-decomp](https://github.com/Yokimitsuro/khdays-decomp)** — matching Nintendo DS decompilation foundation.
- **KongaTime** — this PS5-port release's repository and distribution documentation; specific implementation contributions should be credited according to the project's source history.
- **PS5 homebrew and dependency contributors** — SDL3, Vulkan/RADV and associated components. Refer to [full third-party notices](THIRD_PARTY_NOTICES.md) and [Credits](docs/CREDITS.md).

Independent homebrew project. Not affiliated with or endorsed by Disney, Square Enix, Nintendo, or Sony. The game and its contents belong to their respective rights holders. **No game ROMs, extracted game assets, or HD collection media are provided.**

> **Redistribution note:** The package includes components under MIT, LGPL, GPL and other licenses. Before distributing a binary release, verify compliance with applicable source-availability and license-notice obligations; see [Credits and licenses](docs/CREDITS.md).
