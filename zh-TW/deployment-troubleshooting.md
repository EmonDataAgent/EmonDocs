---
page_id: deployment-troubleshooting
title: "部署與疑難排解"
locale: zh-TW
sourced_from_kus:
  - dora.deployment.data-agent
  - dora.deployment.troubleshooting.row_limit
  - dora.deployment.troubleshooting.report_token_consumption
  - dora.llm.troubleshooting.prechecks
  - dora.llm.troubleshooting.connection_test_fails
  - dora.llm.troubleshooting.timeout_or_no_response
  - dora.llm.troubleshooting.tool_call_unsupported
  - dora.llm.troubleshooting.http_422_error
  - dora.llm.troubleshooting.system_content_error
  - dora.llm.troubleshooting.azure_endpoint_error
  - dora.llm.troubleshooting.context_length_insufficient
  - dora.llm.troubleshooting.azure_content_safety
  - dora.llm.troubleshooting.service_unavailable
  - dora.llm.troubleshooting.insufficient_balance
generated_at: "2026-06-04T08:05:05+08:00"
---
<!-- RENDERED
brand: emon
brand_display_name: Emon
locale: zh-TW
rendered_at: 2026-06-07T09:25:29Z
source_master: data/dora/locale/zh-TW/pages/deployment-troubleshooting.md
-->

## Data Agent 部署指南

部署 Data Agent 前，請確認已使用運維平台成功部署 OrangeBI（版本需為 7.0.7 及以上）。運維平台版本需為 V2.26.0 及以上。若在內網環境，請務必使用全量版離線安裝包部署運維平台，否則將無法獲取 OrangeBI 相關元件映像檔。部署 OrangeBI 時必須選擇『運維平台部署』，不支援『非運維平台部署』。

### 伺服器與環境要求

- **伺服器配置**：建議為 Data Agent 單獨準備一台伺服器，以免資源競爭，並為後期增加大模型做準備。推薦配置為 CPU 16 核、可用記憶體 64G、可用磁碟 100G（AI 元件獨占伺服器）。若與專案共用伺服器，最低配置要求為 CPU 8 核、可用記憶體 16G、可用磁碟 80G。不建議在虛擬機中部署 Emon Corp 應用，且不支援 Kubernetes 環境。
- **作業系統**：需為 Linux（支援 X86_64 和 ARM 架構），內核 3.10 及以上。推薦使用 Ubuntu 22。必須安裝 `tar` 與 `sed` 命令。
- **權限與時間**：部署使用者必須具備 `sudo` 權限（優先推薦 root），且使用者的 ssh 連線密碼不得包含英文單引號字元。伺服器時間與時區必須與專案其他伺服器完全一致（時間差不超過 5 秒）。
- **通訊埠**：需開放 FineAI (<!-- AUTHOR_NOTE: FineAI -->)（7666）、語意解析小模型（8666）與 FineAI Redis（6679）所需之通訊埠。

### 部署步驟

1. 登入運維平台，匯出部署資訊以獲取 `resources` 資料夾路徑。
<div class="visual-pending" id="upload-export-001">
```yaml
visual_id: upload-export-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在運維平台上匯出部署資訊以尋找資源目錄路徑。
```
</div>

2. 將獲取的 FineAI 元件與語意解析小模型元件映像檔（`.tar.gz`），上傳至伺服器的 `resources` 資料夾中。
<div class="visual-pending" id="upload-folder-001">
```yaml
visual_id: upload-folder-001
role: screenshot
locale_sensitivity: none
brand_sensitivity: none
purpose: 展示將映像檔檔案上傳到伺服器的 resources 資料夾。
```
</div>

3. 在運維平台的『維護中心>映像檔管理』點選『載入映像檔』，手動將映像檔推送至倉庫（Data Agent 映像檔無法直接從雲端倉庫拉取）。
<div class="visual-pending" id="load-image-001">
```yaml
visual_id: load-image-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在運維平台載入上傳的映像檔檔案。
```
</div>

