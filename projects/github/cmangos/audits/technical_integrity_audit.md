# OSCAR Technical Integrity Audit: Case #2026-03-29

**Project:** cMaNGOS
**Primary Actors:** insunaa (Contributor/Representative), Meson Upstream  
**Subject:** Analysis of Technical Debt Externalization and Legacy Dependency Anchoring

## Executive Summary
This audit documents a divergence from modern architectural standards, resulting in an attempt to externalize project-specific technical debt into the **Meson Build System** [Issue #12821](https://github.com/mesonbuild/meson/issues/12821) - [Archived](https://web.archive.org/web/20241008172420/https://github.com/mesonbuild/meson/issues/12821). Despite being provided with a standard-compliant C++20 solution from the **EmberEmu** project, project representatives opted to defend a "hacky" legacy model anchored to a discontinued 2018 Oracle dependency.

## Primary Evidence: The "Legacy Gravity"
Analysis of the build configuration reveals a project fundamentally incompatible with modern build system standards:

* **The cMaNGOS Anchor:** [CMakeLists.txt](https://github.com/cmangos/mangos-classic/blob/master/CMakeLists.txt) - [Archived](https://web.archive.org/web/20260329205012/https://github.com/cmangos/mangos-classic/blob/master/CMakeLists.txt)
  * **Hardcoded Pathing:** Lines 148-152 and 226-238 prove the project relies on manually crawling `C:\Program Files` and `dep/` folders for `libmysql.dll`.
  * **Standard Bypass:** The project bypasses `find_package()` in favor of manual DLL pathing, a methodology that has been deprecated for nearly a decade.

* **The Rejected Solution (EmberEmu Reference):**
  * As documented in [EmberEmu PR #90](https://github.com/EmberEmu/Ember/pull/90/changes) - [Archived](https://web.archive.org/web/20260329205735/https://github.com/EmberEmu/Ember/pull/90) / [Changes](https://web.archive.org/web/20260329205922/https://github.com/EmberEmu/Ember/pull/90/files), a proper modern implementation uses `find_package(mysql-concpp REQUIRED)` and `mysql::concpp-jdbc-static`. 
  * This solution was provided to representatives and rejected in favor of maintaining the legacy hack.

## The "Lost Audit" (Blocked Meta-Commentary)
The following technical findings were drafted for the Meson issue tracker but were restricted from submission:

* **Technical Finding:** The implementation in Issue #12821 bypasses standard dependency lookups. The project attempts to link a C++20 codebase against the `mysql-concpp` wrapper by treating it as raw C bindings. This defeats the purpose of a modern build system. Even if they insist on using the raw C bindings they are not even aware they are now packaged as `libmysqlclient`, and has been since 2018.
* **The 8-Year Lifecycle Gap:** Standalone 'Connector/C' reached **End-of-Life (EOL)** in 2018. Building custom 'System' lookup logic for a product that hasn't seen a standalone release since **July 2017** sets a problematic maintenance precedent for upstream build tools.

### Exhibit A: Peer Review Exchange
The following exchange ([Source](https://github.com/cmangos/mangos-classic/commit/df6e281737667464a66440ad288209fcabfe4298) - [Archived](https://web.archive.org/web/20260329205337/https://github.com/cmangos/mangos-classic/commit/df6e281737667464a66440ad288209fcabfe4298)) documents the project's refusal to implement standard-compliant dependency handling.

* **Auditor:** "Dude... it’s not mysql or libmysql. The package is mysql-concpp. I already solved this for EmberEmu (...) it will never work reliably on Windows until you stop hardcoding paths and start using proper targets.."
* **Representative (insunaa):** "I honestly **do not give a shit about windows**, lol. I've included **hacky windows support for this shit** only by request."
* **Auditor:** "Also maybe don't trouble meson with hacking their repository to support this hackjob then."
* **Representative (insunaa):** "jesus you're insufferable... go bother someone else."
* **Auditor:** "So much for trying to help you not to waste your time by giving you the solution."  

**Analysis:** The representative acknowledges the implementation is 'hacky' while simultaneously requesting upstream support for the same logic in Meson Issue #12821.

## Findings on Project Philosophy

| Factor | Modern Standard | cMaNGOS Methodology |
| :--- | :--- | :--- |
| **Dependency Name** | `mysql-concpp` / `libmysqlclient` | Hardcoded "libmysql" strings |
| **Path Discovery** | Automated (CMake/Pkg-Config) | Manual Directory Crawling |
| **Lifecycle Awareness** | Unified Connector (Post-2018 EOL) | Discontinued Connector/C (2017) |
| **Maintainer Portability Goal** | Portability and Compliance | "Do not give a shit about Windows" |

**Technical Note:** Per Oracle’s official documentation, the MySQL Connector/C (libmysqlclient) was integrated into the MySQL Connector/C++ (mysql-concpp) in 2018. The project’s insistence on a standalone 2017-era DLL violates current Oracle-recommended integration paths.

## Conclusion: Architectural Regression
The evidence shows a documented preference for deprecated dependency models over standard-compliant alternatives. By refusing to utilize modern dependency targets and instead lobbying upstream tools to support 8-year-old deprecated models, the project has moved from "technical debt" into "ecosystem interference" and is creating **upstream noise**. The restriction of technical peer review on public trackers allows this misinformation to persist, creating a state where the project's build system is anchored to a 2017-era "hackjob" that maintainers refuses to correct.

---
**Disclaimer:** This report analyzes the **procedural and technical compliance** of the project organization. It does not target individuals but documents the public actions of account holders acting as project representatives in a public version control environment.
