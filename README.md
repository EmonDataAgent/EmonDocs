<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/getting-started.md
-->
---
page_id: getting-started
title: "Dora 快速入門"
locale: zh-TW
sourced_from_kus:
  - dora.platform.intro
  - finereport.agent.workspace.intro
  - finereport.agent.workspace.dora_general_agent
  - finereport.agent.workspace.expert_agent
  - finereport.agent.workspace.admin_backend
  - dora.getting_started.use_agent.overview
  - dora.getting_started.use_agent.select_and_new_chat
  - dora.getting_started.use_agent.dialogue_interaction
  - dora.getting_started.use_agent.dialogue_correction
  - dora.getting_started.use_agent.session_operations
  - dora.getting_started.use_agent.workspace
generated_at: "2026-06-04T08:05:05+08:00"
---

## 平台介紹

Dora 是一款企業級資料 Agent（Data Agent <!-- AUTHOR_NOTE: Data Agent 疑似品牌或專有名詞，暫保留原樣 -->）平台，具備企業級資料安全底座與 Agent 編排引擎能力。它能實現在不同業務場景的資料分析、報告、預警、推送等全鏈路閉環。根據任務複雜度，平台會自動「思考」（規劃下一步行動）並「行動」（呼叫對應技能），高效回應業務需求。

此平台主要面向資料分析人員與關注資料報告的企業管理者。其核心定位在於降低資料分析門檻、提升分析效率，並賦能業務自助化。Dora 可為財務、營運、銷售等不同業務線建立專屬 Agent 助手，實現資料能力的重複使用與沉澱。

**問數類 Agent**
問數類 Agent 是 Dora 最基礎的核心能力。它支援使用者透過自然語言對話直接查詢業務資料，並能自動識別提問中的關鍵資訊（智慧解析意圖），精準傳回結果，同時支援多場景查詢。