4. 記錄推送後的新映像檔版本號。
<div class="visual-pending" id="image-version-001">
```yaml
visual_id: image-version-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在映像檔管理中查看並記錄推送的新映像檔版本號。
```
</div>

5. 在『更新升級>部署列表>手動修改』中，修改對應 AI 元件的版本號，確保與映像檔管理中的版本一致。
<div class="visual-pending" id="update-version-001">
```yaml
visual_id: update-version-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在運維平台手動修改 AI 元件的部署版本號。
```
</div>

6. 確認映像檔倉庫中存在 `v20.3.0-6.2.17` 及以上版本的 `redis` 映像檔。
<div class="visual-pending" id="check-redis-001">
```yaml
visual_id: check-redis-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在映像檔管理中確認 redis 映像檔版本。
```
</div>

7. 在『維護>元件管理』點選『新增元件』，選擇『業務服務>AI』。
<div class="visual-pending" id="add-component-001">
```yaml
visual_id: add-component-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在運維平台新增業務服務元件的操作介面。
```
</div>

8. 新增並選擇目標節點，配置對應通訊埠，並務必修改 FineAI Redis 元件的隨機預設密碼（部署後將無法修改），完成後點選開始部署。
<div class="visual-pending" id="add-node-001">
```yaml
visual_id: add-node-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示新增節點介面及磁碟空間要求。
```
</div>
<div class="visual-pending" id="select-node-001">
```yaml
visual_id: select-node-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示選擇節點並查看其資源的介面。
```
</div>
<div class="visual-pending" id="component-config-001">
```yaml
visual_id: component-config-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示配置 Data Agent 各元件的主機通訊埠和密碼。
```
</div>

9. 在 OrangeBI 平台的『管理系統>外掛管理>應用商城』，選擇從本機安裝下載好的 Data Agent 外掛。
<div class="visual-pending" id="install-plugin-001">
```yaml
visual_id: install-plugin-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在 OrangeBI 外掛管理中從本機安裝 Data Agent 外掛。
```
</div>

10. 聯絡銷售獲取 Data Agent 授權並安裝後，OrangeBI 右上角將顯示『Data Agent』按鈕，即代表配置成功。
<div class="visual-pending" id="check-success-001">
```yaml
visual_id: check-success-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示 Data Agent 按鈕以確認配置成功。
```
</div>

11. 若需升級原 FineChatBI (<!-- AUTHOR_NOTE: FineChatBI -->) 元件，可推送最新映像檔包至倉庫後，透過運維平台的『元件管理』進行更新以平滑使用。
<div class="visual-pending" id="component-update-001">
```yaml
visual_id: component-update-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在運維平台中升級原 FineChatBI 元件。
```
</div>

12. 升級 ElasticSearch 元件至 `v20.4.5-8.17.3` 及以上版本且確認處於 running 狀態，並自訂環境變數將 `INSTALL_FINE_PLUGIN` (<!-- AUTHOR_NOTE: INSTALL_FINE_PLUGIN -->) 的值修改為 `yes`。
<div class="visual-pending" id="check-es-001">
```yaml
visual_id: check-es-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在運維平台中確認 ElasticSearch 元件版本並保持運行狀態。
```
</div>
<div class="visual-pending" id="env-es-001">
```yaml
visual_id: env-es-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在開發者模式下修改 ElasticSearch 環境變數。
```
</div>

13. 部署完成後，前往 Data Agent 管理後台的『開放整合>其他』新增 OrangeBI 地址並點選『連接測試』以確保互通。
<div class="visual-pending" id="test-connection-001">
```yaml
visual_id: test-connection-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示新增後台地址並點選連接測試的介面。
```
</div>

14. 隨後前往『模型』頁面對已新增的目標模型執行『連接測試』，確保大模型服務為可用狀態。
<div class="visual-pending" id="test-model-001">
```yaml
visual_id: test-model-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在模型管理頁面點選連接測試以保證模型可用。
```
</div>

## 大模型連線問題排查

