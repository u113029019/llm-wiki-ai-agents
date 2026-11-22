# S1 Anthropic — Building effective agents
- URL：https://www.anthropic.com/research/building-effective-agents（亦見 /engineering/ 路徑）
- 作者：Erik Schluntz、Barry Zhang（Anthropic）
- 頁面標示發布日：2024-12-19；頁面頂端另有註記：2024 年 12 月之後工具生態已有變化，最新做法請看 Managed Agents 文件。
- 擷取方式：WebFetch 全文（2026-11-22）
- 來源類型：第一手

## 重點筆記（本人整理，非原文）
- 定義：agentic systems 分兩類——workflow（LLM 與工具由「預先寫好的程式路徑」編排）與 agent（LLM 自己動態決定流程與工具使用）。
- 建議：先找最簡單的解法，必要時才加複雜度；很多情況下「單次 LLM 呼叫 + 檢索 + 範例」就夠。Agentic 系統通常用延遲與成本換取更好表現。
- 框架：可以幫忙起步，但多一層抽象會遮住 prompt 與回應、增加除錯難度；建議先直接用 API。
- 基本積木：augmented LLM = LLM + 檢索 + 工具 + 記憶。文中提到 MCP 是整合第三方工具的一種方式。
- 五種 workflow：
  1. Prompt chaining：把任務切成固定步驟，前一步輸出餵給下一步，中間可加程式檢查（gate）。
  2. Routing：先分類輸入，再導向專門的後續流程。
  3. Parallelization：sectioning（獨立子任務並行）與 voting（同任務多次執行取共識）。
  4. Orchestrator-workers：中央 LLM 動態拆解任務、交給 worker、再整合；子任務不是預先固定的。
  5. Evaluator-optimizer：一個 LLM 產生、另一個評估回饋，形成迴圈；適合有明確評估標準時。
- Agent：從人類指令或互動討論開始，之後自己規劃與執行；每一步要從環境取得 ground truth（工具結果、程式執行結果）；可在檢查點或遇阻時暫停問人；通常設停止條件（例如最大迭代次數）。實作上常只是「LLM 在迴圈中依環境回饋使用工具」。
- 風險：成本較高、錯誤可能累積；建議在沙箱中大量測試並加護欄。
- 三原則：簡單（simplicity）、透明（顯示規劃步驟）、精心設計 ACI（agent-computer interface，即工具文件與測試）。
- 工具設計：工具定義要花與 prompt 同等心力；建議站在模型角度檢視、用大量範例測試、poka-yoke（讓錯誤更難發生）。SWE-bench 案例：花在最佳化工具的時間比最佳化 prompt 更多；改成一律要求絕對路徑後模型用得很穩。
- 應用：客服（對話 + 工具 + 可衡量解決率）與 coding agent（可用測試驗證，但仍需人審）。
- 範例中的模型名稱（Claude Haiku 4.5 / Sonnet 4.5）是頁面後來更新過的，與 2024 年原始發布時不同——**日期與版本引用時要小心**。
