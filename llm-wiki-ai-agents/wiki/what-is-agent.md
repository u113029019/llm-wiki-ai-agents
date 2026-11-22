---
title: 什麼是 AI Agent
sources: [S1, S3, S4]
---
# 什麼是 AI Agent

- Anthropic 的用法：把「由 LLM 與工具構成的系統」統稱為 agentic systems，再分成 workflow 與 agent 兩種 [S1]。其中 agent 是「LLM 自己動態決定流程與工具使用、掌控任務如何完成」的系統 [S1]。
- OpenAI 的簡短定義：agent 是擁有 instructions（該做什麼）、guardrails（不該做什麼）與 tools（能做什麼），能代使用者採取行動的 AI 系統 [S4]。
- Lilian Weng 的描述：以 LLM 當「大腦」，再搭配規劃、記憶、工具使用三類元件 [S3]。
- 實作上常常很單純：agent 通常只是「LLM 依環境回饋在迴圈裡使用工具」 [S1]。
- 白話整理（推論）：agent ≠ 聊天機器人；差別在於它能「採取行動並根據結果調整下一步」。

## 爭議/注意
- 「agent」一詞沒有單一定義；有人指完全自主的系統，有人指照預定流程走的實作 [S1]。簡報需先講清楚本簡報採用哪種定義。

相關：[[workflow-vs-agent]]、[[agent-components]]、[[agent-loop]]
