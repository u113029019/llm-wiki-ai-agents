# S2 Yao et al. — ReAct: Synergizing Reasoning and Acting in Language Models
- URL：https://arxiv.org/abs/2210.03629（arXiv v1 2022-10-06；v3 2023-03-10 為 ICLR 2023 camera-ready）
- 輔助：Google Research blog（2022-11-08）說明與圖例
- 擷取方式：WebSearch 摘要與論文片段（2026-11-22）；**未讀全文，只讀到摘要、貢獻段與第 2 節開頭**
- 來源類型：論文（第一手）

## 重點筆記
- 問題：過去「推理（如 chain-of-thought）」與「行動（如產生行動計畫）」被分開研究。
- 方法：讓 LLM 以交錯方式產生「推理軌跡」與「任務行動」；推理幫助模型歸納、追蹤、更新行動計畫與處理例外，行動讓模型能接觸外部來源（如知識庫、環境）取得更多資訊。
- 形式：把 agent 的行動空間擴充為「原本行動 ∪ 語言空間」；語言形式的 thought 不影響環境，只更新內部脈絡。
- 實驗設定：以凍結的 PaLM-540B 搭配少量 in-context 範例（1–6 個）。
- 結果（摘要原文所載）：HotpotQA、Fever 上，透過簡單 Wikipedia API 互動，減緩 CoT 中的幻覺與錯誤傳遞；ALFWorld、WebShop 上，成功率分別比模仿學習與強化學習方法高出絕對 34% 與 10%。
- 附帶發現（Google blog）：最佳結果來自 ReAct 與 CoT 結合；允許人類檢視者編輯推理軌跡以修正行為（ALFWorld 示例）。
- 限制：論文自述在 prompting 設定下對推理/行動行為的支援有限，並做了初步 fine-tuning 實驗。
