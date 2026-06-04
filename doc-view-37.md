<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/doc-view-37.md
-->
---
page_id: doc-view-37
title: 儀表板檢索
locale: zh-TW
sourced_from_kus: 
  - dora.dashboard_search.concept.intro
  - dora.dashboard_search.procedure.setup
generated_at: "2026-06-03T22:47:19+08:00"
---

## 1. 簡介

### 1.1 功能簡介

儀表板檢索技能可於已綁定的儀表板範圍內檢索資產數據，以回答指標查詢、趨勢分析與對比彙整等業務問題。

### 1.2 使用場景

- **看板查數**：針對已綁定儀表板中的圖表與指標，直接提問以獲取數值、排名、同比及環比等數據。
- **報告生成**：基於儀表板數據，自動彙整關鍵指標與趨勢變化，並輸出結構化的分析報告。

### 1.3 效果演示

以發佈 Agent 至 FineBI 平台為例，可以實現儀表板檢索的效果。

## 2. 設定步驟

### 2.1 使用前準備

1. **確認 ElasticSearch 元件版本**：請確保將 ElasticSearch 元件升級至 v20.4.5-8.17.3 及以上版本，並確保元件處於 running 狀態。
2. **自訂 ElasticSearch 元件環境變數**：請透過開發者模式，自訂 ElasticSearch 元件的環境變數，並將 `INSTALL_FINE_PLUGIN` 的值修改為 `yes`。

### 2.2 準備 Agent

在平台上建立一個用於儀表板查數分析的 Agent，並完成儀表板數據的添加。

### 2.3 添加技能

進入「Agent 配置頁面 > 技能」，選擇並添加「儀表板檢索」技能。

### 2.4 配置技能

選擇技能可檢索的儀表板範圍，以鎖定數據邊界。限定範圍可避免以下兩類問題：
- 範圍過小：導致查詢無數據返回。
- 範圍過大：導致無關數據干擾結果，並增加 token 消耗。

### 2.5 發佈 Agent

完成上述配置後，可透過不同的發佈方式發佈 Agent，使其對終端使用者可用。Agent 支援發佈至以下三個渠道，各渠道的使用方式與適用場景如下：

| 發佈方式 | 使用者使用方式 | 適用場景 |
| --- | --- | --- |
| **工作台** | 在 Data Agent 平台以會話形式，對已綁定儀表板的數據進行提問與分析。 | Data Agent 平台內部使用者，日常查數與分析。 |
| **獨立 URL** | 透過獨立連結存取 Agent，以會話形式進行提問與分析。 | 需向外部人員分享 Agent，且無需登入 Data Agent 平台的場景。 |
| **FineBI 平台** | 在 FineBI「目錄」中，於 Agent 可見範圍內的儀表板頁面透過側邊欄喚起 Agent，直接提問分析。 | FineBI 使用者在瀏覽看板的過程中即時提問，無需切換頁面。 |

<!-- 本頁已依品牌規則處理 2 條過濾項 -->
