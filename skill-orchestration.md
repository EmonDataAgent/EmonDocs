<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/skill-orchestration.md
-->
---
page_id: skill-orchestration
title: "Dora 技能編排指南"
locale: zh-TW
sourced_from_kus:
  - dora.agent.skills.intro
  - dora.skill_management.custom_skills
  - finereport.skills.chart-visualization
  - finereport.skill.data_query_analysis_comparison
  - finereport.skill.fr_report_query
  - finereport.skills.dashboard-retrieval
  - dora.skill.dialog_subscription
  - dora.skill.ai-fixed-report
  - dora.skill.pptx_template.overview
  - dora.skill.pptx_template.preprocessing_rules
  - dora.skill.pptx_template.setup_and_global_config
  - dora.skill.pptx_template.page_config
  - dora.skill.pptx_template.reupload
  - dora.skills.report-generation-comparison.concept
  - dora.skills.report-generation-comparison.procedure
generated_at: "2026-06-04T15:21:01+08:00"
---

# Dora 技能編排指南

技能是 Dora 中提供給 Agent 呼叫的核心能力單元。Agent 透過選配不同技能，實現多樣化的資料分析與處理任務，滿足不同場景下的使用需求。目前系統已內建 20 種可公用的官方技能，包含：資料查詢與分析、資料視覺化、報告生成、研究與分析、內容創作、程式碼能力、對話與互動、元能力與治理等類型。

## 技能總覽與自訂

除官方內建技能外，平台亦支援透過匯入外部技能或上傳技能包兩種方式快速自訂專屬技能。自訂技能可按需定製，適配企業、團隊或個人的需求，助力 Agent 輸出更貼合業務的內容。

### 建立自訂技能

平台支援解析技能包配置，並自動生成可直接使用的技能。您可以直接使用「Dora 通用 Agent」，在對話中輸入技能需求，由 AI 協助自動生成完整技能包。

1. 以管理員身分進入『管理後台』>『技能』頁面。
2. 選擇『公共』或『我的』分頁，點選右上角『+ 技能』。
   - **匯入外部技能**：支援透過外部技能詳情頁 URL，或指向單個 `.zip` 技能包的 URL 來快速匯入。
   - **上傳技能包**：上傳準備好的本機自有技能包或平台生成的技能包（檔案大小不超過 50MB，且格式必須為 `.zip`，根目錄需包含 `SKILL.md`）。
3. 平台上傳並解析完成 `SKILL.md` 檔案後，將提取技能名稱、描述、觸發規則等資訊，生成完整的預覽卡片。

<!-- VISUAL_PENDING
visual_id: custom-skill-preview
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示解析技能包後生成的預覽卡片
placement_hint: 2.4 確認技能文件
source:
  original_url: ''
  local_path: data/dora/assets/1778588763Y2lB.png
  content_hash: dummy
  ocr_text: |
    csk-001e887e933d0017 可用
    上传 “来源文件: meow-woof-skill.zip
    文件
    @ SKILL.md
    name: csk-5a50a09d632ba9a8
caption_zh_TW: 自訂技能解析預覽卡片
-->

4. 確認解析無誤後，點選『確定』即可完成建立。

> [!NOTE]
> 技能使用權限由上傳時所選的分頁決定，建立後不可修改。在『公共』分頁上傳的技能歸入公共分類，全體開發使用者皆可查看與使用，請勿上傳敏感資訊；在『我的』分頁上傳的技能，僅限建立者本人查看與使用。

自訂技能建立後，建立者可對其匯出 zip 或刪除。技能內容不支援線上編輯，如需修改請重新上傳。刪除技能前，請務必確認無 Agent 依賴該技能。

## 資料查詢與圖表分析技能

資料查詢與分析分類中，共包含四種主要類型技能。建議按資料源為每個 Agent 匹配單一專屬的查詢技能，以規避無效檢索，提升執行速度並減少 Token 消耗。

