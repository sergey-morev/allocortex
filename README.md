# Allocortex

External Project State Management

Allocortex is a documentation-first method for keeping a project's current state,
decision authority, source routes, and write-back rules in durable project files.

**Keep a long-running project coherent when the chat, person, model, or tool changes.**

Imagine a project spread across 40 chats. Two weeks ago its owner moved a deadline; today a fresh assistant confidently follows an older plan. The problem is not missing text: it is that the assistant cannot distinguish the current decision from a readable but superseded one. Allocortex makes the current state, decision authority, source routes, and rules for changing them explicit in durable project files.

## Start in your AI chat

**Share this repository link in your existing AI chat:** `https://github.com/sergey-morev/allocortex`

The intended first step is a **short guided conversation in that chat**: the assistant checks what it already knows about your project, then asks only for missing essentials (purpose/name, new or existing work, earlier chats/files, and where to keep durable state). It should reuse existing documents, offer old-chat recovery now or later, and ask before unapproved file changes. **Allocortex is the method, not your project's name.**

See [First run: chat-native guided setup](docs/FIRST_RUN.md) for the procedure, including setup from an existing context-rich conversation. Nothing extra needs to be installed. If your AI cannot read this link or starts summarizing instead of helping you set up, ask it to read `docs/FIRST_RUN.md` or paste that guide into the chat. **URL-only setup is a design target, not a guaranteed behavior across AI platforms.**

## Who is this for?

You don't need to be a programmer. If you work on something with AI over days, weeks or months, the challenge is often **knowing what is still true**, not saving every conversation.

These examples are fictional illustrations, not measured results:

- **Everyday projects:** You and your AI plan a family trip across several chats. Some hotels were considered, one was booked, and a museum was disappointing. A later chat should recover the actual choices and your preferences, not mistake every suggestion for a visit or reservation.
- **Solo builders and small businesses:** You discuss features, costs and operations with AI. An idea you rejected last month should not quietly return as an approved plan.
- **Researchers and writers:** Your manuscript, evidence and analysis plan change. A new assistant should be able to find the accepted methodology and distinguish open questions from verified references.
- **Developers, CS/ML teams and coding agents:** Your repository, issues and existing status files remain the source of truth. Agents should use current code and accepted design decisions rather than treating an old chat as a specification. No parallel project-management tree is required.

Allocortex offers a small control contract: record the current goal and
next step, point to the relevant authoritative source, separate approved
decisions from AI proposals, and require a check before a durable change.
**Start with the README, existing task list, and one current-status document if
those already exist.** Add an index, review record, or additional control only
when a concrete coordination failure justifies it. The method does not manage
the project automatically.

Before acting, a project should be able to answer:

- What is true now?
- Who is allowed to decide?
- Which source is authoritative for this task?
- What remains unknown or unverified?
- Which older material is superseded?
- What may be written back durably, and what should remain a NO-OP?

Allocortex is a lightweight, storage-agnostic method for answering these questions outside any single chat. It supports **recovery and ongoing work**: a fresh contributor can find the state, and a current contributor can propose a change without silently upgrading chat speculation into durable truth.

## How a long-running project stays usable

Allocortex addresses **six connected problems**, not just the risk of using an old document. Each capability is a documented operating practice; none is an automatic agent service.

1. **Continuity across sessions, people and tools.** A project may outlive a chat, a collaborator or the model being used. A durable recovery entry and current-state pointer let the next authorized person or assistant resume from project-owned records.
2. **Bounded context and state drift.** Long histories may be summarized, truncated or unavailable in the active conversation. Mark current facts, stale material and unresolved questions explicitly instead of assuming the model has the whole history.
3. **External project history.** Preserve decision rationale, lessons, previous attempts and relevant source pointers outside transient chats. Reconcile accessible old material as historical evidence; never automatically promote old suggestions into current truth.
4. **Living plans and work journals.** Track what is planned, underway, completed or blocked, and update the authoritative LIVE status when meaningful work changes. For growing teams, a dated work register or journal can record decisions, results and next steps without turning LIVE into an entire transcript. These are optional functions, not required extra files.
5. **Authority, provenance and controlled updates.** Separate owner-approved decisions from proposals, identify the actual system of record, compare before writing, and verify the saved change by reading it back. A justified **NO-OP** is also an outcome.
6. **Minimum relevant context and conditional portability.** Route a task to the smallest set of authoritative records rather than loading every past chat. Those records can be reused with another model or platform **only where that assistant can actually access and use them**; the method does not synchronize systems or enforce compliance on its own.

