# Known issues — ATLAS Desktop v0.6.1-alpha

This is an alpha. These are the issues we know about. If you find something that isn't listed here, please [report it](https://github.com/milivoja-labs/atlas-desktop/issues/new/choose).

## Installing

- **The installer and ATLAS are not code-signed.** Windows SmartScreen will warn about an unrecognised app with an unknown publisher. Verify the SHA-256 checksum ([INSTALLATION.md](INSTALLATION.md#2-verify-the-download)). Signing is planned.
- **Large download.** Setup downloads about 12 GB (Python, Ollama, the AI model, speech recognition, the voice) and can take 30–90 minutes. Packages come from PyPI, PyTorch, Ollama and Hugging Face. If one of them is down, a step fails; press **Retry** later.
- **Fresh installs on many different PCs haven't been tested yet.** This release was tested on our development PC and preliminarily by a few testers. Installation reports are especially welcome.

## Hardware

- **8 GB NVIDIA cards haven't been measured.** ATLAS should work, using the same chat model as on 12 GB cards, with less room to spare.
- **Without an NVIDIA graphics card**, the AI runs on the processor (slow), and ATLAS speaks with the Windows voice.
- **AMD and Intel graphics** are treated as "no NVIDIA card".

## Voice and speech

- **The male and female voice settings currently sound the same.** ATLAS uses Chatterbox-Turbo's built-in voice for both. Separate recorded voices are planned.
- **Spoken replies are English.** Other languages may be understood and shown on screen, but the voice is English-only.
- **Talking over ATLAS to interrupt it** works on our development PC. It hasn't been tested across many headsets and speaker setups yet (Experimental).
- **Smooth voice** (Settings) waits for the whole reply before speaking: slower first sound (about 1.3 s instead of 0.7 s). Turn it on only if the sound crackles.
- Every spoken reply carries Resemble AI's inaudible **PerTh watermark**, which marks it as AI-generated speech. It's built into the voice model.

## Features

- **Conversations aren't kept after a restart.** What ATLAS *learned* about you is kept (memory), but the conversation itself starts fresh.
- **The Wi-Fi list in Settings is empty when Windows Location is off.** Recent Windows 11 builds only let apps scan for Wi-Fi networks with Location enabled (Windows Settings → Privacy & security → Location). Windows' own `netsh` behaves the same way.
- **Wi-Fi and Bluetooth connection, power actions, and headset unplug/replug recovery** are Experimental.
- **Mail** isn't available yet (Planned).
- **Web search** needs the internet and uses DuckDuckGo.

## Stability

- ATLAS restarts its own background services if they crash (up to 5 times). In earlier versions **ATLAS occasionally closed without an error** (rare, cause still being investigated). If it happens, start ATLAS again, and send us the logs (Settings → About → Send logs).

## Offline and network

- After setup, ATLAS works offline, except web search and websites.
- **On older Windows 10 PCs** without Microsoft WebView2, the first launch needs the internet to install it.
- The ATLAS screen loads its fonts from Google Fonts when online. Offline, it uses a system font. See [PRIVACY.md](PRIVACY.md).
