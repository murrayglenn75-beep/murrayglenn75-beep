# CI evidence and repository metadata review

Snapshot: **2026-10-11**. GitHub Actions states are point-in-time observations and may change. Inspect the linked runs and the relevant default-branch commit before drawing conclusions.

| Project | Observed recent run | Important qualifier |
| --- | --- | --- |
| [AI Authority Kernel](https://github.com/murrayglenn75-beep/ai-authority-kernel) | [Workflow run — in progress at review](https://github.com/murrayglenn75-beep/ai-authority-kernel/actions/runs/38112647741) | PR check, not a final success |
| [Ethical Hacker](https://github.com/murrayglenn75-beep/ethical-hacker) | [Workflow run — success](https://github.com/murrayglenn75-beep/ethical-hacker/actions/runs/38110435457) | PR check; does not replace a default-branch verification |
| [Fluxo](https://github.com/murrayglenn75-beep/fluxo) | [Workflow run — success](https://github.com/murrayglenn75-beep/fluxo/actions/runs/38112096029) | Push check on the reviewed README update |
| [Signet](https://github.com/murrayglenn75-beep/signet) | [Workflow run — success](https://github.com/murrayglenn75-beep/signet/actions/runs/38112092233) | Push check on the reviewed README update |
| [Brain AI](https://github.com/murrayglenn75-beep/Brain-AI) | [Passing PR run](https://github.com/murrayglenn75-beep/Brain-AI/actions/runs/38110442782) and [failed PR run](https://github.com/murrayglenn75-beep/Brain-AI/actions/runs/38110442700) | Mixed checks must be investigated, not represented as fully green |
| [Glenn Murray Portfolio](https://github.com/murrayglenn75-beep/glenn-murray-portfolio) | [Failed PR run](https://github.com/murrayglenn75-beep/glenn-murray-portfolio/actions/runs/38110446430) | Investigate logs and fix root cause |

These observed statuses are not equivalent to executing tests in an independent local environment, and do not represent an audit or certification.

## Suggested GitHub topics

These are **proposals**, not yet applied as GitHub repository settings.

| Repository | Suggested topics |
| --- | --- |
| AI Authority Kernel | `ai-agents`, `authorization`, `agent-security`, `python`, `audit-logging` |
| Ethical Hacker | `appsec`, `security-scanner`, `static-analysis`, `nodejs`, `sarif` |
| Fluxo | `fintech`, `nextjs`, `typescript`, `supabase`, `pix` |
| Signet | `event-sourcing`, `nextjs`, `supabase`, `typescript`, `audit-trail` |
| Brain AI | `ai-research`, `evidence-provenance`, `ai-safety`, `bayesian-inference` |
| Glenn Murray Portfolio | `developer-portfolio`, `nextjs`, `typescript`, `ai-engineering` |

## Licensing decision

No license was recognized in repository metadata for the six reviewed repositories at the time of inspection. Some repositories contain NOTICE files, which do not necessarily establish a standard reusable code license.

**Do not add a default license automatically.** Decide separately whether each implementation, demo, and partial public research disclosure should be open-source, source-available, or all-rights-reserved. The Brain AI disclosure explicitly keeps a research core private; public source visibility alone does not grant redistribution rights.

## Next evidence upgrades

1. Resolve failing and running checks, with a run link and commit SHA.
2. Publish test commands, dependencies and observed results for the exact tagged release.
3. Add small, reproducible walkthroughs or screenshots with accessible captions.
4. Add license files and repository topics only after confirming the intended distribution policy.
5. Track external bugs and accepted contributions separately from self-reported benchmarks.

## Diagnosed failing steps (2026-10-11)

### Brain AI evidence check

The failed `verify-public-evidence` job reported `PASS: R-013 published arithmetic and disclosure metadata`, followed by `FAIL: Public manifest mismatch`. The reported missing manifest entry is `.github/workflows/security-baseline.yml`; there were no extra or changed hashes in that particular log result. This suggests regenerating the manifest using the repository's intended generator and verifying it in CI, **not** disabling hash checks or weakening the validation. [Review failed run](https://github.com/murrayglenn75-beep/Brain-AI/actions/runs/38110442700).

### Glenn Murray Portfolio npm audit

The failed `security-baseline` job's production dependency audit reported **five advisories (four high, one critical)** in its resolved tree, mentioning Next.js-related dependencies, PostCSS, sharp and source-map-js. The log suggested `next@15.5.27` for some forced fixes; upgrading outside the declared dependency range must be evaluated and tested before committing. **Do not suppress the failing audit merely to turn CI green.** [Review failed run](https://github.com/murrayglenn75-beep/glenn-murray-portfolio/actions/runs/38110446430).

Neither issue is marked resolved by this report; fixes require source changes and fresh successful checks.
