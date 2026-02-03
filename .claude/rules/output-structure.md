---
name: Output Structure
description: 規範所有產出團隊結構的目錄配置和命名規則
---

# Output Structure（產出資料夾結構規範）

## 適用範圍

- 適用於：`generation-lead`, `agent-writer`, `skill-writer`, `rule-writer`

## 規則內容

### 目錄結構

所有產出的團隊結構必須遵循以下目錄配置：

```
teams/{team-name}/
├── agents/
│   ├── {coordinator}.md          ← 調度者，位於 agents/ 根目錄
│   ├── {group-a}/                ← 按職能或流程分組
│   │   ├── {agent-1}.md
│   │   └── {agent-2}.md
│   └── {group-b}/
│       └── {agent-3}.md
├── skills/
│   ├── {skill-1}/                ← 每個 skill 一個資料夾
│   │   └── SKILL.md              ← 固定檔名（大寫）
│   ├── {skill-2}/
│   │   └── SKILL.md
│   └── {skill-3}/
│       └── SKILL.md
└── rules/
    ├── {rule-1}.md
    └── {rule-2}.md
```

### 命名規範

- 團隊名稱：kebab-case，反映團隊用途（如 `english-teaching-content`）
- 資料夾名稱：kebab-case
- 檔案名稱：kebab-case，以 `.md` 結尾
- 禁止使用空格、底線、大寫字母

### 位置規範

- 調度者 .md 必須位於 `agents/` 根目錄，不可放入子資料夾
- 非調度者 agent 必須位於 `agents/` 的子資料夾中
- 每個 skill 必須有獨立資料夾，資料夾內放置 `SKILL.md`（大寫）
- 所有 rules 位於 `rules/` 根目錄，rules 不設子資料夾

## 違反判定

- 調度者 .md 出現在子資料夾中 → 違反
- 非調度者 agent 直接放在 `agents/` 根目錄（與調度者同級）→ 違反
- skill 直接以 `.md` 檔案存在而非 `{skill-name}/SKILL.md` 格式 → 違反
- 檔案或資料夾名稱不符合 kebab-case → 違反

## 例外情況

- 如果團隊只有 1 個分組（例如所有 agent 都屬於同一個專業），仍然必須建立至少一個子資料夾，不可將所有 agent 直接放在 `agents/` 根目錄
