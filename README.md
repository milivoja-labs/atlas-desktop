# ATLAS Desktop

**A voice AI computer that runs entirely on your PC.** Talk to it, and it answers out loud in about 0.7 seconds. It works with your files and apps, and it remembers what matters to you. No cloud, no account with us, and it works offline after setup.

<p align="center">
  <a href="https://github.com/milivoja-labs/atlas-desktop/releases/tag/v0.6.1-alpha"><b>Download the Windows alpha</b></a> ·
  <a href="#what-you-can-say">What it does</a> ·
  <a href="#requirements">Requirements</a> ·
  <a href="https://github.com/milivoja-labs/atlas-desktop/discussions">Discussions</a> ·
  <a href="https://www.atlascomputers.ai">atlascomputers.ai</a>
</p>

> **Public alpha (v0.6.1).** It's an early test version with rough edges, released so people can try it and shape it. Needs Windows 10/11 and, for the full experience, an NVIDIA card with 8 GB or more. [Tell us how setup went →](https://github.com/milivoja-labs/atlas-desktop/issues/1)

---

## What you can say

| You say | ATLAS |
|---|---|
| "Summarise the documents in my Downloads folder." | Reads them and gives you a short spoken summary. |
| "Tidy up my Desktop." | Suggests a new folder layout and moves files only after you approve each change. |
| "Remind me at 5 to call Ana." | Sets the reminder. It still fires after a restart. |
| "I prefer short answers." | Remembers that, reads it back ("Is that right?") and uses it from then on. |
| "Why did you say that?" | Explains how it got to its answer. |
| "Open SolidWorks." / "Turn the volume down." | Opens apps and changes system settings. |

Everything above runs on your own PC: the AI model, speech recognition and the voice.

## Why ATLAS

Today you adapt to the computer: you learn each app, manage windows and connect everything yourself. ATLAS turns that around. It's a computer that learns how you work, remembers what matters and runs your software for you.

ATLAS Desktop is the software half, running as an app on Windows. A dedicated ATLAS computer is in development (you can [reserve one](https://www.atlascomputers.ai) for free).

## Download and install

1. Download **[`ATLAS_Setup_0.6.1_Alpha.exe`](https://github.com/milivoja-labs/atlas-desktop/releases/tag/v0.6.1-alpha)** (about 25 MB).
2. Optional: check it against [`SHA256SUMS.txt`](https://github.com/milivoja-labs/atlas-desktop/releases/tag/v0.6.1-alpha) ([how](INSTALLATION.md#2-verify-the-download)).
3. Run it. Windows SmartScreen will warn you because the installer isn't code-signed yet: click **More info → Run anyway**. Setup checks your PC first and needs no administrator rights.
4. Setup downloads the AI model, speech recognition and the voice (about 12 GB, 30–90 minutes).
5. Launch ATLAS and say hello.

Full guide and troubleshooting: [INSTALLATION.md](INSTALLATION.md).

## Requirements

| | Minimum | Recommended |
|---|---|---|
| System | Windows 10 (22H2) or 11, 64-bit, Intel or AMD | Windows 11 |
| Graphics | NVIDIA, 8 GB | NVIDIA, 12 GB or more |
| Memory | 16 GB RAM | 32 GB RAM |
| Disk | 30 GB free | |
| Audio | Microphone and speakers | A headset |

Without an NVIDIA card ATLAS still runs, but slowly, and it uses the Windows voice. Details: [SYSTEM_REQUIREMENTS.md](SYSTEM_REQUIREMENTS.md).

## What works today

**Available now**, tested on our development PC:
- Voice conversation with a local AI model (Whisper for speech, Ollama for chat, Chatterbox-Turbo for the voice)
- Memory that lasts across restarts, which you can check ("Is that right?") and question ("Why did you say that?")
- Files: browse, search, summarise and organise (each change needs your approval)
- Open apps; volume, sound devices and screen brightness
- Calendar and reminders
- 3D model viewer (STL, OBJ, 3MF, STEP)
- Music from your own Music folder
- Works offline after setup, except web search and websites
- Settings → About → Send logs, for bug reports

**Experimental**, built but not fully tested: interrupting ATLAS while it speaks, web search, one-click diagnostics, headset reconnection, Wi-Fi/Bluetooth and power actions, and recording your own voice for ATLAS.

**Next up:** a signed installer, conversation history across restarts, support for smaller graphics cards, separate male and female voices, and mail.

Known problems: [KNOWN_ISSUES.md](KNOWN_ISSUES.md).

## Help shape it

This alpha's biggest unknown is how setup goes on PCs other than ours. The most useful thing you can do is try it and tell us.

- **Installed it?** Add your GPU and how setup went to the [installation reports thread](https://github.com/milivoja-labs/atlas-desktop/issues/1), even if it all just worked.
- **Found a bug or missing feature?** [Open an issue](https://github.com/milivoja-labs/atlas-desktop/issues/new/choose). There are templates for bugs, installation problems and feature requests.
- **Have an idea or question?** Start a [discussion](https://github.com/milivoja-labs/atlas-desktop/discussions).

Please never upload passwords, personal documents or private conversations. Send logs creates a zip of logs and PC specs only, so look through it before you attach it. Report security problems privately: see [SECURITY.md](SECURITY.md).

## Privacy

Your data stays on your PC, in `%LOCALAPPDATA%\AtlasOS`. There's no telemetry, no analytics and no account with us. The few things that do use the internet, such as web searches you ask for, are listed in [PRIVACY.md](PRIVACY.md).

## Models

| Part | Model | Licence |
|---|---|---|
| Chat AI (picked for your graphics memory) | `qwen3-vl:4b-instruct` (8–12 GB), `qwen2.5:14b` (larger), `llama3.2:3b` (small cards) | Apache-2.0; Apache-2.0; Llama 3.2 Community License |
| Memory search | `embeddinggemma` | Gemma Terms of Use |
| Speech recognition | Whisper large-v3-turbo (faster-whisper) | MIT |
| Voice | Chatterbox-Turbo by Resemble AI | MIT |

Every model keeps its own licence. The full list ships with ATLAS as `THIRD_PARTY_NOTICES.txt`.

## About this repository

This repository holds the installer releases, documentation and issue tracking. **ATLAS Desktop is closed-source for now.** Use of it is governed by the [LICENSE](LICENSE).
