# OSCAR Meta Audit: Systematic Metadata Removal, Attribution Laundering, and Financial Conflict of Interest (2016 to 2026)

**Project:** cMaNGOS
**Primary Actors:** killerwife (Maintainer), cyberium (Project Leadership)  
**Subject:** Analysis of Recurring GPLv2/GPLv3 Compliance Failures and Monetary Incentives

---

## Executive Summary
This document synthesizes incident reports, license audits, and financial evidence. The data demonstrates a recurring **Standard Operating Procedure (SOP)** in project governance. Over a ten-year period, high-value community contributions have been intentionally decoupled from original authorship metadata to centralize credit within a closed circle of maintainers. The removal of authorship metadata coincides with a documented financial incentive, as the primary maintainer utilizes a project-branded profile to solicit personal donations. Furthermore, the project has engaged in unauthorized license versioning and expressed a documented apathy toward legal compliance, viewing the GPL as a cosmetic suggestion rather than a binding legal constraint.

## The "Stall, Steal, and Smother" Workflow
The analysis of documented Incident Reports identifies a recurring three-stage lifecycle for high-value community contributions:

* **Functional Stagnation:** A contributor submits a high value Pull Request (PR). The PR is either ignored for years, publicly questioned on utility, or withheld for political reasons, despite having technical approval.
* **Metadata Extraction:** Technical logic is manually re-integrated into maintainer-owned commits or branches, effectively decoupling the technical progress from the original Git ledger.
* **Administrative Shielding:** When the metadata removal is identified, project leadership (**cyberium**) provides administrative cover. Tactics include claiming a different source, citing personal copy exceptions for public branches, or using administrative power to silence dissent.

## Comparative Audit of Systematic Violations

| Incident | Primary Tactic | Maintainer Action (killerwife) | Monetary/Governance Impact |
| :--- | :--- | :--- | :--- |
| **PR #193 (2016)** | **Source Diversion** | Re-implemented 2FA logic under a single commit, stripping 11 original commits. | Centralized "security expert" status on a profile used for financial solicitation. |
| **PR #334 (2018)** | **Political Stalling** | Stalled an approved SQL refactor for 9 months before re-committing identical logic. | Claimed "Core Developer" credit for structural database research performed by a third party. |
| **PR #520 (2026)** | **Manual Re-typing** | Re-typed 14 commits of PetAI logic into a WIP branch under his own name. | Falsified record of high-frequency output; utilized the "Fix it Later" trap to silence the original author. |
| **Meson #12821 (2026)** | **Technical Externalization** | Attempted to force legacy path-crawling for 2017 dependencies onto upstream. | Defended legacy models to maintain a status quo that avoids modern, portable peer-review. |

## Monetary Conflict of Interest: Branding and Solicitation
Analysis of the maintainer’s public profile reveals a long-standing financial incentive for the centralization of attribution.

* **Branded Revenue Channel:** Historical records show a transition from a personal PayPal handle (`paypal.me/killerwife`) in 2020 to a project-branded handle (`paypal.me/killerwifeatcmangos`) by 2026.
* **The Productivity-Donation Link:** By re-typing community logic into personal commits, the maintainer creates a statistically skewed record of productivity. This "marketable" progress is used to solicit personal funds for "ventures in wow-emu" on a profile bio.
* **Incentive to Launder:** The existence of a project-branded revenue stream creates a documented incentive to delay or bypass standard Pull Request merging. This ensures that major architectural progress is attributed solely to the individual receiving the funds.

## License Instability and Governance Apathy
Analysis of repository history between 2017 and 2019 reveals a pattern of unauthorized "License Flip-Flopping."

