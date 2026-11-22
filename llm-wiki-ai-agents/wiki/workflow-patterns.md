---
title: 五種常見 Workflow 模式
sources: [S1]
---
# 五種 Workflow 模式（Anthropic）

1. **Prompt chaining**：把任務切成固定步驟，每次 LLM 呼叫處理前一步的輸出，中間可加程式檢查（gate）；用延遲換較高準確度 [S1]。例：先寫大綱、檢查大綱是否合格、再寫全文 [S1]。
2. **Routing**：先分類輸入，再導向專門的後續流程 [S1]。例：客服分流成一般問題、退款、技術支援；或把簡單問題給小模型、困難問題給大模型 [S1]。
3. **Parallelization**：sectioning（獨立子任務並行）與 voting（同一任務跑多次取多元結果） [S1]。例：一個模型回答、另一個模型審查內容是否適當 [S1]。
4. **Orchestrator-workers**：中央 LLM 動態拆解任務、分派給 worker、整合結果；子任務不是預先固定的 [S1]。例：一次改多個檔案的 coding 產品 [S1]。
5. **Evaluator-optimizer**：一個 LLM 產生、另一個評估並回饋，形成迴圈；在有明確評估標準、且迭代能帶來可量測價值時有效 [S1]。

## 與「自主 agent」的關係
- 以上前四種流程骨架由程式或編排者決定；agent 則更進一步由 LLM 自己掌控迴圈 [S1]。（推論：orchestrator-workers 與 evaluator-optimizer 介於兩者之間。）
- 這些模式不是規定，可組合與調整；關鍵是量測效果並迭代，只在確實改善成果時才增加複雜度 [S1]。

相關：[[workflow-vs-agent]]、[[when-to-use-agents]]
