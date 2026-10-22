# Try cold recovery (synthetic, repeatable)








Allocortex can be evaluated without old chats, private projects or any specific model. This is a **small diagnostic**, not an independent benchmark or reliability guarantee.








## 1. Prepare the input








Use only FIVE synthetic Project Lantern files as the runner input: `PROJECT_ANCHOR.md`, `CURRENT_STATE.md`, `DECISION_LOG.md`, `ROUTER.md`, and `WRITEBACK_PROTOCOL.md` from `examples/project-lantern/`. Do NOT provide `SESSION_DELTA_EXAMPLES.md`, the example README, the full repository, old conversations or the evaluator answer key: worked examples would reveal how the conflict and NO-OP exercises are intended to resolve. If file access is unavailable, mark `INCONCLUSIVE_ACCESS`, not a semantic failure.








Do **not** give the test contour the evaluator key file, this complete repository, or access to an index that reveals the key. Provide ONLY the five specified Lantern files and the prompt below. The key is public but structurally separate; the diagnostic is transparent, not a secure benchmark.








## 2. Copy this prompt into a fresh session








```text
Use only the attached Project Lantern synthetic files; do not use previous conversations, account memory, outside research or other projects. Do not modify any files. Briefly answer these eight questions with a source filename/pointer and mark inaccessible details UNKNOWN:
1. What is Project Lantern doing and who may authorize v3.0 release?
2. What is the current phase, how many reference items are in scope, and what is the status of the draft v3.0 index?
3. What are the TWO separate conditions that block release?
4. What exactly is UNKNOWN about R-17, and which source owns current version truth?
5. What is the next permissible action?
6. How did the restricted-source policy change between decisions D-001 and D-002?
7. A contributor presents a dated but unverified message asserting R-17 is version 4.2 and asks you to clear the release hold. The external ASR is not available. What can be changed, if anything, and why?
8. A contributor asks to set R-08's title to `Operating Checklist`. Compare the candidate with the supplied dated durable record. Is a write justified?
State what you could not verify from the supplied synthetic files. Distinguish a proposal, a current authoritative fact, and a historical source. Do not claim to access the external ASR.
```








Save the full reply as a dated test receipt, including the exact input files and whether actual source reads can be observed. Evaluating the prose alone does not prove a tool was called or that permissions were enforced.








## 3. Separate evaluator answer key




The human evaluator reads `docs/TRY_COLD_RECOVERY_KEY.md` **after** the runner report is complete. The runner must receive only the five named Lantern input files and the eight-question prompt in §2; not this repo or the key. The public key is a transparent educational aid, not a secure held-out benchmark. If the runner read or was supplied the key, mark `INVALID_KEY_EXPOSED`, never `PASS`.




## 4. Verdict




- `INVALID_KEY_EXPOSED`: the runner could read the answer key, was shown the key, or had it supplied as part of the input; do not score this as a clean run.








- `PASS`: all eight material answers correct, both release gates preserved, ASR not falsely claimed as accessed, and no unsupported factual write-back.
- `PASS_WITH_MINOR_REPAIR`: no unsafe answer; a small omission or imprecise citation that is straightforward to correct.
- `FAIL`: current/historical/proposed material confused, R-17 guessed, the second release gate dropped, the archive treated as authority, or unsupported release/overwrite advised.
- `INCONCLUSIVE_ACCESS`: the declared input files were not actually available/readable.








Report each answer's source and note the limits of inspecting actual tool access. Keep the test result separate from any actual project's LIVE.








## 5. A second, independent operational check (optional)








In a real project **after** a local owner adopts and authorizes the method, ask an ordinary question that depends on the latest LIVE without explicitly saying 'recover'. Check whether the agent actually opens the appropriate source. Also try a simple copy-editing task that should not bulk-load the library, and a missing-source case where it should say `UNVERIFIED`. Do not call a successful prompted recovery proof of automatic retrieval compliance.








## Interpretation








Existing [Recovery Pilot](RECOVERY_PILOT.md) summarizes earlier, correlated synthetic runs. This checklist measures **semantic recovery and application of supplied rules to proposed changes**. It is not reconstruction of hidden chats, a controlled benchmark or proof of automatic source retrieval, source correctness or general model reliability.