<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/example-agents.md
-->
---
page_id: example-agents
title: 內建 Agent 應用範例
locale: zh-TW
sourced_from_kus:
  - dora.agent.recommended_questions
  - finereport.agent.admin_attendance.intro
  - finereport.agent.admin_attendance.build
  - finereport.agent.admin_attendance.usage
  - finereport.agent.market_potential.intro
  - finereport.agent.market_potential.build
  - finereport.agent.market_potential.usage
generated_at: "2026-06-04T08:05:05+08:00"
---

# 內建 Agent 應用範例

透過實際案例展示 Agent 的應用場景，引導使用者了解如何設定並運用這些內建的智能助手來提升工作效率。

## 推薦問題設定範例

管理員可分類配置一系列的推薦問題，方便使用者在首次提問時更快捷有效地提問。

例如：
- 銷售場景中，可提前配置『問回款』、『問達成』或『問業績』等推薦問題。
- 經營分析場景中，可提前配置『問利潤』、『問銷售』等推薦問題。
- 行政場景中，則可提前配置『問出勤』、『問公差』等推薦問題。

**操作步驟：**

1. **開啟首輪推薦問題**：進入『Agent 工作台 > 對話體驗』，打開首輪推薦問題開關。
   
   <!-- VISUAL_PENDING
   visual_id: recommended-questions-switch
   role: screenshot
   locale_sensitivity: high
   brand_sensitivity: none
   purpose: 展示如何進入工作台並開啟首輪推薦問題開關
   placement_hint: 步驟「開啟首輪推薦問題」
   production_method: recreate
   -->

2. **新增問題**：在分類中點選『+』，以新增一個或多個問題內容。
3. **新增分類**：點選『新建分類』按鈕，新增一個問題分類，並可按需重新命名。
4. **調整問題與分類**：透過滑鼠拖曳，對分類與問題進行快速排序，或跨分類移動問題。
5. **問題預覽**：配置過程中，您可在右側預覽區域內即時查看效果並進行調整。

## 案例一：行政考勤資料助手

行政考勤資料助手可應用於考勤與公差查詢。它能協助行政管理人員快速且詳細地分析出差、請假等資料。這有助於降低資料分析門檻，並節省人力投入。

### 搭建步驟

1. **準備資料與建立 Agent**：以管理員身分登入 Data Agent<!-- AUTHOR_NOTE: "Data Agent" 未列入 tokenization-rules，予以保留 --> 平台。新增行政類資料與知識庫後，建立『行政考勤資料助手』Agent 並進入配置頁面。

   <!-- VISUAL_PENDING
   visual_id: prerequisite-data
   role: screenshot
   locale_sensitivity: high
   brand_sensitivity: high
   purpose: 展示前置操作中準備資料與知識庫的後台位置
   placement_hint: 步驟「準備資料與建立 Agent」
   production_method: recreate
   -->
   
   <!-- VISUAL_PENDING
   visual_id: agent-config-page
   role: screenshot
   locale_sensitivity: high
   brand_sensitivity: high
   purpose: 展示進入 Agent 配置頁面的整體介面
   placement_hint: 步驟「準備資料與建立 Agent」
   production_method: recreate
   -->

2. **配置模型與提示詞**：選擇已在『管理後台 > 模型』新增的 AI 大模型（如 deepseek-v3.2）。配置詳細的系統提示詞，賦予 Agent 專業助手角色並明確分析範圍，以利準確回傳內容。
3. **新增資料與技能**：將 FineBI 中所需的行政考勤類分析主題資料新增至 Agent 中。選擇並新增『分析主題資料查詢』技能，將其重新命名為『行政考勤資料查詢』。
4. **調整技能配置**：在技能配置頁面中，打開行政考勤出差資料，確保技能可依賴該資料運作。
5. **配置對話體驗**：設定合適的歡迎語與首輪推薦問題，以提高問答效率。推薦問題範例如下：
   - 高管們 3 月第 1 週出差情況？
   - 哪個部門公差最為頻繁？
   - 3 月誰請假總時長超過 3 天？
   - 哪個層級人員的請假最多？
   - 公差和請假人數比例是多少？
   - 結合目前公差和請假情況，提供些管理最佳化建議？
