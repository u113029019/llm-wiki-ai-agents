# S5 Model Context Protocol（MCP）介紹 — 二手整理
- 主要來源：IBM Think「What is Model Context Protocol (MCP)?」https://www.ibm.com/think/topics/model-context-protocol
- 輔助：Microsoft Tech Community 文章、Hugging Face 社群文章（2025-03-18）、Grafana 文件（皆為二手）
- 擷取方式：WebSearch 片段（2026-11-22）；**未取得 Anthropic 官方 MCP 公告全文**
- 來源類型：二手整理，**需謹慎**；S1 內有一句提及 MCP（第一手但只一句）

## 重點筆記
- MCP 是連接 AI 應用/agent 與外部工具、資料庫、API、資料來源的「開放標準」，由 Anthropic 於 2024 年提出（IBM；另一篇二手稱 2024 年 11 月 → 月份未由第一手來源核對）。
- 架構：host 內有 client，client 與 server 通訊；server 對外公開資料與工具。
- 工具附有描述參數與型別的 JSON schema（Microsoft）。
- 通訊使用 JSON-RPC 2.0（Hugging Face 社群文章）。
- 常見比喻：AI 的「USB-C」（Hugging Face 社群文章，比喻非官方定義）。
- 是否由 LLM 決定呼叫哪個工具：IBM 說明為 LLM 依使用者請求脈絡決定。
- 已知取捨：一次載入所有工具定義會佔用大量 context（Microsoft）。
- 安全：有二手頁面提到存在安全漏洞議題，細節未核對 → 不寫入概念頁。
