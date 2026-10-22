# Core Specification




## 1. Project identity and recovery
Every implementation of Allocortex needs a low-drift recovery surface that states the project mission, owner/final authority, delegated roles, durable-state location, recovery order, authority hierarchy, and fail-closed rule.




Where the storage supports stable object identifiers, recovery pointers should include them. Display names alone are not reliable identity.




## 2. Authoritative mutable current state
The project must declare one current-state surface for what is true now. It should include freshness metadata, current phase, baseline, open work, blockers, unknowns, next gate, and prohibitions.




If an external system owns a fact, current state should contain an explicit pointer to that authority rather than pretending to replace it.




Freshness metadata can make staleness visible; it does not keep state current automatically.




## 3. Authority is explicit
Tool capability does not imply authority. The system must distinguish who may propose, update working state, accept decisions, change scope, or authorize release/action.




## 4. Stable rules are separate from mutable state
Mission, authority, recovery order, and low-drift epistemic rules should not be mixed with fast-changing project facts.




## 5. Decisions append and supersede
Accepted decisions are distinct from proposals, advice, reviews, and model suggestions. Revisions should be represented by append-and-supersede semantics rather than silent history rewriting.




## 6. Evidence and provenance remain typed
Primary source, system-of-record fact, owner statement, working note, review, interpretation, proposal, and unknown should not collapse into one undifferentiated memory layer.




External/contributor material should enter as `PROPOSED` or another explicit non-authoritative status until reviewed.




## 7. Retrieval is task-conditioned


The source being attached, linked or indexed does not establish that an agent has actually opened it. Source activation should be verified where a consequential answer depends on freshness; otherwise explicitly preserve `UNVERIFIED`. A simple formatting task does not require loading the entire library.
The system should define which source classes are activated for which tasks. Retrieval relevance does not determine authority.




Navigation should prefer stable identifiers where the storage supports them. A display name may be useful for humans but should not be assumed to uniquely identify an object.




## 8. Write-back is governed
Chat/model output is candidate delta, not durable truth. Before writing:




1. read current state;
2. read the relevant authority source;
3. classify the candidate delta;
4. compare with existing durable state;
5. verify support;
6. select the correct destination;
7. write the smallest justified consequence.




## 9. Deliberate non-write is valid
If information is already represented with equal or better support, is weaker, is duplicate, or remains unresolved, NO-OP may be the correct result.




## 10. Supersession and archive semantics are explicit
Readable historical material is not automatically current. Superseded material should remain available for provenance while visibly losing present authority.




## 11. Fail closed
If required current state or external authority cannot be established, preserve `UNVERIFIED` / `UNKNOWN` and pause state-sensitive action. Do not reconstruct certainty from archive or chat memory.




## 12. Authority and freshness are different dimensions
The newest source is not necessarily authoritative, and an accepted decision is not necessarily fresh evidence about mutable external reality.




## Implement the functions, not a fixed file tree


The control functions can be mapped to existing README/STATUS/DECISIONS, issues and repository history. Templates provide optional starting text for new projects. A coherent existing project should reuse its authorities instead of adding competing copies. Project Sources and platform instructions, if used, are optional adapters rather than mandatory parts of the method.


## Design constraints
- **Minimal sufficient durable state:** optimize for future decision quality, not memory volume.
- **Storage agnostic:** plain files must be sufficient for the core method.
- **External systems of record may own truth:** store pointers and reconciled consequences where appropriate.
- **Proportional governance:** overhead should scale with consequence, ambiguity, volatility, volume, and collaboration complexity.