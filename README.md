# Allocortex

External Project State Management

Allocortex is a documentation-first method for keeping a project's current state,
decision authority, source routes, and write-back rules in durable project files.

**Keep a long-running project coherent when the chat, person, model, or tool changes.**

Imagine a project spread across 40 chats. Two weeks ago its owner moved a deadline; today a fresh assistant confidently follows an older plan. The problem is not missing text: it is that the assistant cannot distinguish the current decision from a readable but superseded one. Allocortex makes the current state, decision authority, source routes, and rules for changing them explicit in durable project files.

## Where this helps

These fictional situations illustrate the same coordination problem:

- **Research and manuscripts:** A researcher has an accepted analysis plan, but
  an outdated manuscript draft describes an earlier method. A new collaborator
  needs to find the accepted plan, identify superseded text, and keep suggested
  changes separate from approved decisions.
- **Solo founders building with AI:** A founder uses AI across a storefront,
  customer records, and operational tasks. A rejected feature returns in a new
  chat; the next session needs the current scope and the repository or business
  source that controls each fact.
- **Software maintenance with multiple agents:** A maintainer coordinates
  several agents working across issues and branches. One agent follows a
  superseded approach; contributors need the current decision, task ownership,
  and relevant commit before proposing an update or duplicating work.

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

**Repository:** `external-project-state`.

The original Allocortex documentation and templates in this package are offered under the [MIT License](LICENSE). External websites, referenced projects, and third-party material retain their own licenses; the MIT grant does not override those rights.

## Non-goals and evidence boundary

This method does not replace retrieval/search, establish enterprise IAM/compliance, validate the accuracy of underlying sources, guarantee fresh source reads or autonomous enforcement, or prove improved model accuracy/safety. It has been exercised in small synthetic recovery/adoption diagnostics; these are not a statistical reliability study, a model comparison, or proof of universal generality.

**Status:** Design preview / experimental documentation, not validated
production infrastructure.