6. **測試與發佈**：配置完成後，您可在右側預覽測試區域內，即時查看問答首頁效果。傳送對話以測試 Agent 的回答準確度。確認無誤後點選『保存』，發佈至工作台與獨立 URL。

### 使用方式

一般使用者可在 Data Agent 平台首頁進入發佈後的 Agent。建立新對話並開始提問，即可快速獲取所需的分析結果。

## 案例二：全國市場潛量洞察報告員

全國市場潛量洞察報告員適用於協助管理員生成硬編排格式的市場潛量報告。產出的報告內容包含資料概覽與趨勢、市場佔有率分析等。

該 Agent 支援生成多種維度的分析報告。例如：全國各行業、全國特定行業、特定省份各行業，以及特定省份特定行業的分析報告。

<!-- VISUAL_PENDING
visual_id: market-potential-effect
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示全國市場潛量洞察報告員在對話和生成報告時的整體效果
placement_hint: 案例二簡介段落
production_method: recreate
-->

### 搭建步驟

1. **準備資料與建立 Agent**：以管理員身分登入 Data Agent 平台，新增客戶市場潛量分析相關資料與知識庫。接著建立『全國市場潛量洞察報告員』Agent 並進入配置頁面。

   <!-- VISUAL_PENDING
   visual_id: prerequisite-market-data
   role: screenshot
   locale_sensitivity: high
   brand_sensitivity: high
   purpose: 展示前置操作中新增潛量分析知識庫及資料的後台介面
   placement_hint: 步驟「準備資料與建立 Agent」
   production_method: recreate
   -->
   
   <!-- VISUAL_PENDING
   visual_id: market-potential-config
   role: screenshot
   locale_sensitivity: high
   brand_sensitivity: high
   purpose: 展示建立全國市場潛量洞察報告員 Agent 的配置介面
   placement_hint: 步驟「配置模型與提示詞」
   production_method: recreate
   -->

2. **配置模型與提示詞**：選擇已新增的 AI 大模型。配置系統提示詞，以幫助 Agent 明確其角色定位、行為約束與技能呼叫流程。
3. **匯入資料與建立範本**：將 FineBI 中用於生成報告的儀表板資料新增至 Agent 中。新增『儀表板報告生成』技能，選擇『上傳報告範本』透過 AI 生成範本。
4. **調整全篇與標題設定**：加入全篇提示詞，以約束整篇報告的風格格式及欄位過濾邏輯。將報告與章節標題修改為帶有變數佔位符（如【地區】）的實際標題。執行時，佔位符會自動對應提問中的維度資訊。
5. **配置章節內容與資料**：撰寫章節提示詞，以自然語言描述圖表內容、分析方向、資料源選取與計算邏輯。您可選擇儀表板中的明細表元件，將其作為表格與附件插入相關章節。
6. **設定章節可用資料**：點選章節標題左側的資料配置按鈕，選擇儀表板中的元件為各章節配置資料。例如：「區域資料概覽」章節可配置區域年份資料、省市複合增長率等。

   <!-- VISUAL_PENDING
   visual_id: config-section-data-icon
   role: icon
   locale_sensitivity: none
   brand_sensitivity: none
   purpose: 配置章節資料入口圖示
   placement_hint: 步驟「設定章節可用資料」
   production_method: keep_original
   -->

7. **配置對話體驗與發佈**：設定歡迎語與首輪推薦問題，以提升問答效率。在右側預覽測試區域即時查看首頁效果並進行對話測試。確認無誤後即可儲存並發佈。

### 使用方式

發佈完成後，一般使用者可在平台首頁選擇該 Agent 建立新對話。透過提問，即可快速獲取所需的市場潛量分析報告。