*   **儀表板檢索**：在已綁定的儀表板範圍內檢索資產資料，回答指標查詢、趨勢分析、對比彙總等業務問題。典型場景包括看板查數和看板分析。
*   **資料分析**：支援對 Excel / CSV 格式的資料源查詢、彙總與匯出。適用於本機檔案上傳後的直接查數與分析。
*   **FR 報表查詢**：對接 FineReport 平台，支援報表搜尋、預覽、資料分析與參數調整。
*   **分析主題資料查詢**：針對已新增的 FineBI 分析主題資料源或 Excel 資料源，支援透過自然語言查詢結構化資料。

### 配置 FR 報表查詢技能

配置此技能前，必須在目標 FineReport 工程中完成外掛安裝與範本檢索配置：

1. 在 FineReport 平台中安裝檢索外掛（請直接安裝壓縮包，切勿解壓縮）。
2. 進入『管理系統』>『範本檢索』>『模型配置』，配置大語言模型與向量模型，並點選『測試並連接』確保模型可用。
3. 進入『管理系統』>『範本檢索』>『範本配置』，配置範本以生成元資料。

完成上述步驟後，在 Agent 配置頁面新增『FR 報表查詢』技能。若平台已記錄歷史連線，可直接複用；否則需點選『新建連接』，填寫自訂的連線名稱與服務地址。

<!-- VISUAL_PENDING
visual_id: fr-query-demo
role: diagram
locale_sensitivity: high
brand_sensitivity: medium
purpose: 展示在會話中透過自然語言直接搜尋和預覽 FR 報表的效果
placement_hint: 段落「1.3 效果演示」
source:
  original_url: ''
  local_path: data/dora/assets/1779185883vWak.png
  content_hash: dummy
  ocr_text: |
    四”当前你可以查看哪些数据                                            @ 内存用量: 388 MB
    当前你可以查看哪些数据
caption_zh_TW: 會話中預覽 FR 報表效果
-->

### 配置儀表板檢索技能

使用儀表板檢索功能前，必須確保 ElasticSearch 元件已升級至 v20.4.5-8.17.3 及以上版本，並處於 running 狀態。此外，需透過開發者模式自訂 ElasticSearch 元件的環境變數，將 `INSTALL_FINE_PLUGIN` 的值修改為 `yes`。

配置該技能時，需嚴格限定可檢索的儀表板範圍以鎖定資料邊界。範圍過小會導致無資料傳回，範圍過大則容易受到無關資料干擾並增加 Token 消耗。

配置完成後，您可以根據使用場景發佈 Agent：
*   **工作台**：供平台內部使用者日常查數與分析。
*   **獨立 URL**：便於向外部人員分享，對方無需登入即可使用。
*   **FineBI 平台**：使用者可在儀表板頁面透過側邊欄喚起 Agent，在瀏覽看板時即時提問。

### 圖表視覺化技能

在生成報告或問數分析等場景中，若需要 Agent 分析並輸出可預覽的圖表，可新增『圖表視覺化』技能。該技能可根據上游資料查詢結果，自動選擇圖表類型並生成視覺化圖表。

> [!NOTE]
> 地圖生成功能需聯網使用。若為本機部署使用者，需將 `antv-studio.alipay.com` 及 `mdn.alipayobjects.com` 網域加入存取白名單。

## 報告生成與訂閱推送技能

### 報告生成類技能

報告生成包含五種類型技能，可根據不同場景選配：

1.  **html報告**：基於文字內容與分析結論，動態生成可預覽的 HTML 報告，無格式限制，支援 AI 自主探索內容方向。
2.  **從範本建立html報告**：基於上傳的 HTML 範本與結構化資料源生成定製化報告，AI 需嚴格遵循範本約束輸出。
3.  **PPT報告**：基於文件、大綱或主題，快速生成結構化的工作匯報類 PPT。
4.  **PPTX範本填充**：支援上傳預先處理後的 PPT 範本，透過配置 AI 提示詞並綁定儀表板資料，自動生成標準化的 PPT 報告。
5.  **AI固定報告**：基於預先配置的報告大綱、本機範本與關聯資料源，自動整合資料、梳理邏輯，生成固定排版的標準化分析報告（如通用總結報告、歸因分析報告、對比分析報告）。

在 Agent 配置頁面中新增『AI固定報告』與『PPTX範本填充』技能時，需要詳細配置。

#### AI 固定報告配置細節

AI 固定報告支援從空白新建，或從內建範本（通用總結、歸因分析、對比分析）新建，亦可上傳本機 `.docx` 格式文件自動分析並生成範本。

