# Installing ATLAS Desktop (v0.6.1-alpha)

This guide is for everyone. No technical knowledge needed.

**Quick start:**
1. check your PC (part 1);
2. download Setup and check it (part 2);
3. run Setup (part 3);
4. create your account and say "Hello, Atlas" (part 5).

Your first spoken answer comes a few seconds after the first start finishes loading.

---

## 1. Check your PC

| | Minimum | Recommended |
|---|---|---|
| Windows | Windows 10 (22H2) or Windows 11, 64-bit, Intel or AMD processor | Windows 11 |
| Graphics card | NVIDIA with 8 GB | NVIDIA with 12 GB, current driver |
| Memory (RAM) | 16 GB | 32 GB |
| Free disk space | 30 GB | 50 GB |
| Internet | During setup (about 12 GB to download) | A fast connection |
| Sound | Microphone and speakers | A headset |

- **No NVIDIA card?** ATLAS still installs and runs, but answers are slow and it speaks with the Windows voice.
- **ARM PCs** (e.g. Snapdragon) aren't supported.

More detail: [SYSTEM_REQUIREMENTS.md](SYSTEM_REQUIREMENTS.md).

Before installing:
- update your NVIDIA driver (NVIDIA App, or nvidia.com/drivers);
- close games and other heavy programs.

## 2. Verify the download

