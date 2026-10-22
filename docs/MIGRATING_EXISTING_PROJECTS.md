# Migrating Existing Projects




**Status:** PUBLIC DRAFT CANDIDATE  
**Purpose:** recover historical project knowledge from old chats/files without turning the migration itself into a second source of truth.




Allocortex can start from a clean project, but many real projects already contain old chats, stale uploads, repository copies, milestone recaps, and partially remembered decisions.




The migration objective is:




recover useful historical knowledge with high recall, then centrally deduplicate and promote only the smallest justified durable state.




## Stage 0 — Optional source-surface hygiene




Before destructive cleanup of any active source layer:




1. inventory every active source object using stable IDs when available;
2. classify current canonical duplicates, immutable bootstrap files, historical auxiliary material, unique primary evidence, and unknowns;
3. preserve a complete external snapshot;
4. create a snapshot index and archive receipt;
5. verify preservation before deleting anything.




See PROJECT_SOURCE_HYGIENE.md.




Do not delete a source merely because a current repository copy appears to exist. Preserve provenance first.




## Stage 1 — Parallel historical-chat extraction




Run the recall-first source extractor in multiple historical chats in parallel.




Each source chat is a witness to its own accessible history.




Default mode for bulk migration: LOCAL_EXTRACTION.




Source chats should not write current project state and should not independently decide what the present project truth is.




Each chat should:




- scan all materially accessible historical workstreams;
- extract all materially useful distinct knowledge units;
- preserve owner decisions, chronology, conflicts, genealogy, negative/superseded history, artifact pointers, and evidence gaps;
- distinguish direct turns from summaries/model reconstruction;
- avoid an arbitrary candidate-item cap;
- split a large report into parts instead of suppressing useful material;
- exclude current migration-control machinery from substantive project knowledge.




Multiple old chats may run at the same time. They do not need to wait for each other.




## Stage 2 — Central/local-PM reconciliation




After source reports are collected, one locally designated merge authority reviews the batch.




The central reconciler:




1. inventories expected/found reports and report parts;
2. checks report completeness and coverage;
3. groups candidates by underlying source/event;
4. identifies correlated repeats;
5. performs semantic deduplication;
6. compares candidates against current authoritative state;
7. preserves conflicts and evidence gaps;
8. distinguishes chat-visible artifacts from externally preserved artifacts;
9. verifies owner decisions versus assistant proposals;
10. promotes only the smallest accepted consequence;
11. records NO-OP when current state already represents the material;
12. archives/dispositions processed reports.




The Allocortex maintainer does not automatically become the consumer project's merge authority. The local owner/PM decides who performs promotion.




## Stage 3 — Separate fresh verification




Fresh web/current-source research is not recovered legacy-chat evidence.




When a historical candidate needs verification:




- mark VERIFY_WITH_SOURCE;
- verify separately under local project authority;
- preserve the new verification with its own provenance;
- do not attribute it to the old chat.




## Stage 4 — Migration closeout




A completed knowledge-reconciliation pass does not itself prove archive completeness or project attachment cleanup. If a platform's active Sources are changed, separately verify (a) preserved originals, (b) current membership by tool/UI or owner attestation, and (c) correct recovery in the intended runtime. Label those proof levels explicitly. A prompted fresh-session recovery does not prove that ordinary future tasks will independently consult LIVE.




After central reconciliation:




- ensure every report has a disposition;
- remove processed reports from active intake;
- keep only minimal accepted active state;
- archive deep provenance;
- rerun source hygiene if migration artifacts enlarged the active source surface;
- run a clean recovery test from the intended bootstrap/routing layer.




## Why source extraction is recall-first




Compression at the source-chat stage can permanently lose unique decisions, chronology, conflicts, or artifact pointers.




Therefore:




- extraction maximizes materially useful recovery;
- reconciliation performs compression;
- active state remains intentionally small.




The method minimizes promoted state, not source extraction.




## Common-source rule




Several reports repeating the same user statement, artifact, imported prompt, or summary are not independent confirmation.




The central reconciler should group them into one source family and preserve the strongest provenance.




## Migration-control cutoff




The extraction prompt, migration work order, reconciliation reports, batch tooling, current migration discussion, and inbox mechanics are normally control metadata.




Do not ingest them as substantive project history merely because they appear in the source chat during migration.




Exception: a genuine project decision made during the migration is still project knowledge.




## Project Sources are optional




Project Instructions, one immutable gateway file, several nonduplicative Sources or no Project Sources are all local platform choices. Do not install a source kit by default, and never assume a file's presence guarantees fresh retrieval.




A project may use:




- zero Project Sources;
- one gateway file;
- a small immutable bootstrap kit;
- repository documents;
- Google Drive;
- another document store;
- another external-state system.




The method is about authority, recovery, provenance, and write-back—not a specific storage product.




## Recommended operating pattern




For a project with many historical chats:




PARALLEL OLD CHATS
→ PROPOSED RECALL-FIRST REPORTS
→ ONE LOCAL MERGE AUTHORITY
→ SOURCE-FAMILY DEDUP + CURRENT-STATE CHECK
→ MINIMAL VERIFIED PROMOTION
→ ARCHIVE + SOURCE HYGIENE
→ CLEAN RECOVERY TEST




## Success condition




Migration succeeds when:




- materially useful historical knowledge is not lost merely for brevity;
- old chats cannot silently override current authority;
- correlated reports are not mistaken for independent evidence;
- unique artifacts and provenance remain recoverable;
- active state is smaller and cleaner than the migration intake;
- a fresh contour can recover current project state without loading the historical archive by default.