# ATLAS Desktop v0.6 — Windows Alpha (v0.6.1-alpha)

**Public alpha · Windows 10/11 · pre-release · not code-signed**

ATLAS Desktop is an experimental, local-first AI computing experience. You talk, it answers out loud, and it learns about you as you use it. The AI, speech recognition and voice run on your own PC.

> **Alpha:** expect rough edges. This build was tested on our development PC and preliminarily by a few testers. Fresh installs on many different PCs haven't been tested yet, and your installation report helps.
> **Hardware not included:** ATLAS computers are in development and not shipping yet. Reserve one free of charge at [atlascomputers.ai](https://www.atlascomputers.ai). No payment is needed.

## Download

| File | What it is |
|---|---|
| `ATLAS_Setup_0.6.1_Alpha.exe` | The installer (about 25 MB). It downloads about 12 GB more during setup. |
| `SHA256SUMS.txt` | SHA-256 checksum of the installer. Verify before running: [INSTALLATION.md](https://github.com/milivoja-labs/atlas-desktop/blob/main/INSTALLATION.md#2-verify-the-download). |

The installer is **not code-signed**, so Windows SmartScreen will warn that the app is unrecognised.

## Requirements

- Windows 10 (22H2) or 11, 64-bit;
- NVIDIA graphics card with 8 GB or more (12 GB recommended);
- 16 GB RAM, 30 GB free disk, internet during setup.

Details: [SYSTEM_REQUIREMENTS.md](https://github.com/milivoja-labs/atlas-desktop/blob/main/SYSTEM_REQUIREMENTS.md).

## What's in this release

**Available now** (tested on our development PC):
- Talking to ATLAS by voice, with speech recognition on your PC (Whisper large-v3-turbo).
- Spoken replies with Chatterbox-Turbo, streamed: about **0.7 s** from the end of your sentence to ATLAS's first word (median of 20 turns on an RTX 4070 SUPER, 12 GB, measured with 0.6.0; the 0.6.1 built-in voice uses the same engine).
- A local AI chat model through Ollama, chosen to fit your graphics card.
- Memory that survives restarts: ATLAS reads back what it learned ("Is that right?") and explains its answers ("Why did you say that?"). You can correct or remove anything it learned.
- Files: browsing, search, document summaries, and organising folders after your approval.
- Opening apps; volume, sound devices and brightness; calendar and reminders; a 3D model viewer; music from your Music folder.
- Offline use after setup (except web search and websites).
- Settings → About → Send logs, for bug reports.

**Experimental:**
- Interrupting ATLAS by talking.
- Web search and "open it".
- One-click diagnostics.
- Headset unplug recovery.
- Wi-Fi and Bluetooth connection, power actions.
- Recording your own voice for ATLAS.

**New since the private tester build (0.6.0):**
- Starts completely empty: no sample data. ATLAS learns everything from you.
- Every user creates their own account, with a password of at least 6 characters.
- Uses Chatterbox-Turbo's own built-in voice (MIT).
- Only components licensed for this use are included. The optional XTTS-v2 voice and the music-mood models are no longer part of ATLAS (both were licensed for non-commercial use only).
- Python packages are installed at exact, tested versions, so new releases elsewhere can't break your install.
- Microsoft's WebView2 installer is run only after Windows confirms it's signed by Microsoft.
- Public-alpha labels; development-PC information removed from the program files.

## Known issues

See [KNOWN_ISSUES.md](https://github.com/milivoja-labs/atlas-desktop/blob/main/KNOWN_ISSUES.md). The main ones:
- the installer is unsigned;
- 8 GB graphics cards haven't been measured;
- the male and female voice settings currently sound the same;
- conversations aren't kept after a restart;
- the Wi-Fi list needs Windows Location to be on.

## Feedback

Please report bugs, installation problems and ideas through [GitHub Issues](https://github.com/milivoja-labs/atlas-desktop/issues/new/choose). Don't upload passwords, personal documents or private conversations.

ATLAS has no telemetry: your reports are how we learn what to fix. Privacy details: [PRIVACY.md](https://github.com/milivoja-labs/atlas-desktop/blob/main/PRIVACY.md).

Use of ATLAS Desktop is governed by the [LICENSE](https://github.com/milivoja-labs/atlas-desktop/blob/main/LICENSE).
