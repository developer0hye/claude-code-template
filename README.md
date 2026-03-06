# claude-code-template

`claude-code-template` is a reusable template repository for AI-assisted software development.
It is meant to be copied into either a brand-new project or an existing codebase when you want clear, project-level instructions for coding agents such as Claude Code, Codex, and other OpenAI-compatible tools.

The template is intentionally language-agnostic and project-agnostic.
Its purpose is to give any software project a consistent operating model for agent behavior, development methodology, formatting, and PRD authoring.
Its primary goal is to make projects easier to build with AI doing as much of the routine development work as practical, while humans focus on direction, review, and exceptions.

## What this template is for

Use this template when you want to:

- start a new project with AI-ready repository instructions from day one
- retrofit an existing project with explicit agent rules and development conventions
- shape the project so AI agents can handle as much implementation work as possible with low ambiguity
- keep methodology, formatting, and task execution rules in version control
- provide the same project context to different AI coding tools without rewriting instructions

## Core files

- `CLAUDE.md`: the main repository operating rules for the agent. It defines how work should be done, including TDD expectations, logging, naming, typing, comments, git workflow, and when to consult other project files.
- `METHODOLOGY.md`: the project-agnostic software development methodology. It covers universal decision-making principles such as clarifying goals, shipping the smallest useful increment, verification, robustness, and design principles.
- `FORMATTING.md`: the single source of truth for formatting commands. It tells the agent which formatter to run and what fallback to use if the project does not define one yet.
- `AGENTS.md`: the OpenAI-compatible agent entry file. It points agents to the main rules in `CLAUDE.md` and exposes available local skills.
- `README.md`: the human-facing overview of what this template contains and how to adopt it in another repository.

## Agent entry points

- `.claude/commands/prd.md`: Claude Code command entry point for PRD-related work.
- `.claude/agents/prd-authoring.md`: Claude Code subagent definition for PRD creation, revision, and audit tasks.
- `.agents/skills/prd-authoring/`: reusable PRD authoring skill for OpenAI-compatible agents.

## How to use it

1. Copy the Markdown files and the relevant `.claude/` and `.agents/` directories into your target repository.
2. Update `FORMATTING.md` with the real formatting command for that project.
3. Adjust `CLAUDE.md` to match the project's workflow, test strategy, and repository rules.
4. Keep `METHODOLOGY.md` mostly general so it remains reusable across tasks and repositories.
5. Add a project-specific `PRD.md` when you want agents to execute against an explicit product or feature specification.

## Scope

This template does not assume a specific language, framework, architecture, or deployment model.
It is intended to be a portable baseline that can be dropped into almost any software project and then customized only where the project genuinely differs.
