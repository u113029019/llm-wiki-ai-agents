---
title: 工具、ACI 與 MCP
sources: [S1, S3, S4, S5]
---
# 工具、ACI 與 MCP

## 為什麼工具重要
- Agent 靠工具與外部服務互動；因此工具集與文件的設計很關鍵 [S1]。
- Weng：工具讓 agent 取得模型權重中缺的資訊，如最新資訊與程式執行能力 [S3]。
- OpenAI：工具是 agent 可使用的外部函式或 API [S4]；工具太多時可考慮拆成多個 agent，agent 本身也可當工具 [S4]。

## ACI（agent-computer interface）
- 經驗法則：人機介面花多少心力，agent-電腦介面就該花同等心力 [S1]。
- 做法：站在模型角度檢視工具描述是否明顯易用；工具定義宜含範例用法、邊界情況、輸入格式與和其他工具的區隔；用大量範例測試並迭代；poka-yoke（讓錯誤更難發生） [S1]。
- 案例：SWE-bench agent 花在最佳化工具的時間比最佳化 prompt 還多；把檔案路徑改成一律要求絕對路徑後，模型使用得很穩 [S1]。

## MCP（Model Context Protocol）
- Anthropic 在 agent 文章中把 MCP 當成整合第三方工具生態的一種方式 [S1]。
- 二手說明：MCP 是連接 AI 應用與外部工具、資料來源的開放標準，由 Anthropic 於 2024 年提出 [S5]；工具附 JSON schema 描述參數 [S5]；由 LLM 依脈絡決定呼叫哪個工具 [S5]。
- 取捨：若啟動時載入所有工具定義，會消耗大量 context [S5]。

## 爭議/注意
- MCP 細節（協定格式、安全議題）主要來自二手來源 [S5]，簡報中只講「是什麼、為什麼」，不講細節。
- S1 頁首註記指出 2024 年 12 月後工具生態已有變化 [S1]，簡報不應把 S1 的工具清單當作現況。

相關：[[agent-components]]、[[guardrails-and-risks]]
