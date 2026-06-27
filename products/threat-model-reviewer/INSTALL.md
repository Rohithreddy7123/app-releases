# Installing Threat Model Reviewer

Threat Model Reviewer is a **Windows desktop application**. Three download options are
attached to every release on the
**[releases page](https://github.com/Rohithreddy7123/app-releases/releases)** — pick one.

## System requirements

- **Windows 10 (1809 / build 17763) or Windows 11**, 64-bit (x64).
- ~400 MB free disk space.
- **No .NET install needed** — every download is self-contained (the .NET runtime is bundled).
- **Optional:** a **GitHub Copilot** subscription, only if you want the AI features. The
  app uses your signed-in seat; the deterministic review works fully offline without it.

---

## Option 1 — Portable (zip) — *simplest, recommended*

1. Download `ThreatModelReviewer-vX.Y.Z-win-x64-portable.zip`.
2. Right-click → **Properties** → tick **Unblock** (clears the "downloaded from the
   internet" mark), then **Extract All** to a folder you control (e.g. `C:\Apps\ThreatModelReviewer`).
3. Run **`ThreatModelReviewer.exe`**.

> Keep the files together — `ThreatModelReviewer.exe` needs the folder beside it
> (including `runtimes\win-x64\native\copilot.exe`, which powers the Copilot features).

## Option 2 — Installer (`Setup.exe`)

1. Download `ThreatModelReviewer-vX.Y.Z-setup.exe`.
2. Run it. It installs **per-user** (no administrator rights required), adds a Start-Menu
   shortcut, and registers an uninstall entry.
3. If **SmartScreen** shows "Windows protected your PC", click **More info → Run anyway**
   (the build isn't Authenticode-signed yet, so its reputation is still building).

## Option 3 — MSIX package — *experimental*

The MSIX is signed with a **self-signed** certificate, so you must trust it first:

1. Download `ThreatModelReviewer-vX.Y.Z-x64.msix` **and** `ThreatModelReviewer-publisher.cer`.
2. Right-click `ThreatModelReviewer-publisher.cer` → **Install Certificate** →
   **Local Machine** → **Place all certificates in the following store** →
   **Trusted People** → Finish. (This step needs administrator rights.)
3. Double-click the `.msix` and click **Install**.

> **Heads-up:** under MSIX the app runs in a packaged container. The Copilot SDK spawns a
> CLI child process and makes network calls, which can hit container/filesystem
> restrictions — so **AI features may be limited under MSIX**. For full Copilot support,
> prefer the **portable** or **installer** options.

---

## Signing in to GitHub Copilot (optional)

The first time you use an AI feature, the app uses your **GitHub Copilot** seat:

- If you're already signed in to Copilot on this machine (e.g. via the GitHub CLI or an
  IDE), it's picked up automatically.
- Otherwise, follow the in-app prompt to sign in.
- Prefer not to use Copilot? Open **AI provider** in the header to point at an
  OpenAI-compatible endpoint (Azure OpenAI / OpenAI / local), or just don't use the AI
  buttons — the verdict, score, and findings are computed deterministically without AI.

## Uninstalling

- **Portable:** delete the folder.
- **Installer:** *Settings → Apps → Threat Model Reviewer → Uninstall* (or the Start-Menu
  uninstall shortcut).
- **MSIX:** right-click the Start-Menu tile → **Uninstall**.

## Troubleshooting

See [FAQ.md](FAQ.md). Still stuck? Open an issue:
<https://github.com/Rohithreddy7123/app-releases/issues>.
