<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/doc-view-20.md
-->
---
page_id: doc-view-20
title: "開放整合介紹"
locale: zh-TW
sourced_from_kus:
  - dora.open-integration.introduction.overview
generated_at: "2026-06-03T22:47:18+08:00"
---

## 簡介

Data Agent 支援對接外部 AI 平台（例如：OpenClaw），並提供開放 API 對接能力，進一步實現企業的自動化分析需求。

整合外部 AI 平台可實現以下功能：
- 將 Data Agent 分析產生的圖表或報表等內容，定時推播給負責人閱覽
- 自動發佈 Agent
- 自動查詢歷史會話

## 整合外部平台

請依照介面提示，依序完成『發送安裝對話』>『發送整合對話』>『檢查整合狀態』操作後，即可完成 Data Agent 與 OpenClaw 的整合對接。

## Key 管理

您可以在『Key 管理』頁面中，勾選一個或多個可存取 OpenClaw 的介面權限，即可產生新的 OpenClaw 存取 Key。

可選的介面權限包含：
- 查詢已發佈 Agent 詳情 (openclaw:agents:detail)
- 中斷對話 (openclaw:interrupt)
- 查詢會話歷史 (openclaw:history)
- 查詢已發佈 Agent 列表 (openclaw:agents:list)
- 查詢會話列表 (openclaw:sessions:list)
- 查詢 Skill 列表 (openclaw:skills:list)
- 建立 Agent 草稿 (openclaw:agents:create)
- 發佈 Agent (openclaw:agents:publish)
- 流式對話 (openclaw:chat:sse)
- 查詢 Agent 可編輯配置 (openclaw:agents:editable)
- 保存 Agent 配置 (openclaw:agents:save)
- 查詢 LLM 配置列表 (openclaw:llm:configs:list)
- 對話 (openclaw:chat)

## 外接 MCP

在 Agent 建立過程中，外接 MCP 可用來擴充 Agent 的可用資料與技能工具範圍。
詳情請參考：[外接MCP](/open-integration/mcp)。

## 其他部署設定

在完成 Data Agent 平台部署後，需進行以下兩項操作：
1. 在『後台地址』中加入對應的 FineBI 地址。
2. 點擊『連接測試』，以確保 FineAI 外掛程式與 FineBI 平台互通且版本一致。


