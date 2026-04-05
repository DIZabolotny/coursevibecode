# Rule: Course Structure

## Scope

This rule applies to all structural files in the course:
- `**/program*.md` (course outline, syllabus)
- `**/index*.md` (table of contents)
- `**/00-*.md` (summary and overview files)
- `**/meta.yaml` (course metadata)

## Course Metadata (meta.yaml)

A course must have a `meta.yaml` file with these fields:

```yaml
title: "Course Title"
description: "1-2 sentence course description"
version: "1.0"
author: "Author Name"
type: "course"
format: "practical"          # or theoretical, hybrid
level: "beginner"           # beginner, intermediate, advanced
duration_hours: 20          # Estimated total hours
target_audience: "Who is this course for?"
learning_outcomes:
  - "Student will be able to X"
  - "Student will be able to Y"
  - "Student will be able to Z"
prerequisites: "What should students know before starting?"
tags:
  - tag1
  - tag2
```

All fields are required. The `learning_outcomes` list should be 3-5 items, each matching course-level objectives.

## Module Organization

Lessons must be numbered and grouped into modules/sections:

### File Structure

```
Course-Name/
├── 00-course-summary.md         # Condensed overview
├── 00-course-index.md           # Full table of contents
├── Section-01-Module-Name/
│   ├── lesson-01.md
│   ├── lesson-02.md
│   ├── lesson-03.md
├── Section-02-Module-Name/
│   ├── lesson-04.md
│   ├── lesson-05.md
├── ...
└── meta.yaml                    # Course metadata
```

### Naming Conventions

**Module/Section folder:**
- Format: `Section-XX-Short-Name` or `Module-XX-Short-Name`
- Use hyphens instead of spaces
- Keep names concise but descriptive
- Example: `Section-01-Fundamentals`, `Module-02-API-Integration`

**Lesson file:**
- Format: `lesson-XX.md` or `XX-Lesson-Title.md`
- Numbers must be sequential within the course (not just within section)
- Example: `lesson-01.md`, `lesson-02.md`, ... `lesson-25.md`

**Numbering across modules:**
- Module 1 lessons: 01-05
- Module 2 lessons: 06-10
- Module 3 lessons: 11-15
- Maintain continuous numbering throughout the course

## Module Design

Each module (section) must have:

### 1. Clear Module Outcome

One measurable outcome students achieve by completing the module:

```markdown
## Module Outcome

By completing this module, you will be able to [action verb] [specific skill/knowledge].
```

Example: "By completing this module, you will be able to implement authentication in a Claude Code application using OAuth 2.0."

### 2. Prerequisite Knowledge

Explicitly state what students should know before starting:

```markdown
## Prerequisites

- Knowledge of [Topic A]
- Familiarity with [Topic B]
- [Optional: Experience with Tool C]
```

Optional items are marked as such. If no prerequisites, state: "No prerequisites — this is a foundational module."

### 3. List of Lessons

```markdown
## Lessons

1. [Lesson 1 Title](./lesson-01.md) — Brief description
2. [Lesson 2 Title](./lesson-02.md) — Brief description
3. [Lesson 3 Title](./lesson-03.md) — Brief description
```

Each lesson must be linked with a relative markdown link and have a one-line description.

## Index File (00-course-index.md)

A comprehensive table of contents for the entire course:

### Format

```markdown
# [Course Name] — Index

**Course Overview:** [One paragraph about the course]

## Modules & Lessons

| Module | Lesson | Duration | Description |
|--------|--------|----------|-------------|
| Module 1 — Title | [01. Lesson 1](Section-01/lesson-01.md) | 45 min | What this lesson teaches |
| | [02. Lesson 2](Section-01/lesson-02.md) | 60 min | What this lesson teaches |
| Module 2 — Title | [03. Lesson 3](Section-02/lesson-03.md) | 50 min | What this lesson teaches |
| | [04. Lesson 4](Section-02/lesson-04.md) | 55 min | What this lesson teaches |
```