配置頁面整體佈局分為左側「可用資料區」與右側「內容編輯區」：

<!-- VISUAL_PENDING
visual_id: layout-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示報告技能編輯頁面的左側可用資料區和右側內容編輯區佈局。
placement_hint: "2.3 介面介紹"
source:
  original_url: null
  local_path: data/dora/assets/17757364945orV.png
  content_hash: dummy
  ocr_text: |
    (= 通用总结报告 全
    可用数据区 ”内容编辑区
    S 可用数据
    1整体
caption_zh_TW: AI 固定報告配置介面佈局
-->

*   **左側可用資料區**：展示報告技能可引用的資料來源（皆來自 Agent 配置中的資料資訊項）。支援按照「整體」與「章節資料」維度關聯對應資料模組。
    *   **整體資料**：可全文件通用，支援在整篇報告的任意章節中直接呼叫。
    *   **分章節資料**：針對右側編輯區域的單個章節獨立配置，僅允許該章節呼叫指定的儀表板資料。同時，您可透過自然語言描述儀表板的過濾條件。
*   **右側內容編輯區**：作為提示詞編輯區域，支援以 Markdown 格式排版內容與編輯格式。幫助技能正確識別並精準生成報告。
    *   您可以插入可用資料區中儀表板包含的圖表、表格及附件（儀表板明細表將作為附件嵌入，報告生成後可點選下載）。
    *   支援插入全篇提示詞，統一規範文件的整體分析框架、輸出標準與行文風格。
    *   支援以 `【】` 作為佔位符，標註地區、行業、年份等變數欄位。技能執行時，將自動匹配使用者提問中的對應維度資訊，完成內容的動態適配與生成。

> [!TIP]
> 點選報告生成技能名稱右側的編輯按鈕，支援修改技能名稱、技能描述。

#### PPTX 範本填充配置細節

此技能適用於金融、銷售等行業需要批次生成標準化 PPT 報告的場景。範本預先處理需遵循以下規範：
*   純文字內容建議使用 `{{內容名稱}}` 格式（如：`{{本月總結}}`）。
*   純數值內容建議寫成 `{{數值來源}}`（如：`{{銷售額}}`），避免使用 `xxxx` 等模糊格式，亦支援如 `{{銷售額}}元` 的混合寫法。
*   圖片位置無需特殊標記，平台會自動識別圖片佔位。
*   範本需儲存為 `.pptx` 格式，保證佔位符唯一。

上傳範本後，平台將自動解析並展示頁數、元件數、可替換數與綁定數。

<!-- VISUAL_PENDING
visual_id: pptx-setup-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示在 Agent 配置頁面新增技能及基本設定的位置
placement_hint: 1
source:
  original_url: data/dora/assets/1779955547kBcP.png
  local_path: data/dora/assets/1779955547kBcP.png
  content_hash: sha1
  ocr_text: |
    销售分析PPT (通过模板生成)
    基础配置
    数据
    技能
    MCP
caption_zh_TW: PPTX 範本填充技能配置
-->

*   **全域配置**：可新增適用於全 PPT 頁面的資料過濾規則（僅對綁定的儀表板生效）。
*   **逐頁配置**：可分別配置文字與圖片佔位的生成規則。帶數值的文字類型必須先在『可用資料』新增儀表板元件；圖片佔位則可關關聯儀表板元件並設定獨立過濾條件，平台會自動同步並填充資料。請提供具體的提示詞以獲得更貼合業務的內容。

若範本修改後重新上傳，平台會羅列所有不一致項。您可以逐一確認映射關係，將舊佔位符對應至新位置。若新版範本頁數更多，可開啟『只看新增頁』來快速配置。

### 對話訂閱技能

『對話訂閱』技能主要用於管理使用者的定時任務。當使用者需要在對話中建立、查詢、修改、開啟、關閉或刪除定時任務時，必須呼叫此技能。常見的應用場景包括日報定時推送與資料預警推送（如銷售風險定時預警）。您可以為 Agent 同時新增資料分析技能與對話訂閱技能，實現完整的資料監控自動化閉環。

<!-- 本頁已依品牌規則處理 1 條過濾項 -->
