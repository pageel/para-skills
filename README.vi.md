<div align="center">
  <img src="https://raw.githubusercontent.com/pageel/para-workspace/main/docs/assets/logo.svg" alt="PARA Workspace Logo" width="120" />
  <h1>para-skills 🧠</h1>
  <p><b>Bộ kỹ năng AI Agent và workflow <code>/para-skill</code> cho PARA Workspace.</b></p>
  
  <p>
    <a href="README.md"><b>🇺🇸 English</b></a> •
    <a href="README.vi.md"><b>🇻🇳 Tiếng Việt</b></a> •
    <a href="README.zh-CN.md"><b>🇨🇳 中文</b></a>
  </p>

  <p>
    <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT"></a>
  </p>
</div>

<br/>
## Tổng quan

**para-skills** cung cấp:

1. **Workflow `/para-skill`** — Trình Co-Author hướng dẫn tạo, kiểm tra và test các skill cho AI Agent
2. **Skill templates** — Template sẵn sàng cho các loại skill phổ biến (project-profile, tool/utility)
3. **Quality checklist** — Bộ 27 tiêu chí đánh giá chất lượng skill (đã bao gồm Sandbox Test)

## Bắt đầu nhanh

```bash
# Cài workflow vào PARA Workspace
cp skills/para-skill/para-skill.md .agents/workflows/para-skill.md

# Tạo skill đầu tiên
/para-skill add project-profile --template project

# Kiểm tra chất lượng
/para-skill validate project-profile
```

## Tài liệu

Xem [README tiếng Anh](README.md) để biết đầy đủ chi tiết.

## Giấy phép

[MIT License](LICENSE)

---

Xây dựng cho hệ sinh thái [PARA Workspace](https://github.com/pageel/para-workspace).
