# Installation guide — PS5 V1.0

[← Back to README](../README.md)

These instructions are based on the `PPSA99852/README.txt` and `console-transfer/README.txt` in the supplied `KHDays 358-2 V1.0.zip` archive.

## 1. Before you begin

You need a homebrew-capable PS5 and a launcher/mounting setup supporting native homebrew (the included documentation mentions **ShadowMount+**), the PS5 package `PPSA99852/`, and **your own game data** from Kingdom Hearts 358/2 Days. The package itself does not contain game assets or HD movies.

For the easiest transfer route you also need:

- A Windows PC with **Python 3.11+** on PATH.
- The [Kingdom Hearts 358/2 Days PC port](https://github.com/Yokimitsuro/khdays-port) already prepared from your own game copy, containing `data/extracted/`.
- Optional `data/cutscenes/cinematics/` generated on your PC from your own HD collection.
- FTP access to your PS5, typically on **port 2121**.

## 2. Install the PS5 title

Extract the V1.0 release archive. Transfer the entire `PPSA99852` directory so its layout on the PS5 is:

```text
/data/homebrew/PPSA99852/
├── eboot.bin
├── sce_module/
│   └── libc.prx
├── sce_sys/
├── ps5-settings-default.ini
└── licenses/
```

Use your compatible PS5 homebrew mounting/launching tool to register/launch this title (the package instructions mention ShadowMount+). **Keep the folder name `PPSA99852`.**

## 3. Transfer your game data

**Close the PS5 title before starting a transfer.**

In the release archive, open the `console-transfer/` folder and double-click:

```text
transfer-to-ps5.cmd
```

Follow the prompts:

1. Supply the folder where your prepared PC port is installed — the folder containing `data/extracted/`.
2. Enter your PS5's local IP address (the one used for FTP).
3. Choose whether to transfer the optional HD cutscenes. According to the helper, these are about **6.4 GB**.
4. Let the script pack and copy the prepared data to the PS5. The helper verifies pack hashes and resumes/skips already transferred files where possible.

Alternatively, from a Windows terminal:

```bat
transfer-to-ps5.cmd "C:\path\to\KH 358-2 Days" 192.168.1.100
```

Replace the example path and IP with your actual values. The script copies to `data/extracted/`, optional `data/cutscenes/cinematics/`, and `mods/` when supplied.

**Important:** The standalone bundle is designed for transferring *already prepared* PC game data. Preparing the game from a ROM directly requires tools from the upstream PC-port repository and is not the recommended path with this standalone package.

## 4. Launch and configure

Launch **Kingdom Hearts 358/2 Days (Native)** from your PS5 homebrew launcher. Press **L3** to open the port settings menu.

The shipped defaults use a single screen, 16:9 aspect ratio, Vulkan rendering and network discovery off (`online = off`). Saves are kept in `saves/`.

## Troubleshooting

- **Missing game data:** confirm the PC-port folder contains `data/extracted/` and the transfer script completed.
- **FTP failed:** check the console IP, FTP service, port 2121, and local network connectivity.
- **Transfer stops:** make sure the PS5 game is closed. Re-run the transfer to resume.
- **HD cutscene missing:** confirm `data/cutscenes/cinematics/` was prepared on the PC; otherwise the port's documented fallback uses available game assets.
- **Unexpected controls/settings:** see [Controls and settings](CONTROLS.md).

Do not submit ROMs, original game files or HD movies in issue reports.
