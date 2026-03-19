# SNAPSHOT — coursevibecode

*Last updated: 2026-03-18*

## Current State

**Version:** 1.17
**Status:** `2_lessons` expansion in progress
**Branch:** `codex/2-lessons-session-reset`

## Project Overview

`coursevibecode` is a markdown-first course repository for non-technical readers who want to move from ordinary AI chats toward structured work with agent tools.

The active development line is `2_lessons/`, where the repository now holds:
- two short learning-path outlines;
- a full book on Codex;
- a full book on Claude Code;
- a growing set of practical playbooks.

## Current Structure

```text
coursevibecode/
├── README.md
├── COURSE-INDEX.md
├── CHANGELOG.md
├── 2_lessons/
│   ├── README.md
│   ├── AGENTS.md
│   ├── BACKLOG.md
│   ├── SESSION-HANDOFF.md
│   ├── codex-agent-learning-path.md
│   ├── claude-code-agent-learning-path.md
│   ├── codex-book/
│   ├── claude-code-book/
│   └── playbooks/
├── .claude/
├── .codex/
└── src/framework-core/
```

## Recent Progress

- [x] Added a global `COURSE-INDEX.md` and a section index for `2_lessons/`
- [x] Built `2_lessons/codex-book` chapters `01`-`09`
- [x] Built `2_lessons/claude-code-book` chapters `01`-`09`
- [x] Added both learning-path outline files for Codex and Claude Code
- [x] Added playbooks wave 1: `01`-`05`
- [x] Added section-level handoff and next-session files for reset-safe continuation
- [x] Corrected `AGENTS.md` hierarchy so local course-writing files override framework background guidance

## Active Work

- [ ] Write playbooks wave 2: `06`-`09`
- [ ] Run an editorial pass across all playbooks after wave 2 is complete
- [ ] Decide whether to add a separate practice-level `Codex vs Claude Code` comparison guide

## Next Steps

- [ ] Resume at `2_lessons/playbooks/06-weekly-content-production-cycle.md`
- [ ] Continue through `07-building-project-instructions.md`
- [ ] Continue through `08-safe-growth-of-autonomy.md`
- [ ] Continue through `09-agent-organization-for-small-team.md`
- [ ] Refresh indexes after each new playbook

## Key Concepts

- The audience is non-technical and needs literal interface guidance.
- Full lessons must be self-sufficient, not just link collections.
- `AGENTS.md` + `BACKLOG.md` + handoff files form the operating layer for long work.
- Autonomy depends on configuration, explicit artifacts, and fresh session context.
- Root framework memory lives in `.claude/`; section-specific resume logic lives closer to the active folder.

---
*Primary root-level context for the next session. Pair with `.claude/SESSION-HANDOFF.md` when resuming after a reset.*
