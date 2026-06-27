# app-releases

**Download hub, documentation, and issue tracker** for Windows apps by
[@Rohithreddy7123](https://github.com/Rohithreddy7123). Source code lives in private repos;
this repo hosts the **releases**, the **docs**, and the **issues**.

## Apps

| App | What it does | Docs | Latest |
| --- | --- | --- | --- |
| **Threat Model Reviewer** | Reviews, fixes, analyzes & creates Microsoft Threat Modeling Tool (`.tm7`) threat models, powered by your GitHub Copilot seat. The verdict & 0–100 score are deterministic. | [docs](products/threat-model-reviewer/) | [Releases ›](https://github.com/Rohithreddy7123/app-releases/releases) |

> More apps will be added here over time, each under `products/<app>/` with its own docs and
> its own product-prefixed release tags.

## Download

Go to **[Releases](https://github.com/Rohithreddy7123/app-releases/releases)** and pick the
asset for the app and format you want. Releases are tagged `‹app›-v‹x.y.z›`
(e.g. `threat-model-reviewer-v1.0.0`). Every Windows build is **self-contained** — no .NET
install required.

## Report an issue / request a feature

Open one here — it'll ask which app it's about:
**[New issue ›](https://github.com/Rohithreddy7123/app-releases/issues/new/choose)**.

For **security vulnerabilities**, please use
[private reporting](https://github.com/Rohithreddy7123/app-releases/security/advisories/new)
instead of a public issue.

## License

Docs and release assets in this repo are under the [MIT License](LICENSE).
