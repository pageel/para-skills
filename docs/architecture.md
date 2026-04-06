# para-skills — Architecture

> **Version**: 0.1.0 | **Last reviewed**: 2026-04-06

## Overview

para-skills is an OSS library project that researches, develops, and publishes AI Agent skills for the para-workspace ecosystem. The project produces two main outputs: (1) the `/para-skill` workflow — a Co-Author engine for creating, validating, and testing skills, and (2) curated skill templates that ship via `catalog.yml` into any PARA Workspace.

## System Diagram

```
┌─────────────────────────────────────────────────────────────────────┐
│                        para-skills project                          │
│                                                                     │
│  ┌──────────────────────┐    ┌──────────────────────────────────┐   │
│  │  DEVELOPMENT ZONE    │    │  GOVERNANCE ZONE                 │   │
│  │  (sandbox/)          │    │  (.agents/)                      │   │
│  │                      │    │                                  │   │
│  │  para-skill.md  ─────┼─cp─▶  workflows/para-skill.md  [LIVE]│   │
│  │                      │    │                                  │   │
│  │  references/         │    │  rules/                          │   │
│  │  ├ skill-quality-    │    │  ├ oss-compliance.md             │   │
│  │  │ checklist.md      │    │  └ dogfooding-checklist.md       │   │
│  │  └ templates/        │    │                                  │   │
│  │    ├ project-         │    │  skills/                         │   │
│  │    │ profile.md      │    │  └ project-profile/SKILL.md      │   │
│  │    └ tool-skill.md   │    │                                  │   │
│  └──────────────────────┘    └──────────────────────────────────┘   │
│                                                                     │
│  ┌──────────────────────┐    ┌──────────────────────────────────┐   │
│  │  DOCUMENTATION       │    │  ARTIFACTS                       │   │
│  │  (docs/)             │    │  (artifacts/)                    │   │
│  │                      │    │                                  │   │
│  │  architecture.md     │    │  plans/                          │   │
│  │  strategy/           │    │  ├ v0.1.0-...-workflow.md        │   │
│  │  skill-research-     │    │  tasks/                          │   │
│  │  analysis.md         │    │  ├ backlog.md                    │   │
│  │  README.md           │    │  ├ sprint-current.md             │   │
│  └──────────────────────┘    │  └ done.md                       │   │
│                              │  para-decisions/                  │   │
│  ┌──────────────────────┐    │  └ brainstorm-...-2026-04-06.md  │   │
│  │  PUBLIC ZONE         │    └──────────────────────────────────┘   │
│  │  (repo/)             │                                           │
│  │                      │    ┌──────────────────────────────────┐   │
│  │  skills/             │    │  GitHub: pageel/para-skills       │   │
│  │  README.md           │    └──────────────────────────────────┘   │
│  │  LICENSE             │                                           │
│  └──────────────────────┘                                           │
└─────────────────────────────────────────────────────────────────────┘
```

## Content Zoning (OSS Compliance R1)

The project enforces strict content separation per `oss-compliance.md`:

```
┌────────────────────────────────┐  ┌────────────────────────────────┐
│  INTERNAL ZONE (VI allowed)    │  │  PUBLIC ZONE (EN only)         │
│                                │  │                                │
│  docs/           → VI internal │  │  repo/           → EN, no      │
│  artifacts/      → decisions   │  │                    brand names │
│  sessions/       → daily logs  │  │  .agents/workflows/ → EN       │
│  .beads/         → friction    │  │  .agents/skills/  → EN          │
│  sandbox/        → development │  │  catalog.yml      → clean       │
│                                │  │                                │
│  ✅ May reference research     │  │  ❌ No third-party brand names │
│     sources with attribution   │  │  ❌ No copied code/text        │
└────────────────────────────────┘  └────────────────────────────────┘
```

## Key Components

### 1. /para-skill Workflow

- **Location**: `sandbox/para-skill-dev/para-skill.md` (source) → `.agents/workflows/para-skill.md` (live)
- **Purpose**: Manage, create, validate, and test AI Agent skills
- **Actions**: `list`, `add`, `install`, `validate`, `standardize`, `test`

