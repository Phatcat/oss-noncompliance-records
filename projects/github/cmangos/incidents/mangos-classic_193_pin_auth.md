# OSCAR Incident Report: Implementation of time-based one-time password & fixed PIN authentication (PR #193)

**Project:** cMaNGOS  
**Affected Authors:** Chaosvex / TrinityCore  
**Original Work:** [Pull Request #193](https://github.com/cmangos/mangos-classic/pull/193) (11 commits, Sep 2016) - [Archived](https://web.archive.org/web/20260329081022/https://github.com/cmangos/mangos-classic/pull/193) / [Changes](https://web.archive.org/web/20260329203754/https://github.com/cmangos/mangos-classic/pull/193/files)  
**Related Work:** [Pull Request #191](https://github.com/cmangos/mangos-classic/pull/191) (Sep, 2016) - [Archived](https://web.archive.org/web/20250816124109/https://github.com/cmangos/mangos-classic/pull/191) / [Changes](https://web.archive.org/web/20260329204438/https://github.com/cmangos/mangos-classic/pull/191/files)  
[TrinityCore Commit ba22bae](https://github.com/TrinityCore/TrinityCore/commit/ba22baebbd1394cc69366d7a19d879da43885430) (Aug, 2013) - [Archived](https://web.archive.org/web/20260329204101/https://github.com/TrinityCore/TrinityCore/commit/ba22baebbd1394cc69366d7a19d879da43885430)  
**Infringing Commit:** [Commit 4b10465](https://github.com/cmangos/mangos-classic/commit/4b10465) (Nov, 2017) - [Archived](https://web.archive.org/web/20260329140131/https://github.com/cmangos/mangos-classic/commit/4b10465)  

## Overview
This entry documents the process of functional stagnation and subsequent reintegration. In 2016, chaosvex provided a full implementation of Two-Factor Authentication (TOTP/PIN). Project leadership publicly questioned the utility of the feature to justify withholding the merge of the PR, the logic was subsequently re-injected into the core under maintainer authorship, resulting in an implementation that was admittedly inferior to the original contributor's PR.

## Technical Evidence
* **Logic Duplication:** Commit `4b10465` utilizes the exact architectural structure changes (e.g., core-handling logic), database schema extensions, and the RFC 6238 TOTP implementation.
* **Metadata Removal:** The 11 original commits, containing the iterative development, bug fixes, and review history, were discarded. The feature was merged as a "clean" maintainer commit, displacing the attribution metadata of the original authors.
* **Strategic Delays:** The work remained in a pending state for over 18 months. During this period of documented stagnation, the logic was manually ported to the master branch under maintainer metadata. The original PR was eventually closed by the author in 2018 after the integration of identical logic in the core rendered the contribution redundant.

## Statements of Intent (Direct Quotes from the implementation on an adjacent repo before backporting;)

https://github.com/cmangos/mangos-wotlk/commit/12ce14f2c399741d67e5f68425032a21240b708f - [Archive](https://web.archive.org/web/20260329081021/https://github.com/cmangos/mangos-wotlk/commit/12ce14f2c399741d67e5f68425032a21240b708f)

### Exhibit A: Admission of "Mistake" and Attribution Failure (cyberium)
> "For me its a mistake and its on discussion to avoid same error in future. Btw in this code there is only part of Chaosvex code. So proper commit order had to be, merge his PR (or crypt part of it) then add Laizerox code (authentificator)."

* **Analysis:** Leadership admitted that the proper legal and technical path was to merge the original PR. By choosing not to do so, they distributed a derivative work without the required historical metadata.

### Exhibit B: Contradictory Attribution Claims (cyberium)
> "Yes after reviewing those code its easy to see that the code is not from Chaosvex PR (his code is better than this commit btw). Only 2 included files are the same... This code come from trinity..."

* **Analysis:** After initially admitting the code belonged to Chaosvex, leadership asserted an alternative provenance that the work was sourced from (TrinityCore, from which the proper authors weren't attributed either) to avoid the attribution requirement. This contradiction obscures the true provenance of the code, as neither original source (Chaosvex or TrinityCore) was credited in the resulting commit.

### Exhibit C: Administrative Intervention Regarding Compliance Reporting (cyberium)
> "We don't care much about your opinion, you already expressed yourself a bit too much here. So try to be more constructive or we don't need anymore any of your reaction here."

* **Analysis:** When confronted with the evidence of metadata removal, leadership utilized administrative power to threaten a ban ("be my guest") against the contributor reporting the license violation. This documentation identifies an administrative response where reports of non-compliance result in threats of account restriction.

## Compliance Conflict
Under **GPLv2 Sections 1 and 2**, the legal right to distribute a derivative work requires a clear record of authorship. By dismissing a contributor's work, acknowledging it was used, then attributing it to an external source to bypass credit requirements, the project has generated a documented breach of the license. The use of administrative threats to silence reports of this non-compliance further demonstrates a systematic bypass of the attribution requirements.

---
**Disclaimer:** This report analyzes the **procedural and legal compliance** of the project organization. It does not target individuals but documents the public actions of account holders acting as project representatives in a public version control environment.
