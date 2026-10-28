---
name: research-notes
description: Structured research note-taking. Use when the user asks to research a topic, take notes, or write a short briefing from findings.
---

# Research notes skill

## When to use

Use this skill for research tasks that should end in a short structured briefing.

## Instructions

1. Gather facts with available tools (search stubs, filesystem, or subagents).
2. Write notes to `/workspace/research-notes.md` using this template:

```markdown
# Topic

## Key points
- ...

## Sources / tools used
- ...

## Open questions
- ...
```

3. Return a 3–5 sentence executive summary to the user (prefer bullets for lists).
