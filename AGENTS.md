# AGENTS.md - 專案協同與擴充開發指南

本專案為「AI Workshop Hub」，旨在以輕量、模組化且結構清晰的方式，展示本學期學習與實作的各項生成式 AI 工具、Agent 架構及互動成果。

---

## 1. 專案目的與核心原則
- **擴充性優先**：任何新頁面或工具，必須遵照一致的設計語言與資料結構，降低重複開發成本。
- **純靜態架構**：不使用重型框架，確保所有頁面可直接在 GitHub Pages 上靜態伺服。
- **資料驅動**：首頁卡片清單由 `data/projects.json` 動態讀取生成，新增專案無需手動修改首頁 HTML。

---

## 2. 視覺風格與 UI 規範
所有頁面必須嚴格引用 `css/style.css`，並遵循以下設計規範：
- **配色系統（Design Tokens）**：
  - 背景色：`#0f172a`（深藍灰）
  - 卡片底色：`#1e293b`（微光半透明 Glassmorphism）
  - 主強調色：`#38bdf8`（科技藍）
  - 輔助強調色：`#a855f7`（霓虹紫）
  - 文字主色：`#f8fafc`
  - 文字次色：`#94a3b8`
  - 邊框線條：`1px solid rgba(255, 255, 255, 0.1)`
- **字體排印（Typography）**：
  - 大標題 `2rem (700)`、區塊標題 `1.25rem (600)`、內文 `1rem (400)`。
  - 行距統一為 `1.6`。
- **圓角與懸浮**：
  - 卡片與按鈕統一採用 `border-radius: 12px`。
  - 懸浮效果（Hover）：位移 `translateY(-4px)` 並加深光暈陰影。

---

## 3. 檔案放置與命名規則
- 所有一般展示子頁面，必須放置於 `pages/` 目錄下。
- 檔案命名必須全小寫 kebab-case，例如：`pages/code-reflection.html`。

---

## 4. 資料模型規範 (`data/projects.json`)
當專案有新工具/頁面加入時，必須在 `data/projects.json` 追加物件：
```json
{
  "id": "專案唯一標識（kebab-case）",
  "title": "專案中文標題",
  "category": "分類標籤",
  "summary": "1~2 句話核心介紹",
  "tags": ["標籤1", "標籤2"],
  "link": "相對路徑（如 pages/demo.html）",
  "icon": "自訂 Emoji 圖標"
}