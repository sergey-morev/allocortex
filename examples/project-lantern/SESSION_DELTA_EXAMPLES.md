# Project Lantern — Session Delta Examples

## Example A — deliberate NO-OP

Chat finding: `R-08 is now titled Operating Checklist.`

Existing durable record already contains R-08 = `Operating Checklist`, with a newer verification date and direct source pointer.

Disposition: `ALREADY_REPRESENTED` -> `NO-OP`.

## Example B — unresolved conflict

A contributor reports R-17 is version 4.2. An older working note says 4.1. No current ASR check has been completed.

Disposition: `CONFLICT / DO NOT OVERWRITE`.

Required resolution evidence: current `ASR:R-17` entry.

Durable consequence: keep R-17 `UNVERIFIED` until ASR is checked.

## Example C — provenance upgrade

R-05 is already reconciled, but provenance says only `owner confirmed`.

An exact dated source artifact becomes available and supports the same content.

Disposition: `PROVENANCE_UPGRADE`.

Write action: update the provenance pointer and verification date; do not create a second R-05 state object.
