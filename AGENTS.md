# Codex Project Instructions

These instructions apply to the GitHub & Cloud Development Practice pilot repository.
This is an SWF v1.4 **pilot**, not an approval or release of SWF v1.4.

## Working Standard
- Follow SWF v1.3 until the user explicitly approves the release of v1.4.
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
- A successful pilot does not by itself authorize SWF v1.4 adoption.

## Completion Report
Summarize:
1. Changes implemented
2. Checks and tests actually performed
3. Results: PASS, FAIL, or BLOCKED
4. Remaining risks and blockers
5. Git branch and commit reference
6. Next recommended action
