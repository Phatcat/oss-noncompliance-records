# Incident Report: PetAI Refactor (PR #520)

**Project:** cMaNGOS  
**Affected Author:** deiteris  
**Original Work:** [Pull Request #520](https://github.com/cmangos/mangos-classic/pull/520) (14 commits, Oct 2023) - [Archived](https://web.archive.org/web/20260329120935/https://github.com/cmangos/mangos-classic/pull/520)  
**Replacement Commit:** [Commit 59534bc](https://github.com/cmangos/mangos-classic/commit/59534bc) (Jan 2026) - [Archived](https://web.archive.org/web/20260329080433/https://github.com/cmangos/mangos-classic/commit/59534bc31447b5977b722417bb32a9e711a52651)  

## Overview
This entry documents the removal of 14 commits of original authorship metadata. The logic, which refactors the core PetAI system, was proposed in 2023 and remained in a pending state for over two years. In January 2026, the logic was manually re-typed into a new commit under the maintainer's name.

## Technical Evidence
* **Logic Duplication:** A line-by-line diff of `PetAI.h` and `PetAI.cpp` confirms that the code in Commit `59534bc` is identical to the code proposed in PR #520, down to the wording of the comments.
* **Metadata Removal:** The original 14-commit history, which serves as the legal record of the author's contributions and timestamps, was discarded.
* **Distribution:** The code was pushed to the official organization namespace under a WIP branch, constituting public distribution of a derivative work without the required preservation of the original author's history.

## Statements of Intent (Direct Quotes)

The following statements were made by project leadership and the maintainer during the discovery of this metadata removal:

### Maintainer Justification (killerwife)
> "Nothing is merged. If it were, PR would be closed. Your point is duly noted and will be resolved when PR code is merged into 'master' branch. Any other branch is 'my' personal copy that I use between computers."

* **Analysis:** This statement acknowledges the extraction of code while attempting to claim a "Personal Copy" exception. The GPL makes no distinction between branches on a public organization namespace; distribution occurs at the point of the public push.

### Leadership Acknowledgment (cyberium)
> "We acknowledge the GPL constraint. That said, finding you here raising this as a critical issue on a WIP branch—before any distribution occurs—feels like history repeating itself. (...) We are committed to proper credit in the final commit."

* **Analysis:** This is a direct admission that the organization was well aware the state of the repository at the time violated the GPL constraint. A promise of future compliance does not excuse any prior, current or future distribution of a derivative work with stripped authorship.

### 3. Contributor Sentiment and Legal Misconceptions (deiteris)
Following the discovery of the metadata removal, the original author provided a statement downplaying the significance of the Git ledger:

> "Git commit metadata is NOT the legal record of authorship because it does not survive the carbon copy. (...) Do I care about improper attribution here? Not really since I had genuine interest in improving the code."

* **Analysis of Precedent:** The author’s personal lack of grievance does not waive the requirements of the GPLv2. Licenses exist to protect the **integrity of the software's history**, not just the feelings of the current author. 
* **The "Metadata Fallacy":** The claim that Git metadata is not a legal record is a dangerous technical error. In software forensics, the Git ledger is the primary evidence of intellectual property creation. By promoting the idea that this history is disposable, project leadership establishes a procedural precedent where community work is integrated without original commit history.
* **The "Fix it Later" Trap:** The author notes he is "annoyed" that the code remains unmerged after three years. This demonstrates the operational delay between contribution and integration. Contributors may prioritize code merge over metadata preservation after years of stagnation.

## Compliance Conflict
Under **GPLv2 Section 1 and 2**, any distribution of the program or a derivative work must provide a clear record of the changes and the authors who made them. By stripping the work of the original git authorship in the infringing commit, the project has falsified the historical record of authorship.
