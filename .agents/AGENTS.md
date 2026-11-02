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

## Execution contract for skill output
- Default behavior: return Markdown in the chat response. Do not create files unless the user explicitly asks to save the result or the workflow requires a file artifact.
- If a file artifact is required, use workspace-relative paths and create parent directories as needed.
- For this repo, the default file paths are:
  - epic docs: `docs/plan/{epic-name}/epic.md`
  - dod docs: `docs/dod/{dod-name}/dod.md`

## Skill catalog and selection guidance
Use the skill that matches the deliverable the user needs:
- `definition-of-done`: use when the user already has a feature, epic, or specification and needs a concise completion checklist.
- `epic-authoring`: use when the user needs a user-focused epic with title, description, and acceptance criteria.
- `specification-authoring`: use when the user needs a full technical specification with requirements, constraints, interfaces, and acceptance criteria.
- `update-skills`: use when the user wants to preserve a repeatable repo learning, recurring pitfall, or important workflow pattern as durable guidance for future sessions.

Avoid switching between multiple skills for the same request unless the user explicitly asks for multiple artifacts. If one skill produces the needed output, do not also create a second artifact unless requested.
Before adding or expanding a skill, review the existing skills' triggers, scopes, procedures, and output contracts. Extend the closest existing skill or clarify boundaries instead of introducing a competing skill for substantially the same deliverable.

## Learnings
- This repo is a skill catalog, not an application runtime. Future sessions should not assume a build/test/lint pipeline exists unless an actual project manifest is added.
- Keep one canonical instruction location. Shared guidance belongs in `.agents/AGENTS.md`; duplicate `.github` instruction files create drift and confusing agent behavior.
- Default to chat output for skills unless the user explicitly asks for a file artifact, and use repo-relative paths only when saving is required.
- When multiple skills appear relevant, choose the one that matches the planned deliverable: completion checklist, epic, specification, or durable repo-learning capture. Avoid creating multiple artifacts in a single request unless the user asks for them.
- Preserve repeatable repo learnings with `update-skills` so future sessions do not rediscover the same pitfalls or duplicate guidance in the wrong location.