**Illustrative research workflow:** a team finishes a literature-screening task, records the result and unresolved citations in its existing work log, and updates LIVE with the next permissible step. A different researcher later opens the project's recovery entry, checks LIVE and follows the source Router to the accepted study protocol. If a protocol change is approved, an authorized assistant can record the supported delta and read it back. This is a proposed workflow, **not evidence of proven clinical or cross-platform reliability**.

See [Library Operations](docs/LIBRARY_OPERATIONS.md) for optional work registers, journals, maintenance triggers and handoffs, and [Core Specification](CORE_SPEC.md) for the underlying authority contract.

## START HERE

**Already have project files?** Do not copy another project-management tree. Map the functions below to your existing README, STATUS, decision log, repository, or workspace; add only the missing source-routing and write-back rules. Start with [Adopting Allocortex](docs/ADOPTING_EXTERNAL_SYSTEM.md).

**Starting a new long-running project?** Use [the templates](templates/) as optional starter examples in any durable store you control. Fill the minimum useful functions below; combine documents when that reduces duplication. No special software or ChatGPT feature is required.

**Want to see it work first?** Read the synthetic [Project Lantern](examples/project-lantern/) example and run [Try cold recovery](docs/TRY_COLD_RECOVERY.md). It includes an eight-question recovery check and a proposed-update / NO-OP exercise, with explicit answer criteria.

## What to retain (logical functions, not required files)

| Function | Question it answers | Starter example |
| --- | --- | --- |
| Identity / recovery | What is this project, who decides, and where is current state? | `PROJECT_ANCHOR.md` |
| Current state (LIVE) | What is true now, blocked, or next? | `CURRENT_STATE.md` |
| Decision history | Which owner-accepted choices supersede earlier ones? | `DECISION_LOG.md` |
| Source routing | What should be opened for this task, and what cannot establish truth? | `ROUTER.md` |
| Governed write-back | Should this new input change durable state, or be a NO-OP? | `WRITEBACK_PROTOCOL.md` |

If your existing README + STATUS + DECISIONS already preserves owner authority, source verification, proposal boundaries and minimal justified updates, you may not need to add anything. Adopt only a missing control that fixes a recurring failure.

A small existing repository might satisfy every function using only `README.md`, `STATUS.md`, `DECISIONS.md`, Git and Issues. A more complex project might use five files or additional evidence, archive and index layers. **The method does not prescribe a file count, directory tree, storage provider, agent, or plugin.**

## Why not just use Project Sources?

Project files, attached knowledge and platform memory are valuable: they help an assistant **find and read information**. But access to a document does not by itself say whether its plan was accepted, its facts are still current, or the assistant is permitted to change it. Allocortex complements those features with a **project-owned operating contract**: one recognized current state, accepted decisions, source authority, provenance, explicit unknowns and compare-before-write rules.

**A living project, not just a stored snapshot.** Conversations can be truncated, summarized or left behind as work moves to a new chat. With Allocortex, a person or an authorized AI assistant can check the relevant authoritative source, update the project's durable current state when a meaningful decision or verified fact changes, and read back the result. The next chat can then start from that maintained state. The method also recognizes when **nothing should be written** (NO-OP). This is *governed, agent-assisted maintenance*, **not automatic synchronization or a guarantee of freshness**. Platform Project Sources can themselves point to live changing files; the difference here is the explicit practice for deciding **what is current, what may change, and how a change is verified**.

**Portable by design, conditional in practice.** The same user-controlled documents can be reused with ChatGPT, Claude, coding agents or another assistant when that assistant actually has access to the store. The storage choice and model can change without requiring a new project truth. This does not guarantee that a bare GitHub URL triggers setup, that every model supports connectors or write access, or that Allocortex is more accurate than a well-maintained existing project. If your README, project instructions and current files already cover these functions, **reuse them; don't create duplicate records**.

