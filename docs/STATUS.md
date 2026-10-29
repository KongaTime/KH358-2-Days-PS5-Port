# Status and known limitations

[← Back to README](../README.md)

**Build documented in supplied archive:** V1.0 / `00.018.903` / `PPSA99852`.

## Reported as tested on PS5

- Boot and native gameplay.
- Combat, mission panel, and save/load screens.
- Intro and story HD movies decoding with audio, and theater music synchronized to a video.
- HD-voiced monologues presented with game text.
- Local multiplayer with PS5 hosting and a PC client (one 229-second Mission Mode session, as stated in the package notes).
- PS5 joining a PC session as client.

These are **tests reported in the ZIP's `PPSA99852/README.txt`**, not independent verification of the entire game.

## Not yet verified / known gaps

- **Full Story Mode playthrough** on PS5 is not documented as completed.
- A **PS5-to-PS5** multiplayer session has not been tested in the package notes.
- Seamless theater music carryover between consecutive videos is implemented but has not been tested end-to-end with the relevant unlocked theater sequence.
- Theater music diagnostics are emitted to the current session's stderr rather than a persistent music-specific record.
- Broader compatibility across firmware versions and homebrew launch methods is not documented.

## Logs

The original package lists diagnostic files including `days-startup.log`, `days-runtime.log`, `days-fault.txt`, and `saves/logs/session-*.log`. When requesting help, share only relevant excerpts after reviewing for personal information.

## File identity

The included package identifies `eboot.bin` as **55,417,080 bytes**, SHA-256:

```text
c84222a506e7d2ea7a0b3646db14e92c1cd51d4bd53e182dcc9b675e38ba0bac
```

The value above comes from the package documentation. It can be checked against the file being distributed.
