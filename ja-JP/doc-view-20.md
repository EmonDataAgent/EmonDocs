<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: ja-JP
rendered_at: 2026-06-03T14:51:59Z
source_master: data/dora/locale/ja-JP/pages/doc-view-20.md
-->
---
page_id: doc-view-20
title: "オープン連携の概要"
locale: ja-JP
sourced_from_kus:
  - dora.open-integration.introduction.overview
generated_at: "2026-06-03T22:47:18+08:00"
---

## 概要

Data Agent は、外部 AI プラットフォーム（例：OpenClaw）との連携をサポートしています。API 連携機能を提供することで、企業の自動化分析のニーズにさらに対応します。

外部 AI プラットフォームとの連携により、以下の機能を実現します。
- Data Agent の分析によって生成されたチャートや帳票などのコンテンツを、定期的に担当者にプッシュ配信します。
- Agent を自動的にリリースします。
- セッションの履歴を自動的に検索します。

## 外部プラットフォームの連携

画面の指示に従い、「インストール対話を送信」>「連携対話を送信」>「連携ステータスを確認」の順に操作を完了すると、Data Agent と OpenClaw の連携が完了します。

## Key 管理

「Key 管理」ページで、OpenClaw にアクセス可能な以下のインターフェース権限を1つ以上選択すると、新しい OpenClaw アクセス Key を生成できます。

選択可能なインターフェース権限は以下の通りです。
- リリース済み Agent の詳細を確認 (openclaw:agents:detail)
- 対話を中断 (openclaw:interrupt)
- セッション履歴を検索 (openclaw:history)
- リリース済み Agent リストを検索 (openclaw:agents:list)
- セッションリストを検索 (openclaw:sessions:list)
- Skill リストを検索 (openclaw:skills:list)
- Agent 下書きを作成 (openclaw:agents:create)
- Agent をリリース (openclaw:agents:publish)
- ストリーミング対話 (openclaw:chat:sse)
- Agent の編集可能な設定を検索 (openclaw:agents:editable)
- Agent の設定を保存 (openclaw:agents:save)
- LLM 設定リストを検索 (openclaw:llm:configs:list)
- 対話 (openclaw:chat)

## 外部 MCP

Agent の作成プロセスにおいて、Agent が使用可能なデータやスキルツールの範囲を拡張するために使用します。
詳細については、[外部 MCP](/open-integration/mcp) をご確認ください。

## その他のデプロイ設定

Data Agent プラットフォームのデプロイが完了した後、以下の2つの操作を行う必要があります。
1. 「バックグラウンドアドレス」に対応する FineBI のアドレスを追加します。
2. 「接続テスト」をクリックして、FineAI プラグインと FineBI プラットフォームが相互通信でき、バージョンが一致していることを確認します。


