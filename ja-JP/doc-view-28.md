<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: ja-JP
rendered_at: 2026-06-03T14:51:59Z
source_master: data/dora/locale/ja-JP/pages/doc-view-28.md
-->
---
page_id: doc-view-28
title: "Dora モデルリソース設定"
locale: ja-JP
sourced_from_kus:
  - dora.models.configuration.intro
  - dora.models.configuration.openai_compatible
  - dora.models.configuration.azure_compatible
  - dora.models.configuration.pricing
generated_at: "2026-06-03"
---

# Dora モデルリソース設定

## 1. 概要

本文では、Data Agent で推奨される主要な大規模言語モデル（LLM）の設定項目と料金体系について説明します。

## 2. OpenAI 互換プロトコル

> [!NOTE]
> API Key は機密情報であるため、プラットフォームによっては作成時にのみコピー可能です。使用できなくなることを防ぐため、作成後すぐにコピーしてください。

| 大規模言語モデル | 設定項目 |
| --- | --- |
| 通義千問 (Qwen) | - EndPoint（Base URL）：`https://dashscope.aliyuncs.com/compatible-mode/v1`<br>- API Key：公式コンソールに登録してログインし、Token の購読を完了して API Key を取得します。<br>- 一般的なモデル名：qwen-turbo、qwen-plus、qwen-max |
| DeepSeek | - EndPoint（Base URL）：`https://api.deepseek.com/v1`<br>- API Key：DeepSeek 公式プラットフォームに登録してログインし、「API keys>API Key の作成」から名前を付けて生成します。<br>- 一般的なモデル名：deepseek-v4-flash、deepseek-v4-pro |
| 智譜 GLM | - EndPoint（Base URL）：`https://open.bigmodel.cn/api/paas/v4`<br>- API Key：智譜 AI オープンプラットフォームに登録してログインし、「API Key>API Key の作成」に移動します。<br>- 一般的なモデル名：glm-4-flash、glm-5.1 |

## 3. Azure 互換プロトコル

Azure 互換プロトコルでは、関連モデルの API Key を共有できます。取得手順は以下の通りです。

1. Azure ポータルに登録し、ログインします。
2. Azure OpenAI を検索します。
3. リソースを作成します（申請と承認が必要です）。
4. 「リソースページ>キーとエンドポイント」に移動します。
5. API Key をコピーします。

作成の詳細は公式ドキュメントをご参照ください。

| 大規模言語モデル | 設定項目 |
| --- | --- |
| Azure OpenAI<br>（GPT シリーズ） | - EndPoint（Base URL）：`https://{あなたのリソース名}.openai.azure.com`<br>- API Version：2025-01-01-preview<br>- 一般的なモデル名：gpt-4o、gpt-4o-mini、gpt-4.1、o1/o3-mini |
| Anthropic Claude<br>（Azure ホスティング） | - EndPoint（Base URL）：`https://<あなたのリソース名>.cognitiveservices.azure.com/anthropic/v1`<br>- API Version：このモデルでは入力不要です<br>- 一般的なモデル名：claude-opus-4.7、claude-sonnet-4.6、claude-haiku-4.5 |
| Google Gemini | - EndPoint（Base URL）：`https://<あなたのリソース名>.cognitiveservices.azure.com/google/v1`<br>- API Version：このモデルでは入力不要です<br>- 一般的なモデル名：gemini-3.1-pro、gemini-3.1-ultra |

## 4. 大規模言語モデル API 料金情報

### 4.1 基本料金の概要

| 推奨モデル | 入力料金<br>（元/百万 Token） | 出力料金<br>（元/百万 Token） | 説明 |
| --- | --- | --- | --- |
| qwen3.6-plus<br>（完全版） | 2（≤256K） / 8（>256K） | 12（≤256K） / 48（>256K） | - CoT (思考の連鎖) をサポート、100 万 Token コンテキスト<br>- Batch 呼び出しで半額 |
| qwen3-max-preview<br>（完全版） | 9（≤256K） / 15（>256K） | 54（≤128K） / 90（>128K） | - CoT (思考の連鎖) をサポート<br>- コンテキストキャッシュ割引あり |
| kimi-k2.6<br>（完全版） | 6.5 | 27 | - CoT (思考の連鎖) をサポート<br>- Token 区間による価格差なし |
| glm-5.1<br>（完全版） | 6（≤32K） / 8（>32K） | 24（≤32K） / 28（>32K） | - CoT (思考の連鎖) をサポート |
| MiniMax-M2.7<br>（完全版） | 2.1 | 8.4 | - 非 CoT モードのみサポート、最も低コスト |

### 4.2 費用の計算式

1 回の呼び出しコスト =（入力 Token 数 / 1,000,000 × 入力単価）+（出力 Token 数 / 1,000,000 × 出力単価）

### 4.3 コストパフォーマンスの参考

1 つのケースにおける平均総量が 20,000 Token であると仮定します。
- 入力：18,000 Token
- 出力：2,000 Token
- 入力と出力の比率：9:1
- CoT を考慮せず、目に見える入出力 Token だけで課金します。

**計算例（qwen3.6-plus の場合）：**
コスト = （18,000 / 1,000,000 × 2）+（2,000 / 1,000,000 × 12）= 0.036 + 0.024 = 0.06 元/ケース

| 推奨モデル | 1 ケースあたりのコスト（元） |
| --- | --- |
| MiniMax-M2.7（完全版） | ≈ 0.055 |
| qwen3.6-plus（完全版） | ≈ 0.060 |
| glm-5.1（完全版） | ≈ 0.156 |
| kimi-k2.6（完全版） | ≈ 0.171 |
| qwen3-max-preview（完全版） | ≈ 0.270 |

<!-- 本頁已依品牌規則處理 1 條過濾項 -->
