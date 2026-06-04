<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/agent-management.md
-->
---
page_id: agent-management
title: "Agent 建立與模型配置"
locale: zh-TW
sourced_from_kus:
  - finereport.agent.create-agent
  - dora.agent.encapsulate.config
  - dora.agent.list.overview
  - finereport.agent.session_record.intro
  - finereport.agent.session_record.fields
  - finereport.agent.session_record.filter
  - finereport.agent.model.intro
  - finereport.agent.model.add
  - finereport.agent.model.manage
  - dora.model.recommended-llm
  - dora.model.resource-config
generated_at: "2026-06-04T08:05:05+08:00"
---

## 建立與封裝 Agent

Agent 是一款面向業務場景的專屬智能分析助手。它能夠自主理解、規劃決策並執行複雜任務。透過拆解模糊指令並呼叫內部知識庫與工具，它能精準完成業務分析目標。相關工具包含資料查詢、視覺化與報告生成等。管理員可根據需求建立多個 Agent。這能滿足成員在銷售問數與經營報告等場景下的日常需求。讓業務人員能透過對話輕鬆完成專業的資料分析。

建立 Agent 前，請先在『模型』頁面新增並測試可用的大語言模型。同時在『資料』頁面準備好所需的資料或儀表板。

**建立步驟**
1. 進入『管理後台 > Agent』頁面，點選右上角的『建立 Agent』按鈕。
<!-- VISUAL_PENDING
visual_id: create-agt-002
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: recreation
purpose: "展示在管理後台 Agent 列表中點選建立 Agent 的入口介面。"
caption_zh_cn: "建立入口"
ocr_text: |
  < Data Agent                         Agent
  ...
-->
2. 選擇『封裝 Agent』或『對接 Agent』。
   - **封裝 Agent**：支援在平台內自選模型與技能，自行構建智能體。您也可以透過外接 MCP 工具，使用外部的資料來源與技能。
3. 進入設定頁面後，點選 Agent 名稱右側的編輯按鈕。以修改名稱、描述與圖示等基礎資訊。
4. 在基礎設定中下拉選擇已新增的大語言模型。並填寫系統提示詞，以定義智能體的角色、回答風格與能力邊界。
5. 點選『+』按鈕新增資料或技能：
   - 選擇已新增的分析主題或儀表板，您可在彈出視窗中點選左側目錄進行預覽。
   - 選擇官方技能或 MCP 工具。Agent 運作時會自動呼叫對應技能。您可以修改技能名稱與描述。也可調整技能可用的資料範圍，以提高執行精準度。目前支援：儀表板檢索、FR 報表查詢、分析主題資料查詢與智能報告。
6. 設定對話體驗。您可以設定 Agent 首頁的歡迎語及使用者首次對話的首輪推薦問題。在設定過程中，右側的預覽區會即時展示效果；您可在該區進行測試，其問答紀錄不會計入歷史對話中。封裝 Agent 預設開啟並支援上下文多輪對話。
7. （選用）為 Agent 新增排程任務並設定推播管道。支援透過平台或企業微信等進行推送。封裝 Agent 也可對接企業微信機器人，實現在企業微信內直接使用。
8. 點選右上角的『發佈』按鈕。在發佈前可設定可見範圍（預設為全部使用者可見，也可指定部分使用者）。
9. 選擇發佈管道：
   - **工作台**：發佈至使用者工作台供業務人員使用。
   - **獨立 URL**：產生獨立連結對外分享。
   - **FineBI 平台**：發佈至目錄資源中，使用者存取資源時可透過側邊欄發起對話。單個 Agent 可發佈至多個資源，但單個資源僅允許關聯一個 Agent。

<!-- VISUAL_PENDING
visual_id: create-agt-009
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
production_method: recreation
purpose: "展示將 Agent 發佈至 FineBI 平台後的實際應用效果。"
caption_zh_cn: "FineBI 平台發佈"
ocr_text: "(原圖無 OCR 文字)"
note: "待人工確認 brand_sensitivity"
-->