<!-- VISUAL_PENDING
visual_id: platform-agent-qa
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示問數類 Agent 的互動介面
production_method: recreate
ocr_text: |
  OQ > 行政考勤数据助手
  Q MX
  (So 定时任务
  历史会话
  3月谁请假总时长超过3天? 哪个…
  3月第1周有多少领导不在岗? 请…
  高管们3月第1周出差情况?
  ‘Up ”行政考勤数据助
  高管们3月第1周出差情况?
  哪个部门公出最为频繁?
  18! 我是你的考勤/公出查询小助手，专门帮你分析公出和请假数据
  领导公出的主要目的地和事由集…
  哪个部门公出最为频繁?                                                                            公出查询            请假查询            综合查询
  生产部门3月的行程安排?                                * 高管们3月第1周出差情况?
-->
*圖：問數類 Agent 介面範例*

**報告類 Agent**
報告類 Agent 則支援基於查詢結果，自動編排並輸出結構化分析報告，滿足企業管理者對資料匯報、復盤的需求。這類 Agent 具備自動整合資料、結構化輸出，以及針對不同業務的場景化適配等優勢。

<!-- VISUAL_PENDING
visual_id: platform-agent-report
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示報告類 Agent 的互動介面
production_method: recreate
ocr_text: |
  OQ & 供应链经营分析师
  Q MX
  (So 定时任务
  历史会话
  请根据你可以查询数据和能力，…
  各运营中心的业务量与效率对比…
  各运营中心的业务量与效率对比…
  各承运人的毛利排名及盈利情况…
  2025年各月供应链收入与成本趋…
  帮有我生成你自己的agent简介吧.….
  公司整体收入成本趋势如何? 是…
  各运营中心供应链收入分月完成…
  上海口岸供应链收入分月完成情…
  供应链收入激励构成是什么，各…
  A  admin(admin)          =: 管理后台
  q
  AL 供应链经营分析师
  我是供应链经营分析师，专注于供应链与项目分类数据查询、多维度经营分析及可视化图表生成，助您用一句话快速获取业务洞察。
  推荐问题
  + 各运营中心的业务量与效率对比如何?
  + 各承运人的毛利排名及盈利情况怎样?
  * 2025年各月供应链收入与成本趋势如何?
-->
*圖：報告類 Agent 介面範例*

## 工作台概覽

工作台即為 Dora 平台的首頁，可讓員工快速選擇合適的 Agent 來處理各種資料分析。使用者可以選擇如『銷售問數 Agent』或『報告分析 Agent』等工具輔助完成工作。開發人員或系統管理員可以建立各種類型的 Agent，並發佈至工作台供員工使用。

### Dora 通用 Agent
Dora 通用 Agent 是 帆軟 Dora 平台內建的通用 Agent，整合了平台全部技能。一般使用者可在工作台直接與它進行對話，而管理員則能為其配置模型、排程任務與 IM 串接。

<!-- VISUAL_PENDING
visual_id: dora-general-agent
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示工作台上內建的 Dora 通用智能體對話入口
production_method: recreate
ocr_text: |
  Data Agent
  =
  UR DARE Z| |
  [s, Ke Dora，全能助手随时待命
  我可以帮你 数据分析
  COCO 探索更多专家 ^
-->
*圖：Dora 通用 Agent 區塊*

### 專家 Agent
點選『探索更多專家』，您可以在專家 Agent 列表中透過名稱或描述快速搜尋目標 Agent。找到合適的 Agent 後，點選該卡片即可進入對話頁面。

<!-- VISUAL_PENDING
visual_id: expert-agent-list
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示專家 Agent 列表頁及搜尋、選擇卡片的操作介面
production_method: recreate
ocr_text: |
  Data Agent
  iis, Ezz Dora，全能助手随时待命
  我可以帮你
  在此
  生成PPT
  COO 探索更多专家 ^
  s                                       四                                       1
  Data Agent
  专家 Agent                                                  Q 搜索名称
  a  检索test jeremy                       a  部门考勤助手                         a   星火人才画像
  二 20200512                         ileit: 20200000                            (eit: 20200u10
  Data Agent                                 查看部门成员出勤数据                         星火人才画像
  人 aexest
  aR: 2028/05/12
  a               02
  IEAM: 2026/0408,
  QQ BPH BBOVen
  BMIRAR: 2026/0421
  潜量分析报告
  A          CMO报告-Dylan
  sBIIRAH: 2026/03/30
  生成壳牌PCMO报告
  QR REMEAELARAGent
  BMI: 2026/08/08
  最分析报告Agent by zhuoyang
  人 afies
  BIR: 2026/04/00
  析问数
  LA HS四coral
  BMH: 2026/03/90
  专家
  A               4
  iE: 2026/04/00
  QR Fittest
  EMM: 2026/05/12
  Data Agent
  QR omtittitagent
  BiGiRE: 2026/0429
  Data Agent
  au
  BENE: 2026/04/08
  hoky-test
-->
*圖：專家 Agent 列表搜尋與選擇*

### 管理後台入口
管理員可以透過點選『去建立』按鈕，或點選左下角的管理後台圖示進入管理後台。在後台中，您可以配置技能、資料、知識庫、模型，並建立所需的 Agent。

<!-- VISUAL_PENDING
visual_id: admin-backend-icon
role: icon
locale_sensitivity: none
brand_sensitivity: none
purpose: 管理後台入口圖示
production_method: reuse
ocr_text: "(原圖無 OCR 文字)"
-->

<!-- VISUAL_PENDING
visual_id: admin-backend-entry
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示從工作台進入管理後台的入口按鈕位置
production_method: recreate
ocr_text: |
  Ea  Jah
  Data Agent
  专家 Agent
  检索test jeremy
  人
  最近编辑: ”2026/05/12
  Data Agent
  alex test
  a
  最近编辑: §~— 2026/05/12
  Aa             02
  最近编辑: 2026/04/08
  潜量分析报告Dylan
  人
  最近编辑: ”2026/04/21
  潜量分析报告
  a     壳牌PCMO报告-Dylan
  最近编辑: ”2026/03/30
  生成壳牌PCMO报告
  部门考勤助手
  A     最近编辑: ”2026/04/03
  查看部门成员出勤数据
  A     B2B市场潜量洞察Agent
  eee
  最近编辑: ”2026/04/08
  潜量分析报告Agent by zhuoyang
  /09
  自动化test
  AA      最近编辑: ”2026/04/09
  连锁经营分析问数
  报告生成-coral
  人 ees
  最近编辑: ”2026/03/30
  周报生成专家
  Q 搜索名称/描述
  星火人才画像
  A     最近编辑: ”2026/04/10
  星火人才画像
  a              is
  最近编辑: ~— 2026/04/09
  不可加test
  人 na
  最近编辑: ”2026/05/12
  Data Agent
  Jeremy.LiMitagent
  ae
  最近编辑: § — 2026/04/23
  Data Agent
  a     hoky
  最近编辑: 2026/04/03
  hoky-test
-->
*圖：管理後台入口位置*

## 開始第一次對話

Dora 的使用場景涵蓋日常資料查詢、多輪對話分析與歷史對話回溯。以下將引導您完成第一次對話分析：

### 發起與互動
1. **輸入與提問**：在介面中間的輸入框輸入您的問題（例如「你能幫我做什麼？」或「25 年每個省份的銷售額同比」），然後點選發送按鈕或按 Enter 鍵提交。Agent 會自動解析意圖、呼叫對應技能並於對話區域內傳回結果。
2. **多輪追問**：如需進一步分析，可在同一對話中繼續輸入追問（例如「其中華東區域 Top3 省份是哪些」或「東區的 top10 的客戶」）。

<!-- VISUAL_PENDING
visual_id: overview-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示透過對話向 Agent 提問並獲取業務資料的結果
production_method: recreate
ocr_text: |
  Data Agent
  连锁经营分析
-->

<!-- VISUAL_PENDING
visual_id: overview-002
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示多輪對話中對 Agent 進行連續追問的效果
production_method: recreate
ocr_text: |
  其中华东区域 Top3 省份是哪些
-->

<!-- VISUAL_PENDING
visual_id: dialog-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示輸入問題並發送的介面操作
production_method: recreate
ocr_text: "(原圖無 OCR 文字)"
-->

<!-- VISUAL_PENDING
visual_id: dialog-002
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示 Agent 分析並傳回結果的過程
production_method: recreate
ocr_text: "(原圖無 OCR 文字)"
-->

<!-- VISUAL_PENDING
visual_id: dialog-003
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示在對話中繼續追問的互動過程
production_method: recreate
ocr_text: |
  B2B市场潜量洞察Agent
  东区的top10 的客户
-->

### 建立新對話與歷史記錄
- **新聊天**：若要開啟全新的分析任務，請點選左側面板的『新聊天』按鈕。這將清空當前上下文。每次點選『新聊天』都會開啟獨立的上下文，Agent 不會記憶上一次的內容，若需連續追問請在同一對話中完成。
- **歷史記錄**：歷史對話記錄會顯示於左側面板，點選即可進入並繼續未完成的分析。

<!-- VISUAL_PENDING
visual_id: select-agent-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示 Data Agent 工作台中已發佈的 Agent 卡片及搜尋框位置
production_method: recreate
ocr_text: "(原圖無 OCR 文字)"
-->

<!-- VISUAL_PENDING
visual_id: new-chat-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示對話介面左側的『新聊天』按鈕及歷史對話記錄
production_method: recreate
ocr_text: "(原圖無 OCR 文字)"
-->

### 智慧糾正與重試
- **提問有誤時**：當您發現提問有偏差，而 Agent 已進入應答流程，可直接在對話框補發精簡正確的指令。Agent 會自動中斷原有任務，改按新問題重新應答。
- **回覆偏差時**：若輸出的結果存在錯誤或未達預期，您可直接提出異議、修正要求或調整指令策略。Agent 將自動復盤反思並重新生成合規結果。

<!-- VISUAL_PENDING
visual_id: correct-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示使用者提問有誤時直接補發修正指令中斷重新應答的效果
production_method: recreate
ocr_text: |
  不对，看张敏的
  星火计划人才画像 — 张敏
-->

<!-- VISUAL_PENDING
visual_id: correct-002
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示 Agent 回覆偏差時使用者提出修正要求並由 Agent 重新生成結果的效果
production_method: recreate
ocr_text: |
  快捷支付章节中，本年新增快捷支付绑卡户数的单位是万户，把报告中该部分的单位补齐
  已完成修正
-->

### 會話評價與分享
- **評價結果**：Agent 輸出內容後，您可以點選下方的按讚或倒讚圖示，即時對對話品質做出評價。
- **重新生成**：若因網路問題未成功輸出，或 Agent 關聯的資料、技能有調整，您可點選重新生成圖示讓 Agent 再次執行。
- **會話分享**：您可多選會話內容，透過連結分享給平台內的其他使用者查看。請注意，分享內容是以快照形式呈現，僅分享最終輸出結果，不包含 Agent 的思考分析過程。

<!-- VISUAL_PENDING
visual_id: session-op-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在會話氣泡下方進行按讚或倒讚評價的位置
production_method: recreate
ocr_text: |
  成本额、销售额
-->

<!-- VISUAL_PENDING
visual_id: session-op-002
role: icon
locale_sensitivity: none
brand_sensitivity: none
purpose: 展示重新生成按鈕的圖示樣式
production_method: reuse
ocr_text: "(原圖無 OCR 文字)"
-->

<!-- VISUAL_PENDING
visual_id: session-op-003
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示點選重新生成按鈕的效果
production_method: recreate
ocr_text: "(原圖無 OCR 文字)"
-->

<!-- VISUAL_PENDING
visual_id: session-op-004
role: decorative
locale_sensitivity: unknown
brand_sensitivity: unknown
purpose: 動圖展示如何多選會話內容並透過連結分享
production_method: reuse
ocr_text: "(原圖無 OCR 文字)"
-->
<!-- NEEDS_VISUAL_REVIEW -->

### 報告工作區 (Workspace)
當生成報告類 Agent 完成任務後，對話框右上角會自動展示『工作區』入口。這裡集中存放了 Agent 任務過程產出的檔案與最終報告。
- **通用操作**：無論是 Markdown、HTML 或 PPT 報告，皆支援切換輸出檔案、切換查看模式（原始碼/視覺化）以及在新頁面開啟。
- **複製內容**：僅支援 Markdown 和 HTML 報告，不支援 PPT 報告。
- **下載格式**：
  - Markdown 報告僅支援下載為 `.md` 格式。
  - HTML 報告僅支援下載為 `.html` 格式。
  - PPT 報告額外支援下載原始 PPT、PDF、頁面 ZIP 以及單獨下載當前頁。

<!-- 本頁已依品牌規則處理 3 條過濾項 -->
