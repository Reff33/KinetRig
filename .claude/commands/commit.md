# /commit [hint]

Analyze current project changes and draft an atomic Conventional Commit:

1. Run `git status` and `git diff --stat` to measure diff volume. If working tree is clean ('nothing to commit, working tree clean'), report 'Working tree clean: nothing to commit.' and stop immediately.
2. Security Check: Ensure `.env`, private keys, secrets, or temporary files are not staged.
3. Scope Grouping: If changes touch multiple unrelated domains, recommend logical atomic split.
4. Formulate Message: Generate an exact Conventional Commit message (`feat`, `fix`, `docs`, `chore`, `test`, `refactor`) with scope according to real diff contents. Never include AI attribution trailers.
5. Confirm with User: Present the suggested commit message and file breakdown. Ask for user confirmation before executing `git commit`.
