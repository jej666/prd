---
name: specification-authoring
description: "Create self-contained, testable technical specifications in structured Markdown. Use when asked to write, draft, or generate a specification, technical spec, or requirements document."
argument-hint: "[specification purpose]"
---

# Specification Authoring

Turn the user's specification purpose into a complete, self-contained technical specification that can be saved under `spec/` in the workspace.

## Procedure

1. Treat the user's request or slash-command argument as the specification purpose. If no purpose is provided, ask for it. Clarify only details that materially change scope or make the requirements impossible to state reliably; otherwise record reasonable assumptions in the document.
2. Identify the solution components, intended audience, scope, requirements, constraints, recommendations, and interfaces implied by the purpose. Do not invent system behavior or external facts. Make assumptions explicit and keep the specification usable without external context.
3. Choose exactly one filename category from `schema`, `tool`, `data`, `infrastructure`, `process`, `architecture`, or `design`. Create a descriptive lowercase ASCII kebab-case slug. The target filename must match `spec-[category]-[slug].md` and be placed in the workspace's `spec/` directory.
4. Write the document using the structure below, in order. Complete every section. If a section has no applicable content, state that explicitly and explain why.
5. Before responding, check the document against the quality checklist. Return only the complete Markdown file content: do not add a code fence, filename, preface, or follow-up text.

## Required Document Structure

Begin with YAML front matter containing:

```yaml
---
title: "<descriptive specification title>"
category: "<one approved filename category>"
status: "draft"
---
```

Then include these sections in exactly this order:

## 1. Purpose & Scope

Describe the purpose, application scope, intended audience, included and excluded behavior, and assumptions.

## 2. Definitions

Define every acronym and domain-specific term used in the document. Use a table with the term and its definition. If none are needed, say so.

## 3. Requirements

List functional and non-functional requirements. Give each a stable identifier (`REQ-001`, `REQ-002`, ...), use **shall** for mandatory behavior, **should** for recommendations, and **may** for optional behavior. Write requirements so that they describe one observable outcome each.

## 4. Interfaces

Specify relevant component boundaries, inputs, outputs, data formats, protocols, error behavior, and interaction rules. Include only interfaces relevant to the stated scope; explicitly say when none apply.

## 5. Constraints

List binding technical, operational, regulatory, compatibility, or resource limitations with stable identifiers (`CON-001`, ...). Do not put recommendations in this section.

## 6. Recommendations

List non-binding guidance with stable identifiers (`REC-001`, ...). Do not present recommendations as mandatory requirements.

## 7. Examples and Edge Cases

Provide concrete examples and meaningful edge cases where they clarify expected behavior. Label illustrative examples as such and ensure they do not conflict with requirements.

## 8. Acceptance Criteria

Provide testable criteria with stable identifiers (`AC-001`, `AC-002`, ...). Use Given-When-Then where it fits; otherwise state an observable, measurable pass condition. Every `REQ` requirement must be covered by at least one acceptance criterion. Reference the related requirement IDs in each criterion.

## Writing Standards

- Use precise, explicit, unambiguous language and structured Markdown.
- Keep requirements, constraints, and recommendations distinct.
- Make the document self-contained; do not rely on unstated context, external documents, or undefined references.
- Avoid idioms, metaphors, and context-dependent language.
- Include concrete values, units, boundaries, and error outcomes when they are known and relevant. Do not fabricate them when they are not known.
- Do not use unresolved placeholders such as `TBD`. Resolve material ambiguity with the user; otherwise state a bounded assumption.
- Ensure all identifiers are unique, stable, and consistently referenced.

## Quality Checklist

- The target path is `spec/spec-[category]-[slug].md`, and the category is one of the seven approved values.
- YAML front matter is present, complete, and valid.
- All eight sections are present, in order, and completed.
- Requirements, constraints, and recommendations are clearly distinguished and consistently identified.
- Every requirement has at least one linked acceptance criterion.
- All acronyms and domain-specific terms are defined.
- Examples and edge cases are included where they aid clarity and do not contradict requirements.
- The document is self-contained and valid Markdown.
