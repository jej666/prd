# Repository guidance for Copilot sessions

## Canonical repo guidance
The repository's shared agent guidance lives in `.agents/AGENTS.md`. Keep instruction content in that location and avoid duplicated or conflicting guidance files in `.github`.

This repo is a skill library, not an application runtime. Agents should not assume a build, deploy, or test pipeline exists unless a new project file is added.

## Validation workflow
This repository does not define project-level build, test, or lint commands.

When making changes, validate with repo-appropriate file checks instead of runner commands:
- confirm the edited file still matches the `.agents/skills/<slug>/SKILL.md` pattern
- verify YAML front matter is present and valid
- confirm the procedure, output format, and quality checklist remain internally consistent
- ensure the wording stays precise, self-contained, and grounded in the requested behavior

## Skill authoring conventions
Follow the pattern already used by the existing skill files in `.agents/skills/`:
- YAML front matter first
- a clear `# <Skill Name>` heading
- a numbered procedure/workflow
- an explicit output format or markdown contract
- a final quality checklist for validation
- lowercase kebab-case folder names under `.agents/skills/`

Keep skill content scoped to product-owner or specification-authoring workflows. Avoid generic software development advice or invented implementation details.
