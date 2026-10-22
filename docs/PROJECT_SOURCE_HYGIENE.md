# Project Source Hygiene


**Status:** PUBLIC DRAFT / AGNOSTIC  
**Purpose:** reduce stale or competing source copies before and after historical-chat migration without losing provenance.


Project Source hygiene is optional. Allocortex does not require ChatGPT Project Sources or any particular product feature.


The goal is not “keep exactly three files.” The goal is:


> keep the active source surface as small and low-drift as practical, while preserving historical material outside that active surface.


## Why hygiene matters


A project can accumulate static copies of:


- repository documents;
- milestone recaps;
- old decision logs;
- source capsules;
- chat exports;
- workflow notes;
- old project-state snapshots.


If the real current authority lives elsewhere, these copies can silently become stale and compete with fresher state.


A source that was useful for recovery yesterday can become misleading if it remains permanently active after its canonical version has moved on.


## Authority first


Before removing anything, identify which system owns which class of truth.


Examples:


- live repository -> current code and canonical repo documentation;
- external document store -> historical evidence, recovery state, reconciliation reports, archives;
- Project Sources -> optional bootstrap/routing layer;
- primary external system -> mutable facts generated outside the project.


Do not create a second source of truth merely to perform hygiene.


## Hygiene workflow


### 1. Inventory the active source surface


Record every active source object with:


- stable object/file ID when available;
- title;
- source kind;
- date/version if known;
- current role;
- whether an external canonical equivalent exists.


Do not deduplicate by title alone.


Two files with the same title may be distinct evidence objects.


### 2. Classify each source


Useful classes include:


- **IMMUTABLE_BOOTSTRAP** — stable routing/operating/recovery instruction;
- **CURRENT_CANON_DUPLICATE** — static copy of a live authoritative object elsewhere;
- **HISTORICAL_AUXILIARY** — useful genealogy/recovery material, not current authority;
- **PRIMARY_UNIQUE** — unique evidence that must be preserved before cleanup;
- **DUPLICATE_TITLE_DISTINCT_OBJECT** — same title, different source identity;
- **UNKNOWN** — do not delete until resolved.


### 3. Snapshot before cleanup


Before removing sources from the active surface, preserve a complete external snapshot.


Prefer raw bytes/text when possible.


For each preserved source, retain:


- original stable ID;
- original title;
- preservation destination;
- source class;
- checksum/hash when practical for immutable bundles;
- exception handling if direct transfer was not possible.


If a connector cannot preserve a source individually, package it in a clearly indexed immutable bundle rather than silently omitting it.


### 4. Create an index and archive receipt


The snapshot should have two separate controls:


**Snapshot Index**
- expected source inventory;
- stable IDs;
- titles;
- classifications;
- destination/preservation route.


**Archive Receipt**
- expected count;
- individually preserved count;
- packaged-exception count;
- missing count;
- duplicate-title handling;
- unresolved exceptions;
- cleanup authorization status.


Do not delete the active sources until the preservation equation closes:


> expected = individually preserved + packaged exceptions + explicitly unresolved


For destructive cleanup, unresolved should normally be zero.


### 5. Build the smallest useful bootstrap kit


If the project chooses to keep Project Sources, keep only low-drift material whose absence would make safe recovery materially harder.


A compact kit may contain:


- a source router / recovery map;
- a role or operating capsule;
- a recovery / reconciliation protocol.


This is an example, not a mandatory three-file architecture.


A project may need zero, one, two, three, or more bootstrap files.


The test is functional, not numerical.


### 6. Make bootstrap files immutable by policy


A static bootstrap should not contain transient configuration/test labels such as `NOT TESTED`, the current count of project attachments, or migration-progress claims. Keep those in the current LIVE or dated closure receipt. Reissue/version a bootstrap only when its identity, authority, routing IDs or operating contract materially change.


Bootstrap files should not carry mutable project state such as:


- current commit hashes;
- current roadmap;
- current release blockers;
- current task queue;
- current milestone status;
- current external facts.


If the operating architecture itself changes:


1. create a new version;
2. record supersession;
3. retire the old version deliberately;
4. do not silently rewrite the supposedly immutable source.


### 7. Remove stale active copies only after preservation


