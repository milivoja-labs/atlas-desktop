# Security — ATLAS Desktop

## Reporting a vulnerability

Please **don't** report security problems in a public issue.

Use GitHub's private reporting instead:
1. Open this repository's **Security** tab.
2. Click **Report a vulnerability**.

Only the ATLAS team can see these reports. Please include:
- the ATLAS version;
- your Windows version;
- steps to reproduce;
- what an attacker could do.

We'll acknowledge reports as soon as we can. This is a small team and an alpha, so we can't promise a fixed response time yet.

Supported version: **only the latest release** (currently v0.6.1-alpha).

## How ATLAS is built to protect you

- **Local services only.** ATLAS's background services (AI brain, speech recognition, voice, launcher control) listen on `127.0.0.1` only, so other computers on your network can't reach them. Each request must:
  - carry the right host name;
  - come from the ATLAS window;
  - include a secret token that is new every time ATLAS starts.

  Ollama, which runs the AI model, also listens only on `127.0.0.1` (its default). Like any Ollama installation, it doesn't require a token from other programs on the same PC.
- **No administrator rights.** Setup installs for your Windows user only: no services, drivers or system-wide changes. Microsoft's WebView2 installer, if needed on older Windows 10, may ask for permission on its own.
- **Checked downloads:**
  - **Python:** checked against a fixed SHA-256 fingerprint.
  - **Ollama:** its signature must be valid and from Ollama Inc.
  - **WebView2 installer:** its signature must be valid and from Microsoft.
  - **Python packages:** installed at exact, tested versions.
- **File safety.**
  - ATLAS opens only apps on an allow-list, and won't run command shells or scripts.
  - It changes or moves files only after you approve each change.
  - It doesn't serve files from outside your user folders.
- **No secrets inside.** This release's installer was scanned before publishing for keys, tokens, passwords, certificates, email addresses, personal data and development-PC paths. None were found.

## Known limitations

- **The installer and ATLAS are not code-signed.** Windows SmartScreen will warn about them. Verify each download against `SHA256SUMS.txt` from the release page (see [INSTALLATION.md](INSTALLATION.md#2-verify-the-download)). We never ask you to disable SmartScreen or antivirus.
- **Python packages are pinned by version, not by hash.** Setup relies on PyPI's and PyTorch's own download security.
- **ATLAS's background services are an alpha design.** They use a lightweight web server meant for local use only. Don't change ATLAS's network settings to expose them.
