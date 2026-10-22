# Limitations




Allocortex is a design method and starter structure, not a validated safety system.




This repository does **not** establish:
- statistical reliability of cold recovery;
- superiority over other memory, knowledge, governance, or workflow systems;
- universal cross-domain generality;
- correctness of underlying sources;
- enterprise IAM, retention, legal hold, DLP, residency, or regulatory compliance;
- autonomous enforcement of permissions or authority;
- improved model accuracy or safety;
- independence from model/tool/file-handling limitations.




## Recovery evidence is correlated




The included recovery exercises are small engineering diagnostics. Multiple runs against the same frozen package are not independent evidence of truth merely because different contours or platforms agree. Shared source material, shared task design, shared operator choices, transferred conventions, and repeated coding passes can create correlated results.




The narrow supported claim is that the supplied synthetic package was semantically recoverable by several clean contours in the tested setup.




## Visible staleness is not automatic freshness




Fields such as `VALID_AS_OF`, `LAST_VERIFIED`, and `REVERIFY_TRIGGER` can make stale state visible. They do not keep state current, guarantee re-verification, or prevent an abandoned project from becoming stale.




Any automatic "stale after N days" threshold is project/domain-specific because volatility differs by source and task.




## Portability observations are not validation




Reuse of the same control pattern across different private projects can support a design hypothesis about portability. It does not establish independent replication or validated cross-domain generality, especially when projects share an owner, operating method, or transferred templates.




A project still needs human governance, source verification, and domain-appropriate controls.
## Source availability is not verified retrieval


Attaching a Project Source, adding a link, or writing a platform instruction does not prove that a model opened an up-to-date file before answering. The outcome of an explicitly prompted recovery test does not establish routine unprompted source-use compliance. When current verification is material, check actual accessible sources or mark the relevant claim `UNVERIFIED` and hold dependent action. Project Instructions and file-handling capabilities differ by platform and are not universal enforcement mechanisms.


## Adoption exercises do not establish deployment reliability


Two small synthetic clean-adoption reports (one new project and one existing project) show that a reader could *propose* correct control functions and avoid duplicate governance using the public package. They did not create or maintain real target-project files, audit ongoing agent reads, or measure performance across users. A reproducible semantic diagnostic is available in `TRY_COLD_RECOVERY.md`.