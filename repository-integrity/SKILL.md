---
name: repository-integrity
description: Preserve repository integrity for software changes in any coding project. Use whenever work will change code, tests, configuration, documentation, branches, commits, pushes, pull requests, application testing, or browser-based workflow validation. Follow test-driven development where applicable; create a dedicated feature branch before implementation; keep changes intentionally scoped; use conventional, human-authored commit messages with no AI attribution; clean up test processes; and open a pull request for the user to merge manually.
---

# Repository Integrity

Treat Git history as a developer-owned record. Make every change traceable, reviewable, durably saved, and ready for the user to merge themselves.

## Required workflow

1. Inspect the working tree, current branch, and repository guidance before modifying anything. Preserve unrelated and untracked user work.
2. For a new feature or fix, create a purpose-named branch before implementation. Use a Conventional Commits-compatible prefix where practical, such as `feat/`, `fix/`, `docs/`, or `test/`.
3. Use TDD when implementation behavior can be tested: write or update the most relevant failing unit, integration, or end-to-end test first; implement only enough to pass it; then refactor safely. For work where test-first is not applicable, such as documentation, visual assets, or launch settings, state why and run the narrowest meaningful verification.
4. Run relevant automated checks before committing and report commands and results accurately.
5. When an implementation is exposed through a browser, validate the actual user-facing functionality and workflows after automated tests. Launch the application when needed and use the Codex or ChatGPT browser to exercise representative paths, including the intended result and important failure or permission states. Report what was tested and what could not be tested.
6. After launching an application, dev server, test host, or other process for validation, stop every process you started before completing the task. Confirm that the ports it used are free. Do not terminate processes that were already running or belong to the user.
7. Review the complete diff. Stage only intentional files and hunks; never use broad staging commands when unrelated changes may exist. Do not stage generated files, credentials, editor settings, temporary files, or another persons work.
8. Write the commit message from the reviewed diff. Use a concise Conventional Commit message, such as `feat(auth): add password reset request` or `fix(web): use localhost launch URLs`. Do not rely on opaque generated summaries or add `Co-authored-by` lines for an AI, agent, bot, model, or assistant.
9. Inspect the staged diff and commit metadata immediately before committing. Confirm the author, committer, branch, and message are correct. Do not amend, force-push, rebase published work, or rewrite history unless the user explicitly requests it.
10. Push the branch and open a pull request against the requested base branch, normally `main`. Include a clear summary and exact testing status. The user merges manually; never merge a PR yourself unless explicitly instructed.

## Commit and PR standards

- Keep each commit focused on one logical change.
- Use conventional types such as `feat`, `fix`, `docs`, `test`, `refactor`, `build`, `ci`, or `chore`.
- Include a scope when it improves clarity, for example `fix(api): ...`.
- Make the subject imperative, specific, and no longer than necessary.
- In PRs, explain what changed, why, which automated and browser checks ran, and any intentionally untested paths.

## Safeguards

- Persist user-requested work in the repository or the requested durable destination; do not treat temporary storage, caches, or conversation context as the saved result.
- Never make a commit merely to preserve context.
- Never add AI, model, tool, or agent authorship or co-authorship to Git history.
- Never merge, delete a branch, discard local changes, or modify repository configuration without explicit user authorization.
- If existing local changes block safe branch work, stop and explain the conflict rather than absorbing or overwriting them.
- After creating a PR, provide its URL and leave the merge decision to the user.

## Completion report

Report the branch name, commit hash and message, automated and browser checks run, test processes stopped, PR URL, and anything not run or not persisted.