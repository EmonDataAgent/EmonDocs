---
page_id: "doc-view-48"
title: "常見問題排查"
locale: "zh-TW"
sourced_from_kus: 
  - "dora.troubleshooting.row-limit"
  - "dora.troubleshooting.token-consumption"
generated_at: "2026-06-03T22:47:20+08:00"
---
<!-- RENDERED
brand: emon
brand_display_name: Emon
locale: zh-TW
rendered_at: 2026-06-07T09:25:29Z
source_master: data/dora/locale/zh-TW/pages/doc-view-48.md
-->

## 1. 底層行資料限制

**問題詳情：**

透過直連模式連接至 PG (PostgreSQL) 資料庫時，觸發了底層 100 萬行資料的限制。

**排查步驟：**

1. 檢查 OrangeBI 的『系統管理 > BI參數 > 資料存取限制』，確認資料存取量的限制是否設定過低。
2. 調高資料存取量的限制設定。

## 2. 報告類技能 Token 消耗

**問題詳情：**

輸出一份中等長度的報告時，大約需要消耗多少額度的 Tokens？

**問題解答：**

使用『AI固定報告』技能，從輸入報告提示詞到輸出一份中等長度的報告，大約需要消耗 80 萬至 200 萬個 Tokens。