```
/para-skill add [name] --template [project|tool]
     │
     ├── Step 0: Pre-flight (re-read indices + rules)
     ├── Step 1: Template Selection
     ├── Step 2: Draft-First Co-Author ← KEY INNOVATION
     │   ├── Phase A: Auto-scan project context
     │   ├── Phase B: Generate draft SKILL.md
     │   └── Phase C: Present for user approval/edit
     ├── Step 3: Quality self-review (checklist)
     ├── Step 4: Create files
     ├── Step 5: Update skills index
     └── Step 6: Report
```

### 2. Skill Quality Checklist

- **Location**: `sandbox/para-skill-dev/references/skill-quality-checklist.md`
- **Purpose**: 24-point quality framework for validating skills
- **Groups**: P (PARA Structure), D (Description), C (Content), W (Writing), B (Bundled), T (Test)

### 3. Skill Templates

- **Location**: `sandbox/para-skill-dev/references/templates/`
- **Templates available**:

| Template  | File                  | Use case                               |
|:----------|:----------------------|:---------------------------------------|
| `project` | `project-profile.md`  | Project DNA — conventions, checklists  |
| `tool`    | `tool-skill.md`       | Utility/automation — scripts, commands |

### 4. Project Rules

- **Location**: `.agents/rules/`
- **Rules**:

| Rule                   | Purpose                                          |
|:-----------------------|:-------------------------------------------------|
| `oss-compliance.md`    | Content zoning, brand name prohibition, attribution |
| `dogfooding-checklist.md` | 25-point test matrix for workflow validation   |

## Data Flow

```
Research (Resources/references/)
     │
     │  Analyze (methodology only, no copy)
     ▼
Sandbox Development (sandbox/para-skill-dev/)
     │
     │  cp (when ready to test)
     ▼
Live Workspace (.agents/workflows/, .agents/skills/)
     │
     │  Dogfood → fix bugs → iterate
     ▼
Ship to Template Repo (repo/ → para-workspace/repo/templates/)
     │
     │  ./para update (end users)
     ▼
End User Workspace (.agents/workflows/para-skill.md)
```

## Development Workflow

```
                    ┌─────────┐
                    │ Research │  Read open-source references
                    └────┬────┘  (Resources/references/)
                         │
                    ┌────▼────┐
                    │  Draft  │  Write in sandbox/
                    └────┬────┘
                         │
              ┌──────────▼──────────┐
              │   Install to Live   │  cp → .agents/workflows/
              └──────────┬──────────┘
                         │
              ┌──────────▼──────────┐
              │     Dogfood         │  Run workflow on this project
              └──────────┬──────────┘
                         │
                   ┌─────▼─────┐
            ┌──────│  Bug?     │──────┐
            │ Yes  └───────────┘  No  │
            ▼                         ▼
     Fix in sandbox/          ┌───────────────┐
     Re-copy to live          │  OSS Scan     │
     Re-dogfood               │  (grep brands)│
                              └───────┬───────┘
                                      │
                              ┌───────▼───────┐
                              │  Ship to repo/│
                              │  (EN, clean)  │
                              └───────────────┘
```

## Dependencies

| Dependency              | Type       | Purpose                              |
|:------------------------|:-----------|:-------------------------------------|
| para-workspace v1.7.5+  | Ecosystem  | Governance framework, catalog system |
| `.agents/` conventions  | Standard   | Skill/rule/workflow discovery        |
| `catalog.yml` schema    | Schema     | Governed library registration        |
| PARA project structure  | Convention | project.md, artifacts/, docs/        |

## Governance Triad

`/para-skill` forms the third pillar of the Governance Triad:

```
.agents/workflows/
├── para-rule.md       ← Pillar 1: Rule lifecycle
├── para-workflow.md   ← Pillar 2: Workflow lifecycle
└── para-skill.md      ← Pillar 3: Skill lifecycle ⭐ NEW
```

All three follow identical patterns:
- Same action vocab: `list`, `add`, `install`, `validate`, `standardize`
- Same catalog governance: `catalog.yml` registration
- Same index system: `rules.md` / `skills.md` trigger tables
- Same context routing: workspace-level vs project-level

---

_Last updated: 2026-04-06_