* **Unauthorized Downgrade:** Leadership executed a downgrade from GPLv3 back to GPLv2. Legally, code contributed under GPLv3 cannot be reverted to GPLv2 without explicit permission from every contributor during that window.
* **The Dependency Paradox:** Leadership justified the downgrade by citing third party code compatibility. However, the dependencies in question were already licensed under "GPLv2 or later," which explicitly allows those dependencies to be used within a GPLv3 project. By "downgrading" to comply with the dependency, leadership actually chose to violate the primary project license to solve a non-existent legal conflict.
* **Legal Fog:** In 2019, it was documented ([Issue #1825](https://github.com/cmangos/issues/issues/1825) - [Archived](https://web.archive.org/web/20260329081639/https://github.com/cmangos/issues/issues/1825)) that the project's NEWS.md, README, and LICENSE files were in direct conflict, referencing non-existent files (e.g., COPYING) and stating incorrect license versions. This creates a state of Legal Fog where contributors and users cannot verify the actual terms of distribution.

### Documented Admissions of Non-Compliance
* **The "Nobody Will Sue" Defense (cyberium, 2017):** "i dont care much about license because i personally consider everyone can/are already doing what they want with an open-source software that no authors will engage any legal proceeding."
* **The "Holiday Priority" Dismissal (xfurry, 2017):** "Guys, I think there are more important topics to take care of, other than licenses (for example summer holiday)... I don't think that any of the authors will actually care if you change one open source license with another open source license (I personally don't)."

---

## Analysis of Project Governance
The recurring nature of these events involving the same maintainer and the same leadership indicates a willful bypass of **GPLv2 Sections 1 and 2**. 

* **The "History Repeating" Admission:** In 2026, leadership stated that the conflict felt like history repeating itself. While intended as a commentary on the persistence of the whistleblower, the statement functions as a de facto acknowledgment of the project's recurring friction regarding GPL compliance. It confirms that leadership is aware this specific issue has been a point of contention for a decade, yet the internal workflow has not been adjusted to prevent it.
* **The Strategic Contradiction:** In 2026, leadership attempted to minimize the removal of metadata as a non-critical issue on a WIP branch. This contradicts their [2017 admission](https://github.com/cmangos/mangos-wotlk/commit/12ce14f2c399741d67e5f68425032a21240b708f) - [Archive](https://web.archive.org/web/20260329081021/https://github.com/cmangos/mangos-wotlk/commit/12ce14f2c399741d67e5f68425032a21240b708f) where they explicitly stated that failing to merge a contributor's PR was a mistake and that the proper technical path was to preserve the original authorship. This demonstrates that the project's current non-compliance is a choice made with full prior knowledge of the legal requirements.
* **The Metadata Fallacy:** The project's internal policy treats Git metadata as a non-legal artifact. This establishes a procedural precedent where community research is treated as raw material rather than protected intellectual property under GPLv2 Section 1.
* **License as Suggestion:** The combination of unauthorized license versioning and the "nobody cares" model creates a hostile environment for intellectual property. If leadership does not respect the license version itself, they cannot be expected to respect the authorship metadata requirements (GPLv2 Sections 1 & 2) that protect individual contributors.
* **Power Imbalance:** The use of Strategic Delays forces contributors into a Fix it Later trap, where they are pressured to accept the theft of their metadata simply to see their technical work finally integrated after years of stagnation.
* **Ecosystem Interference:** The project has graduated from internal technical debt to externalizing that debt onto upstream tools. By lobbying Meson to support deprecated 2017 era integration models, the project actively degrades the integrity of the broader FOSS toolchain to avoid fixing its own internal legacy anchors.

## Conclusion
The documented record indicates a consistent pattern of Attribution Laundering, License Instability, and Financial Conflict of Interest. By systematically decoupling technical logic from original authorship, the project maintains a centralized record of productivity that correlates with project-branded financial solicitation. These actions represent a documented divergence from the transparency requirements of the GPLv2 and a failure of standardized project governance.

---
**Disclaimer:** This Meta-Audit synthesizes technical, legal, and financial data from public version control records and historical archives. This analysis evaluates **organizational governance and licensing compliance.** It does not target individuals but documents the operational intersection of metadata manipulation, unauthorized license reversion, and project-branded financial solicitation.
