Kingdom Hearts 358/2 Days - native PS5 port
Title 00.018.903, homebrew title PPSA99852

This is the console build of the PC port: the rewritten game, its ROM/VFS
runtime, SDL3 over RADV for pictures, native DualSense input and AudioOut, the
PC frontend with its settings menu, HD MP4/H.264/AAC decoding through FFmpeg,
and the HD collection's theater music over the scenes.

WHAT THIS PACKAGE IS
The build the console has been playing since 21 October 2026, taken back off it
for this package, not a rebuild:

  eboot.bin        55,417,080 bytes
                   SHA-256 c84222a506e7d2ea7a0b3646db14e92c1cd51d4bd53e182dcc9b675e38ba0bac
  sce_sys/         param.json (contentVersion 00.018.903), icon0.png, pic0.dds, pic1.dds
  sce_module/      libc.prx

Installing the signed SELF makes the console's FTP server store the ELF inside
it (zeroing two program headers on the way), and that stored file is what runs
- it is the file here. Its startup log opens "title 00.018.903"; if that line is
not there, the running file is not this build.

WHAT IS NOT HERE
This package is the title only. It carries no game data and no HD media:

  data/extracted              the DS game's files, from your own copy of the game
  data/cutscenes/cinematics   the HD collection's videos, their subtitles, and
                              music/<video>.txt with music/<track>.ogg

Without them the port still runs: each scene, movie and monologue falls back to
the game's own assets, and the log names the file it wanted. Nothing of the HD
collection is redistributed here.

GETTING THEM ONTO THE CONSOLE
Build them on a PC with the port, which makes data/extracted from your ROM and
data/cutscenes from your own HD collection, then transfer them with the port's
own tool - it needs neither the ROM nor the collection, only the PC folder:

  python ps5/tools/setup-console.py --from-install "C:\path\to\KH 358-2 Days" --host <console ip>

It packs data/extracted and data/cutscenes, verifies each pack's SHA-256, and
installs them over FTP, skipping files already on the console at the expected
size. Close Days first: the tool refuses to install while the title is running.

HOW TO INSTALL THIS PACKAGE
Copy the PPSA99852 folder to the console (FTP path /data/homebrew/PPSA99852) and
let ShadowMount+ register it, or install it with your usual homebrew tool. The
folder is what runs and the launcher's own entry is a stub pointing at it.

DEFAULTS
The settings menu is L3. This package ships the port's defaults with the
network switched off and no server set (online = off, server = empty): Mission
Mode's multiplayer finds rooms on the local network, and you turn online
discovery on yourself if you want it. Saves stay in saves/.

CONTROLS (defaults)
Cross = A, Circle = B, Triangle = X, Square = Y; Options = Start;
touchpad click = Select; L1/R1 = L/R; D-pad or left stick = directions;
L3 opens the port's settings menu. R1 locks on, R2 changes target, R3 is DS R.

VERIFIED ON THE CONSOLE WITH THIS BUILD
The game plays: the intro's HD movies decode with their own sound, a story scene
plays its HD video, the theater's music runs on its schedule over a video and
fades with it, the days' monologues speak their HD voice over the game's text
pages, and saving, the load screen, combat and the mission panel work. Multiplayer
has run both ways: a console-hosted room that a PC guest joined (build 00010001
on both sides, 2.5-4.1 ms round trips, 229 seconds of Mission Mode, no fault
report), and a session with the console as the guest.

KNOWN GAPS
- The theater's music carrying from one video into the next is wired and its data
  installed, but no shipped pair has been played end to end: the theater unlocks
  only after Story Mode is cleared, and the story map gives no scene two videos.
- Two consoles in one session has not been played. Each role has, separately.
- The music's log lines go to stderr (the running session's log), so a theater
  playtest leaves no lasting record of its music.

DIAGNOSTICS
days-startup.log, days-runtime.log, days-fault.txt, saves/logs/session-*.log,
saves/settings.ini, and GPU readbacks days-enhanced-00060.png, 00180 and 00600.

LICENSING
The original port portions are MIT (licenses/khdays-MIT.txt). SDL3 is zlib.
FFmpeg is LGPL-2.1-or-later, built without GPL components; its license text is
licenses/FFmpeg-LGPLv2.1.txt and its source is FFmpeg n8.0
(github.com/FFmpeg/FFmpeg, revision 140fd653aed8cad774f991ba083e2d01e86420c7).
The payload SDK and the Vulkan driver materials are GPL-3.0-or-later and carry
their own texts here; THIRD_PARTY_NOTICES.md has the full inventory with the
revisions used. The port's own source is the project repository at the tag this
package was built from; no runtime source archive is bundled here.