1. Download `ATLAS_Setup_0.6.1_Alpha.exe` and `SHA256SUMS.txt` from the [Releases page](https://github.com/milivoja-labs/atlas-desktop/releases/tag/v0.6.1-alpha). Only download ATLAS from there.
2. Open **PowerShell**: press the Windows key, type `PowerShell`, press Enter.
3. Go to your Downloads folder and compute the file's fingerprint:

   ```powershell
   cd $HOME\Downloads
   Get-FileHash .\ATLAS_Setup_0.6.1_Alpha.exe -Algorithm SHA256
   ```

4. Compare the long `Hash` value with the line for `ATLAS_Setup_0.6.1_Alpha.exe` in `SHA256SUMS.txt`. Letter case doesn't matter.
   - **They match:** the file is exactly what we published.
   - **They don't match:** don't run it. Delete it, download again, and [tell us](https://github.com/milivoja-labs/atlas-desktop/issues/new/choose) if it still doesn't match.

### About the Windows SmartScreen warning

This alpha installer is **not code-signed**. Windows SmartScreen protects you from unrecognised programs, so when you open Setup it will most likely show **"Windows protected your PC"**, with the publisher listed as unknown. That is how Windows treats any new program from a publisher without a code-signing certificate and a download history.

What that means for you:
- The checksum in step 2 is how you confirm the file is exactly what we published.
- Whether to run unsigned software is your decision. If you're not comfortable with it, or your work or school PC doesn't allow it, please wait for a signed release, and don't change any security settings to get around it.
- We never ask you to turn off antivirus or SmartScreen.

## 3. Run Setup

1. Double-click `ATLAS_Setup_0.6.1_Alpha.exe`.
2. Setup shows the **minimum requirements**, each marked:
   - **✓** your PC meets it;
   - **!** your PC falls short (Setup explains below the list).

   If it says "Atlas OS can't be installed on this PC", your PC can't run ATLAS.
3. **Install location:** keep the default (`%LOCALAPPDATA%\Atlas OS`) or click **Browse**.
4. Click **Install**. Setup installs for your Windows user only and needs no administrator rights.

## 4. What Setup downloads

Each step shows its own progress. If one fails (usually the internet), press **Retry**: Setup carries on where it stopped.

| Step | What it is | Size (approx.) |
|---|---|---|
| ATLAS program files | ATLAS itself, Start menu and desktop shortcuts, an entry in Windows Settings → Apps | 30 MB |
| Python 3.13 | Installed for ATLAS only: not added to your PATH, doesn't affect other programs. Checked against python.org's fingerprint. | 30 MB |
| Brain and speech-to-text packages | ATLAS's own Python environment, exact tested versions | 0.2 GB |
| Ollama | The program that runs the AI model; skipped if you already have it. Checked to be signed by Ollama Inc. | 1.6 GB |
| AI model | The chat model that fits your graphics card (12 GB card: `qwen3-vl:4b-instruct`) | 2–9 GB |
| Memory search model | `embeddinggemma` | 0.6 GB |
| Speech recognition | Whisper large-v3-turbo | 1.6 GB |
| Voice (Chatterbox-Turbo) | NVIDIA only: the voice and its PyTorch environment | 5.5 GB |

When it finishes, you'll see **"Atlas OS is installed."** Click **Launch**, or use the desktop shortcut later.

The install log is at `<install folder>\atlas-os\launcher-logs\install.log`.

## 5. First start

1. ATLAS opens full screen. The first start can take up to a minute while the AI and voice load.
   - On older Windows 10 PCs without Microsoft's WebView2 component, ATLAS installs it first (needs internet). It runs Microsoft's installer only if Windows confirms it is signed by Microsoft.
2. **Create your account:** a name and a password of **at least 6 characters**, typed twice. Each person who uses the PC can create their own account. Accounts and passwords stay on this PC.
3. ATLAS introduces itself and asks what to call you and how you like to be spoken to.
4. **Microphone:** if Windows asks whether ATLAS may use the microphone, allow it. If ATLAS doesn't hear you:
   - check Windows Settings → Privacy & security → Microphone → "Let desktop apps access your microphone";
   - pick your microphone in ATLAS Settings → Volume.
5. Say **"Hello, Atlas."** It answers out loud.

**Check everything at once:** say "open settings" (or press **Ctrl+,**), scroll to **About** and click **Check everything (diagnostics)**. Speak during the 2-second microphone test.

**Handy keys:**
- **Shift:** hold to talk.
- **/:** type instead of talking.
- **F1:** all shortcuts.

## 6. Using it offline

After setup, ATLAS works without internet: talking, answers, the voice, memory, files, calendar, reminders and apps.

Without internet you can't:
- search the web or open websites;
- download new models.

## 7. Updating

Run a newer Setup over your current installation. Your accounts, memory, calendar, notes and settings are kept. Unchanged parts are skipped, so updates are faster than the first install.

## 8. Troubleshooting

| Problem | What to do |
|---|---|
| The checksum doesn't match | Don't run the file. Download again from the Releases page. |
| A Setup step fails | Check your internet connection and press **Retry**. Details are in `install.log`. |
| Stuck on the start screen | Wait two minutes. Then close ATLAS with **Ctrl+Shift+Q** and start it again. |
| ATLAS doesn't hear you | Run diagnostics; check the Windows microphone permission and the microphone in ATLAS Settings → Volume. |
| No sound, or a robotic voice | Run diagnostics; check the sound output in Settings. Turn **Smooth voice** on if the sound crackles. |
| Very slow answers | Run diagnostics: the AI model should say "on the graphics card". Close games and restart ATLAS. |
| The Wi-Fi list in Settings is empty | Windows only lets apps see Wi-Fi networks when **Location** is on (Windows Settings → Privacy & security → Location). |
| ATLAS closed by itself | Start it again. ATLAS restarts its own services automatically and logs what happened. |

## 9. Collecting logs for a bug report

1. ATLAS Settings → About → **Send logs**.
2. A zip named `ATLAS-logs-<date>.zip` appears on your Desktop. Nothing is uploaded.
3. The zip holds ATLAS's log files and your PC's specs only: no memory, notes or conversations. Open it and look through it before attaching it to a [GitHub issue](https://github.com/milivoja-labs/atlas-desktop/issues/new/choose).

## 10. Uninstalling

Windows Settings → Apps → **Atlas OS** → **Uninstall**. You're asked separately:
- whether to **delete your data** (accounts, memory, notes, logs). "No" keeps it for a later reinstall;
- whether to **delete the downloaded AI models** (frees many GB).

Ollama stays installed. Remove it separately in Apps if you want.

Your data lives in `%LOCALAPPDATA%\AtlasOS`, separate from the program. Notes are ordinary files in `Documents\ATLAS Notes`; uninstalling leaves them alone.
