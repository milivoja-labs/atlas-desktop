# Privacy — ATLAS Desktop v0.6.1-alpha

ATLAS is local-first. The AI, speech recognition, the voice and your memory all run on your own PC.

**What ATLAS doesn't do:**
- It has **no telemetry and no analytics**.
- It sends **no usage data, crash reports or recordings** to us.
- It has **no account with us**: your ATLAS account and password exist only on your PC.

## What stays on your PC

Everything ATLAS keeps about you is stored in `%LOCALAPPDATA%\AtlasOS` on your PC:
- your account;
- what ATLAS has learned about you (memory);
- calendar, reminders and settings;
- logs.

It's separate from the program folder, so it survives updates, and ATLAS makes a local backup of it on every start. Notes you write in ATLAS are saved as ordinary files in `Documents\ATLAS Notes`.

- **Your voice:** what you say is turned into text on your PC and isn't saved as audio. If you record your own voice for ATLAS (Settings → Record my voice), that clip is kept in your data folder.
- **Conversations:** kept in the ATLAS window only while it's open, never saved to disk or sent anywhere.
- **Files:** ATLAS works with files in the folders you open in it or give it access to. It reads them on your PC, and it changes or moves files only after you approve each change.

## When ATLAS uses the internet

ATLAS is not fully offline. This is every case we know of.

**During setup** (one time), Setup downloads from:
- **python.org:** Python, checked against a fixed SHA-256 fingerprint;
- **PyPI and download.pytorch.org:** Python packages, exact versions;
- **ollama.com:** Ollama, checked to be signed by Ollama Inc.; plus the AI models from Ollama's registry;
- **huggingface.co:** speech recognition and voice models;
- **Microsoft:** the WebView2 component, if your PC doesn't have it (older Windows 10). It's run only if Windows confirms it's signed by Microsoft.

**While you use ATLAS:**
- **Web search:** when you ask ATLAS to search, your search words go to **DuckDuckGo**.
- **Websites:** when you ask ATLAS to open a website or a map, that site loads as in any browser.
- **Fonts:** when online, the ATLAS screen loads its two fonts (Space Grotesk and Inter) from **Google Fonts**. As with any website that uses them, Google receives your IP address and a standard browser request. No ATLAS content is sent. Offline, ATLAS uses a system font.
- **Speech recognition start-up:** when online, the speech-recognition component checks **Hugging Face** for its model files at start (a standard model-download check; nothing you say is sent). Offline, it uses the copy on your PC.
- **Ollama:** Ollama is a separate program with its own update checks and [privacy policy](https://ollama.com/privacy).

The services ATLAS runs in the background listen only on your own PC (`127.0.0.1`). They can't be reached from the network. See [SECURITY.md](SECURITY.md).

## Bug reports

**Send logs** (Settings → About) saves a zip to your Desktop. **Nothing is uploaded.** The zip holds:
- ATLAS's log files, with anything you said and anything ATLAS learned about you removed;
- your PC's specs (Windows version, graphics card, memory).

It may still contain file or app names from things you asked ATLAS to do, so **please look through it before attaching it** to a public GitHub issue. Never post passwords, personal documents or private conversations in an issue.

## Generated speech

Every spoken reply carries Resemble AI's inaudible **PerTh watermark**, built into the Chatterbox-Turbo voice model. It marks the audio as AI-generated. It holds no information about you.

## Deleting your data

- **Uninstall** (Windows Settings → Apps → Atlas OS) asks whether to delete your data and whether to delete the downloaded AI models.
- You can also delete `%LOCALAPPDATA%\AtlasOS` yourself while ATLAS is closed. Notes in `Documents\ATLAS Notes` are your own files; delete them like any other.
- Inside ATLAS you can correct or forget individual things it learned.

## Questions

Ask through [atlascomputers.ai](https://www.atlascomputers.ai) or open a [GitHub issue](https://github.com/milivoja-labs/atlas-desktop/issues/new/choose). Don't include personal data.

*This notice describes ATLAS Desktop v0.6.1-alpha and will be updated with each release.*
