# Landscape and Neighbors


Initial landscape checked: 2026-10-02. Selected public references rechecked: 2026-10-22; this is not an exhaustive market survey.


Allocortex sits near several active categories. It should not be presented as replacing them, and none of the categories below is a safe novelty claim by itself.


## Persistent agent memory


### Letta
Letta persists agent state and exposes structured memory blocks that can be shared and updated across interactions. Its focus is agent memory/state and context management.


- https://docs.letta.com/v1-sdk/memory/memory-blocks
- https://docs.letta.com/api/resources/agents


### Mem0
Mem0 positions itself as a memory layer for AI applications, focused on extracting, storing, and reusing interaction context.


- https://guide.mem0.ai/


### Basic Memory
Basic Memory stores AI memory as user-owned Markdown, adds search/relations, and exposes read/write/context tools through MCP. It is a close neighbor on portability and plain-file persistence.


- https://docs.basicmemory.com/start-here/what-is-basic-memory


### Zep / Graphiti
Graphiti and Zep emphasize temporal knowledge graphs, provenance, changing facts, and hybrid retrieval. This overlaps with temporal provenance and supersession concerns.


- https://help.getzep.com/graphiti/getting-started/welcome
- https://www.getzep.com/ai-agents/temporal-knowledge-graph/


## Project context and software workflows


### Cline Memory Bank
Cline's Memory Bank uses a structured set of Markdown files to preserve software-project context across stateless sessions.


- https://github.com/cline/prompts/blob/main/.clinerules/memory-bank.md


### GitHub Spec Kit
Spec Kit is a structured, agent-assisted process harness with durable specifications, plans, tasks, workflows, templates, and agent integrations.


- https://github.com/github/spec-kit
- https://github.com/github/spec-kit/blob/main/docs/index.md


### BMAD Method
BMAD is a structured agent-assisted software-delivery framework with durable decisions, project context, role/workflow artifacts, and review gates.


- https://github.com/bmad-code-org/BMAD-METHOD


## Continuity architecture and governance


### AI Continuity Architecture Method
AI Continuity Architecture Method is a particularly close methodology neighbor. Its public materials describe a structured external context system for preserving project identity, state, decisions, authority, provenance, uncertainty, privacy, supersession, and continuity across sessions, models, platforms, and human-AI boundaries. It also uses current-state and portable-workstate concepts and includes synthetic continuity testing.


- https://github.com/psycedelicAI/AI-Continuity-Architecture-Method


Implication: governance-centered continuity architecture, portable workstate, explicit authority/status, and synthetic continuity testing are not safe category-level novelty claims.


### CIRISConformance
CIRISConformance frames AI governance as epistemic governance with accountable authorization and conformance checks. It is more runtime/institutional than Allocortex, but it is relevant to the broader authority/governance landscape.


- https://github.com/CIRISAI/CIRISConformance


Implication: explicit governance and authorization boundaries for AI systems are established neighboring work.


### Runtime Assurance Contracts
The paper "Trust Is Not a Score: Runtime Assurance Contracts for High-Risk AI Agents" formalizes non-compensatory gates in which a failed or unknown mandatory gate blocks, defers, escalates, or stops consequential action.


- https://arxiv.org/abs/2609.39717


Implication: fail-closed behavior on UNKNOWN/failed gates is not a safe novelty claim. The paper addresses runtime authorization rather than durable project-state continuity.


### Proof-of-Continuity
"Proof-of-Continuity" proposes a temporal/causal discipline for propagating authority across distributed systems and AI-agent execution chains.


- https://arxiv.org/abs/2607.08906


Implication: authority continuity and lineage are established concerns in adjacent formal work, although the problem differs from project-state recovery.


## Positioning boundary


Allocortex should not claim that persistent context, Markdown memory, decision logs, temporal provenance, structured agent workflows, role continuity, explicit authority, fail-closed governance, governance-centered continuity architecture, or executable governance checks are new.


The current design emphasis is narrower:


- project state belongs to the work, not to a particular model/session;
- authority is explicit and separate from retrieval relevance;
- external systems of record may own truth;
- UNKNOWN/UNVERIFIED can block state-sensitive action;
- durable write-back is compare-first and governed;
- deliberate non-write is valid;
- supersession is explicit;
- navigation should use stable identifiers where the storage supports them;
- the minimum implementation can be plain files with no mandatory memory engine, vector database, or agent runtime.


These are design choices and positioning hypotheses, not novelty or superiority claims.