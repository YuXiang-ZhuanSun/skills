---
name: tree-structured-docs
description: Restructure flat, confusing, or interface-heavy documentation into a tree-shaped 总-分-总 manual with a mind-map overview, grouped sections, clear reading order, and a final checklist. Use when writing or revising README files, user manuals, design docs, architecture docs, API guides, onboarding docs, or any document that currently reads like a long flat list of points.
---

# Tree Structured Docs

Use this skill to turn documentation from a flat list into a guided tree.

The goal is not to add more text. The goal is to help readers build a mental map before they see details.

## Core Shape

Use a 总-分-总 structure:

```text
总: first give the reader a map
  +-- what this document is for
  +-- who should read it
  +-- the one-sentence mental model
  +-- the tree / mind-map overview

分: then explain grouped branches
  +-- each branch answers one coherent question
  +-- each branch moves from concept -> mechanism -> example
  +-- details are nested under the branch, not exposed as 20+ peer headings

总: finally return to synthesis
  +-- recap how the pieces work together
  +-- provide a checklist
  +-- provide a recommended learning or execution path
```

## When Refactoring Existing Docs

First diagnose the current failure mode:

```text
Flat list:
  Many peer headings with no hierarchy.

Interface encyclopedia:
  Many APIs are explained, but the reader cannot see how they cooperate.

Missing map:
  Details appear before the reader knows the overall system.

Wrong order:
  Advanced concepts appear before the basic workflow.

No return:
  The document ends after details, without a summary or checklist.
```

Then reorganize before rewriting sentences.

## Workflow

1. Identify the reader and task.

```text
Reader:
  Who opens this document?

Task:
  What should they be able to do after reading?

Primary confusion:
  What blocks understanding today?
```

2. Extract all existing topics.

Do not preserve current heading levels by default. Treat headings as raw material.

Group topics into 3-6 major branches. Good branch names answer reader questions:

```text
What is this?
How do the parts work together?
What are the core concepts?
How do I use it?
How do I debug or validate it?
What should I do next?
```

3. Build the mind-map overview.

Place this near the top:

```text
System / Document Topic
  +-- Branch A
  |     +-- Concept
  |     +-- Mechanism
  |     +-- Example
  |
  +-- Branch B
  |     +-- ...
  |
  +-- Summary
        +-- checklist
        +-- learning path
```

4. Write the document in layered order.

For each branch:

```text
Start with the purpose of the branch.
Define new concepts before using them.
Show how concepts cooperate.
Then show the API / mechanism / example.
End the branch with a short practical rule.
```

5. Collapse long peer lists.

If a document has many same-level headings, promote groups and demote details:

```text
Before:
  ## Interface A
  ## Interface B
  ## Interface C
  ## Interface D
  ## Interface E

After:
  ## Core Interfaces
  ### Time-related interfaces
  ### Execution interfaces
  ### Observability interfaces
```

6. Add synthesis at the end.

End with one or more of:

```text
Mental model recap
Good implementation checklist
Common mistakes
Recommended reading path
Next exercise
```

## Writing Rules

- Prefer 3-6 top-level sections after the intro.
- Avoid 10+ top-level peer headings unless the document is a reference index.
- Introduce a concept before using it in examples.
- Explain relationships before listing APIs.
- Put examples after the reader understands the cooperating parts.
- Use tree diagrams for structure and flow diagrams for behavior.
- Keep reference detail, but nest it under meaningful groups.
- Preserve useful existing content; change its shape first, wording second.
- Do not hide important warnings at the end.

## Good Target Structure

For a user manual:

```text
# Manual Title

## Overview
  +-- one-sentence mental model
  +-- mind-map
  +-- glossary
  +-- complete example path

## Part 1: Runtime / Workflow
  +-- what happens first
  +-- how execution proceeds
  +-- minimal runnable example

## Part 2: Core Concepts and APIs
  +-- grouped by role, not alphabetically
  +-- each API tied back to the workflow

## Part 3: Building Real Things
  +-- templates
  +-- patterns
  +-- examples

## Part 4: Debugging and Validation
  +-- logs
  +-- stats
  +-- tests
  +-- common mistakes

## Summary
  +-- checklist
  +-- learning path
```

For an architecture document:

```text
# Architecture Title

## System Positioning
## Architecture Map
## Layer Responsibilities
## Data / Control Flow
## Extension Points
## Boundaries and Non-goals
## Review Checklist
```

## Quality Check

Before finishing, verify:

```text
The first page gives a useful map.
The top-level headings form a tree, not a list.
Each major section answers one reader question.
New concepts are introduced before use.
APIs are grouped by how they cooperate.
There is at least one complete end-to-end example.
The ending returns to a summary/checklist.
The document can be skimmed by reading only headings and diagrams.
```