> [!NOTE]
> 未發佈的 Agent 為草稿狀態，僅管理員可見與編輯。已發佈的 Agent 若修改了設定，必須重新發佈才能生效。若需刪除，必須先點選『取消發佈』；取消發佈後，一般成員將無法在首頁搜尋到該 Agent，且獨立 URL 也會失效。

## 模型與資源配置

AI 大模型是 Agent 的底層智能引擎。提供自然語言理解、邏輯推理、SQL 生成與報告生成等核心能力。Agent 在運行時必須綁定大模型。管理員可在『模型』模組中對可呼叫的大模型進行統一設定與管理。

已新增的模型會依據權限分為『公共』（全員公開可用）與『我的』（僅建立者個人可見與使用）。您可在模型列表中搜尋、進行連線測試，或刪除不再使用的模型。模型刪除後無法恢復，操作前請確認未被 Agent 引用。

平台支援連接符合 OpenAI 或 Azure 介面規範的本地與雲端大模型。為確保運行效果，大模型必須支援 `tool_call`。建議優先選擇完整參數的滿血版（最低參數需求為 235B）。並需具備 ≥128k tokens 上下文視窗及 TPM ≥20w tokens 的處理能力。單次併發建議每分鐘輸入約 20w tokens、輸出 1~2k tokens。單步消耗約 20k~30k Token，每分鐘可執行 5~7 步。

**推薦大模型**
- **準確性優先場景**（財務報表查詢、合規核對、決策支援）：推薦使用 `qwen3-max-preview`（滿血版），不適合對即時性要求極高的場景。
- **速度與穩定性優先場景**（高頻資料查詢、大量併發）：推薦使用 `qwen3.6-plus`（滿血版），不適合複雜金融查詢。
- **日常輕量查詢場景**（簡單檢索、報表查看）：推薦使用 `qwen3-max-preview`（滿血版），不適合複雜分析。
- **成本敏感場景**：可考慮 `deepseekV3.2`、`qwen3.6-35b-a3b` 或 `MiniMax-M2.7`，但穩定性與效果呈現較為一般。
- *不推薦*：`qwen3.5` 系列（存在已知嚴重 BUG）、`deepseek-v3`、`deepseek-v3.1` 及參數小於 235B 的小模型。

**新增模型步驟**
1. 以超級管理員或具備模型管理權限的開發者身分，進入『管理後台 > 模型』。
2. 點選右上角的『新增模型』，在彈出視窗中選擇介面呼叫協議（OpenAI 兼容協議或 Azure 兼容協議）。

<!-- VISUAL_PENDING
visual_id: model-add-example
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: recreation
purpose: "展示填寫 deepseek-v3 模型資訊的示例效果。"
caption_zh_cn: "新增模型示例"
ocr_text: |
  編輯模型
  接口調用協議
  OpenAI 兼容協議
-->

3. 填寫模型基礎資訊：
   - **ApiKey**：模型官方提供的 API 金鑰。因涉及隱私，建議建立後立即複製以避免遺失。通義千問需至官方控制台完成 Token 訂閱並獲取。DeepSeek 需登入官方平台進入 API keys 頁面建立。智譜 GLM 需至智譜 AI 開放平台的 API Key 頁面建立。
   - **EndPoint / Base URL**：模型服務的 API 介面位址。
     - 通義千問：`https://dashscope.aliyuncs.com/compatible-mode/v1`
     - DeepSeek：`https://api.deepseek.com/v1`
     - 智譜 GLM：`https://open.bigmodel.cn/api/paas/v4`
     - Azure OpenAI：`https://{你的資源名}.openai.azure.com`
     - Anthropic Claude (Azure 託管)：`https://<你的資源名>.cognitiveservices.azure.com/anthropic/v1`
     - Google Gemini：`https://<你的資源名>.cognitiveservices.azure.com/google/v1`
   - **API-Version**：僅在 Azure 兼容協議下需填寫（如 Azure OpenAI 填寫 `2025-01-01-preview`，Claude 或 Gemini 則無需填寫）。
   - **模型名稱**：必須與服務商提供的官方名稱完全一致，否則會導致呼叫異常。通義千問常用模型包括 `qwen-turbo`、`qwen-plus`、`qwen-max`。DeepSeek 常用模型包括 `deepseek-v4-flash`、`deepseek-v4-pro`。智譜 GLM 常用模型包括 `glm-4-flash`、`glm-5.1`。Azure OpenAI 常用模型包括 `gpt-4o`、`gpt-4o-mini`、`gpt-4.1`、`o1/o3-mini`。Claude 常用模型包括 `claude-opus-4.7`、`claude-sonnet-4.6`、`claude-haiku-4.5`。Gemini 常用模型包括 `gemini-3.1-pro`、`gemini-3.1-ultra`。您也可以點選『獲取模型名稱』自動擷取。Azure 兼容協議下的模型 ApiKey 可共用。
