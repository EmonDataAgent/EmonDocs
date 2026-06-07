---
page_id: doc-view-34
title: チャート可視化
locale: ja-JP
sourced_from_kus:
  - dora.skills.chart_visualization
---
<!-- RENDERED
brand: emon
brand_display_name: Emon
locale: ja-JP
rendered_at: 2026-06-07T09:25:29Z
source_master: data/dora/locale/ja-JP/pages/doc-view-34.md
-->

## 1. 概要

### 1.1 機能の概要

自動的にチャートタイプを選択し、可視化チャートを生成します。

### 1.2 利用シーン

レポートの生成やデータクエリ分析などのシーンで、Agent が分析してプレビュー可能なチャートを出力する必要がある場合、「チャート可視化」スキルを使用できます。

### 1.3 効果プレビュー

データクエリシーンにおいて、Agent に最も売上高の高い店舗の売上状況を分析させる場合を例とします。効果は以下の通りです：


## 2. 設定手順

データクエリ分析シーンを例とします。

### 2.1 Agent の準備

Data Agent<!-- AUTHOR_NOTE: 疑似ブランド/製品名 "Data Agent" が tokenization-rules にないため、そのまま保持しています --> プラットフォーム上で、データクエリ分析用の Agent を準備します。

### 2.2 スキルの追加

「Agent 設定ページ > スキル」にて、「チャート可視化」および「分析テーマデータクエリ」スキルを選択して追加します。

### 2.3 注意事項

1）チャート可視化の地図生成機能は、ネットワークに接続して使用する必要があります。オンプレミス展開のユーザーは、以下の2つのドメインをアクセスホワイトリストに追加してください：

- `antv-studio.alipay.com`
- `mdn.alipayobjects.com`

## 3. 効果プレビュー

Agent の公開が成功した後、会話内で効果を体験できます。詳細は【1.3 効果プレビュー】をご参照ください。


