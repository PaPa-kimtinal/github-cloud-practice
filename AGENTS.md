# Codex Project Instructions

These instructions apply to the GitHub & Cloud Development Practice repository.
SWF v1.4 (Phases A/B/E) was **APPROVED & RELEASED on 2026-10-19**. Phases C (automatic synchronization) and D (metrics) remain deferred and unapproved.

## Working Standard
- Follow released SWF v1.4 and preserve all inherited SWF v1.3 security, testing, environment readiness, and production-release gates.
- Respect project-specific workflow exceptions and explicit user decisions.
- Do not claim acceptance or release without supporting test evidence and approval.

## Development
- Inspect relevant existing files before modifying them.
- Make focused, minimal changes; avoid unrelated modifications.
- Preserve existing behavior unless the task explicitly requires otherwise.
- Keep the pilot isolated from operational and production repositories.

## Testing
- Run checks and tests appropriate to each change.
- Report PASS, FAIL, or BLOCKED honestly, with evidence.
- Fix failures caused by the change and rerun the relevant tests.
- Never claim an unexecuted test has passed.

## Git Workflow
- Prefer feature branches and pull requests for changes.
- Do not force-push or rewrite shared history.
- Record meaningful implementation checkpoints as commits.
- Do not merge into `main` without explicit user approval.
- Report changed files and the resulting commit reference.

## Safety & Release Gates
- Never expose or commit credentials, tokens, or other secrets.
- Do not perform destructive actions without explicit approval.
- Do not deploy to production without authorization.
- Use isolated staging and synthetic data when release testing is needed.
- Require an independent review for high-risk changes before production release
  (including authentication, permissions, RLS, payments, migrations, and security).
- SWF v1.4 release authorization covers only approved Phases A/B/E; it does not authorize Phase C/D, destructive operations, automatic cross-project changes, or production deployments.

## Mandatory Codex Cloud Manual Instruction Gate

- Cloud automatic AGENTS.md loading remains **FAIL / unresolved** (Support case 16736756); do not claim it passed.
- At the start of every new Codex Cloud development task, explicitly read `/workspace/github-cloud-practice/AGENTS.md` and verify repository path, branch, HEAD and relevant worktree state using `git -C /workspace/github-cloud-practice` before changes.
- Report instruction source as **MANUAL** and confirm active SWF v1.4 and safety/testing rules before implementing. If reading or verification fails, report BLOCKED and stop.
- Codex Desktop autonomous `.git` writes previously failed with permission errors; use approved non-destructive GitHub/PowerShell routes as needed without changing security permissions.

## Completion Report
Summarize:
1. Changes implemented
2. Checks and tests actually performed
3. Results: PASS, FAIL, or BLOCKED
4. Remaining risks and blockers
5. Git branch and commit reference
6. Next recommended action
