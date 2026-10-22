# Project Lantern — Project Anchor

Status: STABLE / LOW-DRIFT / SYNTHETIC

## Project
Project Lantern.

## Mission
Update and reconcile a 24-document professional reference library and release a reviewed v3.0 index without losing source provenance or allowing stale source versions to become current.

## Owner / final authority
Project Owner.

## Delegated role
Project Coordinator may classify sources, update working state, prepare candidate changes, and maintain routing metadata. The Coordinator cannot independently accept scope changes or release v3.0.

## Durable state location
Project Lantern durable workspace.

## Current state pointer
`CURRENT_STATE.md`

## Recovery order
1. Read this Anchor.
2. Read `CURRENT_STATE.md`.
3. Read `DECISION_LOG.md` when accepted choices or supersession matter.
4. Use `ROUTER.md` to retrieve the minimum relevant source.
5. Use `WRITEBACK_PROTOCOL.md` before durable updates.

## Source / authority priority
Current external system-of-record entry or exact primary source
> CURRENT_STATE after reconciliation
> accepted DECISION_LOG
> working notes / reviews
> archive / chat reconstruction.

## External system of record
The fictional Authoritative Source Registry (ASR) owns current version/status for restricted source documents. The External System stores pointers and reconciled consequences; it does not replace ASR.

## Fail-closed rule
If `CURRENT_STATE.md` cannot be read, set current state to `UNVERIFIED`. Historical work may be inspected, but release/state-sensitive decisions pause until current state is verified.

## Stable operating rules
- Accepted decision != proposal.
- Source summary != primary source.
- Relevance != authority.
- Preserve UNKNOWN when evidence is insufficient.
- Write only material delta.
- Do not duplicate restricted source content merely to centralize everything.
