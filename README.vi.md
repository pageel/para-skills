# 🧠 para-skills

> Bộ kỹ năng AI Agent và workflow `/para-skill` cho [PARA Workspace](https://github.com/pageel/para-workspace).

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