**Requirements:**
- All lessons listed in order
- Each lesson linked with relative path
- One-line description per lesson (10-20 words)
- Duration estimate for each lesson
- Modules clearly separated

## Summary File (00-course-summary.md)

A condensed, thesis-style overview (not a transcript or full text):

### Format

```markdown
# [Course Name] — Summary

## Course Overview

[2-3 sentences: What the course teaches, who it's for, what you'll be able to do after.]

## Key Modules

### Module 1: [Title]
- [Key concept 1] → [Lesson X](Section-01/lesson-0X.md)
- [Key concept 2] → [Lesson Y](Section-01/lesson-0Y.md)
- [Key concept 3] → [Lesson Z](Section-01/lesson-0Z.md)

### Module 2: [Title]
- [Key concept 1] → [Lesson A](Section-02/lesson-0A.md)
- [Key concept 2] → [Lesson B](Section-02/lesson-0B.md)

## Core Concepts & Terminology

- **Term 1:** Short definition
- **Term 2:** Short definition
- **Term 3:** Short definition

## Learning Outcomes

- You will be able to [X]
- You will be able to [Y]
- You will be able to [Z]

## Practical Skills

- Skill 1 learned in [Module X](Section-XX)
- Skill 2 learned in [Module Y](Section-YY)

## Study Path

**Recommended order:** Start with Module 1. Modules 2 and 3 can be done in any order.

**Time estimate:** [X] hours total
```

**Rules:**
- Every key concept should link back to the lesson where it's taught
- Summary should be readable in 10-15 minutes
- Focus on practical outcomes, not technical details
- Keep to 1-2 pages maximum

## Cross-References

All internal links must use **relative markdown links**:

### Correct
```markdown
[Lesson 5](../Section-02/lesson-05.md)
[Module Overview](./README.md)
[Next Lesson](./lesson-02.md)
```

### Incorrect
```markdown
[Lesson 5](https://example.com/lessons/05)  # Absolute URL (avoid)
[Lesson 5](/lesson-05.md)                    # Absolute path (avoid)
```

## Module Numbering

Modules are numbered sequentially:
- Module 1, Module 2, Module 3, etc.
- OR Section 1, Section 2, Section 3, etc.
- Pick ONE naming convention and stick to it throughout the course

## Course Length

**Typical:** 8-15 modules
**Each module:** 3-7 lessons
**Each lesson:** 30-90 minutes

**Total course:** 20-40 hours typical for a comprehensive course

If course is 100+ hours, break into multiple courses or levels (Beginner, Intermediate, Advanced).

## Lesson Sequence Rules

### Pedagogical Order
1. Foundational concepts (module 1)
2. Core skills (modules 2-5)
3. Integration/advanced (modules 6+)

### Dependency Tracking

Ensure no circular dependencies:
- Lesson X cannot require knowledge of Lesson Y if Lesson Y comes after Lesson X
- Document all prerequisites in each lesson (see `lesson-content.md`)

### No Knowledge Jumps

Every new concept must be scaffolded:
- Simple before complex
- Concrete before abstract
- Theory before application

## Accessibility & Navigation

Students should be able to:
- Understand course structure at a glance (from index)
- Navigate from any lesson to any other
- Know where they are (which module, which lesson)
- Know where they're going next

Use relative links and clear labeling to enable this.

## Quality Checklist

- [ ] `meta.yaml` exists with all required fields
- [ ] `00-course-index.md` lists all modules and lessons
- [ ] `00-course-summary.md` provides condensed overview
- [ ] Module folders follow naming convention (Section-XX)
- [ ] Lesson files numbered sequentially
- [ ] Each module has clear learning outcome
- [ ] Prerequisites explicitly stated
- [ ] No circular dependencies
- [ ] All internal links are relative markdown links
- [ ] All linked lessons exist and have content
- [ ] Lesson order is logical (simple to complex)
- [ ] Index descriptions match actual lesson content
- [ ] Course level appropriate for target audience

## Related Rules

- See `lesson-content.md` for individual lesson structure
- See `exercises-quizzes.md` for practice materials placement
