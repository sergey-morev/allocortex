# Adopting Allocortex in Another Project








**Status:** PUBLIC DRAFT / AGNOSTIC  
**Purpose:** show how a project can adopt the method without the Allocortex maintainer taking over that project's governance.








## First-time entry from an AI chat

The recommended entry is to share the Allocortex repository URL **within the AI chat already in use**. Follow [First run — chat-native guided setup](FIRST_RUN.md): inspect the actually available conversation/project context, ask only for unresolved details, inventory prior chats and existing files, and reuse rather than duplicate existing authority. An existing chat may need **zero** questions; a new chat may start with a single question about purpose. Offer history recovery now or later. The consumer project's name is not `Allocortex`.

Keep onboarding in-chat. Platform-native choices are optional; brief text questions work where rich widgets do not exist. No separate onboarding website or compulsory Project Source is required. A bare URL does not reliably trigger setup on all products; disclose a failed repository read and let the user provide the guide. Before durable writes, establish target and authority; verify saved files with readback. See the full first-run contract for the branches and failure cases.

## Choose an adoption path (START HERE)








**Existing organized project:** map five logical functions to the project's current authoritative surfaces before creating anything. For example, a repository's README can hold identity, owner and recovery order; STATUS can remain the single current state; DECISIONS can remain the accepted-decision log; Issues and Git retain their own source roles. Add only missing source-routing and governed write-back rules. Do not create duplicates or copy templates by default.








**Concrete existing-repository mapping (example, not a new file tree):**




| Existing artifact | Allocortex function | Keep/change |
| --- | --- | --- |
| `README.md` or a stable existing project guide | Identity, owner, recovery entry, source-routing/writeback trigger | Add a short stable operating section only if absent |
| `STATUS.md` | **Sole LIVE/current state** | Keep it; do **not** also create `CURRENT_STATE.md` |
| `DECISIONS.md` | **Sole accepted-decision/supersession log** | Keep it; do **not** also create `DECISION_LOG.md` |
| GitHub Issues | Work queue and proposals | Point to issues rather than copying every task into STATUS |
| Git history and repository files | Code/document provenance | Use exact commit/path/revision, not chat recollection |




**Minimal README operating rule (copy/edit as needed):**
```text
Owner decides scope and release; model suggestions remain PROPOSED.
For state-sensitive tasks: read STATUS.md, then the exact authoritative source.
For accepted decisions/supersession: read DECISIONS.md.
For task progress: consult Issues; for code truth: inspect Git/repository.
If the required current source cannot be read, state UNVERIFIED and do not change state.
Before writing: classify, compare with existing state and acceptance evidence;
write only the supported difference or explicitly choose NO-OP.
Never create a second LIVE/decision log just to install a template.
```




Combining logical functions means reusing existing authoritative surfaces, **not** mixing stable owner/authority rules into a fast-changing status blob. If README is frequently rewritten, put stable rules in the least-changing existing file or one small CONTROL.md only if needed.




**New long-running project:** begin with the five logical functions (identity/recovery, current state, accepted decisions, routing, write-back). The files in `templates/` are optional examples, not a mandatory directory structure. Combine functions when safe, choose any durable store, and record stable IDs only after they exist.








**Both paths:** try one clean recovery and one proposed-update / deliberate NO-OP test (see `docs/TRY_COLD_RECOVERY.md` and the synthetic `examples/project-lantern/`). An accepted result verifies the tested scenario, not automatic source reads in all later conversations.








## Ownership boundary








Allocortex is a method/control layer.








It should provide:
- templates;
- recovery and migration procedures;
- examples;
- validation criteria;
- optional folder/file patterns.








It should **not** assume authority over a consumer project.








The consumer project's owner or local PM decides:
- whether an external state layer is useful;
- which storage provider to use;
- what counts as authoritative;
- which folders/files to create;
- who may write;
- what Project Sources, repository files, or other sources should remain active;
- when migration or cleanup is complete.








A cross-project reviewer may propose a structure. It should not create or mutate that structure unless the local project explicitly authorizes it.








## Project Sources and platform instructions (optional)








Project-specific instructions can remind an assistant *when* to consult current state, and a low-drift source file can route it to the right records. Neither guarantees that a current Drive/repository record was actually opened. Where material, verify the read or mark the claim `UNVERIFIED` rather than infer freshness from the presence of a link. Platform-specific Instructions/Sources are optional adapters, not a core requirement.
















Allocortex must not assume that a project has ChatGPT Project Sources.








A valid project may have:
- zero Project Sources;
- one stable gateway;
- several source documents;
- a repository only;
- a document store only;
- a mixed setup.








The recovery contract is about authority and retrieval, not about a particular product feature.








## Generic reference topology








This is an **example**, not a required folder tree.








External project state may include:








- **Anchor / identity**
  - project purpose
  - owner/final authority
  - systems of record
  - recovery order
  - fail-closed behavior








- **Current state**
  - phase
  - accepted present facts
  - open unknowns
  - next gate








- **Decision log**
  - accepted decisions
  - supersession
  - rationale when needed








- **Router**
  - where different classes of information live
  - which source is authoritative for which question








- **Reconciliation intake**
  - PROPOSED reports from old chats or contributor contours








- **Recovery / diagnostics**
  - frozen packets
  - test receipts
  - migration results








- **Archive**
  - processed reports
  - superseded state
  - provenance that should not remain active








A project may combine or omit these pieces when simpler structure works.








## Generic adoption handoff








A method maintainer or outside reviewer should hand the local PM something like:








1. **Problem statement**
   - what continuity/state problem was observed








2. **Agnostic starter template**
   - possible Anchor / Current State / Router / Decision Log fields








3. **Migration tools**
   - source-chat extraction prompt
   - central batch reconciliation prompt








4. **Constraints**
   - historical chats are candidate evidence
   - local project authority wins
   - no direct contributor write-back during bulk migration unless the local project explicitly authorizes it
   - exact object identity before reconciliation claims








5. **Acceptance test**
   - a clean contour can recover current state and next permissible action from the local project's chosen external sources








Then the **local PM** instantiates the structure.








## Example folder pattern








If a project chooses a folder-based external store, one possible topology is:








00_CONTROL  
01_RECONCILIATION_INBOX  
02_RECOVERY  
99_ARCHIVE








This is intentionally non-normative.








The same logical roles could be:
- repository directories;
- Notion databases;
- Obsidian folders;
- SharePoint libraries;
- plain files;
- another provider.








## When the local PM should refuse the template








Do not create a new external layer merely because the method offers one.








Refuse or simplify the template when:
- the project already has a coherent system of record;
- a repository already contains sufficient current state;
- duplication would create a second source of truth;
- the project has no migration problem;
- one gateway/pointer is enough.








## Public examples








Public examples should be synthetic or clearly marked examples.








A real project's folder names, personas, local decisions, or tool-specific history should not become normative public architecture merely because that project was used as a pilot.








## Self-contained operating model








A consumer project should not need access to a private pilot or reference project to learn the operating structure.








Use `docs/LIBRARY_OPERATIONS.md` for the agnostic continuity model: minimum control plane, complexity profiles, indexing triggers, LIVE-state discipline, optional work register, handoff behavior, update triggers, hygiene, and clean-recovery acceptance tests.








Use `templates/INDEX_TEMPLATE.md` when a collection becomes nontrivial enough that a fresh contour cannot reliably choose the right artifact from the folder listing alone.








Reference projects may demonstrate the method, but they are evidence, not required dependencies.








Governance should scale with observed complexity. A small project should not inherit a high-assurance project's risk maps, registers, audit volume, or release machinery unless those controls close a concrete failure mode.