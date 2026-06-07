---
page_id: doc-view-32
title: "FineReport 報表查詢技能"
locale: zh-TW
sourced_from_kus:
  - dora.skills.fr_report_query.concept
  - dora.skills.fr_report_query.setup
generated_at: 2026-06-03
---
<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-07T08:31:49Z
source_master: data/dora/locale/zh-TW/pages/doc-view-32.md
-->

# FineReport 報表查詢技能

## 功能簡介

對接 FineReport 平台後，支援報表搜尋、預覽、資料分析與參數調整。您無需手動翻找報表，在對話中直接提問即可呼叫 FR 工程中的報表資料。

- **報表搜尋與預覽**：透過自然語言描述快速定位目標報表並預覽內容。
- **報表資料分析**：對報表中的資料進行指標查詢、趨勢分析與對比彙總。

完成 Agent 設定並發佈後，即可在對話中直接呼叫已連接 FR 工程中的報表資料，進行搜尋、預覽與分析，無需切換至 FineReport 平台手動操作。

## 準備 FineReport 環境

在設定『FR 報表查詢』技能前，需先在目標 FR 工程中完成『FR 檢索外掛』安裝與範本檢索設定，確保 FR 工程具備被 Agent 呼叫的能力。

1. **安裝外掛**：下載並安裝 FR 檢索外掛。請勿解壓縮，直接安裝即可。安裝成功後，於跳出的對話方塊點選『確定』。
2. **模型設定**：安裝外掛後，點選『管理系統>範本檢索>模型設定』，配置大型語言模型與向量模型。設定完成後，點選『測試並連接』以保證模型可用。
3. **範本設定**：點選『管理系統>範本檢索>範本設定』，配置範本以產生中繼資料。

## 設定技能

1. 在 Data Agent 平台上，準備一個用於 FR 報表查詢與分析的 Agent。
2. 於『Agent 設定頁面>技能』中，選擇並新增『FR 報表查詢』技能。
3. 為技能設定所連接的 FR 工程，指定目前技能可存取的 FR 工程範圍。
4. 設定連接方式，支援從已建立的連接中選擇，或新建連接。
   - **已建立的連接**：在 Data Agent 平台中，其他 Agent 已建立的 FR 工程連接會被自動記錄，可直接複用，無需重複設定。
   - **建立連接**：若無可複用的歷史連接，點選『新建連接』以建立新的 FR 工程連接。請輸入自訂的『連接名稱』以利區分與快速識別，並填寫『FR 服務位址』（即已完成外掛安裝與設定的 FR 工程環境位址）。

<!-- 本頁已依品牌規則處理 4 條過濾項 -->
