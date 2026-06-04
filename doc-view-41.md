<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/doc-view-41.md
-->
---
page_id: "doc-view-41"
title: "報告生成類技能對比"
locale: "zh-TW"
sourced_from_kus:
  - "dora.skill-orchestration.report-generation.comparison"
generated_at: "2026-06-03"
---

## 1. 技能對比

報告生成共包含以下幾種類型的技能：

| 技能名稱 | 簡介 | 典型場景 |
| --- | --- | --- |
| html報告 | 基於文本內容、分析結論，動態生成可預覽的 HTML 報告。 | 開放式報告生成，支援 AI 自主探索內容方向，無格式限制。 |
| 從模板創建html報告 | 基於上傳的 HTML 模板與結構化資料來源（Excel/CSV），生成客製化 HTML 報告。 | 適用於有固定格式約束的報告生成，需要 AI 嚴格遵循模板輸出。 |
| PPT報告 | 基於文件、大綱、主題等輸入內容，生成結構化 PPT。 | 快速生成銷售、工作彙報類 PPT 材料。 |
| [PPTX模板填充](https://help.fanruan.com/finereport/doc-view-50.html) | 支援使用者上傳預先處理後的 PPT 模板，透過配置 AI 提示詞並綁定儀表板資料，自動生成標準化的 PPT 報告。 | 適用於有固定 PPT 格式的需求，輸出標準化 PPT 報告。 |
| [AI固定報告](https://help.fanruan.com/finereport/doc-view-21.html) | 基於預先配置的報告大綱與關聯資料來源，自動整合資料並生成標準化分析報告。 | - 通用總結、歸因、對比等標準化分析報告。<br>- 基於本機模板生成固定排版的硬編排報告。 |

## 2. 設定步驟

1. 在 Data Agent 平台上準備一個用於報告生成的 Agent。
2. 在『Agent 配置頁面 > 技能』中，根據您的使用場景需求，添加『報告生成』分類下合適的技能。
3. 若添加了『AI固定報告』或『PPTX模板填充』技能，請對該技能進行詳細配置。

詳細配置請參考：[AI固定報告](https://help.fanruan.com/finereport/doc-view-21.html)、[PPTX模板填充](https://help.fanruan.com/finereport/doc-view-50.html)。


<!-- AUTHOR_NOTE: "Data Agent" 未在 tokenization-rules 提及，保留原樣。 -->
