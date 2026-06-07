---
page_id: doc-view-39
title: 外接 MCP
locale: zh-TW
sourced_from_kus:
  - dora.open_integration.mcp_management.intro
  - dora.open_integration.mcp_management.setup
  - dora.open_integration.mcp_management.notes
generated_at: "2026-06-03"
---
<!-- RENDERED
brand: emon
brand_display_name: Emon
locale: zh-TW
rendered_at: 2026-06-07T09:25:29Z
source_master: data/dora/locale/zh-TW/pages/doc-view-39.md
-->

# 外接 MCP

## 簡介

外接 MCP 功能用於管理 Agent 可使用的外部 MCP (Model Context Protocol) 服務。所有已啟用的 MCP 服務都會下發給 Agent，使 Agent 能夠呼叫外部工具、取得外部資料或執行擴充功能，進而實現 Agent 功能的彈性擴充與生態整合。

使用情境包含外接 12306 平台、外接財務資料平台等。

## 設定步驟

以管理員身分，進入『管理後台>開放集成>外接 MCP』，點選頁面右上角的『添加 MCP』按鈕，即可彈出『添加 MCP』設定視窗。

根據 MCP 服務的實際情況，填寫以下設定項：

*   **名稱**（必填）：自訂 MCP 服務名稱，便於識別與管理。
*   **傳輸方式**（必填）：支援 HTTP、SSE、STDIO 三種傳輸方式，請根據服務協定選擇。
*   **描述**（選填）：服務功能說明，用於區分不同服務用途。
*   **URL**（必填）：MCP 服務的存取端點位址（如 `https://example.com/mcp`）。
*   **請求頭（JSON 對象）**（選填）：用於服務驗證資訊，例如 `{"Authorization": "Bearer xxx"}`。
*   **啟用狀態**（必填）：設定完成後是否立即啟用。啟用後，服務將下發給所有 Agent。

所有設定項填寫完成後，點選『確定』儲存，服務將新增至 MCP 列表中。

若啟用狀態為『已啟用』，則會自動下發給 Agent，可供選擇設定。如需修改設定，可在列表中點選服務項目進入編輯模式，修改後儲存即可生效。

## 注意事項

1.  **傳輸方式說明**：平台支援 HTTP、SSE、STDIO 三種主流 MCP 傳輸方式，以適應不同情境的外部服務整合需求。
    *   **HTTP**：適用於標準 REST API 形式的 MCP 服務，透過 HTTP 請求與回應實現互動。
    *   **SSE (Server-Sent Events)**：適用於需要伺服器主動推送資料的情境，例如即時資料流、狀態更新。
    *   **STDIO**：適用於本機處理程序形式的 MCP 服務，透過標準輸入輸出流進行通訊。
2.  服務啟用後將自動下發給所有 Agent。停用後 Agent 將無法呼叫該服務，需提前評估影響範圍。
3.  需根據外部 MCP 服務的實際協定選擇對應的傳輸方式，協定不符將導致連線失敗。
4.  MCP 名稱不建議包含中文字元，相關中文說明可新增在描述中。
5.  不建議新增同類 MCP 及與 Emon 自有技能重複的功能，避免造成誤觸發或呼叫不準確的問題。
6.  若找不到對應 MCP，可依序檢查：優先檢查傳輸方式是否正確；接著檢查 MCP 是否過期；最後檢查 URL 位址是否正確。
7.  若 MCP 知識庫需要基於 OrangeBI 使用者進行驗證，且 MCP 伺服器已支援從請求標頭中取得使用者名稱，則可在『請求頭 (JSON 对象)』中設定：`{"fine_username": "${fine_username}"}`。


