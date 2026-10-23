# Project Lantern — Write-back Protocol

Before writing:
1. read current state;
2. read the authority source relevant to the proposed change;
3. identify the candidate delta.

Candidate classes:
`PROPOSED`, `NEW_FACT`, `ACCEPTED_DECISION`, `STATE_CHANGE`, `RESOLVED_UNKNOWN`, `CORRECTION`, `PROVENANCE_UPGRADE`, `CONFLICT`, `ALREADY_REPRESENTED`.

Rules:
- PROPOSED stays in an existing working note or Issue until authorized; it is not an accepted decision.
- Accepted decisions require an approval reference, date, and authorized actor in a real project.
- Check the existing durable record before adding material; choose NO-OP for duplicates.
- genuinely new + supported -> update the correct destination;
- accepted decision changed -> append a new decision and mark supersession;
- evidence improved but broad fact unchanged -> update provenance without a duplicate state object;
- unresolved conflict -> preserve conflict and name resolution evidence;
- already represented -> `NO-OP`;
- unsupported -> do not promote.

After an authorized durable update, read back the actual saved record, confirm the correct destination and content, and retain a minimal verification receipt. If the destination cannot be checked, report `WRITEBACK_UNVERIFIED` instead of asserting success. A NO-OP requires no write receipt.

If current state or required external authority cannot be checked, fail closed.
