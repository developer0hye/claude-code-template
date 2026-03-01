# Project Rules

- Always communicate and work in English.
- Before starting development, check if `PRD.md` exists in the project root. If it does, read and follow the requirements defined in it throughout the development process.
- **IMPORTANT: Follow Test-Driven Development (TDD).** Always write tests first before implementing functionality. Follow the Red-Green-Refactor cycle: (1) Write a failing test, (2) Write the minimal code to make it pass, (3) Refactor while keeping tests green. Every new feature or bug fix must have corresponding tests.
- **IMPORTANT: Read and follow `METHODOLOGY.md`** before starting any task.
- When editing `CLAUDE.md`, use the minimum words and sentences needed to convey 100% of the meaning.
- After completing each planned task, run tests and commit before moving to the next task.
- **After any code change (feature addition, bug fix, refactoring, PR merge), check if `README.md` needs updating.** If project description, usage, setup, architecture, or API changed, update `README.md` with clear, concise language. Keep it minimal — only document what users need to know.

## Logging

- Add structured logs at key decision points, state transitions, and external calls — not every line. Logs alone should reveal the execution flow and root cause.
- Include context: request/correlation IDs, input parameters, elapsed time, and outcome (success/failure with reason).
- Use appropriate log levels: `ERROR` for failures requiring action, `WARN` for recoverable issues, `INFO` for business events, `DEBUG` for development diagnostics.
- Keep logging thread-safe. Use thread/coroutine IDs in log context for multi-threaded environments.
- Never log sensitive data (credentials, tokens, PII). Mask or omit them.
- Avoid excessive logging in hot paths — logging must not degrade performance or increase latency noticeably.

## Naming

- Names must be self-descriptive — understandable without reading surrounding code. Avoid cryptic abbreviations (`proc`, `mgr`, `tmp`).
- Prefer clarity over brevity, but don't over-pad. `user_email` > `e`, `calculate_shipping_cost` > `calc` — but no need for `calculate_the_total_shipping_cost_for_user`.
- Booleans should read as yes/no questions: `is_valid`, `has_permission`, `should_retry`.
- Functions/methods should describe the action and target: `parse_config`, `send_notification`, `validate_input`.

## Comments

- Explain **why**, not what. Code already shows what it does — comments should capture intent, constraints, and non-obvious decisions.
- Comment business rules, workarounds, and "why this approach over the obvious one" — context that can't be inferred from code alone.
- Mark known limitations with `TODO(reason)` or `FIXME(reason)` — always include why, not just what.
- Delete comments when the code changes — outdated comments are worse than no comments.

## Git Configuration

- All commits must use the local git config `user.name` and `user.email`. Verify with `git config user.name` and `git config user.email` before committing.
- All commits must include `Signed-off-by` line (always use `git commit -s`). The `Signed-off-by` name must match the commit author.

## Branching & PR Workflow

- All changes go through pull requests. No direct commits to `main`.
- Branch naming: `<type>/<short-description>` (e.g., `feat/add-parser`, `fix/table-bug`).
- One branch = one focused unit of work.
- **Use git worktrees** for all branch work. Do not use `git checkout`/`git switch` in the main repo.
  - Create: `git worktree add ../<repo-name>-<branch-name> -b <type>/<short-description>`
  - Work and push from inside the worktree.
  - Do not delete worktrees immediately after task completion — remove only when starting new work or upon user confirmation.

## PR Merge Procedure

Follow all steps in order:

1. Rewrite PR description if empty/unclear via `gh pr edit`. Include: what changed, why, key changes, and relevant context.
2. Cross-reference related issues (`gh issue list`). Use "Related: #N" — avoid auto-close keywords unless instructed.
3. Check for conflicts. If `main` has advanced, rebase/merge as needed.
4. Wait for CI to pass: `gh pr checks <number> --watch`. Abort if tests fail.
5. Final code review via `gh pr diff <number>` — check for debug statements, hardcoded paths, credentials, unused imports.
6. Merge: `gh pr merge <number> --merge`. **Never use `--delete-branch`** (worktree depends on the branch).
7. Return to main repo, `git pull` to sync.
8. Remove worktree: `git worktree remove ../<repo-name>-<branch-name>`
9. Delete local branch: `git branch -d <branch-name>`
10. Delete remote branch: `git push origin --delete <branch-name>`

## Releases

- When creating a GitHub Release, include a **Contributors** section crediting all external contributors since the previous release.
- Use `git log <prev-tag>..HEAD --format='%an' | sort -u` to find contributors. List each with their GitHub profile link and a brief summary of their contribution.
