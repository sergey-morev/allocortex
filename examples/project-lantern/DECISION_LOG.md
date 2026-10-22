# Project Lantern — Decision Log

Status: ACCEPTED DECISIONS ONLY

**Synthetic fixture rule:** the example stipulates that Project Owner accepted D-001 through D-004. Actual owner acceptance artifacts are not supplied. In a real project, record a direct acceptance-evidence pointer; do not infer it from a model's classification or rationale.

## D-001
DATE: 2026-09-01
DECISION: Copy every in-scope source document into the Project Lantern durable workspace.
ACCEPTED_BY: Project Owner (stipulated synthetic fixture; external acceptance artifact not supplied).
BASIS: initial migration simplification.
STATUS: PARTIALLY SUPERSEDED BY D-002 FOR RESTRICTED SOURCES.

## D-002
DATE: 2026-09-05
DECISION: Restricted sources remain in the external ASR. The durable workspace stores a pointer, verification date, and smallest verified project consequence instead of duplicating restricted content.
ACCEPTED_BY: Project Owner (stipulated synthetic fixture; external acceptance artifact not supplied).
BASIS: data-minimization review.
SUPERSEDES: D-001 where restricted sources are concerned.
STATUS: ACTIVE.

## D-003
DATE: 2026-09-20
DECISION: v3.0 cannot be released while any in-scope source version remains `UNVERIFIED`.
ACCEPTED_BY: Project Owner (stipulated synthetic fixture; external acceptance artifact not supplied).
BASIS: release-readiness requirement.
STATUS: ACTIVE.

## D-004
DATE: 2026-09-20
DECISION: v3.0 also requires a final source-to-index consistency check covering all 24 entries after authoritative versions are reconciled.
ACCEPTED_BY: Project Owner (stipulated synthetic fixture; external acceptance artifact not supplied).
BASIS: final release quality gate.
STATUS: ACTIVE.
