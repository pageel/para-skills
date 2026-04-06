# Contributing to para-skills

Thank you for your interest in contributing! 🎉

## How to Contribute

### Reporting Issues

- Open an issue on [GitHub](https://github.com/pageel/para-skills/issues)
- Include clear steps to reproduce the problem
- Mention which PARA Workspace version you're using

### Submitting Skills

We welcome new skill contributions! To submit a skill:

1. **Fork** this repository
2. Create your skill in `skills/[your-skill-name]/`
3. Ensure your skill passes validation:
   ```bash
   /para-skill validate [your-skill-name]
   ```
4. Include a `SKILL.md` with proper YAML frontmatter (`name`, `description`, `version`)
5. Submit a **Pull Request** with a clear description

### Quality Standards

All contributed skills must pass the [Skill Quality Checklist](skills/para-skill/references/skill-quality-checklist.md):

- ✅ YAML frontmatter with `name`, `description`, `version`
- ✅ Description includes clear trigger context (>= 20 words)
- ✅ Content under 500 lines (use `references/` for overflow)
- ✅ At least 1 concrete example (Input → Output)
- ✅ No hardcoded absolute filesystem paths

### Code Style

- **Markdown files:** Use standard Markdown with GitHub Flavored extensions
- **YAML:** 2-space indentation
- **File naming:** `kebab-case` for all files and directories

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE).
