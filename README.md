# 🧠 para-skills

> Curated AI Agent skills and the `/para-skill` workflow for [PARA Workspace](https://github.com/pageel/para-workspace).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Overview

**para-skills** provides:

1. **`/para-skill` workflow** — A Co-Author engine that guides you through creating, validating, and testing AI Agent skills
2. **Skill templates** — Ready-to-use templates for common skill types (project-profile, tool/utility)
3. **Quality checklist** — A 24-point framework for ensuring skill quality

## 🚀 Quick Start

### Install the workflow

Copy the workflow into your PARA Workspace:

```bash
# From your PARA workspace root
cp skills/para-skill/para-skill.md .agents/workflows/para-skill.md
```

### Create your first skill

```bash
# Create a project-profile skill for your project
/para-skill add project-profile --template project

# Or create a utility skill
/para-skill add my-tool --template tool
```

### Validate & test

```bash
# Check quality compliance
/para-skill validate project-profile

# Run conversational evaluation
/para-skill test project-profile
```

## 📦 What's Included

```
skills/
├── catalog.yml                    # Skill registry
└── para-skill/
    ├── para-skill.md              # The workflow (6 actions)
    └── references/
        ├── skill-quality-checklist.md   # 24-point quality framework
        └── templates/
            ├── project-profile.md  # Project DNA template
            └── tool-skill.md       # Utility/automation template
```

## 🛠 Workflow Actions

| Action        | Description                                                    |
| :------------ | :------------------------------------------------------------- |
| `list`        | Compare active skills vs. governed catalog                     |
| `add`         | Create a new skill via guided Co-Author interview              |
| `install`     | Install or update a skill from the governed catalog            |
| `validate`    | Check a skill for PARA + quality compliance (read-only)        |
| `standardize` | Upgrade an existing skill to current standards                 |
| `test`        | Run conversational eval with user-provided test prompts        |

## 📋 Skill Templates

### 🏗️ Project Profile (`--template project`)

Creates a **project DNA** skill covering:
- §1. Project Identity (type, language, build system)
- §2. Naming Conventions (plans, branches, commits)
- §3. Maintenance Patterns (version bump, dogfooding)
- §4. Quality Standards (build/test commands)
- §5. Documentation Flow (internal vs public)
- §6. Plan Review Checklist (the most powerful section — catches planning mistakes)

### 🔧 Tool Skill (`--template tool`)

Creates a **utility/automation** skill with:
- Workflow steps in imperative form
- Input/Output format specification
- Edge case handling
- Script and reference bundling

## 🔍 Quality Checklist (27 Points)

| Group | Points | What it checks |
|:------|:-------|:---------------|
| P1-P5 | PARA Structure | Frontmatter, folder, index, naming, version |
| D1-D4 | Description | Trigger context, pushy, length, specificity |
| C1-C4 | Content | Length, progressive disclosure, references, TOC |
| W1-W5 | Writing Style | Explain why, imperative, examples, scope, safety |
| B1-B3 | Resources | Scripts, references, assets organization |
| T1-T3 | Test Readiness | Test prompts, expected output, testability type |
| TM1-TM3| Test Mode      | Sandbox overrides, containment paths, report templates |

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📄 License

[MIT License](LICENSE)

---

Built for the [PARA Workspace](https://github.com/pageel/para-workspace) ecosystem.
