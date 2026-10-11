# Independent engineering review guide

This guide is for recruiters, engineering managers, security reviewers and open-source contributors evaluating the public projects.

## Suggested 15-minute evaluation

1. **Start with the design constraint:** [The Murray Method](https://glenn-murray-portfolio.vercel.app/engineering-approach) separates model suggestions from permissions, verified state and irreversible effects.
2. **Inspect AI Authority Kernel:** [source](https://github.com/murrayglenn75-beep/ai-authority-kernel). Read the threat boundaries, inspect the gateway/resource/broker/audit separation, and follow the documented Git Bash setup and deterministic test commands. Local tests are not proof of production security.
3. **Inspect Ethical Hacker:** [source](https://github.com/murrayglenn75-beep/ethical-hacker). Follow the quick start, run `npm test`, then run the local dashboard or project scan in an authorized test environment. Evaluate false-positive handling, SARIF and confidence-based build gates.
4. **Inspect Fluxo:** [source](https://github.com/murrayglenn75-beep/fluxo). Review integer money handling, idempotency boundaries, RLS work and the difference between a sandbox interaction and a real provider-backed financial effect.
5. **Inspect Signet:** [source](https://github.com/murrayglenn75-beep/signet). Review the event kernel, organization-scope authorization, deterministic signal calculation and read-only AI narration.
6. **Inspect Brain AI:** [public research showcase](https://github.com/murrayglenn75-beep/Brain-AI). Public materials can verify disclosed evidence consistency; they do not reproduce private research simulations.

## Claim-to-evidence checklist

| Question | Where to check | What **not** to infer |
| --- | --- | --- |
| Is it implemented? | Source tree, exact default-branch commit, architecture documentation | A README feature list alone is not implementation proof |
| Does it run? | Local quick start, CI run at the inspected commit, test command and output | A historical test count does not imply the current branch passes |
| Is it secure? | Threat model, attack tests, authority boundaries and deployment assumptions | Simulations are not a security certification or independent penetration test |
| Does it work in production? | Live deployment, authenticated flows, monitoring, operator evidence | A Vercel demo alone does not prove production hardening |
| Can the research be reproduced? | Public scripts, fixtures, manifests and documented missing artifacts | Hash verification does not rerun private experiments |

## Project status vocabulary

- **Demo / sandbox:** a working product surface without claims of regulated or externally audited deployment.
- **Prototype:** implemented proof of selected concepts; important environment and scale assumptions may remain unverified.
- **Release candidate:** candidate for further validation, not a certification.
- **Public evidence showcase:** selected disclosures; not necessarily a complete runnable system.

## Feedback welcome

Specific reproducibility failures, security-model questions, documentation corrections and constrained issues are useful. When reporting security-sensitive findings, avoid posting exploitable secrets or private account data in public issues.

**Last reviewed:** 2026-10-11. Always verify the repository's current commit and workflow run rather than treating this document as a live status dashboard.
