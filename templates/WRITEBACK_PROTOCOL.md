# Write-back Protocol

Status: STABLE OPERATING RULE

## Before writing
1. Read `CURRENT_STATE.md`.
2. Read the authority source relevant to the proposed change.
3. Identify the candidate delta.

## Classify the candidate
- PROPOSED / REVIEW_REQUIRED: contributor or model suggestion; never owner-accepted by classification alone
- NEW_FACT
- ACCEPTED_DECISION
- STATE_CHANGE
- RESOLVED_UNKNOWN
- CORRECTION
- PROVENANCE_UPGRADE
- CONFLICT
- ALREADY_REPRESENTED

## Compare first
Ask whether the durable system already contains the same material with equal or better evidence.

## Write rule
- New + supported -> update the correct existing destination.
- Proposal / review lead -> keep only in an existing Issue, working note or optional intake if useful; do not put it in the accepted Decision Log or promote it to LIVE without verification and relevant authorization.
- Owner-accepted decision -> record who accepted it, when, and a pointer to the acceptance act (where available); append a new decision and mark supersession.
- Evidence improved but the broad fact did not -> update provenance; do not create a duplicate state object.
- Claims conflict and authority is unresolved -> preserve the conflict and name the evidence required to resolve it.
- Already represented -> `NO-OP`.
- Unsupported -> do not promote; classify as UNVERIFIED or discard/NO-OP when not useful.
- An owner's decision about project actions is different from an owner's unsupported claim about facts belonging to an external system of record.

## Smallest justified consequence
Do not paste an entire conversation into durable state when one verified sentence, decision entry, or source pointer is sufficient.

## Fail closed
If current state or required external authority cannot be checked, do not reconstruct current truth from archive or chat memory.

## After an attempted write: verify the durable result

Read back the actual destination through an available tool or have the owner verify it. Check the expected file/object identity, location, accepted content and version/revision when supported. Record what was observed separately from what was merely requested.

If the write succeeded but readback or destination verification is unavailable, state `WRITEBACK_UNVERIFIED`; do **not** report an accepted durable update as confirmed. If no write is justified, return an explicit `NO-OP` and name the reason.

## End-of-session check
A productive discussion with no state/evidence/decision delta requires no durable write.
