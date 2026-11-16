# ATLAS Desktop

**A computer that grows with you.**

ATLAS Desktop is an experimental, local-first AI computing experience for Windows. You talk to it, and it answers out loud. It works with your files and apps. It starts knowing nothing about you and learns as you use it. The AI, speech recognition and voice all run on your own PC. After setup, everyday use doesn't need the internet.

> **Public alpha: a test version.** Not everything is here yet, and not everything is perfect. That's on purpose.
> ATLAS is shaped by the people who use it. Tell us what works, what doesn't, and what you wish it did: [send feedback](https://github.com/milivoja-labs/atlas-desktop/issues/new/choose).
> We read every report and improve ATLAS release by release.
> ATLAS Desktop is an app that runs on Windows. It does not replace Windows.
> **Hardware not included:** ATLAS computers are in development and not shipping yet.

<!-- SCREENSHOT PLACEHOLDER: replace with a real capture before publishing (see docs/screenshots/README.md) -->
*Screenshot coming soon.*

---

## Download

**[Latest release → v0.6.1-alpha](https://github.com/milivoja-labs/atlas-desktop/releases/tag/v0.6.1-alpha)**: `ATLAS_Setup_0.6.1_Alpha.exe`, about 25 MB. Setup downloads the rest, about 12 GB.

Before running it, verify the file's SHA-256 checksum against [`SHA256SUMS.txt`](https://github.com/milivoja-labs/atlas-desktop/releases/tag/v0.6.1-alpha). How to do that: [INSTALLATION.md](INSTALLATION.md#2-verify-the-download).

**The installer is not code-signed yet**, so Windows SmartScreen will warn you about an unrecognised app. See [Known issues](KNOWN_ISSUES.md).

## What it can do today

Status key: **Available now** = works and was tested on our development PC. **Experimental** = built, but not fully tested yet. **Planned** = not in this release.

| Feature | Status |
|---|---|
| Talk to ATLAS with your voice; speech recognition runs locally (Whisper) | Available now |
| Spoken replies with a natural local voice (Chatterbox-Turbo, NVIDIA graphics cards) | Available now |
| Chat with a local AI model (runs through Ollama on your PC) | Available now |
| Memory that lasts: ATLAS remembers what you tell it across restarts, reads back what it learned ("Is that right?"), and explains its answers ("Why did you say that?") | Available now |
| Files: browse, search, summarise documents, and organise folders after you approve each change | Available now |
| Open apps; change volume, sound devices and screen brightness | Available now |
| Calendar and reminders (reminders survive a restart) | Available now |
| 3D model viewer (STL, OBJ, 3MF, STEP) | Available now |
| Play music from your own Music folder | Available now |
| Works offline after setup (except web search and websites) | Available now |
| "Send logs": saves a log zip to your Desktop for bug reports | Available now |
| Interrupt ATLAS by talking while it speaks | Experimental |
| Web search, answered by ATLAS, plus "open it" to see the page | Experimental |
| One-click diagnostics in Settings (graphics card, AI model, speech, voice, microphone) | Experimental |
| Recovering when you unplug and replug a headset | Experimental |
| Wi-Fi and Bluetooth connection, power actions | Experimental |
| Your own voice for ATLAS (Settings → Record my voice) | Experimental |
| Separate male and female voices | Planned |
| Mail | Planned |
| Conversation history that survives a restart | Planned |
| Signed installer | Planned |

## Requirements (summary)

- Windows 10 (22H2) or Windows 11, 64-bit, on an Intel or AMD processor
- **NVIDIA graphics card with 8 GB or more** (12 GB recommended) for the full experience
- 16 GB RAM (32 GB recommended), 30 GB free disk space
- Internet during setup: about 12 GB of downloads, roughly 30–90 minutes
- A microphone and speakers (a headset works best)
- No administrator rights needed

Without an NVIDIA card, ATLAS still runs, but slowly, and it speaks with the Windows voice. Details: [SYSTEM_REQUIREMENTS.md](SYSTEM_REQUIREMENTS.md).

## Install in short

1. Download `ATLAS_Setup_0.6.1_Alpha.exe` and verify its checksum.
2. Run it. Setup checks your PC against the minimum requirements, then installs per user (no administrator rights).
3. Wait while it downloads the AI model, speech recognition and the voice.
4. Launch ATLAS, create your account (it stays on this PC), and say hello.

Step-by-step guide with troubleshooting: [INSTALLATION.md](INSTALLATION.md).

## The local models

| Part | Model | Licence |
|---|---|---|
| Chat AI, chosen for your graphics memory | `qwen3-vl:4b-instruct` on 8–12 GB cards; `qwen2.5:14b` on larger cards; `llama3.2:3b` on small cards | Apache-2.0; Apache-2.0; Llama 3.2 Community License |
| Memory search | `embeddinggemma` | Gemma Terms of Use |
| Speech recognition | Whisper large-v3-turbo (faster-whisper) | MIT |
| Voice | Chatterbox-Turbo by Resemble AI, with its built-in voice | MIT |

Every model keeps its own licence. The full list ships with ATLAS as `THIRD_PARTY_NOTICES.txt`.

## Offline

After setup, talking, answers, the voice, memory, files, calendar, reminders and apps all work without internet. Offline, these don't work:
- web search and websites;
- downloading new models;
- on older Windows 10 PCs, the first launch, if Microsoft's WebView2 component still has to be installed.

## Privacy

ATLAS keeps your data on your PC, in `%LOCALAPPDATA%\AtlasOS`. It has no telemetry, no analytics and no account with us. A few things do reach the internet, such as web searches you ask for and font downloads. All of them are listed in [PRIVACY.md](PRIVACY.md).

## Known issues

Read [KNOWN_ISSUES.md](KNOWN_ISSUES.md) before installing. The main ones:
- the installer is unsigned;
- 8 GB graphics cards haven't been measured yet;
- the male and female voice settings currently sound the same.

## Report a bug or ask for a feature

Use [GitHub Issues](https://github.com/milivoja-labs/atlas-desktop/issues/new/choose). There are templates for bugs, installation problems and feature requests.

**Please never upload passwords, personal documents or private conversations.** Settings → About → Send logs creates a zip of logs and PC specs only; look through it before attaching it.

Security problems: see [SECURITY.md](SECURITY.md). Please don't post them as public issues.

## Roadmap (short)

- Signed installer
- Separate recorded male and female voices
- Conversation history across restarts
- Support for smaller graphics cards
- Mail

## About

ATLAS is being built at **[atlascomputers.ai](https://www.atlascomputers.ai)**, where you can also reserve ATLAS hardware. Reservations are free and need no payment. The hardware is in development and not shipping yet.

This repository holds the installer releases, documentation and issue tracking. ATLAS's source code is not published here. Use of ATLAS Desktop is governed by the [LICENSE](LICENSE).
