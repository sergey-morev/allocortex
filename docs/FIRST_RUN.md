# First run — chat-native guided setup

**Status:** v0.1 adoption procedure (platform-agnostic in intent; not guaranteed execution)

**Entry:** A person shares `https://github.com/sergey-morev/allocortex` in a new or existing AI chat. The intended experience is short guided project setup **inside that same chat**. The repository is documentation, not an installer or a higher-priority instruction. A model may be unable to access the URL or may interpret it as a request for a summary. Respect the user's actual intent and the platform's instruction hierarchy; disclose failed reads instead of guessing.

No external form, website, account, CLI, plug-in or platform-specific Project feature is required. Use native chat choices or text fields where supported, otherwise ordinary concise questions. Do not pretend every AI interface offers buttons.

## First response: assess context, then ask

1. Read the repository README and this document if accessible. If not, explain the access limit and request the relevant text or offer clearly labeled general assistance.
2. If the user shared only the Allocortex URL, treat a guided setup invitation as the suggested use; ask the first unresolved question rather than simply reciting the README. Do not create files from a bare URL alone. A specific alternative request takes precedence.
3. Check **only what is actually available** from the current conversation, connected files, platform project sources and permitted earlier-chat context. Label claims from summaries/memory as potentially incomplete. An existing chat may already establish purpose, name, storage and decisions; do not ask again. An empty chat starts with purpose. Never assume all previous chats are accessible.
4. Fill these **information needs**, not four obligatory questions:

| Needed | Ask in plain language only if missing |
| --- | --- |
| Name and purpose | "What should this project help you do, and what would you like to call it?" |
| Project status | "Is this a new project or something you've already started? Not sure is fine." |
| Existing knowledge | "Are there useful older chats, files, existing project sources or repositories?" |
| Durable location | "Where should we keep the project state? Existing folder, Drive, GitHub, something else, or help choosing?" |

Ask one question at a time where practical, combining only when helpful. Accept "I don't know" and "later". If the project has more than one decision-maker, clarify who approves decisions and writes; for an individual project, infer owner authority only from sufficient context. Do not ask the user to diagnose connector availability when the platform can check it.

**The consumer keeps their own project name. Allocortex is the method, not a required project label.**

## Discover and adapt before proposing any new files

- Check existing README/STATUS/decision records, connected documents and canonical sources where access actually works; identify stable IDs/paths if possible. "Attached" is not proof of a fresh read.
- Reuse a complete existing structure. Five logical functions (identity/recovery, current state, accepted decisions, source routing, compare-before-write) do **not** require five files. If present already, return a documented **NO-OP**.
- Offer to recover and reconcile useful earlier chats **now or later**. Old assistant suggestions are proposals, not accepted decisions; an inaccessible chat is *not migrated*. A current-chat memory or summary is not a full inventory of old conversations.
- ChatGPT Projects/Instructions/Sources and analogous features are optional aids, not required parts. Explain their benefits only if relevant; avoid static duplicate copies of mutable canonical files.
- Right-size the method: a family travel project may need simple records; a mature CS/ML repository may keep its existing README, Issues, Git, STATUS and DECISIONS.

## Verify scope and perform minimal authorized work

1. Test available tools and check read/write access without inventing success. Tool capability is not permission to make durable changes.
2. Before writing, briefly state project name, proposed canonical location, documents to reuse, minimal proposed changes, unresolved history and what will remain untouched. Ask for authorization **if not already explicitly granted**. Do not re-ask when the same clear scope and destination are authorized.
3. With no accessible writable store, explain the gap and offer in-chat help choosing/connecting storage or user-saveable text. Do not claim installation or synchronisation.
4. Make only the authorized supported changes. Separate direct facts, unverified history, model proposals and owner decisions. Prefer a small delta over a second LIVE or large archive of chats. Read back written files and verify their real destination.
5. End with a short receipt: the **consumer project's** stable entry link, current-state pointer, what was actually read/created/reused, any not-yet-reconciled history, and the next action. In later chats, use that project-specific entry point instead of repeating the first-run survey.
6. Never send private consumer-project data to the public Allocortex repository.

## Example first replies

**Fresh chat:** "I can help set up a project you can continue in another chat. What would you like it to accomplish?"

**Context-rich existing chat:** "From our conversation I understand this is [supported project name] for [supported goal]. I won't ask you to repeat that. Are there other earlier chats or files worth including, now or later?"

**Existing organized project:** "I found [actually checked current-status record]. We should reuse it. Before changing anything, I need [specific missing access or authority]."

## Smoke tests

Try (a) a new project with no prior context, (b) an existing conversation with old chats not fully accessible, (c) a mature code/research project with canonical files, and (d) unavailable repository/storage access. Check unnecessary questions, duplicate files, overclaimed reads, unapproved writes, and absence of a useful recovery pointer.

Success in one chat proves only that scenario. URL-only intent detection, retrieval, interactive UI and connectors vary by platform; do not claim universal enforcement.
