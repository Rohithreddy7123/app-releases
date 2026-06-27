# FAQ & Troubleshooting

### What file types can it review?
Microsoft Threat Modeling Tool **`.tm7`** files, and OWASP **Threat Dragon `.json`**.

### Do I need .NET installed?
No. Every download is **self-contained** — the .NET runtime is bundled.

### Do I need GitHub Copilot?
No. The **verdict, 0–100 score, and findings are fully deterministic** and work offline.
Copilot only powers the optional, advisory enrichments (explain, deep analysis, draft
fixes, critique, gap analysis). You can also point at an OpenAI-compatible endpoint via
**AI provider** in the header.

### Is my threat model sent anywhere?
The deterministic review is **100% local**. AI features send only **minimal, redacted**
context (finding text, a DFD summary) to **your** Copilot seat — never the raw `.tm7`, and
secrets are stripped by a redaction pass first.

### Windows SmartScreen says "Windows protected your PC".
The portable `.exe` and installer aren't Authenticode-signed yet, so SmartScreen warns
until reputation builds. Click **More info → Run anyway**. (Production code-signing is
planned.)

### The MSIX won't install / AI features don't work in the MSIX.
- Install the included **`ThreatModelReviewer-publisher.cer`** into **Trusted People**
  (Local Machine) first — see [INSTALL.md](INSTALL.md).
- Under MSIX the app runs in a container that can restrict the Copilot CLI child process,
  so **AI may be limited**. Use the **portable** or **installer** download for full Copilot
  support.

### "Copilot CLI runtime not found" / AI buttons fail in the portable build.
Keep the extracted folder intact — `ThreatModelReviewer.exe` needs the files beside it,
including `runtimes\win-x64\native\copilot.exe`. Don't copy the `.exe` out on its own.

### Why is the verdict NOT READY even though the score is high?
The score measures **maturity**; readiness is a separate **gate**. Any must-fix (gating)
finding — e.g. an un-triaged threat — forces NOT READY, just like a Microsoft SDL reviewer
would. Clear the gating findings (the Fix tab automates most) and the verdict flips.

### A finding looks wrong / too noisy.
Open an issue with the check ID and a sanitized snippet:
<https://github.com/Rohithreddy7123/app-releases/issues>. Many checks are advisory and use
deliberately tight triggers; we tune them from real reports.

### Can I add my own organization's checks?
Yes — implement `IRubricCheck` and compose it:
```csharp
var engine = RubricEngine.WithAdditionalChecks(new[] { new MyOrgPolicyCheck() });
```

### How do I report a bug or request a feature?
Use the issue templates at
<https://github.com/Rohithreddy7123/app-releases/issues/new/choose>.
