---
name: repository-integrity
description: Preserve repository integrity for software changes in any coding project. Use whenever work will change code, tests, configuration, documentation, branches, commits, pushes, or pull requests. Follow test-driven development where applicable; create a dedicated feature branch before implementation; keep changes intentionally scoped; use conventional, human-authored commit messages with no AI attribution; push the branch and open a pull request for the user to merge manually.
---

# Repository Integrity

Treat Git history as a developer-owned record. Make every change traceable, reviewable, and ready for the user to merge themselves.

## Required workflow

1. Inspect the working tree, current branch, and repository guidance before modifying anything. Preserve unrelated and untracked user work.
2. For a new feature or fix, create a purpose-named branch before implementation. Use a Conventional Commits-compatible prefix where practical, such as `feat/`, `fix/`, `docs/`, or `test/`.
3. Use TDD when implementation behavior can be tested: write or update the most relevant failing unit, integration, or end-to-end test first; implement only enough to pass it; then refactor safely. For work where test-first is not applicable, such as documentation, visual assets, or launch settings, state why and run the narrowest meaningful verification.
4. Run relevant checks before committing and report commands and results accurately.
5. Review the complete diff. Stage only intentional files and hunks; never use broad staging commands when unrelated changes may exist. Do not stage generated files, credentials, editor settings, temporary files, or another persons work.
6. Write the commit message from the reviewed diff. Use a concise Conventional Commit message, such as `feat(auth): add password reset request` or `fix(web): use localhost launch URLs`. Do not rely on opaque generated summaries or add `Co-authored-by` lines for an AI, agent, bot, model, or assistant.
7. Inspect the staged diff and commit metadata immediately before committing. Confirm the author, committer, branch, and message are correct. Do not amend, force-push, rebase published work, or rewrite history unless the user explicitly requests it.
8. Push the branch and open a pull request against the requested base branch, normally `main`. Include a clear summary and exact testing status. The user merges manually; never merge a PR yourself unless explicitly instructed.

## Commit and PR standards

- Keep each commit focused on one logical change.
- Use conventional types such as `feat`, `fix`, `docs`, `test`, `refactor`, `build`, `ci`, or `chore`.
- Include a scope when it improves clarity, for example `fix(api): ...`.
- Make the subject imperative, specific, and no longer than necessary.
- In PRs, explain what changed, why, and which checks ran or did not run.

## Safeguards

- Persist user-requested work in the repository or the requested durable destination; do not treat temporary storage, caches, or conversation context as the saved result.
- Never make a commit merely to preserve context.
- Never add AI, model, tool, or agent authorship or co-authorship to Git history.
- Never merge, delete a branch, discard local changes, or modify repository configuration without explicit user authorization.
- If existing local changes block safe branch work, stop and explain the conflict rather than absorbing or overwriting them.
- After creating a PR, provide its URL and leave the merge decision to the user.

## Completion report

Report the branch name, commit hash and message, checks run, PR URL, and anything not run or not persisted.