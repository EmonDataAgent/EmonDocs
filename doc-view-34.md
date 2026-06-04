<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/doc-view-34.md
-->
---
page_id: doc-view-34
title: 圖表視覺化
locale: zh-TW
sourced_from_kus:
  - dora.skills.chart_visualization
---

## 1. 簡介

### 1.1 功能簡介

自動選擇圖表類型並產生視覺化圖表。

### 1.2 使用場景

在產生報告、問數分析等場景中，需要 Agent 分析並輸出可預覽圖表時，可以使用「圖表視覺化」技能。

### 1.3 效果預覽

以在問數場景中，要求 Agent 分析銷售額最高的門市銷售情況為例，效果如下所示：


## 2. 設定步驟

以問數分析場景為例。

### 2.1 準備 Agent

在 Data Agent<!-- AUTHOR_NOTE: 疑似品牌/產品名 "Data Agent" 未列於 tokenization-rules，保留原樣 --> 平台上，準備一個問數分析的 Agent。

### 2.2 新增技能

在「Agent 設定頁面 > 技能」中，選擇並新增「圖表視覺化」與「分析主題資料查詢」技能。

### 2.3 注意事項

1）圖表視覺化的地圖生成功能需連網使用。本地部署使用者，請將以下兩個網域加入存取白名單：

- `antv-studio.alipay.com`
- `mdn.alipayobjects.com`

## 3. 效果預覽

將 Agent 成功發佈後，可在對話中體驗效果，詳細效果請參考【1.3 效果預覽】。