排查大模型連線問題前，請先確認大模型的參數與並發能力滿足推薦大模型要求，並已完成 FineAI 外掛、平台互通測試以及大模型連接測試。

### 連接測試失敗或超時
- 透過瀏覽器開發者工具（按 F12）檢視 `test` 請求回應的 `error_message` 欄位，可判斷是 BI 與 FineAI 斷線，或是 FineAI 無法連線大模型。
<div class="visual-pending" id="connection-test-fail-001">
```yaml
visual_id: connection-test-fail-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示透過 F12 開發者工具查看 test 請求回應的過程。
```
</div>
- 檢查 FineAI 節點是否正常運行。無法正常回應或請求超時多為網路通訊問題引起，OrangeBI Web 端需與 FineAI 進行雙向通信。

### 工具呼叫 (tool_call) 異常
- 若第一個請求報錯，第二個請求正常，通常是因為該大模型不支援 `tool_call` 功能（Emon 強制依賴此功能）。
- 可透過帶有與不帶 `tool_call` 的 `curl` 命令進行驗證，若不支援時需更換模型。

**帶 `tool_call` 測試命令**：
```bash
curl -X POST 'http://<your-model-endpoint>/v1/chat/completions' -H 'Accept: application/json' -H 'Content-Type: application/json' -H 'Authorization: Bearer <your-apikey>' -d '{"model": "<your-model-name>", "messages": [{"role": "user", "content": "Hello!"}], "tools": [{"type": "function", "function": {"name": "get_weather", "description": "", "parameters": {"type": "object", "properties": {"city": {"type": "string", "description": ""}}, "required": ["city"]}}}], "tool_choice": "auto", "stream": false}'
```

**不帶 `tool_call` 測試命令**：
```bash
curl -X POST 'http://<your-model-endpoint>/v1/chat/completions' -H 'Accept: application/json' -H 'Content-Type: application/json' -H 'Authorization: Bearer <your-apikey>' -d '{"model": "<your-model-name>", "messages": [{"role": "user", "content": "Hello!"}], "stream": false}'
```

### 其他錯誤代碼與狀態
- **422 狀態碼**：部署的大模型可能不符合 OpenAI 介面協議規範，請提供介面日誌交由研發人員排查。
- **system content 報錯**：部分模型限定 `system content` 必須為字串 (string) 格式，不支援其他格式，請確認並調整請求格式。
- **ai-server-error 錯誤**：代表大模型支援的上下文長度不足 128K，請確保使用符合最低要求的大模型。
- **Azure OpenAI 錯誤**：
  - 連接測試不通：Azure 暫不支援 `responses` API 格式的 endpoint，請將 endpoint 改為 base URL 格式。
  - 回應中斷或異常：Azure 內建內容安全拒識機制，觸發關鍵字時將中斷回應，請更換提問方式。
- **無法存取或欠費**：當服務提示無法存取，可能是模型服務壓力過大，請稍後重試；若提示欠費相關錯誤，請進行儲值。

## 一般常見問題

### 觸發底層列資料限制
透過直連模式連線至 PostgreSQL (PG) 資料庫時，可能會觸發底層 100 萬列資料的限制，並顯示報錯訊息。
<div class="visual-pending" id="row-limit-001">
```yaml
visual_id: row-limit-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示觸發底層 100 萬列資料限制時的報錯資訊。
```
</div>

**解決方案**：
1. 檢查 OrangeBI 的『系統管理>BI參數>資料存取限制』，查看資料存取量的限制是否過低。
2. 將資料存取量的限制調高。
<div class="visual-pending" id="row-limit-002">
```yaml
visual_id: row-limit-002
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示在系統管理中調高資料存取量限制的位置。
```
</div>

### 報告類技能 Token 消耗
使用『AI固定報告』技能時，輸入報告提示詞並輸出中等長度的報告，大約需消耗 80 萬至 200 萬 Token。

<!-- 本頁已依品牌規則處理 7 條過濾項 -->
