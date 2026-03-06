---
name: prd-authoring
description: Create, revise, or audit a project-specific PRD.md into a self-contained, execution-oriented specification with explicit objective, baseline, scope, interfaces, phased work, and verification. Use when a repository needs a new PRD, an existing PRD is vague, or a brief must be converted into an actionable specification.
---

# PRD Authoring

Use this subagent to create or improve a project-specific `PRD.md`.

## Workflow

1. Read `.claude/references/prd-standard.md` before editing any PRD.
2. Check whether the target repository already has a project-specific `PRD.md`.
3. If `PRD.md` exists, revise it against the standard and preserve valid project-specific detail.
4. If `PRD.md` does not exist, create a new one instead of blocking.
5. Gather only the repository context needed for the task: current behavior, relevant files, build or test commands, contracts, and constraints.
6. Make scope boundaries explicit, including no-change surfaces.
7. Ensure every requirement maps to at least one phase and at least one verification item.
8. If ambiguity remains, record the owner, default, trigger, risk, and whether work should stop, ask, or proceed.
9. Delete placeholders, stale requirements, and resolved questions.

## Output Rules

- Write in English unless the user explicitly requests another language.
- Prefer exact commands, paths, payloads, fields, flags, error codes, thresholds, and evidence over narrative prose.
- Write `None` for required fields that do not apply.
- Keep the PRD self-contained for project-specific execution and review.
- Do not assume the repository already contains a usable `PRD.md`.

## Review Priority

- Missing baseline context that forces repository guesswork
- Ambiguous scope boundaries
- Requirements without contracts or failure behavior
- Requirements without verification
- Phases that are too large to review safely
- Unknowns that do not say whether work must stop or may proceed

When no PRD exists yet, prioritize:

- Creating a complete first draft instead of a placeholder
- Capturing current state before target state
- Defining explicit no-change surfaces
- Writing exact contracts and verification from the first draft

## Validation

- Confirm the PRD includes: metadata, objective, current state, scope, requirements, interfaces, decisions or unknowns, phase plan, verification matrix, and change log.
- Confirm each `FR-#` and `NFR-#` maps to at least one `V-#`.
- Confirm each changed behavior maps to at least one phase.
- Confirm each phase has exact completion criteria and evidence.
- Confirm project-specific execution does not depend on another unspecified document.
