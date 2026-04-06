<div align="center">
  <img src="https://raw.githubusercontent.com/pageel/para-workspace/main/docs/assets/logo.svg" alt="PARA Workspace Logo" width="120" />
  <h1>para-skills 🧠</h1>
  <p><b>适用于 PARA Workspace 的精选 AI Agent 技能库与 <code>/para-skill</code> 工作流。</b></p>
  
  <p>
    <a href="../../README.md"><b>🇺🇸 English</b></a> •
    <a href="vi.md"><b>🇻🇳 Tiếng Việt</b></a> •
    <a href="zh-CN.md"><b>🇨🇳 中文</b></a>
  </p>

  <p>
    <a href="../../LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT"></a>
  </p>
</div>

<br/>

## 概述

**para-skills** 提供：

1. **`/para-skill` 工作流** — 一个帮助您创建、验证和测试 AI Agent 技能的联合引擎
2. **Skill 模板** — 即插即用的项目类型模板 (project-profile, tool/utility)
3. **质量检查清单** — 包含 沙盒测试 (Sandbox Test) 在内的 27 项质量审查标准

## 快速入门

```bash
# 将工作流安装到您的 PARA Workspace
cp skills/para-skill/para-skill.md .agents/workflows/para-skill.md

# 创建您的第一个技能
/para-skill add project-profile --template project

# 质量检查
/para-skill validate project-profile
```

## 文档

请参阅 [英文 README](../../README.md) 获取完整详情。

## 许可证

[MIT License](../../LICENSE)

---

为 [PARA Workspace](https://github.com/pageel/para-workspace) 生态系统构建。
