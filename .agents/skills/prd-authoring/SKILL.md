---
name: prd-authoring
description: Draft, create, revise, or audit a project-specific PRD.md into a self-contained, execution-oriented specification with explicit objective, baseline, scope, interfaces, phased work, and verification. Use when writing a new PRD from scratch, tightening a vague PRD, reviewing PRD quality, or converting a loose brief into an actionable project specification.
metadata:
  short-description: Draft or tighten a PRD
---

# PRD Authoring

Use this skill when the task is to create, revise, or review a project-specific `PRD.md`.

## Workflow

1. Read `references/prd-standard.md` before editing any PRD.
2. Check whether the target repository already has a project-specific `PRD.md`.
3. If `PRD.md` exists, revise it against `references/prd-standard.md` and preserve valid project-specific detail.
4. If `PRD.md` does not exist, create a new one using `references/prd-standard.md` as the structure and required content baseline.
5. Gather only the repository context needed for the task: current behavior, relevant files, build or test commands, contracts, and constraints.
6. Write or revise the target PRD so it stands on its own for project-specific execution and review.
7. Make scope boundaries explicit, including no-change surfaces.
8. Ensure every requirement maps to at least one phase and at least one verification item.
9. If ambiguity remains, record the owner, default, trigger, risk, and whether work should stop, ask, or proceed.
10. Delete placeholders, stale requirements, and resolved questions.

## Output Rules

- Write in English unless the user explicitly requests another language.
- Prefer exact commands, paths, payloads, fields, flags, error codes, thresholds, and evidence over narrative prose.
- Write `None` for required fields that do not apply.
- Treat the PRD as the authoritative source for project-specific scope and definition of done.
- Keep the document concise, but never omit baseline context, contracts, or verification.
- Do not assume the repository already contains a usable `PRD.md`.
- If the repository has no `PRD.md`, create one instead of blocking.

## Review Priority

When reviewing an existing PRD, prioritize:

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
- Confirm the task is not blocked merely because the repository started without `PRD.md`.
