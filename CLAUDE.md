# Wiki Schema：AI Agents 入門 LLM Wiki

## 0. 討論紀錄（先討論、後生成）
生成任何頁面之前，先決定下列事項並固定下來：

| 問題 | 決議 |
|---|---|
| 主題 | AI Agents（以 LLM 為核心的 agent） |
| 讀者 | 完全不熟悉 agent 的人（大學生程度） |
| 最終用途 | 產出「AI Agents 是什麼？」教學 HTML 簡報 |
| 範圍內 | 定義、與 workflow 的差異、組成元件、運作迴圈、常見模式、工具/MCP、護欄、何時該用 |
| 範圍外 | 各家框架的 API 細節、模型排行、價格 |
| 來源門檻 | 優先官方/論文等第一手資料；二手整理只能當輔助，且要標註 |
| 時效 | 來源日期必須記錄；日期不一致要記錄在 log.md |

## 1. 目錄結構
```
raw/        原始來源筆記（來源網址、擷取日期、重點；只增不改）
wiki/       LLM 整理後的知識頁（概念頁 + 來源頁）
wiki/index.md   目錄與頁面狀態
wiki/log.md     ingest / lint / query 的時間序紀錄
```

## 2. 頁面規則
1. 每個概念頁 frontmatter 必須有 `sources: [S1, S2, ...]`。
2. 每一個事實性陳述後面都要標 `[S#]`。沒有來源的句子必須標 `（推論）`。
3. 數字（百分比、日期、版本）一律回到 raw/ 的來源筆記核對後才能寫入。
4. 來源互相矛盾時，不擅自擇一，寫在頁面的「爭議/注意」段並記錄於 log.md。
5. 頁面之間用 `[[頁名]]` 互相連結；不可有孤立頁面。

## 3. 來源編號
| 編號 | 來源 | 類型 |
|---|---|---|
| S1 | Anthropic, *Building effective agents* | 官方工程文章（第一手） |
| S2 | Yao et al., *ReAct* (ICLR 2023, arXiv:2210.03629) | 論文（第一手） |
| S3 | Lilian Weng, *LLM Powered Autonomous Agents* (2023-06-23) | 技術綜述部落格 |
| S4 | OpenAI, *A practical guide to building agents* | 官方指南（第一手） |
| S5 | Model Context Protocol 介紹（IBM Think 等） | 二手整理，需謹慎 |
| S6 | de Lamo Castrillo et al., *Fundamentals of Building Autonomous LLM Agents* (arXiv:2510.09244) | 綜述論文（僅讀到摘要與緒論） |

| S7 | Sam Bhagwat, *Agents vs Workflows: Why Not Both?* (AI Engineer 2025 頁面摘要) | 演講摘要，講者觀點（lint 後補登） |

## 4. 操作
- **ingest**：讀來源 → 寫 raw 筆記 → 更新/新增 wiki 頁 → 更新 index → 寫 log
- **lint**：檢查來源標註、矛盾、孤立頁面、缺漏概念
- **query**：只從 wiki/ 取材，不直接憑記憶；wiki 沒有的內容要先回頭 ingest
