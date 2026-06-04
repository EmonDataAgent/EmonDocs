<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/doc-view-28.md
-->
---
page_id: doc-view-28
title: "Dora 模型資源配置"
locale: zh-TW
sourced_from_kus:
  - dora.models.configuration.intro
  - dora.models.configuration.openai_compatible
  - dora.models.configuration.azure_compatible
  - dora.models.configuration.pricing
generated_at: "2026-06-03"
---

# Dora 模型資源配置

## 1. 簡介

本文將說明推薦在 Data Agent 中使用的主流大模型的配置項目與其收費標準。

## 2. OpenAI 兼容協議

> [!NOTE]
> 由於 API Key 為隱私內容，大模型平台可能只允許在建立時可見可複製 API Key。建議建立後立即複製，以免無法使用。

| 大模型 | 配置項目 |
| --- | --- |
| 通義千問 | - EndPoint（即 Base URL）：`https://dashscope.aliyuncs.com/compatible-mode/v1`<br>- API Key：註冊並登入官方控制台，完成 Token 訂閱並取得 API Key。<br>- 常用模型名稱：qwen-turbo、qwen-plus、qwen-max |
| DeepSeek | - EndPoint（即 Base URL）：`https://api.deepseek.com/v1`<br>- API Key：註冊並登入 DeepSeek 官方平台，進入『API keys頁面>建立 API Key>命名並生成』。<br>- 常用模型名稱：deepseek-v4-flash、deepseek-v4-pro |
| 智譜 GLM | - EndPoint（即 Base URL）：`https://open.bigmodel.cn/api/paas/v4`<br>- API Key：註冊並登入智譜 AI 開放平台，進入『API Key>建立 API Key』。<br>- 常用模型名稱：glm-4-flash、glm-5.1 |

## 3. Azure 兼容協議

Azure 兼容協議下，相關模型的 API Key 可共用同一套。取得步驟如下：

1. 註冊並登入 Azure 門戶。
2. 搜尋 Azure OpenAI。
3. 建立資源（需提交申請並審批)。
4. 進入『資源頁>金鑰和終端點』。
5. 複製 API Key。

建立詳情可參考官方文件。

| 大模型 | 配置項目 |
| --- | --- |
| Azure OpenAI<br>（GPT 系列） | - EndPoint（即 Base URL）：`https://{你的資源名}.openai.azure.com`<br>- API Version：2025-01-01-preview<br>- 常用模型名稱：gpt-4o、gpt-4o-mini、gpt-4.1、o1/o3-mini |
| Anthropic Claude<br>（Azure 託管） | - EndPoint（即 Base URL）：`https://<你的資源名>.cognitiveservices.azure.com/anthropic/v1`<br>- API Version：本模型下無需填寫<br>- 常用模型名稱：claude-opus-4.7、claude-sonnet-4.6、claude-haiku-4.5 |
| Google Gemini | - EndPoint（即 Base URL）：`https://<你的資源名>.cognitiveservices.azure.com/google/v1`<br>- API Version：本模型下無需填寫<br>- 常用模型名稱：gemini-3.1-pro、gemini-3.1-ultra |

## 4. 大模型 API 費率資訊

### 4.1 核心費率速覽

| 推薦模型 | 輸入價格<br>（元/百萬 Token） | 輸出價格<br>（元/百萬 Token） | 說明 |
| --- | --- | --- | --- |
| qwen3.6-plus<br>（滿血版） | 2（≤256K） / 8（>256K） | 12（≤256K） / 48（>256K） | - 支援思維鏈，100 萬 Token 上下文<br>- Batch 呼叫 5 折 |
| qwen3-max-preview<br>（滿血版） | 9（≤256K） / 15（>256K） | 54（≤128K） / 90（>128K） | - 支援思維鏈<br>- 上下文快取享折扣 |
| kimi-k2.6<br>（滿血版） | 6.5 | 27 | - 支援思維鏈<br>- 無 Token 區間價差 |
| glm-5.1<br>（滿血版） | 6（≤32K） / 8（>32K） | 24（≤32K） / 28（>32K） | - 支援思維鏈 |
| MiniMax-M2.7<br>（滿血版） | 2.1 | 8.4 | - 僅支援非思維模式，成本最低 |

### 4.2 費用計算公式

單次呼叫成本 =（輸入 Token 數 / 1000000 × 對應輸入單價）+（輸出 Token 數 / 1000000 × 對應輸出單價）

### 4.3 性價比參考

假設每條案例平均總量為 20000 Token，其中：
- 輸入：18000 Token
- 輸出：2000 Token
- 輸入輸出比例：9:1
- 不考慮思維鏈，僅按可見輸入/輸出 Token 計費

**計算範例（以 qwen3.6-plus 為例）：**
成本 = （18000 / 1000000 × 2）+（2000 / 1000000 × 12）= 0.036 + 0.024 = 0.06 元/條

| 推薦模型 | 單條用例成本（元） |
| --- | --- |
| MiniMax-M2.7（滿血版） | ≈ 0.055 |
| qwen3.6-plus（滿血版） | ≈ 0.060 |
| glm-5.1（滿血版） | ≈ 0.156 |
| kimi-k2.6（滿血版） | ≈ 0.171 |
| qwen3-max-preview（滿血版） | ≈ 0.270 |

<!-- 本頁已依品牌規則處理 1 條過濾項 -->
