# Recovery Pilot




Date: 2026-09-30.




This repository was developed with a small engineering diagnostic: could a clean AI contour recover the same decision-relevant project state from a self-contained External System package without access to the original chats?




## Round 01




A synthetic project package (Project Lantern) encoded mission, authority, current state, an unresolved UNKNOWN, an external system-of-record pointer, accepted decisions and supersession, fail-closed behavior, and write-back examples.




Six completed clean-contour reports recovered all decision-relevant invariants in the checklist. No semantic recovery failure was observed.




Round 01 also exposed recurring usability friction, including:
- an insufficiently explicit path to the external authority item;
- duplicated authority/source-priority wording;
- Router classes that looked like missing files;
- one hidden referent in a NO-OP example;
- minor supersession and terminology ambiguity.




The package was revised rather than treating agreement as validation.




## Round 02




Five clean contours ran a corrected single-file confirmation package. All five marked every semantic invariant PASS. Four reported `RECOVERED`; one reported `RECOVERED_WITH_FRICTION` due to a remaining release-gate wording issue, which was corrected.




## What this supports




The tested synthetic package was semantically recoverable across several clean contours when the input transport was readable. In particular, contours recovered:
- mission and authority;
- current state and UNKNOWN;
- external system-of-record ownership and exact authority pointer;
- next permitted action and DO-NOT-DO boundaries;
- partial decision supersession;
- fail-closed behavior;
- deliberate NO-OP;
- conflict preservation;
- provenance upgrade;
- the separation of routing/relevance from authority.




## What this does not support




This was not a benchmark, statistical reliability study, safety evaluation, or model/platform ranking. The sample was small, the project was synthetic, and the expected invariants were known in advance.




Do not interpret the pilot as evidence of universal model independence, generality across all domains, or superiority over other memory/project-state systems.




## Clean-adoption check (two synthetic cases, 2026-10-13)




Separate from the semantic recovery rounds above, two clean-contour adoption tasks used the public draft method. In a **greenfield synthetic project**, the responder proposed a minimal set of five logical controls and kept a collaborator's unverified policy claim out of current truth. In an **existing synthetic repository**, the responder reused existing README, status, decisions, issues and Git instead of building a parallel project-management tree. Both written proposals were assessed internally against a prewritten rubric; the prompts, detailed grading, and underlying receipts are **not published in this package**. These observations are author-reported rather than independently auditable here.




These checks tested **proposed adoption decisions**, not operational deployment, continued file maintenance, or source-read enforcement. One real usability ambiguity remained: the early README template-copy instruction could look mandatory despite the project's reuse/anti-duplication rule. That onboarding text was revised in this public draft following internal review.




Readers can repeat a bounded, transparent synthetic diagnostic using [Try cold recovery](TRY_COLD_RECOVERY.md); passing does not establish general reliability.