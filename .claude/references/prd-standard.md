# Project PRD Standard

- Use `PRD.md` as the authoritative, project-specific source of truth for goals, scope, constraints, contracts, phases, and definition of done.
- Assume the reader has only the current working tree and this file. Do not rely on prior discussion, implied defaults, or undocumented team habits.
- Write in English.
- Keep it concise, but never omit context required to make correct implementation or review decisions.
- If a field does not apply, write `None`. Do not leave required fields blank.

## Non-Negotiable Rules

- Keep required project-specific instructions in this file. Reference other documents only for secondary detail, not for core execution context.
- Separate facts, decisions, assumptions, unknowns, and open questions.
- Use stable IDs:
  - Functional requirements: `FR-#`
  - Non-functional requirements: `NFR-#`
  - Decisions: `D-#`
  - Assumptions: `A-#`
  - Unknowns: `U-#`
  - Open questions: `Q-#`
  - Verification items: `V-#`
  - Phases: `P1`, `P2`, `P3`, ...
- Use `must` for required behavior. Use `should` only for deliberate, non-critical preferences.
- Replace vague words such as `fast`, `intuitive`, `robust`, `support`, `improve`, `stable`, and `handled gracefully` with exact, testable meaning.
- Use exact names: repository-relative paths, modules, functions, commands, endpoints, tables, fields, flags, environment variables, status codes, and thresholds.
- Every requirement must map to at least one verification item.
- Every requirement that changes behavior must map to at least one phase.
- Every unresolved item must state whether work must `stop`, `ask`, or `proceed with default`.

## Required Sections

- Metadata
- Objective
- Current State and Baseline
- Scope and Boundaries
- Requirements
- Interfaces and Data Contracts
- Decisions, Assumptions, Unknowns, and Open Questions
- Phase Plan
- Verification Matrix
- Change Log

## Required Content Rules

- Capture the current state before the target state.
- Make out-of-scope and no-change surfaces explicit.
- Write functional and non-functional requirements separately.
- For each requirement, state trigger or input, required behavior or output, failure behavior, constraints, and verification IDs.
- Include exact contracts for each touched surface: UI, API or CLI, data or schema, jobs or workers, rollout, permissions, and integrations when relevant.
- For each unresolved item, include owner, default, trigger, risk, and execution rule.
- Break work into small, independently valuable, independently verifiable phases.
- For each verification item, include working directory, command or manual action, expected result, and evidence to capture.
