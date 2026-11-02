---
name: update-skills
description: "Capture repeated repository learnings, non-obvious constraints, or recurring pitfalls as durable skill or instruction guidance. Use when a user asks to learn, update skills, or preserve repo-level knowledge for future sessions."
argument-hint: "[learning or repo pattern to preserve]"
---

# Update Skills

Convert a repeatable discovery into durable guidance so future sessions do not rediscover the same issue or make the same avoidable mistake.

## Procedure

1. Treat the user's request or slash-command argument as the learning to preserve. If the learning is not clear enough to define a concrete rule, ask for the missing context before writing.
2. Identify whether the finding is:
   - a small rule that fits naturally in an existing instruction file,
   - a distinct procedural workflow that belongs in a dedicated skill, or
   - a project-wide rule that should be enforced automatically for matching files.
3. Prefer the smallest durable unit that will help future sessions:
   - update an existing instruction when the learning is 1 to 4 sentences and refines an existing guidance file,
   - create or update a skill when the knowledge includes a multi-step method, examples, or a reusable workflow,
   - create or update an instruction when the rule should apply automatically based on file patterns or project-wide conventions.
4. Check the repository for the best existing home before creating a new file. In this repo, shared guidance belongs in `.agents/AGENTS.md`, and skill content belongs in `.agents/skills/<slug>/SKILL.md`.
5. Write the learning in a format that is specific and actionable:
   - state the problem or pitfall,
   - explain why it matters,
   - describe the correct approach,
   - include a concrete example or explicit do/don't rule when it improves clarity.
6. Keep the guidance narrow and grounded in real repo behavior. Do not write generic advice or include invented architecture that the repository does not support.
7. Validate the final artifact against the repo's conventions:
   - YAML front matter should be present and valid,
   - the skill or instruction should be self-contained,
   - the scope should remain consistent with the repository's purpose,
   - the rule should clearly tell the agent when to use or apply it.

## Output Format

Return a short summary that includes:

```markdown
## Captured Learning
- What was discovered
- Where it was stored
- Why that location fits
- Whether it updates an existing file or creates a new one
```

If the user explicitly asks for a file artifact, create the relevant skill or instruction file in the repo, using the canonical path for the location chosen in the procedure.

## When to Use This Skill

Use this skill when the user asks to capture a learning, preserve a repo pattern, avoid future confusion, or formalize a recurring rule as durable guidance.

## File Output

Default behavior is to return the summary in the chat response. If the user explicitly asks to save the result to the repo, place the artifact in the appropriate canonical path:
- `.agents/skills/<skill-name>/SKILL.md` for a reusable procedure or workflow
- `.agents/instructions/<name>.instructions.md` for file-pattern-driven rules when required
- `.agents/AGENTS.md` only for repo-wide shared guidance that should remain centralized

## Quality Checklist

- The learning is specific enough to be actionable.
- The rule is general enough to help future sessions, not just a one-off fix.
- The chosen location matches the repo's canonical structure.
- The guidance is grounded in a real repository fact or repeatable workflow.
- The output clearly states when the skill or instruction should be used.
- The rule does not duplicate another learning without a clear reason.
