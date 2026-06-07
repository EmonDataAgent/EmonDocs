<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: ja-JP
rendered_at: 2026-06-03T14:51:59Z
source_master: data/dora/locale/ja-JP/pages/doc-view-48.md
-->
---
page_id: "doc-view-48"
title: "よくある質問とトラブルシューティング"
locale: "ja-JP"
sourced_from_kus: 
  - "dora.troubleshooting.row-limit"
  - "dora.troubleshooting.token-consumption"
generated_at: "2026-06-03T22:47:20+08:00"
---

## 1. 最下層行データ制限

**問題の詳細：**

直接接続モードでPG(PostgreSQLデータベース)に接続する際、最下層の100万行データ制限がトリガーされます。

**トラブルシューティング手順：**

1. FineBIの「システム管理」>「BIパラメータ」>「データアクセス制限」を確認し、データアクセス量の制限値が低すぎないか確認します。
2. データアクセス量の制限値を引き上げます。

## 2. レポート類スキルのToken消費

**問題の詳細：**

中程度の長さのレポートを出力する場合、どの程度のTokensを消費しますか。

**回答：**

「AI固定レポート」スキルを使用し、レポートのプロンプトを入力して中程度の長さのレポートを出力する場合、およそ80万〜200万Tokensを消費します。


