# Flagship Engineering Proof Plan — 18 October 2026

This page is a **verification backlog**, not a record of completed production tests. It prioritizes evidence that a hiring engineer can independently reproduce.

## 1. AI Authority Kernel (AAK) — secure execution
**Public source:** https://github.com/murrayglenn75-beep/ai-authority-kernel

**Question to prove:** Can a compromised or mistaken agent be prevented from performing an action outside an exact, independently authorized manifest?

**Reproducible demonstration target**
1. Pin a release commit and supported Windows/Python dependencies.
2. Show a legitimate action approved once and recorded with an audit receipt.
3. Mutate the resource, method, parameters, destination, principal and manifest; verify every unauthorized mutation is rejected.
4. Replay the same grant; verify zero duplicate provider effects.
5. Inject a broker timeout and ambiguous provider response; demonstrate quarantine and safe reconciliation rather than blind retry.
6. Publish commands, expected outputs, test artifacts, threat model, limitations and commit SHA.

**Graduation gate:** Another engineer can run the suite, independently inspect broker/provider side effects, and reproduce both authorized and denied paths. Local fixture tests are not external production certification.

## 2. APEX Local AI Engine — autonomous software repair
**Source visibility:** No APEX repository was found in the linked public GitHub repository inventory on 18 October 2026. Treat this as a private/unpublished candidate until a source or distributable review artifact is available.

**Question to prove:** On Windows with integrated graphics and <=16 GB RAM, can a local model repair an unseen repository end to end without unauthorized effects?

**Benchmark protocol target**
1. Fix a set of unfamiliar, pre-registered GitHub tasks with answer leakage prevented.
2. Record inspect -> plan -> patch -> test -> independent verify -> recover for each run.
3. Track task completion, false success claims, approval violations, time-to-fix, tokens, peak RAM and CPU utilization.
4. Compare against a transparent baseline with identical tools, budgets, tasks and hardware.
5. Preserve failed trials and report success rates with denominators; do not promote synthetic-test results to live-model claims.

**Graduation gate:** Repeated independently reproducible task successes, zero observed unauthorized execution within the documented test campaign, and usable Windows installation/recovery evidence.

## 3. Fluxo — mobile-first fintech sandbox
**Public source:** https://github.com/murrayglenn75-beep/fluxo
**Demo listed by project:** https://fluxo-fintech-xi.vercel.app/

**Question to prove:** Does every demonstrated banking-style workflow behave correctly on actual mobile viewports, while preserving financial invariants?

**Demo/release checklist**
1. Confirm deployed build SHA matches the intended tested commit.
2. Audit every demo navigation route and full feature access, including Activity scrolling, dialogs and safe areas.
3. Confirm approved forest-green login, emerald action button, contrast, settings themes and responsive behavior.
4. Run deterministic money arithmetic, insufficient-balance, duplicate-payment, receipt and data-reset tests.
5. Test accessibility, keyboard focus, browser storage reset and mobile device behavior.
6. Record video and reproducible build/typecheck/unit-test results.

**Graduation gate:** A recruiter can open the public sandbox without special credentials, explore all promised demo screens and observe testable valid/invalid state transitions. The sandbox does not settle real Pix transactions or issue bank cards.

## Portfolio publication standard

For each flagship, publish: problem and audience; 60–90 second demo; architecture and threat boundaries; setup commands and pinned versions; CI links and test artifacts; one success and one failure example; quantified results with denominators; candid limitations; next release gate.

**Honesty rule:** A passing unit suite, README statement, successful Vercel deployment or attractive screenshot is not independent proof of end-to-end production behavior.

**Prioritized sequence:** (1) Fluxo deployed mobile demo checks, (2) AAK adversarial reproducibility campaign, (3) APEX source visibility and live autonomous benchmark, (4) case-study landing page and comparative scorecard.
