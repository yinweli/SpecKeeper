# SpecKeeper

**SpecKeeper** 是可供 Claude Code 與 Codex 使用的軟體設計規格管理 Skill，協助維持規格的權威性、一致性與可追溯性。

## 功能

- 管理規格的權威來源，區分定案、草稿、未決、歷史與 PoC 資料。
- 將規則維護於單一主要文件，避免重複定義。
- 發現規格衝突時提出問題，不自行替使用者定案。
- 維護跨文件術語、引用與相依關係。
- 只修改與本次需求相關的設計規格。

## 預設慣例

- 規格放在 `Design/`。
- `Design/` 可直接放文件，也可使用**最多一層分類子目錄**，例如 `Design/會員/登入.md`；不新增更深層分類。
- `Design/總覽.md` 為入口文件，只列出各規格的連結與一行用途；細節規則寫在負責的文件。
- 每份規格在 frontmatter 標示 `status`：`定案`、`草稿`、`歷史` 或 `PoC`；只有 `定案` 具權威性。
- 優先使用 Obsidian；內部文件使用 `[[Wiki Links]]`，外部網站使用一般 Markdown 連結。
- 未決事項使用 Obsidian 標籤 `#待確認`，例如 `#待確認 每日登入獎勵是否可補領？`；不自行定案。
- 專案若有明確不同規範，以專案規範為準。

## Repository 結構

```text
SpecKeeper/
├── README.md
├── CHANGELOG.md
└── skills/
    └── spec-keeper/
        └── SKILL.md
```

## 安裝

將 `skills/spec-keeper/` **整個資料夾**複製到欲使用工具的 Skill 目錄：

| 工具 | 個人 Skill 目錄 | 專案 Skill 目錄 |
| --- | --- | --- |
| Claude Code | `~/.claude/skills/` | `.claude/skills/` |
| Codex | `~/.agents/skills/` | `.agents/skills/` |

例如，安裝後應有 `~/.claude/skills/spec-keeper/SKILL.md` 或 `~/.agents/skills/spec-keeper/SKILL.md`。請依實際工具版本確認讀取路徑與重新載入方式。

## 使用情境

- 「檢查目前系統規格是否有矛盾或重複定義。」
- 「把已經定案的遊戲資源規則更新到設計文件。」
- 「整理歷史討論，標出尚未確認的需求。」

## 維護原則

- 一個 Repository 維護一個主要 Skill；無須依賴其他 Skill。
- 保持 `SKILL.md` 精簡；只有必要時才加入 `references/`。
- 先在實際專案驗證觸發、規格衝突處理、未決事項與引用更新，再發行穩定版。
- 發布公共版本前，請由 Repository 擁有人決定是否加入授權條款（`LICENSE`）。
