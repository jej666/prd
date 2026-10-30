---
name: definition-of-done
description: "Write a concise, verifiable Definition of Done (DoD) from an experienced Product Owner perspective. Use when asked to create or improve DoD, completion criteria, or a Definition of Done for a feature, specification, or product purpose."
argument-hint: "[specification purpose]"
---

# Definition of Done

Turn the user's specification purpose into a focused Definition of Done that makes completion objectively assessable.

## Procedure

1. Treat the user's request or slash-command argument as the specification purpose. If it is missing or too vague to identify what is being delivered, ask for the purpose before drafting criteria.
2. Identify the intended outcome, relevant users, scope, constraints, and any acceptance conditions stated in the purpose. Use only this context; do not invent product behavior, technologies, metrics, or commitments.
3. Draft 8 to 12 distinct criteria. Each criterion must describe one observable, binary condition that can be marked done or not done. Tailor the criteria to the purpose, covering relevant behavior and quality concerns such as acceptance conditions, error and edge cases, usability, accessibility, security, performance, testing, or documentation only when applicable.
4. Make each criterion specific enough to verify from an artifact, test, demonstration, or other observable evidence. Avoid subjective terms such as "good," "appropriate," or "user-friendly" unless the purpose supplies a measurable definition. Avoid compound criteria that bundle multiple independent outcomes.
5. Check that the criteria collectively cover the stated outcome and constraints, are not duplicates or contradictory, and do not rely on unstated assumptions. Keep the list concise.

## Output Format

Return only a bulleted list of 8 to 12 criteria. Use Markdown checkboxes (`- [ ]`) so each item can be marked done or not done. Do not include a heading, introduction, explanation, assumptions, or closing text.
