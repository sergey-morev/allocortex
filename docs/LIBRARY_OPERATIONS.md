# Library Operations








Status: PUBLIC DRAFT / AGNOSTIC








Purpose: give a new project a reproducible operating structure for continuity, current-state control, indexing, handoff, evidence, recovery, and archive without requiring access to another private project as a model.








## 1. Reproducibility rule








A method is incomplete if a user must be told to inspect another private project to learn how to organize their own.
Pilot projects may supply evidence, but the reusable mechanism must be present in this repository as templates, operating rules, triggers, and recovery tests.








## 2. Minimum control plane








For a nontrivial long-running project, start with five logical functions:
- Project Anchor: mission, owner, authority, systems of record, recovery order, fail-closed rule.
- Current State / LIVE: what is true now, current phase, blockers, unknowns, immediate next gate.
- Decision Log: accepted decisions and supersession.
- Router: what source classes exist, where they live, when to activate them, and what they must not be used as.
- Writeback Protocol: how candidate chat/model output becomes, or does not become, durable state.








These are logical functions, not mandatory filenames or folders.








## 3. Optional operating layers








Add only when the project actually generates the corresponding artifact class:
- Evidence
- Audits / independent reviews
- Working analysis
- Drafts
- Handoffs
- Outputs / releases
- Reconciliation inbox
- Recovery / diagnostics
- Archive








A folder-based implementation may use CONTROL -> AUDITS -> EVIDENCE -> HANDOFFS -> RECOVERY -> ARCHIVE, but this is an example, not a required topology.








## 4. Complexity profiles








### Minimal
Use when one owner and one active workstream can still recover the project safely.
Required logical coverage (which may be combined in existing files): identity/recovery, LIVE, accepted decisions, routing, and governed write-back. Do not create duplicate documents when those functions already exist.








### Growing
Use when the project has multiple artifacts, recurring handoffs, old-chat migration, or more than one workstream.
Add indexes to nontrivial collections, a dated handoff note when continuity requires it, and a small work/disposition register if prioritization can no longer be reconstructed safely from LIVE.








### High-assurance
Use only when consequence, collaboration, or verification burden justifies it.
Possible additions: independent audit layer, exact-artifact review, risk register, formal work-package gates, release controls, stronger evidence receipts.








Do not import high-assurance bureaucracy into a small project merely because another project uses it.








## 5. Indexing








Create an index when a fresh competent reader can no longer reliably answer 'what should I open?' from the collection listing alone.








Typical triggers:
- several materially different artifacts coexist;
- multiple statuses are present;
- same or similar titles exist;
- superseded material remains searchable;
- operators repeatedly open the wrong object;
- retrieval depends on remembered history;
- a collection mixes evidence, review, draft, output, and archive objects.








An index should contain only navigation metadata:
- title
- stable ID/path when supported
- date/period
- status
- semantic class
- one-line 'open when' description
- provenance when useful
- supersedes / superseded-by when relevant
- access/sensitivity note when needed








An index is not a second Current State or a narrative summary.








## 6. LIVE / Current State








LIVE answers one question: what is true now and what is the next permissible action?








Recommended fields:
- VALID_AS_OF / LAST_VERIFIED
- current phase
- current baseline
- open work
- hold / blocked
- explicit unknowns
- immediate next gate
- do-not-do-now constraints








Keep LIVE small enough for routine cold-start reading.








Update LIVE on material state transitions, not because a chat ended.








## 7. Work / disposition control








Add a tracker or control register only when multiple work items compete or status can no longer be held cleanly in LIVE.








Useful fields:
- item ID
- work package / finding
- class or bucket
- evidence status
- impact / urgency when relevant
- dependency / collision
- owner/lead
- status
- next gate








The reusable function is work/disposition control. A spreadsheet is only one implementation.








## 8. Journal








A lightweight journal can preserve chronology when event ordering matters.








Use it for material events only:
- date
- event
- exact artifact/state
- result
- evidence status
- source








