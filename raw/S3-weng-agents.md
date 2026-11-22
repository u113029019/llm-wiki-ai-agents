# S3 Lilian Weng — LLM Powered Autonomous Agents
- URL：https://lilianweng.github.io/posts/2023-06-23-agent/（日期 2023-06-23）
- 擷取方式：WebSearch 片段，含 gwern 鏡像頁的部分全文（2026-11-22）；**未逐段讀完全文**
- 來源類型：技術綜述部落格（作者為 OpenAI 研究者，見轉載頁標註；屬個人技術文章）

## 重點筆記
- 系統總覽：LLM 作為 agent 的「大腦」，搭配三類元件——Planning、Memory、Tool use。
- Planning：
  - 子目標拆解（subgoal and decomposition）。
  - 反思與改進（reflection and refinement）：自我批評、從錯誤學習。
  - 任務拆解方式：CoT（「一步步想」）、Tree of Thoughts（每步探索多種想法、形成樹）、LLM+P（交給外部經典規劃器，使用 PDDL）。
  - ReAct 範本：Thought → Action → Observation，重複多次。
  - Reflexion：以（失敗軌跡, 理想反思）兩例教模型反思，反思寫入工作記憶，最多三條。
- Memory：短期記憶 ≈ in-context learning；長期記憶 = 外部向量庫 + 快速檢索。
- Tool use：呼叫外部 API 補足模型權重缺的資訊（最新資訊、執行程式、專有資料）。
- 提到 MRKL：LLM 當路由器，把請求轉給專家模組（來自 velog 二手整理轉述，原文段落未直接核對 → 暫不寫入概念頁）。
- 注意：文章寫於 2023 年，後續工具與框架已大幅演進（推論）。
