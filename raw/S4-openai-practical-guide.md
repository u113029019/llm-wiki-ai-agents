# S4 OpenAI — A practical guide to building agents
- URL：https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf
- 頁面：https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/
- 發布日：搜尋到的二手摘要（DEV Community）寫 2025-04-17；官方頁面片段未顯示日期 → **日期為二手資訊，待確認**
- 擷取方式：WebSearch 片段（官方 PDF 目錄與部分內文、官方網頁、developers.openai.com 學習頁）（2026-11-22）；**未讀全文**
- 來源類型：官方指南（第一手）

## 重點筆記
- 對象：首次建構 agent 的產品與工程團隊。
- 定義（官方學習頁）：agent 是具有 instructions（該做什麼）、guardrails（不該做什麼）、並能使用 tools（能做什麼）以代使用者採取行動的 AI 系統。
- PDF 轉述：agent 擁有各種工具與外部系統互動（收集脈絡與執行動作），依 workflow 當前狀態動態選工具，且始終在明確護欄內運作。
- 三大基礎：Model（推理與決策的 LLM）、Tools（外部函式或 API）、Instructions（明確指引與護欄）。
- 選模型（PDF 片段）：先用最強模型達成準確度目標，再盡量以較小模型取代以優化成本與延遲。
- 工具數量增加時，考慮拆成多個 agent；agent 本身也可當工具（Manager pattern，管理者 agent 透過工具呼叫協調專才 agent）——此點部分來自二手摘要，PDF 片段亦有出現「Agents themselves can serve as tools」。
- 指令設計：清晰指令減少歧義；把密集資料拆成較小較清楚的步驟。
- 護欄：分層防禦，如資料隱私、品牌/聲譽風險、相關性等（二手摘要）；護欄本身可由另一個 agent 實作（二手摘要）。
- 建議：先從單一 agent 開始，再演進到多 agent（二手摘要）。
