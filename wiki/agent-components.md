---
title: Agent 的組成元件
sources: [S1, S3, S4, S6]
---
# Agent 的組成元件

不同來源切法不同，但重疊很多：

- **Anthropic：augmented LLM** = LLM + 檢索 + 工具 + 記憶；模型能自己產生搜尋查詢、選工具、決定要保留什麼資訊 [S1]。
- **Weng：三元件** [S3]
  - Planning：子目標拆解、反思與改進 [S3]
  - Memory：短期記憶 ≈ in-context learning；長期記憶 = 外部向量庫加快速檢索 [S3]
  - Tool use：呼叫外部 API 補足模型權重裡缺的資訊（最新資訊、執行程式、專有資料） [S3]
- **OpenAI：三基礎** Model、Tools、Instructions [S4]
- 一篇綜述列出的面向：Perception、Reasoning and Planning、Memory、Action、Multi-agent [S6]（僅讀到摘要/緒論）

## 對照表（推論）
| 角色 | Anthropic | Weng | OpenAI |
|---|---|---|---|
| 大腦 | LLM | LLM | Model |
| 做事 | 工具 | Tool use | Tools |
| 記得 | 記憶 | Memory | （片段未明確列出） |
| 想事情 | （隱含於 agent 規劃） | Planning | Instructions 引導 |

相關：[[agent-loop]]、[[tools-and-mcp]]
