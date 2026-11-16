# System requirements — ATLAS Desktop v0.6.1-alpha

| | Setup refuses | Setup warns | Minimum | Recommended |
|---|---|---|---|---|
| **Windows** | Older than Windows 10 | Windows 10 builds older than 17763; ARM PCs | Windows 10 (22H2) or Windows 11, 64-bit, Intel or AMD processor | Windows 11 |
| **Graphics card** | — | No NVIDIA card; under 8 GB graphics memory; NVIDIA driver older than R570 | NVIDIA with 8 GB | NVIDIA with 12 GB and a current driver |
| **Memory (RAM)** | — | Under 16 GB | 16 GB | 32 GB |
| **Free disk space** | Under 20 GB | Under 30 GB | 30 GB | 50 GB |
| **Internet** | — | — | During setup (about 12 GB of downloads) | A fast connection: setup takes roughly 30–90 minutes |
| **Sound** | — | — | Microphone and speakers | A headset |
| **Account rights** | — | — | A normal Windows user; no administrator rights | — |

## What you get on different PCs

| PC | AI chat model | Voice | Speed |
|---|---|---|---|
| NVIDIA, 12 GB or more | `qwen3-vl:4b-instruct` (larger cards: `qwen2.5:14b`) | Chatterbox-Turbo | About 0.7 s from when you stop talking to ATLAS's first word (median of 20 turns on an RTX 4070 SUPER, 12 GB) |
| NVIDIA, 8 GB | `qwen3-vl:4b-instruct` | Chatterbox-Turbo | **Not measured yet** |
| NVIDIA, under about 7 GB | `llama3.2:3b` | Chatterbox-Turbo if it fits | Not measured |
| No NVIDIA card (AMD, Intel or none) | `llama3.2:3b` on the processor | Windows voice | Slow; not recommended for this alpha |

ATLAS reserves about 4.5 GB of graphics memory for speech recognition and the voice, and picks the largest chat model that fits in the rest.

## Measured on our development PC

Windows 11, RTX 4070 SUPER 12 GB, 64 GB RAM. 20 voice turns with the internet blocked:
- end-to-end median **0.70 s**, 90th percentile 0.99 s;
- graphics memory peak **10.5 of 12 GB** with all models loaded;
- RAM: voice about 3.3 GB, speech recognition about 0.8 GB, AI model process about 2.2 GB.

These are results from one PC. Yours may differ.

## Disk space after installation

Roughly 15–25 GB, depending on the chat model:
- the AI models live in Ollama's folder;
- speech recognition and the voice are cached in your user profile;
- ATLAS's own Python environments sit in the install folder.

## Not supported in this alpha

- Windows on ARM
- macOS and Linux
- Running without a microphone (you can type, but ATLAS is built around voice)
