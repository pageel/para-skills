# Skill Development Guide

> **Audience:** Agent Developers, System Architects
> **Target Version:** `para-skill v0.2.0`

This document provides a detailed guide on creating, standardizing, and testing AI skills for the PARA Workspace using the `/para-skill` workflow.

## 1. Skill Development Lifecycle

A high-quality skill is not written arbitrarily. It should be shaped automatically through a DNA Interview or generated from templates, developed iteratively, and evaluated independently before release.

Standard cycle:
1. Scaffold structure using `/para-skill add`
2. Complete the content and run the compliance check via `/para-skill validate`
3. Assess safety using `/para-skill test` (Quick or Sandbox Eval)
4. Fix issues based on the report and formally release.

## 2. Creating a New Skill

```bash
/para-skill add [skill-name] --template [project|tool]
```

- **`project-profile`**: Ideal for defining a project's DNA (coding standards, naming conventions, architecture rules).
- **`tool-skill`**: Ideal for defining actionable utility skills (e.g., generating reports, cache cleanup, security scanning).

The agent will either conduct an interactive interview or scan the current system context to automatically extract rules, generating a draft `SKILL.md`. By default, the skill is created at `.agents/skills/[skill-name]/SKILL.md`.

## 3. Dual-Eval System

As of `v0.2.0`, `/para-skill test` provides two modes targeting different stages of skill development:

### A. Quick Eval (Conversational Simulation)
> Ideal for the Drafting phase. Evaluates the *theory* directly in the current chat.

You provide a few test prompts, and the System simulates how an Agent would respond if it loaded the `SKILL.md`. The limitation is that it doesn't execute real I/O operations, making it useful purely for Logic and Vibe checking.

### B. Sandbox Eval (Live Containment Eval)
> Mandatory before Release. 100% objective evaluation via Override Mechanism.

Sandbox Mode acts as an impartial "Judge", countering the bias of having the same agent draft and test a skill.

**Execution Steps:**
1. Select Mode B when calling `/para-skill test`.
2. The agent creates an isolated containment boundary at `sandbox/evals/...`.
3. Open a completely new chat session (e.g., Open Agent Manager), acting as a fresh AI, and load the target `SKILL.md`.
4. Prompt the new AI to execute a task using the `"Test Mode:"` flag.
5. The new AI will attempt the task but its I/O must abide by the override rules, restricting all outputs strictly into the Sandbox box, generating a `test-report.md`.
6. Return to the original chat and type `conclude test`. The reviewing agent will read the generated report and export an objective evaluation.

## 4. Quality Checklist (27 Points)

The evaluation system scrutinizes 27 criteria of your `SKILL.md`, strictly enforcing:
- **Pushy Language:** The description must mandate usage strongly.
- **Progressive Disclosure:** Do not stuff thousands of lines into one file. Instead, use the `/references` directory and allow the Agent to deep-dive dynamically.
- **Test Readiness:** Every template includes Sandbox Override code to instruct the Agent Manager on the containment rules automatically.

Warnings triggered by these 27 points can be automatically corrected using:
```bash
/para-skill standardize [skill-name]
```
