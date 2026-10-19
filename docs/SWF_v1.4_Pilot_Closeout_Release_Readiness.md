# SWF v1.4 — Project 18 Pilot Closeout and Release Readiness

**Status:** DRAFT FOR FINAL REVIEW — NOT RELEASED  
**Owner:** HUB 18 / WORK 18.02 — GitHub & Cloud Development Practice  
**Current authoritative standard:** SWF v1.3  
**Scope:** Project 18 pilot only; no production-wide adoption from this document

## 1. Approved manual fallback and evidence discipline

On 2026-10-19, the user approved continuing the SWF v1.4 completion work without treating the Codex Cloud automatic-instruction-loading failure as a stop for the entire project, provided instructions can be read manually.

- **Codex Cloud automatic loading of `AGENTS.md`: FAIL / OPEN.** Do not label this PASS or claim it works.
- **Codex Cloud explicit `AGENTS.md` reading: PASS** in the pilot repository.
- **Codex Cloud repository baseline: PASS.** `/workspace/github-cloud-practice` resolves to `abe739f28994e420ec759322e42bebc0d32b1757`; root `AGENTS.md` exists.
- The startup working directory for the failing sessions was `/workspace`, outside the repository directory. This might explain the loading failure; its exact cause is unconfirmed.
- Support investigation remains open under case **16736756**; do not require a support fix before continuing work that satisfies the manual gate.
- Manual reading is an **accepted workaround**, not evidence that automatic loading succeeded. If the manual gate fails, that individual Cloud task is **BLOCKED** until instructions are available.

### Mandatory Cloud new-task start gate (until automatic loading is independently verified)

Before editing any file or executing development tasks in the pilot repository:

1. Use the existing `github-cloud-practice-swf14-pilot` environment; do not create new environments or republish as part of the workaround.
2. Read `/workspace/github-cloud-practice/AGENTS.md` **explicitly** (e.g., `cat /workspace/github-cloud-practice/AGENTS.md`).
3. Verify repository location and HEAD with `git -C /workspace/github-cloud-practice rev-parse HEAD`, and check the worktree/branch as relevant. Do not assume a particular HEAD in future sessions; compare it to the authorized branch/baseline.
4. State the active SWF version, applicable Git/testing/safety rules, and any read/check failures **before implementation**.
5. Record instruction source as **manual**, not automatic; never invent successful tests.

A suggested kickoff prompt:

```text
Project 18 — Mandatory Cloud manual instruction gate.
Before development work, explicitly read /workspace/github-cloud-practice/AGENTS.md,
verify the repository branch and HEAD with git -C /workspace/github-cloud-practice,
and report the active SWF version, safety rules, and exact PASS/FAIL/BLOCKED
results. State that reading is MANUAL and do not claim automatic loading.
Stop if instruction reading, repository identity, or authorization fails.
No file changes, commits, pushes, merges, permissions edits, or deploys
are authorized by this kickoff prompt.
```

## 2. Phase A — persistent Codex instructions (pilot evidence)

| Acceptance area | Recorded result |
| --- | --- |
| A1 scope and instruction design | PASS / approved |
| A2 root `AGENTS.md` on GitHub `main` | PASS; PR #5 merged at `abe739f` |
| Local A-T01 automatic loading | PASS |
| Local A-T02 fresh-session persistence | PASS |
| Local A-T03 development compliance | **ASSISTED PASS only**; Codex edited `pilot-tests/A-T03.md`, Windows PowerShell created local commit `fa58ab7`, clean worktree verified |
| Local A-T04 hypothetical safety decisions | PASS (5/5 scenarios; not proof of technical enforcement) |
| Local A-T05 standardized completion report | PASS |
| Cloud automatic loading | **FAIL — open defect** |
| Cloud manual read and baseline verification | PASS |

