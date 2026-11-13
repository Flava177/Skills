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
5. **Browser verification is required** when an implementation is exposed through a browser. After automated tests, launch the application and use the visible browser of the AI agent in use (Codex, ChatGPT, Claude, or equivalent) to exercise the actual user-facing workflow. Do not declare the work complete from code inspection or automated tests alone. Verify the intended result and important failure or permission states, and report the visible paths tested and anything that could not be tested.
6. **Check every screen size** for any user-facing UI change. Test each touched page at every common width, not a sample: phones (360, 390, 430 px), small tablet (600), tablets (768, 820), laptops (1024, 1180, 1280, 1366, 1440, 1512 for a 14-inch MacBook, 1728 for 16-inch), desktop monitors (1920 for 21–24-inch, 2560 for 27-inch and 32-inch QHD), ultrawide monitors (2560×1080 and 3440×1440 for 29–34-inch, 3840×1600 for 38-inch), 4K displays and projectors (3840), and the largest screens (5120 for 49-inch super-ultrawide and 5K), so the app stays usable on any screen, when projected, or on an extended display. Wide screens must still fill neatly: no content stranded in a narrow column or stretched lines that are hard to read. Fill the page with realistic long data first, because an empty page hides overflow. Look for sideways scroll, text or cards running past the right edge or out of their card (header included), cut-off text, and cramped or overlapping controls; confirm each page actually loaded before trusting a clean result, and look at screenshots, not only automated checks. When finished, restore the browser to its full-size viewport; never leave it at a cut-down test width.
7. After launching an application, dev server, test host, or other process for validation, stop every process you started before completing the task. Confirm that the ports it used are free. Do not terminate processes that were already running or belong to the user.
8. Review the complete diff. Stage only intentional files and hunks; never use broad staging commands when unrelated changes may exist. Do not stage generated files, credentials, editor settings, temporary files, or another persons work.
9. Write the commit message from the reviewed diff. Use a concise Conventional Commit message, such as `feat(auth): add password reset request` or `fix(web): use localhost launch URLs`. Do not rely on opaque generated summaries or add `Co-authored-by` lines for an AI, agent, bot, model, or assistant.
10. Inspect the staged diff and commit metadata immediately before committing. Confirm the author, committer, branch, and message are correct. Do not amend, force-push, rebase published work, or rewrite history unless the user explicitly requests it.
11. Push the branch and open a pull request against the requested base branch, normally `main`. Include a clear summary and exact testing status. The user merges manually; never merge a PR yourself unless explicitly instructed.

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

Report the branch name, commit hash and message, automated and browser checks run (with the screen widths checked), test processes stopped, PR URL, and anything not run or not persisted.
