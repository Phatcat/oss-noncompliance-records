# OSCAR Incident Report: Remove faction duplicate (PR #334)

**Project:** cMaNGOS  
**Affected Author:** Phatcat  
**Original Work:** [Pull Request #334](https://github.com/cmangos/mangos-classic/pull/334) (Mar 2018) - [Archived](https://web.archive.org/web/20260329081251/https://github.com/cmangos/mangos-classic/pull/334) / [Changes](https://web.archive.org/web/20260329203109/https://github.com/cmangos/mangos-classic/pull/334/files)  
**Infringing Commit:** [Commit b72c094](https://github.com/cmangos/mangos-classic/commit/b72c094) (Dec 2018) - [Archived](https://web.archive.org/web/20260329213619/https://github.com/cmangos/mangos-classic/commit/b72c09425c8c68897861cf1d172f5029198c8851)  

## Overview
This entry documents the "Stall and Re-integrate" integration pattern. In March 2018, a contributor proposed a structural database refactor to remove redundant faction columns (`FactionHorde`/`FactionAlliance`) based on reverse-engineering sniffs. Despite immediate approval from other members, the PR remained in a pending state for nine months, only to be closed by a maintainer who implemented the exact same structural changes under their own name.

## Technical Evidence
* **Logic Duplication:** The infringing commit `b72c094` performs the exact schema migration proposed in PR #334: dropping `FactionHorde` and renaming `FactionAlliance` to `Faction`.
* **SQL Parity:** As seen in the comparison of `z2719_01_mangos_creature_template_fixup.sql` (Contributor) and `z2729_01_mangos_creature_template_faction_removal.sql` (Maintainer), the SQL commands are functionally identical, utilizing the same `ALTER TABLE` logic to achieve the refactor.
* **Metadata Removal:** The contributor's commit history, which included the research and justification for the change, was discarded. The maintainer recorded the architectural shift without original contributor metadata.

## Statements of Intent (Direct Quotes)

### Exhibit A: Maintainer Approval and "Political" Avoidance (killerwife - Mar 5, 2018)
> "FactionAlliance/FactionHorde needs to be nuked... My approval, but for political reasons I am staying away from further discussion."

* **Analysis:** The maintainer explicitly approved the logic on day one but withheld the merge, citing "political reasons." This established a period of artificial stagnation despite technical consensus.

### Exhibit B: Strategic Silence and Closing (Dec 10, 2018)
> "Closed by b72c094"

* **Analysis:** After 280 days of inactivity, the maintainer closed the contributor's PR not by merging it, but by referencing their own commit. This is a documented instance of "Attribution Laundering", where a maintainer stalls a contributor PR to re-integrate the work under maintainer-owned metadata.

## Compliance Conflict
Under **GPLv2 Sections 1 and 2**, the legal right to distribute a derivative work requires a clear record of authorship. By intentionally stalling a contributor’s approved refactor for nine months and then re-implementing it to bypass the Git ledger, project leadership has generated a documented inaccuracy in the historical record of who originated the architectural change. This practice treats community research and development as "public domain" material for maintainer-owned distribution, bypassing the attribution requirements.

---
**Disclaimer:** This report analyzes the **procedural and legal compliance** of the project organization. It does not target individuals but documents the public actions of account holders acting as project representatives in a public version control environment.
