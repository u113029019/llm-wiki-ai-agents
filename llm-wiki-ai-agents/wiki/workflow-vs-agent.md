---
title: Workflow 與 Agent 的差異
sources: [S1, S7]
---
# Workflow vs Agent

| | Workflow | Agent |
|---|---|---|
| 誰決定流程 | 預先寫好的程式路徑編排 LLM 與工具 [S1] | LLM 動態決定流程與工具使用 [S1] |
| 擅長 | 定義明確的任務，可預測、一致 [S1] | 需要彈性與模型決策、難以預先固定步驟的問題 [S1] |
| 代價 | 較不彈性（推論） | 成本較高、錯誤可能累積 [S1] |

- Anthropic 建議：先找最簡單的解法，必要時才增加複雜度；許多應用只要「單次 LLM 呼叫 + 檢索 + 範例」就夠 [S1]。
- Agentic 系統常用延遲與成本換取更好的任務表現 [S1]。
- 一個選擇準則：流程能事先寫死 → workflow；步驟數無法預測、不能硬編碼路徑 → agent [S1]。

## 爭議/注意
- AI Engineer World's Fair 2025 的一場演講頁面稱 Anthropic 文章的語氣偏「反 workflow」，並把問題改寫成：每個操作該用裁量還是較受限的流程 [S7]（講者觀點，僅讀到頁面摘要）。→ 簡報採「依任務選擇」而非「agent 一定較好」。

相關：[[what-is-agent]]、[[workflow-patterns]]、[[when-to-use-agents]]
