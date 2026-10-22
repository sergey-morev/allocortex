# Project Lantern — Router

Status: CURRENT NAVIGATION METADATA

## Project Anchor
SEMANTIC_CLASS: stable control
ACTIVATION: ALWAYS on cold start
USE_WHEN: recovering project identity, authority, and recovery rules
DO_NOT_USE_AS: current mutable state

## Current State
SEMANTIC_CLASS: authoritative mutable state
ACTIVATION: ALWAYS before state-sensitive work
USE_WHEN: checking current phase, blockers, unknowns, and next gate
DO_NOT_USE_AS: primary source for an external fact that can be checked directly in ASR

## Decision Log
SEMANTIC_CLASS: accepted project decisions
ACTIVATION: TASK
USE_WHEN: a question depends on accepted strategy or supersession
DO_NOT_USE_AS: evidence that an external source is currently valid

## External system of record — ASR
SEMANTIC_CLASS: external authority / system of record
ACTIVATION: TASK / CONDITION
USE_WHEN: verifying restricted-source version/status
LOCATION: external; not packaged. Obtain item key from `CURRENT_STATE.md` `AUTHORITY_POINTER`.
DO_NOT_USE_AS: copied source content

## Working Notes — optional / not instantiated in this minimal example
SEMANTIC_CLASS: analysis / review
ACTIVATION: TASK
USE_WHEN: comparing candidate changes
DO_NOT_USE_AS: accepted decision or authoritative source

## Archive — optional / not instantiated in this minimal example
SEMANTIC_CLASS: historical / superseded
ACTIVATION: MANUAL
USE_WHEN: provenance or reconstruction is explicitly needed
DO_NOT_USE_AS: current instruction

## Authority priority
See `PROJECT_ANCHOR.md`. This Router governs activation and use; it does not redefine the authority hierarchy.

## Minimum retrieval rule
Read only the source classes needed for the task. Do not bulk-load the full history.

## Archive rule
Readable does not mean current. Superseded material must retain visible non-current status.
