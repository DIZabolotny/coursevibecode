# ARCHITECTURE — coursevibecode

*Repository structure and operating model*

## Overview

`coursevibecode` is a markdown-first course workspace.
It combines content authoring with a lightweight agent framework layer.
The main active product is the `2_lessons/` section, which is organized into books, learning paths, and practical playbooks.

**Tech Stack:**
- Markdown content files
- Git / GitHub workflow
- Shared framework memory in `.claude/`
- Codex adapter layer in `.codex/`
- Shared runtime commands in `src/framework-core/`

## Directory Structure

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
│   ├── NEXT-SESSION-PROMPT.md
│   ├── codex-agent-learning-path.md
│   ├── claude-code-agent-learning-path.md
│   ├── codex-book/
│   │   ├── AGENTS.md
│   │   ├── BACKLOG.md
│   │   ├── README.md
│   │   └── 01-09 chapters
│   ├── claude-code-book/
│   │   ├── AGENTS.md
│   │   ├── BACKLOG.md
│   │   ├── README.md
│   │   └── 01-09 chapters
│   └── playbooks/
│       ├── AGENTS.md
│       ├── BACKLOG.md
│       ├── README.md
│       ├── SESSION-HANDOFF.md
│       ├── NEXT-SESSION-PROMPT.md
│       └── 01-05 playbooks
├── .claude/
├── .codex/
└── src/framework-core/
```

## Key Components

### Root Course Navigation
**Location:** `README.md`, `COURSE-INDEX.md`
**Purpose:** Provide entry points into the course and surface the new `2_lessons` line.

### `2_lessons/codex-book`
**Location:** `2_lessons/codex-book/`
**Purpose:** Full structured book on Codex for non-technical readers.

### `2_lessons/claude-code-book`
**Location:** `2_lessons/claude-code-book/`
**Purpose:** Full structured book on Claude Code for non-technical readers.

### `2_lessons/playbooks`
**Location:** `2_lessons/playbooks/`
**Purpose:** Short, scenario-based practical guides built on top of the two books.

### Framework Memory
**Location:** `.claude/`
**Purpose:** Root snapshot, backlog, architecture, and handoff state used to restart work after context resets.

### Runtime Layer
**Location:** `src/framework-core/`, `.codex/`
**Purpose:** Shared framework commands and adapter entry points for session start/completion workflows.

## Architecture Pattern

**Pattern:** markdown content workspace with layered agent instructions

**Description:**
- Root framework files define shared operational memory.
- Section-level `AGENTS.md` files define authoring rules.
- Folder-level backlog and handoff files localize continuation points.
- Content artifacts stay separated from framework state, but both are updated before closeout.

## Data Flow

```text
User intent
-> root framework context (.claude)
-> section context (2_lessons)
-> local folder context (book or playbooks)
-> new or updated markdown artifact
-> local README / COURSE-INDEX refresh
-> root snapshot/backlog refresh
-> completion protocol and commit
```

## External Dependencies

- Local Git repository
- Codex / Claude agent runtime installed on the workstation
- Optional official web documentation for factual verification of tool behavior

## Configuration

**User-level:** `~/.codex/config.toml`
**Project-level:** `.codex/config.toml`
**Authoring guidance:** layered `AGENTS.md` files inside `2_lessons/`

## Testing Strategy

- Manual structural review of chapter organization
- Link sanity checks through repository indexes
- Human editorial pass for wording consistency and audience fit

## Deployment

Primary deployment target is GitHub as a markdown repository with navigable indexes.

---
*Update this file when section structure, operating layers, or resume flow change materially.*
