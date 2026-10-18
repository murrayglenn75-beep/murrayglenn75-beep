# Engineering evidence scorecard

**Baseline review:** 2026-10-18. This is a work queue and evidence index, **not** a live CI dashboard or security certification. GitHub Actions and default branches may change after this date.

## How to read this

- **Implemented** means source and documentation are available for inspection; it does not mean deployed or independently audited.
- **Reported** means a repository claims a result which this scorecard has not rerun.
- **Verified externally** requires a dated, reproducible run tied to a commit SHA and an independent environment/reviewer.
- **Open** means a necessary validation or repair remains; an absent result is not counted as a pass.

| Project | Public evidence | What remains open | Graduation gate |
| --- | --- | --- | --- |
| [AI Authority Kernel](https://github.com/murrayglenn75-beep/ai-authority-kernel) | Source, threat boundaries, [review quickstart](https://github.com/murrayglenn75-beep/ai-authority-kernel/blob/main/docs/REVIEWER_QUICKSTART.md), CI workflows and repository-reported adversarial test results | Independent external security review, deployable distributed topology and real-provider failover evidence | Fresh CI at pinned SHA; reproduce unauthorized-action rejection and failure recovery in a clean environment; report methodology and limits |
| [Fluxo](https://github.com/murrayglenn75-beep/fluxo) | Sandbox source, [live UI](https://fluxo-fintech-xi.vercel.app/), deterministic ledger test instructions and mobile build documentation | Real-device/mobile UX regression matrix, production provider integrations (deliberately absent), and independently verified end-to-end demo coverage | Pin build commit; execute and publish reproducible demo navigation, state persistence, accessibility, error and responsive-screen checks |
| [Ethical Hacker](https://github.com/murrayglenn75-beep/ethical-hacker) | Security scanner source and CI/test instructions | Benchmark corpus, detection precision/recall and false-positive comparison with documented baselines | Fixed labeled fixtures, repeatable scan command, published TP/FP/FN counts, runtime and known blind spots |
| [Signet](https://github.com/murrayglenn75-beep/signet) | Public source and operational evidence concepts | Reliable demo access, failure-path replay evidence and production boundary review | Clean replay from recorded events with expected deterministic outputs and published failure cases |
| [Brain AI](https://github.com/murrayglenn75-beep/Brain-AI) | Public evidence showcase and verifier | Earlier [reported manifest mismatch](https://github.com/murrayglenn75-beep/Brain-AI/actions/runs/38110442700) requires fresh confirmation; private experiments may not be reproduced from public materials | Regenerate manifest using intended method and confirm full verification passes on current SHA; label undisclosed work |
| [Portfolio](https://github.com/murrayglenn75-beep/glenn-murray-portfolio) | Recruiter-facing website and source | Earlier [reported dependency audit failures](https://github.com/murrayglenn75-beep/glenn-murray-portfolio/actions/runs/38110446430) require current rerun and dependency remediation | Reproduce audit, upgrade safely, run tests/build and publish fresh successful checks |

## Flagship benchmark: autonomous agent with enforced authority

**Target:** Show a local APEX-style engineering agent inspecting an unfamiliar repository, proposing a patch, receiving explicit scope-limited approval through AAK, executing only the authorized test/build commands, then independently verifying and reporting the result.

Do not mark this as completed until there is a runnable public integration.

1. Pin agent version, model, runtime/hardware, repository commit, tasks and time budget.
2. Use unfamiliar held-out tasks with expected behavior rather than preloaded reference answers.
3. Measure task success, regressions, elapsed time, CPU/RAM usage, unnecessary tool calls and abstentions.
4. Test prompt injection, attempted command escalation, stale approvals, replay, output manipulation, missing audit storage and interrupted execution.
5. Publish a machine-readable run manifest, logs with secrets removed, hashes, sample sizes and confidence intervals.
6. Repeat on Windows with CPU-first hardware and no assumption of discrete-GPU availability.

**Minimum credible outcome:** A third party can reproduce at least one end-to-end successful authorized fix and one rejected unauthorized request on a pinned commit. Broader comparisons require larger held-out suites and independent replication.

## Review order

1. Recheck the two historical CI failures, and update this scorecard only from fresh run links.
2. Publish a clean AAK reproduce-and-attack demonstration.
3. Complete Fluxo mobile workflow/UX regression evidence.
4. Run the benchmark above; report failures and abstentions, not just successes.
5. Collect independent review or real-user outcomes with permission.

Further background: [Independent engineering review guide](REVIEW_GUIDE.md) · [Historical CI and repository metadata findings](CI_AND_METADATA_REVIEW.md).

**Integrity rule:** Never equate a README claim, simulated attack count, or green CI badge with a third-party production assurance or a proven comparison against another engineer.
