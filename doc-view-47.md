<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/doc-view-47.md
-->
---
page_id: doc-view-47
title: "Dora大模型問題排查指南"
locale: zh-TW
sourced_from_kus:
  - dora.troubleshooting.large_model
generated_at: 2026-06-03
---

# Dora大模型問題排查指南

本文介紹 Dora 大模型相關連線與請求錯誤的排查方法。

## 1. 前置檢查

在開始排查具體問題前，請確認以下事項：

- **確認大模型規格**：大模型及其參數、併發能力需滿足[推薦大模型](https://help.fanruan.com/finereport/doc-view-26.html)的要求。
- **確認連線測試完成**：請確保已完成[連線測試](https://help.fanruan.com/finereport/doc-view-22.html#6efaa47240586242)，包含：
  - FineAI 插件與 FineBI 平台互通測試。
  - 大模型連線測試。

## 2. 常見問題

### 2.1 連線測試失敗

- **FineAI 插件與 FineBI 平台互通測試失敗**
  按 `F12` 開啟瀏覽器開發者工具，查看 `test` 請求回應中的 `error_message` 欄位。透過該欄位可判斷是 BI 連不上 FineAI，還是 FineAI 連不上 BI。
- **大模型連線測試失敗**
  同樣透過 `F12` 查看請求回應中的 `error_message`，以定位具體原因。

### 2.2 Dora 無法正常回應，請求超時或無返回

**原因：** 網路通訊問題。
**排查步驟：**
1. 檢查 FineAI 節點是否正常運作。FineAI 可直接連通大模型，而 BI-Web 需與 FineAI 雙向通訊。
2. 可點擊連線測試來驗證連通情況。
3. 若連線測試不通，透過 `F12` 查看 `error_message`，判斷斷線位置。

### 2.3 第一個請求報錯，第二個請求正常

**原因：** Dora 必須依賴 `tool_call`，而當前使用的大模型不支援。
**排查步驟：**
使用兩條 curl 指令進行比對測試：
- 第一條指令（帶 `tool_call`）：若大模型不支援則會報錯。
- 第二條指令（不帶 `tool_call`）：正常返回。
若出現第一條報錯而第二條正常的現象，說明當前模型不支援 `tool_call`，需更換模型。

### 2.4 請求返回 422 狀態碼

**原因：** 部署的大模型可能不符合 OpenAI 介面協議規範。
**排查步驟：** 請提供介面日誌，由研發人員介入排查。

### 2.5 請求中 system content 相關欄位報錯

**原因：** 部分大模型只支援 `system content` 為 string 類型，不支援其他格式。
**排查步驟：** 確認目前使用的大模型是否對 `system content` 格式有限制，如有則需調整請求格式。

### 2.6 使用 Azure OpenAI 時連線測試不通

**原因：** Azure 暫不支援 `responses API` 格式的 endpoint。
**排查步驟：** 將 endpoint 改為 `base URL` 格式即可連通。

### 2.7 返回 ai-server-error 錯誤

**原因：** 大模型上下文長度不足 128k。
**排查步驟：** 確認模型上下文長度是否滿足 128K 的最低要求。

### 2.8 Azure 模型回應內容異常或中斷

**原因：** Azure 模型內建內容安全拒識機制，當觸發關鍵字時會中斷回應。
**排查步驟：** 更換提問方式，避免觸發拒識關鍵字。

### 2.9 模型呼叫失敗，提示無法存取

**原因：** 模型服務壓力過大，暫時無法回應。
**排查步驟：** 稍後再試。建議參考推薦大模型中的併發與效能參考，評估模型負載情況。

### 2.10 模型呼叫返回欠費相關錯誤

**原因：** 模型欠費。
**排查步驟：** 儲值後即可恢復使用。


