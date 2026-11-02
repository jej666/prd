---
name: epic-authoring
description: "Create, draft, or refine product epics with user-focused titles, testable acceptance criteria, and a verifiable Definition of Done. Use when asked to write or improve an epic, epic description, acceptance criteria, or epic-level completion checklist."
argument-hint: "[epic purpose or feature]"
---

# Epic Authoring

Turn the user's feature or business need into a clear, actionable epic that a team can implement and verify.

## Procedure

1. Treat the user's request or slash-command argument as the epic purpose. Identify the user/persona, requested functionality, and business value from the supplied context. Do not invent product behavior or unstated commitments.
2. If the user, desired outcome, or value is unclear enough that writing the epic would require guessing, ask focused clarifying questions before drafting. Do not fill the gap with a plausible-sounding persona, benefit, implementation detail, or product behavior.
3. Write an action-oriented, user-focused title that describes the outcome from the user's perspective. For example: "User can reset password via email."
4. Write the description using exactly this structure:

   ```text
   As a [user type/persona]
   I want [specific functionality]
   So that [business benefit/value]
   ```

5. Write 3 to 5 acceptance criteria. Each criterion must describe one observable outcome that can be verified, and together they must cover the epic's stated outcome. Use Given/When/Then when it improves clarity. Include edge cases or error behavior only when supported by the request or needed to define the stated outcome; do not add implementation choices, thresholds, or failure behavior without evidence.
6. If the supplied context does not support 3 to 5 distinct, testable criteria without padding or inventing behavior, ask a focused question instead of manufacturing criteria.
7. Check consistency: the title, description, and criteria must describe the same user outcome, and every criterion must be verifiable from the information provided.

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

## Quality Checklist

- All three sections are present, in order, and completed.
- Define necessary acronyms or domain-specific terms inline; do not add a glossary section.
- Use precise, explicit, unambiguous language and structured Markdown.
- Make the epic understandable on its own; avoid references that require unstated context or external documents.
- Avoid idioms, metaphors, and context-dependent language.
- Include concrete values, units, boundaries, and error outcomes when they are known and relevant. Do not fabricate them when they are not known.
- Resolve material ambiguity with the user rather than using unresolved placeholders such as `TBD` or inserting an unsupported assumption.
- Confirm each acceptance criterion is specific, independently verifiable, and traceable to the requested outcome.
