---
language: en
license: cc-by-4.0
tags:
- open-source-compliance
- governance
- software-forensics
- license-violations
- attribution-laundering
pretty_name: OSCAR (Open Source Compliance & Attribution Records)
size_categories:
- n < 1K
---

# OSCAR: Open Source Compliance & Attribution Records

This repository serves as a public archive for documenting instances of license non-compliance, the removal of original authorship metadata, conflict of interest and the externalization of technical debt within open-source projects.

## Purpose
The integrity of Open Source software relies on the preservation of provenance. Under licenses such as the **GNU General Public License (GPL)**, the requirement to credit original authors and maintain a clear record of changes is a legal mandate, not an optional courtesy.

OSCAR monitors four core pillars of project health:

* **License Compliance and Stability:** Tracking unauthorized license versioning and version changes that occur without the consensus of copyright holders, creating legal uncertainty for downstream users.
* **Metadata Integrity:** Identifying the systematic decoupling of contributed logic from its original iterative history through methods such as **Direct Injection** and **Commit Laundering**, which masks the true provenance of the software and effectively falsifies the historical record of a project's development.
* **Conflict of Interest:** Identifying instances where project-branded infrastructure, social capital, or centralized attribution is utilized to solicit monetary gains at the detriment of the community at large. This pillar documents the correlation between the suppression of community authorship and the promotion of private revenue channels, establishing a documented incentive for non-transparent project governance.
* **Ecosystem Integrity:** Documenting instances where internal technical debt and deprecated architectural models are externalized onto upstream build systems and tools, forcing the wider FOSS ecosystem to accommodate substandard maintenance practices.

By treating the Git ledger as disposable and the license as a cosmetic suggestion, projects produce a form of **Governance Slop**, a state where the legal, technical, and historical record of the software is as unreliable as unverified code itself.

## Methodology
Entries in this archive under incidents are verified by comparing:
* **Original Work:** Publicly available Pull Requests, contributor branches, or independent repositories.
* **Integrated Work:** Commits pushed to an organization's primary repository.
* **The Discrepancy:** Evidence of line-by-line logic duplication where the original commit history has been discarded and replaced with maintainer authorship.

Entries in this archive under audits are analyses based on synthesized incident data and project governance history.

## Current Archives
The following projects have documented instances of metadata tampering, architectural regression, or license instability:

### [cMaNGOS](./projects/github/cmangos)

---

## Notice
This repository is an independent archive. It is not affiliated with, endorsed by, or representative of the organizations documented herein. All data is sourced from public version control ledgers and is presented for the purpose of transparency, education, and license compliance oversight. 

References to specific project names, trademarks, or codebases are used under **nominative fair use** for the sole purpose of identifying the subjects of technical analysis. 

### Licensing
The original analytical text, reports, and metadata structures in this repository are provided for purposes such as **criticism, comment, and scholarship**, and are licensed under **Creative Commons Attribution 4.0 International (CC-BY-4.0)**. 

**Scope:** This license does not apply to third-party source code referenced via external links or archived mirrors. OSCAR strictly provides analysis and deep-links to public ledgers for evidentiary purposes and does not claim ownership of the referenced codebases.
