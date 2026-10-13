---
name: carems-repository-integrity
description: Preserve repository integrity for CAREMS changes. Use whenever work will change CAREMS code, tests, configuration, documentation, branches, commits, pushes, or pull requests. Follow test-driven development; create a dedicated feature branch before implementation; keep changes intentionally scoped; write conventional, human-authored commit messages with no AI attribution; push the branch and open a PR for the user to merge manually.
---

# CAREMS Repository Integrity

Treat the repository history as a record owned by its developers. Make every change traceable, reviewable, and ready for the user to merge themselves.

## Required workflow

1. Inspect the working tree and current branch before modifying anything. Preserve unrelated or untracked user work.
2. For a new feature or fix, create a new, purpose-named branch before writing implementation code. Use a Conventional Commits-compatible prefix in the branch name when practical, such as `feat/`, `fix/`, `docs/`, or `test/`.
3. Practice TDD: write or update the most relevant failing unit, integration, or end-to-end test before implementation. Implement only enough to make that test pass, then refactor safely. If a test-first approach is not applicable (for example, documentation-only or launch-settings-only work), state why and run the narrowest meaningful verification instead.
4. Run relevant checks before committing. Report commands run and results accurately.
5. Review the complete diff and stage only intentional files and hunks. Never use broad staging commands such as `git add .` or `git add -A` when unrelated changes may exist. Do not stage generated files, credentials, editor settings, temporary files, or another person's work.
6. Write the commit message yourself from the reviewed diff. Use a concise Conventional Commit message, for example `feat(auth): add password reset request` or `fix(web): use localhost launch URLs`. Do not rely on AI-generated commit summaries, copy opaque text, or add `Co-authored-by` lines for an AI, agent, bot, or assistant.
7. Inspect the staged diff and commit metadata immediately before committing. Ensure author, committer, branch, and message are correct. Do not amend, force-push, rebase published work, or rewrite history unless the user explicitly requests it.
8. Push the branch, then open a pull request against the requested base branch (normally `main`). Include a clear human-written summary and exact testing status. The user merges manually; never merge the PR yourself unless explicitly instructed.

## Commit and PR standards

- Keep each commit focused on one logical change.
- Use Conventional Commit types such as `feat`, `fix`, `docs`, `test`, `refactor`, `build`, `ci`, or `chore`.
- Include a scope when it improves clarity: `fix(api): ...`.
- Make the subject imperative, specific, and no longer than necessary.
- PR descriptions should explain what changed, why, and which checks were run or intentionally not run.

## Safeguards

- Never make a commit merely to preserve context. Persist only work the user asked to keep.
- Never add AI, model, tool, or agent authorship or co-authorship to Git history.
- Never merge, delete a branch, discard local changes, or modify repository configuration without explicit user authorization.
- If existing local changes block safe branch work, stop and explain the conflict rather than absorbing or overwriting them.
- After a PR is created, provide its URL and leave the merge decision to the user.

## Completion report

When the workflow is complete, report the branch name, commit hash and message, checks run, and PR URL. Explicitly note anything not run or not persisted.
