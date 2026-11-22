---
title: Agent 運作迴圈（含 ReAct）
sources: [S1, S2, S3]
---
# Agent 運作迴圈

## 一般流程（Anthropic）
1. 從人類的指令或互動討論開始；任務明確後，agent 自行規劃與執行，必要時回頭問人 [S1]。
2. 每一步都要從環境取得「ground truth」（如工具結果、程式執行結果）來評估進度 [S1]。
3. 可在檢查點或遇到阻礙時暫停等人回饋 [S1]。
4. 任務完成即結束，也常設停止條件（如最大迭代次數）維持控制 [S1]。

## ReAct：讓「想」與「做」交錯
- ReAct 讓 LLM 以交錯方式產生推理軌跡與任務行動 [S2]：推理幫助更新計畫與處理例外，行動讓它向外部（如維基百科 API）取得資訊 [S2]。
- 常見提示格式：Thought → Action → Observation，重複多次 [S3]。
- 論文結果：HotpotQA 與 Fever 上，透過簡單的 Wikipedia API 互動，減緩了 CoT 中的幻覺與錯誤傳遞 [S2]；ALFWorld 與 WebShop 上成功率分別比模仿學習與強化學習方法高出絕對 34% 與 10% [S2]。
- 實驗以凍結的 PaLM-540B 加上少量範例進行 [S2]。
- 反思：Reflexion 把失敗經驗轉成反思寫入工作記憶供後續使用 [S3]。

## 爭議/注意
- ReAct 的數據是 2022–2023 年模型與基準上的結果，不能直接外推到現今模型（推論）。簡報引用時需標明年代與設定。

相關：[[agent-components]]、[[guardrails-and-risks]]