After the snapshot, index, receipt, and bootstrap kit are verified:


- remove static duplicates from the active source surface;
- do not re-upload current canonical repo docs as frozen copies;
- do not keep old chat dumps active merely for convenience;
- keep historical evidence external and retrievable;
- keep current truth in its authoritative system.


### 8. Run a clean recovery test


A fresh contour with only the intended bootstrap layer should be able to:


- identify the project;
- locate current authority;
- distinguish current state from historical evidence;
- locate reconciliation/archive material when needed;
- avoid treating historical snapshots as current truth;
- fail closed when current authority cannot be read.


If recovery requires a large static source dump, the hygiene pass is incomplete or the routing layer is insufficient.


## Relationship to legacy-chat migration


Project Source hygiene and historical-chat reconciliation solve different problems.


**Source hygiene**
controls which artifacts remain active.


**Legacy-chat reconciliation**
recovers knowledge from historical conversations.


Recommended relationship:


1. inventory and preserve active Project Sources before destructive cleanup;
2. keep migration tooling and reconciliation reports outside the permanent active source layer;
3. run historical chat extraction as candidate intake;
4. central/local PM reconciles those reports against current authority;
5. promote only minimal accepted consequences;
6. archive processed reports;
7. rerun source hygiene after a large migration if the active surface grew again.


Do not feed migration-control artifacts back into the project as substantive historical knowledge merely because they were present during the migration.


## Duplicate-title rule


Never assume same title = same file.


Use stable object IDs/version IDs.


If two same-named sources are materially distinct, preserve both.


Title-based deduplication is unsafe when provenance matters.


## Failure modes


Avoid:


- deleting before a verified external snapshot exists;
- assuming an upload succeeded without checking destination/count;
- treating a snapshot as current authority;
- keeping changing repository docs as permanent Project Sources;
- preserving only summaries while discarding unique primary source material;
- deduplicating by filename alone;
- silently losing connector-transfer exceptions;
- turning a pilot project's folder structure into a universal template;
- keeping reconciliation reports permanently active after disposition;
- editing “immutable” bootstrap files in place.


## Three separate completion checks


1. **Semantic recovery:** a fresh user/agent can recover current state and authority from the intended active sources. Record `PASS`, `FAIL` or `INCONCLUSIVE_ACCESS` with test limitations.
2. **Archive integrity:** record precisely whether original bytes, expected counts, manifest hashes and any post-upload verification were actually checked. Do not infer file-byte integrity from a readable summary.
3. **Active-source membership:** confirm what is *actually* attached/enabled after cleanup. If no product API/UI readback is available, mark it `USER_ATTESTED / NOT_TOOL_VERIFIED`; content recovery does not prove deletion.


For platforms that support it, an external recovery test followed by an in-project smoke test can be useful after owner-authorized Source replacement. Those are different operational checks using potentially correlated state, not independent scientific replications. Project Sources remain optional; zero, one or several stable files can be justified locally.


## Hygiene receipt — minimum fields


A hygiene closeout should record:


- ACTIVE_SOURCES_EXPECTED
- SOURCES_INVENTORIED
- SOURCES_PRESERVED_INDIVIDUALLY
- PACKAGED_EXCEPTIONS
- UNRESOLVED / MISSING
- DUPLICATE_TITLE_DISTINCT_OBJECTS
- BOOTSTRAP_SOURCES_TO_KEEP
- CURRENT_AUTHORITY
- HISTORICAL_ARCHIVE_LOCATION
- CLEANUP_PERFORMED = YES / NO
- CLEAN_RECOVERY_TEST = PASS / FAIL / INCONCLUSIVE_ACCESS / NOT_RUN
- ARCHIVE_INTEGRITY_EVIDENCE = manifest / size / hashes / independent remote check / not checked
- CURRENT_SOURCE_MEMBERSHIP = TOOL_VERIFIED / USER_ATTESTED / UNVERIFIED


## Success condition


A hygiene pass succeeds when:


- no unique source material is lost;
- the current authority is unambiguous;
- stale static copies no longer compete with current truth;
- historical evidence remains recoverable;
- the active bootstrap surface is intentionally small;
- a fresh contour can recover safely without loading the historical archive by default.