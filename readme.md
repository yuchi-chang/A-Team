
# A-Team

一組運行在 Claude Code 上的團隊設計師 agent 系統。透過深度對話釐清你的需求，自動產出完整的 multi-agent 團隊結構（agents / skills / rules）。

## 解決什麼問題

你知道 agent 要適度分工效果才好，但每次手動規劃角色、逐一撰寫 .md 檔案既耗時又容易遺漏。A-Team 把「團隊設計」這件事本身變成一個可對話、可自動化的流程。

## 快速開始

1. 將本資料夾內容複製到你的專案 `.claude/` 目錄下
2. 在 Claude Code 中啟動 `team-architect` agent
3. 告訴它你想建什麼團隊，例如：「我想幫一個線上英語教學公司建立教材製作團隊」
4. 跟著它的訪談走，回答問題即可
5. 完成後，產出的團隊結構會出現在 `teams/{team-name}/` 目錄下

## 系統架構

```
.claude/
├── agents/
│   ├── team-architect.md            ← 總調度者，主導全流程
│   │
│   ├── discovery/                   ← Phase 1: 需求探索
│   │   ├── requirements-analyst.md  ← 深度訪談，挖掘需求
│   │   └── role-designer.md         ← 職責拆分，定義角色
│   │
│   ├── planning/                    ← Phase 2: 技能規劃
│   │   └── skill-planner.md         ← 規劃 skills 與 rules
│   │
│   └── generation/                  ← Phase 3: 結構生成
│       ├── generation-lead.md       ← 子調度者，統籌生成
│       ├── agent-writer.md          ← 專寫 agent .md
│       ├── skill-writer.md          ← 專寫 skill .md
│       └── rule-writer.md           ← 專寫 rule .md
│
├── skills/
│   ├── shared/                      ← 多 agent 共用的能力
│   │   ├── structured-interview.md  ← 結構化訪談方法論
│   │   ├── role-decomposition.md    ← 職責拆解框架（MECE）
│   │   └── md-generation-standard.md← .md 檔案格式規範
│   │
│   └── specialized/                 ← 特定 agent 專用的能力
│       ├── team-topology-analysis.md← 團隊拓撲分析
│       ├── granularity-calibration.md← 顆粒度校準
│       └── quality-validation.md    ← 產出品質驗證
│
└── rules/
    ├── coordinator-mandate.md       ← 每個團隊必須有調度者
    ├── output-structure.md          ← 產出目錄結構規範
    ├── conversation-protocol.md     ← 對話流程規範
    └── writing-quality-standard.md  ← .md 撰寫品質規範
```

## 工作流程

```
Phase 1: Discovery          Phase 2: Planning       Phase 3: Generation
┌─────────────────────┐     ┌──────────────┐        ┌──────────────────────┐
│ requirements-analyst │     │              │        │   generation-lead    │
│   （需求訪談）        │────▶│ skill-planner│───────▶│     （子調度者）       │
│ role-designer        │     │  （技能規劃）  │        │  ┌─ agent-writer     │
│   （角色設計）        │     │              │        │  ├─ skill-writer     │
└─────────────────────┘     └──────────────┘        │  └─ rule-writer      │
         ▲                                           └──────────────────────┘
         │                                                      │
    team-architect（總調度者，貫穿全流程）──────────────────────────┘
                                                         ▼
                                                  teams/{name}/
                                                  ├── agents/
                                                  ├── skills/
                                                  └── rules/
```

## 產出範例

當你告訴 A-Team「我要建立一個英語教材製作團隊」，它會產出類似這樣的結構：

```
teams/english-teaching-content/
├── agents/
│   ├── project-coordinator.md       ← 調度者（強制存在）
│   ├── content-creation/
│   │   ├── curriculum-designer.md
│   │   ├── content-writer.md
│   │   └── illustrator.md
│   ├── quality/
│   │   ├── education-reviewer.md
│   │   └── language-editor.md
│   └── delivery/
│       ├── web-developer.md
│       └── seo-specialist.md
├── skills/
│   ├── shared/
│   │   └── ...
│   └── specialized/
│       └── ...
└── rules/
    └── ...
```

## 設計原則

**調度者強制存在** — 每個團隊必定有調度者負責任務規劃與分配，調度者不兼任執行工作。超過 7 個 agent 時自動引入子調度者。

**專注產生品質** — generation 階段的三個 writer 各自只負責一種檔案類型（agent / skill / rule），確保每個 .md 都被專心寫好。

**深度對話優先** — 不跳過需求探索。即使你已經有明確想法，A-Team 仍會透過訪談驗證假設、挖掘盲點。

**Skills 共用與專用分離** — 通用能力放 shared，專業能力放 specialized，避免重複也避免耦合。

## 自訂與擴展

A-Team 產出的是初版框架。你可以：

- 直接修改任何 .md 檔案的 prompt 內容
- 增加或移除角色
- 調整 skill 和 rule 的細節
- 將產出的 `teams/{name}/` 資料夾複製到實際專案的 `.claude/` 中使用

## License

MIT
