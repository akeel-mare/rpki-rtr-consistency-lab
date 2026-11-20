# RPKI RTR Authorization Consistency Laboratory

Research artifact by Akeel Mare and Hamed Al-Raweshidy for **Testing RPKI Cache Failover: Authorization Consistency, Service Delivery, and Mitigation Costs**.

## Download the complete artifact

Download **`rpki-rtr-study.zip`** and **`rpki-rtr-study.zip.sha256`** from the repository's version **v1.0.0**, as linked in the release notes. The study ZIP contains the executable source, configuration directories, frozen signed public RPKI objects, raw RTR captures, routing/HTTP events, analysis, and editable manuscript. When using GitHub's automatically generated source archive, extract the nested `rpki-rtr-study.zip` before running the reproduction command.

The measured campaign contains **116 audited runs**: 38 short conditions with three independently initialized repetitions (114 runs), plus two descriptive 650-second automatic-refresh observations. Earlier diagnostic batches are excluded. The artifact does not claim that the manuscript has been submitted or accepted, and no DOI has been assigned.

## Reproduce saved results

1. Extract the study ZIP and enter its `rpki-rtr-study` folder.
2. Install Python packages with `python -m pip install -r requirements.txt`, and install a LaTeX distribution providing IEEEtran, pdflatex, and bibtex.
3. Run `powershell -File reproduce.ps1`.

This verifies the saved file inventory, audits all 116 runs, regenerates the quantitative figures and tables, and compiles the article. It does not rerun containers. This command was successfully checked against the saved release before publication. See the included `extended-study/STUDY_PLAN.md` and `DATA_DICTIONARY.md` for measurement definitions and limitations.

For fresh experiments, follow the included README and use Docker Desktop with Linux containers. Fresh runs produce new timestamped evidence rather than overwriting the saved campaign.

## What the study measures

Signed replacement of an authorization from origin A to B is followed through real validators, RTR traffic, route admission, forwarding, and distinguishable service responses. FRR and BIRD deployments, Routinator and FORT, route preferences, failure conditions, and two explicit controls are evaluated.

BIRD assigned handoff is controller-mediated, while FRR uses native cache priorities. FORT refresh includes endpoint restart and cache reselection. The expected-view gate relies on operator-supplied intended authorization, rather than globally comparable RTR serial numbers. Eight-second holds do not establish indefinite safety or behavior through expiration. Three-run intervals are conditional summaries, not Internet-wide failure probabilities. The contribution is controlled measurement and security/availability tradeoffs, rather than discovery of new ROV semantics.

## Licensing

At the author's request, **no general license is granted for the newly authored laboratory code at this time**. Public availability does not itself grant permission to reuse, modify, or redistribute that code. Third-party components retain their respective licenses. FRR's patch and original license are included under `vendor/` in the artifact.

## Cite

Use the versioned GitHub release URL and the author/title metadata in `CITATION.cff`. No DOI is claimed.