Do not turn the journal into a transcript.








## 9. Handoff continuity








Use a dated handoff note when session replacement or context degradation creates a real continuity risk.








A good handoff contains:
- cold-start order
- current authority pointers
- current open items
- immediate next gate
- operating boundaries
- update rule








Prefer one maintained handoff note over creating a new permanent handoff for every ordinary chat.
Create frozen/date-specific handoffs only for major phase transitions or transfers.








## 10. Recovery order








A default cold-start sequence is:
1. An optional low-drift bootstrap/gateway, if present, points to the Project Anchor. It is NOT a second Router or a competing current-state authority.
2. Read the Project Anchor (or an equivalent stable section in an existing project guide).
3. Read Current State / LIVE (or the existing sole STATUS).
4. For the task, consult Router, accepted decisions, exact systems of record, Issues/work queue or a dated handoff note ONLY as relevant. The Anchor defines the starting order; Router chooses further source files.
5. Before changing durable state, follow governed write-back with evidence, approval and deliberate NO-OP when appropriate.




Do not bulk-load the library by default. A gateway does not replace Router; a dated handoff note is not another LIVE.








Do not bulk-load the library by default.








## 11. Source-of-truth separation








Different systems may own different facts.








Examples:
- repository: code, current tree, refs/tags, repo-native technical docs;
- external document store: PM state, evidence, recovery, reconciliation, archive;
- Project Sources or equivalent: optional low-drift bootstrap only;
- old chats: candidate evidence only.








Do not create a second mutable copy of a source that already has a clear live system of record.








## 12. Supersession and duplicate identity








Archive location alone is weaker than explicit status.
When an artifact loses authority, record SUPERSEDED / ARCHIVED and point to the current replacement when practical.








Never deduplicate by title alone.
Stable object IDs, versions, hashes, or paths control identity when available.








## 13. Maintenance triggers








Update:
- Anchor only when mission, authority, recovery path, or stable operating architecture changes;
- LIVE when material current state changes;
- Decision Log when an authorized decision is accepted/reversed/superseded;
- Router when source location, activation rule, or authority boundary changes;
- Index when a material item is added, moved, reclassified, superseded, or archived;
- Handoff only when material continuity state changes.








After large migration/reconciliation runs, perform hygiene: disposition reports, update indexes, archive migration-only artifacts, keep LIVE compact, and verify the active source surface is still minimal.








## 14. Healthy bureaucracy test








Add a control artifact only if it closes a real failure mode such as:
- stale-state continuation
- wrong-source retrieval
- duplicate work
- authority confusion
- lost provenance
- unresolved contradiction
- history masquerading as current truth
- failed handoff/recovery
- uncontrolled writeback








If an artifact does not reduce a real failure mode, do not add it.








## 15. Clean recovery acceptance test








Use the public `docs/TRY_COLD_RECOVERY.md` for an operator-run eight-question semantic recovery test based on synthetic Project Lantern. Check a governed proposed update and deliberate NO-OP as a separate exercise. The report should say which documents were actually available/read, whether tool access was inspectable, and which external sources were not accessed. A content PASS is not proof of automatic retrieval or live operational deployment.








A fresh competent human or AI with no original chat history should be able to answer quickly:
- What is this project?
- Who decides?
- What is true now?
- What is the next gate?
- What is blocked or unknown?
- Where is evidence for a claim?
- Which artifacts are history/advice only?
- Which system owns mutable truth?
- What may be written back?
- What should not be loaded unless needed?








If recovery requires reading dozens of files, indexing/routing is too weak.
If all answers exist only in one giant summary, separation is too weak.
If the user must consult another private project to learn the operating structure, the public method is incomplete.








## 16. Principle








Artifact over narrative.
Index before bulk context.
LIVE for current state, not history.
Router for activation, not authority.
Preserve evidence; promote only justified consequences.
Archive for provenance, not instruction.
Governance should grow only with demonstrated complexity.