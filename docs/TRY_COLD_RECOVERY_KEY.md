# Try cold recovery — EVALUATOR ANSWER KEY (public teaching artifact)


This file is public so humans can check the exercise. Do not supply it to the runner contour or give the runner open access to its location during a purported clean diagnostic. A contour with this key in its input has INVALID_KEY_EXPOSED, not PASS. Public visibility means this is not a hidden benchmark.


## Expected answers (evaluator only)




| # | Must recover |
| --- | --- |
| 1 | Reconcile 24 reference documents and prepare a reviewed v3.0 index; Project Owner decides release. The Coordinator cannot independently approve release. |
| 2 | Source reconciliation / release-readiness review; 24 in scope, 21 reconciled, 2 restricted represented by external pointers, R-17 unresolved; v3.0 index remains draft and unapproved. |
| 3 | R-17 must be verified **and** the final 24-to-24 source/index consistency check must pass. Neither is optional. |
| 4 | Current authoritative R-17 version is `UNVERIFIED`; fictional external ASR record `ASR:R-17` owns version/status, and ASR is not included in the package. |
| 5 | Verify R-17 against ASR first, reconcile the verified result, then complete the final source/index check; no release until both gates pass. |
| 6 | D-001's copy-all rule was partially superseded by D-002: restricted documents remain in ASR, with pointers/verified consequences rather than duplicated content. |
| 7 | `CONFLICT / DO NOT OVERWRITE`; remain `UNVERIFIED` until ASR is consulted. The contributor/old note are not authoritative substitutes. |
| 8 | `ALREADY_REPRESENTED → NO-OP`; the current R-08 entry already has stronger verification. |