**Git caveat:** Codex Desktop's autonomous writes to `.git` failed with `.git/index.lock` permission denial. Standard Windows PowerShell Git operations succeeded. Keep this limitation disclosed; do not remove sandbox protections, elevate privilege, or mark autonomous Codex Git actions PASS. For appropriate low-risk GitHub operations, the connected ChatGPT–GitHub workflow is another approved pilot route.

**Proposed Phase A disposition:** eligible for final pilot acceptance *with the manual Cloud kickoff gate and an explicit open-defect record*. This document does not itself grant final acceptance.

## 3. Phase B — central status register

**B1–B5: PASS / APPROVED / LOCKED.** Pilot is a manually maintained, private Google Sheets project register for Projects 02, 04, and 18. It mirrors authoritative HUB/WORK decisions rather than replacing them. No automatic synchronization is enabled. Any Google Drive connection failure is an access issue, not proof the existing pilot ceased to exist.

## 4. Smart Tool Routing — approved pilot optimization

- **ChatGPT + GitHub** for small, low-risk repository changes where appropriate; prefer isolated branch, verification, PR.
- **Codex** for substantial multi-file development, debugging, local/automated testing and builds.
- **Risk-based independent review**, staging validation and explicit production approval remain mandatory when relevant, regardless of tool.
- Do not route work in a way that removes necessary tests or weakens access controls.
- This documentation-only GitHub branch/PR is an isolated practical trial of the ChatGPT + GitHub route; evaluate separately, and do not merge without explicit user approval.

## 4A. Existing controls retained without exception

SWF v1.4 does **not** supersede or weaken existing SWF v1.3 controls while unreleased, or after release unless explicitly revised and approved:

- **Environment Readiness Gate:** verify required GitHub, Supabase, Vercel, Codex/PC, sandbox, credentials, access, and tooling prerequisites relevant to each task before implementation. Report missing capabilities as BLOCKED; do not bypass by assumption.
- **AI First, User Last:** routine automated testing is AI-/runner-managed after any authorized setup. Do not shift normal test execution to the user merely to conserve Codex usage.
- **Usage protection:** favor focused automated checks before expensive repeated full-suite/browser runs; still perform essential security, regression, and release acceptance tests.
- **Release safety:** preserve isolated staging where appropriate, risk-based independent security review, traceable Git checkpoints, explicit approvals for dangerous changes, and no unauthorized deployment.

## 5. Phases C and D are deferred

**Phase C — automated synchronization** and **Phase D — performance metrics** were explicitly deferred and require separate authorization. They are not implicit prerequisites for the A+B+E pilot release scope, and this document does not authorize their implementation.

## 6. Phase E — final review and release gate

Before calling SWF v1.4 `RELEASED`, complete all of the following:

- [x] Phase B B1–B5 accepted and locked
- [x] Phase A evidence recorded, including local tests and explicit Cloud manual read
- [x] Cloud automatic loading marked **FAIL**, not silently waived or mislabeled
- [x] Manual Cloud instruction-loading gate specified
- [x] Codex Desktop autonomous Git-permission limitation disclosed with controlled workaround
- [x] Smart Tool Routing approved for pilot evaluation, without loosening safety or testing
- [x] Retained SWF v1.3 environment readiness, AI-managed testing and security/release gates explicitly documented
- [ ] Review/accept Phase A with the documented exceptions and determine if extra targeted manual-gate validation is needed
- [ ] Review/accept the v1.4 final release scope and cross-project adoption/handoff wording
- [ ] Receive **explicit user approval** for the SWF v1.4 release
- [ ] After approval only: update the authoritative workflow/version references and any rollout documentation, with verification and traceable release record

**Until the final release approval:** SWF v1.3 remains authoritative. Do not claim Phase A fully accepted, publish a v1.4 release, synchronize registers automatically, modify other production projects, or merge into `main` based on this draft.

## 7. Immediate next decision

Review this proposed exception-based Phase A closeout and the Phase E checklist. An explicit final release decision remains separate from preparation. OpenAI Support case **16736756** may continue independently.
