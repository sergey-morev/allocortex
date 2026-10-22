# Project Anchor

Status: STABLE / LOW-DRIFT

## Project
[Project name]

## Mission
[What this project is trying to accomplish. Keep this stable and outcome-oriented.]

## Owner / final authority
[Who can accept scope changes, final decisions, and release/action.]

## Delegated roles and limits
- [Role]: may [actions]; may not [actions].

## Durable state location
[Folder/repository/workspace that holds the Allocortex project state.]
STABLE_ID / POINTER: [provider object ID, repository URL, path+ID, or equivalent when supported]

## Current state pointer
`CURRENT_STATE.md`
STABLE_ID / POINTER: [stable object identifier when supported]

Prefer stable identifiers where the storage supports them. Display names are navigation labels, not reliable identity.

## Recovery order
1. Read this Anchor.
2. Read `CURRENT_STATE.md`.
3. Read `DECISION_LOG.md` when accepted choices or supersession matter.
4. Use `ROUTER.md` to retrieve the minimum relevant source.
5. Apply `WRITEBACK_PROTOCOL.md` before durable updates.

## Source / authority priority
[Define the stable authority hierarchy. Example:]

external system of record / exact primary source
> reconciled current project state
> accepted decisions
> working analysis / review
> archive / chat reconstruction

## External systems of record
[List systems that may own truth outside this project. State what each owns.]

## Fail-closed rule
If required current state cannot be established, mark it `UNVERIFIED` / `UNKNOWN` and pause state-sensitive action. Do not reconstruct certainty from stale chat or archive material.

## Stable operating rules
- Accepted decision != proposal.
- Relevance != authority.
- Source summary != primary source.
- Preserve UNKNOWN when evidence is insufficient.
- Write only material durable delta.

## Update trigger
Update this Anchor only if mission, authority, recovery path, durable-state location, or stable control rules materially change.
