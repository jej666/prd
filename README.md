# prd

Copilot skills for product owner workflows.

## Skill catalog

| Skill | Use when | Output |
| --- | --- | --- |
| `definition-of-done` | You already have a feature, epic, or specification and need a concise completion checklist | Markdown checklist only by default |
| `epic-authoring` | You need to turn a feature idea into a user-centered epic with title, description, and acceptance criteria | Markdown epic content; save under `docs/epics/{epic-name}/epic.md` only when asked |
| `prompt-optimizer` | You want to write, rewrite, or improve a prompt for an LLM chat interface | One copy-pasteable prompt in a code block |
| `update-skills` | You need to preserve a repeated repo learning, workflow pitfall, or project-level rule as durable guidance for future sessions | Short summary of the learning and the canonical location chosen |

## Selection guidance
- Use `definition-of-done` when the work already exists and the need is to define completion clearly.
- Use `epic-authoring` when the goal is to shape a user-focused story or feature before implementation.
- Use `prompt-optimizer` when the deliverable is a ready-to-send prompt for a chat-based LLM.
- Use `update-skills` when the team has identified a pattern, constraint, or recurring mistake worth preserving for future sessions.

These skills are intentionally narrow and repo-specific; they are designed for product-owner and specification-writing workflows rather than general application development.