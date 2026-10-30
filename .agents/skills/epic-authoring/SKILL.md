---
name: epic-authoring
description: "Create, draft, or refine product epics with user-focused titles, testable acceptance criteria, and a verifiable Definition of Done. Use when asked to write or improve an epic, epic description, acceptance criteria, or epic-level completion checklist."
argument-hint: "[epic purpose or feature]"
---

# Epic Authoring

Turn the user's feature or business need into a clear, actionable epic that a team can implement and verify.

## Procedure

1. Treat the user's request or slash-command argument as the epic purpose. Identify the user/persona, requested functionality, and business value from the supplied context. Do not invent product behavior or unstated commitments.
2. If the purpose or user/persona is too unclear to write a meaningful epic, ask focused clarifying questions. Otherwise, make only minimal, evident assumptions and state them briefly when needed.
3. Write an action-oriented, user-focused title that describes the outcome from the user's perspective. For example: "User can reset password via email."
4. Write the description using exactly this structure:

   ```text
   As a [user type/persona]
   I want [specific functionality]
   So that [business benefit/value]
   ```

5. Write 3 to 5 acceptance criteria. Make each one specific, observable, and testable. Use Given/When/Then format when it improves clarity. Cover relevant success paths, edge cases, and error scenarios without adding behavior that is not supported by the request.
7. Review the epic for consistency: the title, description, and criteria must describe the same outcome; criteria must be verifiable.

## Output Format

Return the epic using these sections, in order:

```markdown
## Title
[Action-oriented, user-focused title]

## Description
As a [user type/persona]
I want [specific functionality]
So that [business benefit/value]

## Acceptance Criteria
- [3 to 5 specific, testable criteria; use Given/When/Then where appropriate]

```
