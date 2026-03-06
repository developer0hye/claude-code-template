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
- Treat the PRD as a living specification. Update it when scope, requirements, defaults, contracts, or completion criteria change.

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

## Template Skeleton

```md
# [Project / Feature Name]

## Metadata
- Owner:
- Status:
- Last Updated:
- Version:
- Related Documents / Issues:
- Repository Root / Working Directory:

## Objective
- Problem:
- Target User / Operator:
- Desired Outcome:
- Why Now:
- Primary Success Outcome:
- Failure, Cost, or Risk Being Reduced:

## Current State and Baseline
- Current Behavior:
- Known Limitations or Pain Points:
- Relevant Files / Modules / Services:
- Entry Points:
- Setup / Build / Run / Test Commands:
- Existing Contracts That Cannot Break:
- Environment Assumptions:

## Scope and Boundaries
### In Scope
- ...

### Out of Scope
- ...

### Touched Surfaces
- UI:
- API / CLI:
- Data / Schema:
- Jobs / Workers:
- Configuration:
- Observability:
- Documentation / Operations:
- Rollout / Migration:
- External Integrations:

### Explicit No-Change Surfaces
- ...

## Requirements
### Functional Requirements
- FR-1:
  - Requirement:
  - Trigger / Input:
  - Required Behavior / Output:
  - Failure / Error Behavior:
  - Constraints / Compatibility Notes:
  - Verification IDs:

### Non-Functional Requirements
- NFR-1:
  - Requirement:
  - Target / Threshold:
  - Measurement Method:
  - Verification IDs:

## Interfaces and Data Contracts
- UI:
- API / CLI:
- Data / Schema:
- Jobs / Workers:
- External Integrations:
- Rollout / Migration:
- Permissions / Authorization:
- Error Matrix:

## Decisions, Assumptions, Unknowns, and Open Questions
- D-1:
- A-1:
- U-1:
- Q-1:

## Phase Plan
### P1) [Phase Name]
- Purpose:
- Requirement IDs Covered:
- Target Files / Modules / Services:
- Verification IDs:
- Completion Criteria:
  - [ ] ...

## Verification Matrix
- V-1:
  - Requirement IDs:
  - Phase IDs:
  - Working Directory:
  - Command or Manual Action:
  - Expected Result:
  - Evidence to Capture:

## Change Log
- [YYYY-MM-DD]:
  - Change:
  - Reason:
```
