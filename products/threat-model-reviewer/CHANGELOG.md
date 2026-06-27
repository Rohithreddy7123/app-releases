# Changelog

All notable changes to **Threat Model Reviewer** are documented here.
The format is based on [Keep a Changelog](https://keepachangelog.com/), and the
project aims to follow [Semantic Versioning](https://semver.org/).

## [1.0.0] — 2026-06-27

First public release.

### Added
- **Deterministic review** of Microsoft Threat Modeling Tool `.tm7` files (and OWASP
  Threat Dragon `.json`): a stamped **NOT READY / READY-WITH-NOTES** verdict plus a
  **0–100 review score** with a letter grade across the Four-Question dimensions. The
  verdict is never produced by AI.
- **~70 rubric checks** spanning structural completeness, STRIDE-per-element coverage,
  triage & mitigation quality, trust-boundary/identity, data protection, network,
  logging/detection, deprecated cryptography, software supply chain, mismodeled
  stencils, and a deep **AI/agentic** surface (OWASP LLM Top 10 2025, OWASP Agentic,
  MITRE ATLAS). Each finding cites authoritative references (OWASP, MITRE, CWE,
  Microsoft Learn) and ships built-in "what it means / how to fix" guidance.
- **STRIDE-per-element coverage matrix**, **Threats-by-interaction** breakdown
  (worst-gap-first), and a deterministic **Framework coverage** scorecard
  (OWASP Top 10 2021 + STRIDE).
- **Fix / remediation** with round-trip write-back to a valid `.tm7` (add missing
  threats, triage Not-Started, draft justifications, fill out-of-scope reasons).
- **Create** a new `.tm7` from a guided wizard or from Copilot DFD extraction.
- **Copilot enrichment** (optional, advisory): explain findings, deep analysis (DREAD /
  attack tree / Gherkin), draft fixes, whole-model critique, framework-gap analysis, and
  interaction-triage planning — each independent and powered by your GitHub Copilot seat.
- **Exports**: HTML, PDF, Markdown, CSV, JSON, SARIF reports + issue-tracker work items
  (GitHub / Azure DevOps / Jira / JSON), with an optional pre-export "include Copilot
  guidance / deep analysis" step.
- **Packaging**: portable self-contained `.exe` (zip), Inno Setup installer, and a signed
  MSIX package.

[1.0.0]: https://github.com/Rohithreddy7123/app-releases/releases/tag/threat-model-reviewer-v1.0.0
