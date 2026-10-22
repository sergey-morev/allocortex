# Project Lantern — Current State

Status: AUTHORITATIVE MUTABLE STATE

VALID_AS_OF: 2026-09-30
LAST_VERIFIED: 2026-09-30
REVERIFY_TRIGGER: any ASR version change, owner scope change, or new source affecting release readiness.

## Current phase
Source reconciliation and release-readiness review.

## Current baseline
- 24 reference items in scope.
- 21 items classified and reconciled.
- 2 restricted items represented by ASR pointers only.
- 1 additional item, R-17 (separate from the two restricted pointer-only items), has conflicting reported version information and remains `UNVERIFIED`.
- Draft v3.0 index exists but is not accepted for release.
- R-08: reconciled title = `Operating Checklist`; evidence pointer = `LANTERN:SOURCE:R-08` (fictional synthetic source); latest recorded verification = 2026-09-28. This is a durable baseline assertion for the exercise, not an independent ASR read. A candidate from chat must be evaluated against this dated durable record and the applicable source-authority rules.
- R-05: reconciled content is already represented; provenance = `owner confirmed` only, pending any stronger dated direct-source pointer. This is not a new unknown about R-17.

## Open
- Resolve R-17 current version from ASR.
- Complete final source-to-index consistency check: compare all 24 current source identities/statuses against the 24 v3.0 index entries and confirm no stale or missing mapping remains.

## Hold / blocked
Release v3.0 is blocked until **both**:
1. R-17 is verified; and
2. the final source-to-index consistency check passes.

## Unknowns
- UNKNOWN: R-17 current authoritative version.
  - SYSTEM_OF_RECORD: ASR
  - AUTHORITY_POINTER: `ASR:R-17` (fictional external item key; ASR itself is not included in this example)

## Immediate next gate
Check R-17 directly in ASR using `ASR:R-17`, then update current state with the verified version and perform the final 24-to-24 source/index consistency check.

## Do not do now
- Do not infer R-17 version from an old chat.
- Do not release merely because only one in-scope item remains unresolved.
- Do not copy restricted source content into the durable workspace.
