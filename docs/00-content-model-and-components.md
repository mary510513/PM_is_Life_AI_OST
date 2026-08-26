# 階段 0：內容模型、共用元件與設計規則

> 本文件是 Astro／MDX 建置前的資料與介面契約。  
> 正文來源：`../handbook_content_revision_spec-9.md`；prototype 僅作為視覺與互動參考。

## 章節 frontmatter

每個 MDX 章節至少使用以下欄位：

```yaml
title: "建立 PRD 初稿"
description: "把產品機會整理為可檢查、可迭代的 PRD 初稿。"
part: 2
partTitle: "從需求形成 PRD"
chapter: "2.2"
slug: "2-2"
order: 5
readingTime: "8 分鐘"
previous: "2-1"
next: "2-3"
methods: ["User Flow", "Impact Mapping", "MoSCoW", "RICE Scoring", "One-Pager PRD"]
```

- `description`、`readingTime` 在內容遷移時校定；不得從 prototype 的「Prototype demo」說明沿用。
- `previous`／`next` 以章節 slug 表示。4.4 的 `next` 對應 Part 4 結語，可在資料層以 `conclusion` 識別。
- Part 4 為索引／導覽結構，`methods` 可為空陣列或填入該頁工具名稱。

## MDX 正文區塊

| 欄位／區塊 | 用途 | 適用章節 |
| --- | --- | --- |
| `ChapterHeader` | Part、章號、標題、摘要、閱讀資訊與前節差異 | 全章 |
| `WhyHowWhat` | WHY、HOW、WHAT 區段容器 | 1.1–2.3；3.1–3.2 採變體 |
| `MethodCard` | 方法名、單句說明、圖解、外送情境例子 | 平行方法型章節 |
| `DecisionFlow` | 線性問題流程與完整度光譜 | 3.1 |
| `ComparisonTable` | 工具／完整度或其他欄位的橫向比較 | 3.2、部分方法圖解 |
| `StageBlock` | 有先後關係的多階段方法群組 | 2.3 |
| `PromptBlock` | 預設收合、可鍵盤操作、可複製的提示詞 | 有提示詞的章節 |
| `OutputBox` | 本節建議產出 | 全章（依規格書） |
| `ResourceList` | 外部 AI Skill 或延伸連結 | 依規格書出現處 |
| `ChapterNavigation` | 上一章、回總覽、下一章 | 全章 |
| `Sidebar` | Part 導覽與目前章節 | 手冊內容頁 |

## 內容結構規則

- 1.1、1.2、1.3、2.1、2.2：WHY → 平行方法卡 → 提示詞 → 資源 → 建議產出。
- 2.3：WHY → 三階段 HOW → 四段提示詞 → 資源 → 建議產出。
- 3.1：WHY → 三個判斷問題 → 五層完整度光譜 → 一段提示詞 → 建議產出。
- 3.2：WHY → 五層級工具對照表 → 萬用提示詞 → 建議產出；延伸資源移至 `/resources/`。
- 3.3：收集回饋方法 → 回饋診斷框架 → 綜合／診斷提示詞 → 建議產出；重點是診斷，不只收集。
- 4.1–4.4：流程回顧、使用方式、卡點對照與選修延伸；不強套 WHY／HOW／WHAT。
- 相同方法只在一個章節的「方法」位置說明一次；方法工具庫只提供索引與回連，不重複正文。

## 共用視覺 token

prototype 的共同基線為深色介面。正式版採用這組統一 token，並將 3.2 的淺色 prototype 視為內容版型參考，不保留為另一套主題。

```css
:root {
  --color-bg: #0f1115;
  --color-surface: #171a21;
  --color-surface-raised: #1e222b;
  --color-text: #e5e7eb;
  --color-muted: #9ca3af;
  --color-border: #2a2f3a;
  --color-accent: #7dd3fc;
  --color-accent-secondary: #a78bfa;
  --color-success: #34d399;
  --color-warning: #fbbf24;
  --color-danger: #fb7185;
  --radius-card: 14px;
  --font-sans: -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang TC", "Noto Sans TC", "Microsoft JhengHei", sans-serif;
  --font-mono: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
}
```

### 版型與互動規則

- 正文採單欄閱讀，方法卡於桌面可排網格；小螢幕一律單欄，表格須可水平捲動且標示欄位。
- 卡片使用 surface、1px border、14px 圓角；標籤、流程節點與提示詞區塊延續高對比 accent。
- 提示詞正文用 `--font-mono`、保留換行；按鈕需具明確名稱、焦點樣式與複製成功回饋。
- 摺疊內容採原生可存取語意（例如 `details`／`summary`）或等效的按鈕與 `aria-expanded`；不可只靠滑鼠事件。
- 外送場景範例保留為方法圖解的統一示例，除非規格書已指定其他情境。

