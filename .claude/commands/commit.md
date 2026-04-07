Commit all changed files individually — one commit per file.

Steps:
1. Run `git status` to see all changed (modified, added, deleted, untracked) files
2. For EACH changed file, create a **separate individual commit**:
   - Stage only that single file: `git add <file>`
   - Write a concise commit message describing what changed in that specific file
   - Commit it: `git commit -m "<message>"`
3. Do NOT bulk-commit multiple files together. Every file gets its own commit.
4. After all commits are done, run `git log --oneline -20` and show the results.

Rules:
- Never use `git add .` or `git add -A` — always add files one at a time
- Each commit message should be concise (under 72 chars) and describe the change in that file
- Skip files that contain secrets (.env, credentials, etc.) and warn about them
- If there are no changes, say so and stop