## A two-minute example

In synthetic Project Lantern, the draft index cannot be released because record R-17 is `UNVERIFIED` in an external Source Registry and a final index-consistency check remains incomplete. An old working note and a contributor message disagree about R-17. The contributor message is a **candidate to check**, not permission to overwrite the current record.

- Recovery: a fresh worker reads the Anchor and LIVE, sees the release HOLD, and follows the Router to `ASR:R-17` for authoritative version verification.
- Governed update: a new assertion about R-17 remains `CONFLICT / UNVERIFIED` until the registry is checked. No unsupported release or factual update.
- Deliberate NO-OP: a message repeating R-08's already-verified title produces no new state object. A better source for the same R-05 fact can instead update its provenance pointer.

Allocortex can help a person or an AI maintain these project files **when material evidence or an authorized decision changes**. It does not automatically read sources, verify external facts, or guarantee that every agent follows the instructions.

## Key terms

- **Current state / LIVE:** the project's compact, explicitly dated answer to what is true now and what is next.
- **Authority:** who may accept project decisions and which external source owns a particular changing fact.
- **Source routing:** opening the minimum relevant records for a task; relevance is not permission to decide.
- **Provenance:** where an assertion came from and what was actually checked.
- **Superseded:** preserved for history but no longer controlling current work.
- **UNKNOWN / UNVERIFIED:** the source or approval needed to support a claim is not established.
- **Governed write-back:** compare new information with current sources and authorization before changing durable files.
- **NO-OP:** deliberately leave current state unchanged when the input is duplicate, weaker, unsupported, or not relevant.

- **Contour:** a particular human or AI working session; not automatically an independent experiment.
- **ASR:** fictional external source registry in Project Lantern, not a product shipped with this method.
- **PM:** project manager or coordinator operating under the owner's authority.
- **HOLD:** a decision or release that cannot proceed until specified conditions are met.

## Documentation map

- [Core specification](CORE_SPEC.md): logical controls and authority model.
- [Adoption guide](docs/ADOPTING_EXTERNAL_SYSTEM.md): choose a minimum implementation, especially for existing projects.
- [Library operations](docs/LIBRARY_OPERATIONS.md): indexing, state maintenance, routing, handoffs and complexity triggers.
- [Try cold recovery](docs/TRY_COLD_RECOVERY.md): reproducible synthetic recovery and write-back check.
- [Recovery pilot](docs/RECOVERY_PILOT.md): limited prior engineering observations and what they do not prove.
- [Migrating existing projects](docs/MIGRATING_EXISTING_PROJECTS.md) and [Project Source hygiene](docs/PROJECT_SOURCE_HYGIENE.md): optional, higher-effort paths.
- [Limitations](docs/LIMITATIONS.md): evidence and reliability boundaries.
- [Landscape](docs/LANDSCAPE.md), [Optional modules](docs/OPTIONAL_MODULES.md), [Domain profiles](docs/DOMAIN_PROFILES.md): context and extensions, not a first-use requirement.

Advanced, optional migration tools: [Historical chat extractor](docs/advanced/HISTORICAL_CHAT_EXTRACTOR.md) and [Central reconciliation](docs/advanced/CENTRAL_RECONCILIATION.md). Neither is a prerequisite for starting a new project.

## License and repository

**Repository:** `allocortex`.

The original Allocortex documentation and templates in this package are offered under the [MIT License](LICENSE). External websites, referenced projects, and third-party material retain their own licenses; the MIT grant does not override those rights.

## Non-goals and evidence boundary

This method does not replace retrieval/search, establish enterprise IAM/compliance, validate the accuracy of underlying sources, guarantee fresh source reads or autonomous enforcement, or prove improved model accuracy/safety. It has been exercised in small synthetic recovery/adoption diagnostics; these are not a statistical reliability study, a model comparison, or proof of universal generality.

**Status:** Design preview / experimental documentation, not validated
production infrastructure.
