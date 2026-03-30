# OSCAR License Audit: Systematic License Instability and Compliance Failure

**Project:** cMaNGOS
**Primary Actors:** cyberium (Project Leadership)  
**Subject:** Record of Unauthorized License Changes and Stated Compliance Policy

---

## Executive Summary
This document records a pattern of License Flip-Flopping within the cMaNGOS organization. Analysis of the repository history and internal discussions (2017 to 2019) reveals that leadership has repeatedly changed the project legal license (GPLv2 to GPLv3 and back) without the required consensus of copyright holders. This behavior, combined with direct admissions regarding license terms, demonstrates a governance model where the GPL is secondary to maintainer preference.

## The License Flip-Flop (2017 to 2019)
### Exhibit A: Analysis of Unauthorized License Reversion
Internal records confirm that the project underwent a "downgrade" from GPLv3 back to GPLv2. This was executed by project leadership (**cyberium**) under the guise of complying with third party dependencies.

* **Legal Impossibility:** Under the terms of the GPL, a project may upgrade to a later version if the original license included the "or any later version" clause. However, there is no downgrade clause. Once code is contributed under GPLv3, it cannot be unilaterally reverted to GPLv2 without the explicit permission of every contributor who provided code during the GPLv3 window.
* **The Dependency Paradox:** Leadership justified the downgrade by citing third party code compatibility. However, the dependencies in question were already licensed under "GPLv2 or later," which explicitly allows those dependencies to be used within a GPLv3 project. By "downgrading" to comply with the dependency, leadership actually chose to violate the primary project license to solve a non-existent legal conflict.
* **The Ghost License:** In 2019, it was documented ([Issue #1825](https://github.com/cmangos/issues/issues/1825) - [Archived](https://web.archive.org/web/20260329081639/https://github.com/cmangos/issues/issues/1825)) that the project's NEWS.md, README, and LICENSE files were in direct conflict, referencing non-existent files (e.g., COPYING) and stating incorrect license versions. This creates a state of Legal Fog where contributors and users cannot verify the actual terms of distribution.

## Direct Admissions of Governance Apathy
### Exhibit B: Documentation of Leadership Acknowledgment of Non-Compliance
The following quotes from project leadership and maintainers highlight a documented culture of non-compliance:
> — [Source](https://github.com/cmangos/tbc-db/commit/f1d6d16dad22fbbf8fb662f551a3d2a0244d55cb) - [Archive](https://web.archive.org/web/20260329082002/https://github.com/cmangos/tbc-db/commit/f1d6d16dad22fbbf8fb662f551a3d2a0244d55cb)

### The "Nobody Will Sue" Defense (cyberium - July 12, 2017)
> "I dont know much about this but... i dont care much about license because i personally consider everyone can/are already doing what they want with an open-source software that no authors will engage any legal proceeding."

* **Analysis:** Project leadership explicitly defines compliance by the likelihood of legal proceeding rather than the terms of the license. By stating that they do not care about the license because authors won't sue, leadership establishes a precedent where contributor rights are knowingly violated under the assumption of impunity.

### The "Holiday Priority" Dismissal (xfurry - Aug 4, 2017)
> "Guys, I think there are more important topics to take care of, other than licenses (for example summer holiday)... I don't think that any of the authors will actually care if you change one open source license with another open source license (I personally don't)."

* **Analysis:** This dismissal treats the legal framework of the project as a nuisance that interferes with more important activities. It reinforces the organizational belief that the personal feelings of a few maintainers override the legal requirements of the GPL.

## Compliance Conflict
The observed actions create a documented compliance conflict regarding the integrity of the project's legal distribution terms. When project leadership publicly admits they do not respect the license (Cyberium, 2017) and maintainers admit they "indeed made a mistake" while deleting evidence (Killerwife, 2026), the project ceases to be a compliant Open Source entity. 

The decision to downgrade from GPLv3 to GPLv2 is particularly egregious because it ignores the forward-compatibility built into the GPL. Leadership effectively decided that the rights of contributors who committed under GPLv3 were expendable.

## Conclusion
The evidence indicates a governance model where the GPL is treated as a non-binding guideline rather than a set of legal requirements. This environment provides the necessary cover for the Attribution Laundering documented in the Master Audit. If leadership does not respect the license version itself, they cannot be expected to respect the authorship metadata requirements (GPLv2 Sections 1 & 2) that protect individual contributors.

---
**Disclaimer:** This report analyzes the **licensing and legal governance** of the project organization. It documents the public statements and repository history regarding license versioning. This analysis does not target individuals but evaluates the operational impact of unauthorized license changes on the legal requirements of the GPL.
