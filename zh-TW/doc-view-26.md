---
page_id: doc-view-26
title: 推薦大模型
locale: zh-TW
sourced_from_kus:
  - dora.models.recommendations.doc-view-26
generated_at: "2026-06-03"
---
<!-- RENDERED
brand: emon
brand_display_name: Emon
locale: zh-TW
rendered_at: 2026-06-07T09:25:29Z
source_master: data/dora/locale/zh-TW/pages/doc-view-26.md
-->

## 1. 簡介

Data Agent 支援連接符合 OpenAI/Azure 介面規範的本地大模型以及雲端大模型。

**免責聲明：**Emon Corp 僅提供大模型的推薦參考及對接方式，不對大模型本身的問題承擔責任。

## 2. 模型要求

### 2.1 參數要求

- 必須支援 `tool_call`。
- 模型尺寸：優先推薦滿血版，最低需滿足 235B 參數數量。
- 大模型上下文長度要求：需支援 ≥ 128k tokens 上下文視窗。

### 2.2 併發效能

- 大模型每分鐘處理可處理的 Token 吞吐量（TPM）要求：需保證 TPM ≥ 20w tokens。
- 單併發推薦：每分鐘輸入 Token 約 20w，輸出 1~2k。
- 單步消耗：20k~30k Token，每分鐘可執行 5~7 步。
- TPM 為理論上限，實際使用會略低。

## 3. 推薦模型

推薦優先使用滿血版（完整參數版本）模型，以下模型表現較好：

- qwen3.6-plus（優先滿血版）
- qwen3-max-preview（優先滿血版）
- kimi-k2.6（優先滿血版）
- glm-5.1（優先滿血版）
- MiniMax-M2.7（優先滿血版）

注：大模型的配置與定價可參考文件：[模型資源配置](doc-view-28.md)。

## 4. 不推薦模型

- **qwen3.5 系列**：模型存在已知嚴重 BUG。
- **deepseek-v3、deepseek-v3.1**
- **其他參數數量低於 235B 的小模型**

## 5. 場景選擇

1）準確性優先場景

| 適用場景 | 推薦模型 | 注意事項 |
| --- | --- | --- |
| - 財務報表查詢<br>- 合規資料核對<br>- 報告分析產生<br>- 關鍵業務決策支援 | qwen3-max-preview（優先滿血版） | 不適合對即時性要求極高的場景 |

2）速度與穩定性優先場景

| 適用場景 | 推薦模型 | 注意事項 |
| --- | --- | --- |
| - 高頻資料查詢<br>- 大批量併發呼叫 | qwen3.6-plus（優先滿血版） | 不適合複雜金融查詢場景 |

3）日常輕量查詢場景

| 適用場景 | 推薦模型 | 注意事項 |
| --- | --- | --- |
| - 簡單資料檢索<br>- 日常報表檢視<br>- 非關鍵業務查詢 | qwen3-max-preview（優先滿血版） | 不適合複雜資料查詢、報告分析場景 |

4）成本敏感場景

| 適用場景 | 推薦模型 | 注意事項 |
| --- | --- | --- |
| - 預算有限<br>- 對準確性要求適中 | - deepseekV3.2<br>- qwen3.6-35b-a3b<br>- MiniMax M2.5 | 穩定性和效果呈現較為一般 |


