# Repository guidance for AI agents

## Repository purpose
This repository is a lightweight package of custom Copilot skills for product-owner and specification-writing workflows. The primary source files are under `.agents/skills/<skill-name>/SKILL.md`.

Each skill is a prompt-and-procedure document, not an application or service. The agent should treat the repo as a collection of reusable instructions and output contracts rather than as a codebase with a runtime, database, or deploy pipeline.

## Build, test, and lint
This repository does not define project-level build, test, or lint commands.

- No `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `Makefile`, or similar build manifest is present.
- There are no automated test files or repo-wide lint configs.
- For validation, use file-level checks appropriate to a prompt repository:
  - ensure the edited file is still a valid `.agents/skills/<slug>/SKILL.md`
  - verify the YAML front matter remains valid and complete
  - confirm the skill procedure, output format, and quality checklist stay internally consistent
  - read the relevant section and validate that the instruction remains self-contained and non-vague

## High-level architecture
- `.agents/skills/` is the core content directory.
- Each subdirectory under it represents a single reusable skill.
- `SKILL.md` is the canonical artifact for each skill and contains:
  - YAML front matter (`name`, `description`, `argument-hint`)
  - a structured markdown procedure
  - the expected output format or response contract
  - a validation checklist or rules for correctness
- `README.md` is intentionally minimal and describes the repository as a set of Copilot skills.
- The repository does not contain application code, infrastructure, or runtime logic beyond the skill documents themselves.

## Key conventions
- Keep changes scoped to the skill workflow and documentation structure already present in the repo.
- Follow the established pattern used by the existing skills:
  - YAML front matter first
  - a clear `# <Skill Name>` heading
  - a numbered procedure or workflow
  - explicit output format or markdown contract
  - a quality checklist for validating the result
- Use lowercase, kebab-case skill directory names under `.agents/skills/`.
- Prefer precise, testable wording and avoid inventing behavior that is not grounded in the user request.
- Keep Markdown output structured and explicit so the agent can reliably return the required format without ambiguity.
- When adding or editing a skill, preserve the repo's emphasis on product-owner work, specification quality, and clear acceptance criteria.

## Repository-local agent guidance
No repo-local assistant files such as `AGENTS.md`, `CLAUDE.md`, `.cursorrules`, `.windsurfrules`, `CONVENTIONS.md`, or `.clinerules` were present before this file was added. This file intentionally serves as the shared instructions for agent-agnostic workflows in this repository.