4. 點選『連線測試』，確認網路環境可正常存取 API。測試通過後點選『儲存』。

> [!WARNING]
> 帆軟 僅提供大模型的推薦參考及對接方式，不對大模型本身的問題承擔責任。

## Agent 列表與對話紀錄管理

**Agent 列表**
在『管理後台 > Agent』頁面，所有已建立的 Agent 會以卡片形式展示。

<!-- VISUAL_PENDING
visual_id: agent-card-view
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: recreation
purpose: "展示 Agent 卡片包含的資訊與工作台入口。"
caption_zh_cn: "Agent 卡片"
ocr_text: |
  江蘇連鎖經營分析
  最近編輯: 2026/4/2
  已發佈 工作台
-->

- 卡片上會顯示 Agent 名稱、描述、最近編輯時間、發佈狀態（已發佈/未發佈）以及類型標籤（封裝/對接）。
- 點選卡片上的工作台入口，即可跳轉至該 Agent 的設定頁面。
- 支援依發佈狀態和類型進行篩選。點選卡片右下角的『...』可刪除未發佈的 Agent（刪除後不可恢復）。

**對話紀錄管理**
對話紀錄是追溯 Agent 互動日誌的核心模組。可統一記錄所有已發佈 Agent 與使用者的對話過程、執行結果與資源消耗。這能協助管理員排查問題、審計行為與分析使用情況。

1. 進入『管理後台 > Agent 監管 > 對話紀錄』，左側為 Agent 選擇區（支援輸入名稱搜尋），右側為對話紀錄列表。

<!-- VISUAL_PENDING
visual_id: session-record-effect
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: recreation
purpose: "展示對話紀錄頁面的整體效果。"
caption_zh_cn: "對話紀錄"
ocr_text: |
  Agent 監管
  對話紀錄
  執行狀態
-->

2. 列表預設展示當天資料，可透過上方篩選器自訂起止時間，或透過『執行狀態』進行篩選：
   - **運行中**：對話正在執行，未完成。
   - **成功**：對話執行完成，結果正常。
   - **已中止**：對話被手動中止或超時。
   - **失敗**：對話執行出錯。
3. 列表核心欄位包含：
   - **時間**：對話發生的精確時間。
   - **使用者**：發起對話的使用者標識。
   - **原始使用者 Query**：使用者的原始提問內容。
   - **技能**：本次對話呼叫的技能名稱。
   - **耗時**：從請求到回應完成的總耗時 (ms)。
   - **Token 消耗**：大模型消耗的 Token 數量。
   - **使用者回饋**：使用者對本次回覆的評價。
   - **錯誤資訊**：執行失敗時的具體錯誤原因。
   - **執行 SQL**：在實時資料模式下可查看執行的 SQL。
   - **回答紀錄**：點選『詳情』可查看智能體的完整回覆內容與執行過程。

<!-- 本頁已依品牌規則處理 21 條過濾項 -->
