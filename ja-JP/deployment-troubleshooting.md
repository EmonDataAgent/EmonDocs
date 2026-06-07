---
page_id: deployment-troubleshooting
title: "Emon デプロイメントとトラブルシューティング"
locale: ja-JP
sourced_from_kus:
  - dora.deployment.data-agent
  - dora.deployment.troubleshooting.row_limit
  - dora.deployment.troubleshooting.report_token_consumption
  - dora.llm.troubleshooting.prechecks
  - dora.llm.troubleshooting.connection_test_fails
  - dora.llm.troubleshooting.timeout_or_no_response
  - dora.llm.troubleshooting.tool_call_unsupported
  - dora.llm.troubleshooting.http_422_error
  - dora.llm.troubleshooting.system_content_error
  - dora.llm.troubleshooting.azure_endpoint_error
  - dora.llm.troubleshooting.context_length_insufficient
  - dora.llm.troubleshooting.azure_content_safety
  - dora.llm.troubleshooting.service_unavailable
  - dora.llm.troubleshooting.insufficient_balance
generated_at: "2026-06-07T17:28:15+08:00"
---
<!-- RENDERED
brand: emon
brand_display_name: Emon
locale: ja-JP
rendered_at: 2026-06-07T09:39:36Z
source_master: data/dora/locale/ja-JP/pages/deployment-troubleshooting.md
-->

# Emon デプロイメントとトラブルシューティング

本ドキュメントでは、Data Agentのデプロイメントガイドと、大規模言語モデルに関する一般的な問題のトラブルシューティング手順を提供します。

## Data Agent デプロイメントガイド

OrangeBIとData Agentは順番にデプロイする必要があります。まず運用プラットフォームを使用してOrangeBIをデプロイします。

### 1. 前提条件と環境要件

Data AgentおよびOrangeBIは運用プラットフォームを通じてデプロイする必要があります。
- 運用プラットフォームのバージョンはV2.26.0以上である必要があります。イントラネット環境では、OrangeBI関連のコンポーネントイメージを取得するために、完全版のオフラインインストーラーを使用して運用プラットフォームをデプロイする必要があります。
- OrangeBIのバージョンは7.0.7以上である必要があり、デプロイ方法は必ず「運用プラットフォームデプロイ」を選択してください。「非運用プラットフォームデプロイ」はサポートされていません。
- OSはLinux（X86_64およびARMアーキテクチャをサポート）であり、カーネルバージョン3.10以上が必要です。推奨OSはUbuntu 22です。
- サーバにはtarコマンドとsedコマンドがインストールされている必要があります。デプロイに使用するユーザはsudo権限を持っている必要があり、rootスーパーユーザの使用を強く推奨します。また、ユーザのSSH接続パスワードに半角シングルクォーテーション（'）が含まれていないことを確認してください。
- 仮想マシン環境でのEmon Corpアプリケーションのデプロイは推奨されません。リソース競合によるシステム障害が発生する可能性があります。また、Kubernetes環境でのData Agentコンポーネントのデプロイはサポートされていません。

### 2. サーバの推奨設定

必要なリソースが多く、将来的に大規模言語モデルの追加が見込まれるため、Data Agent専用のサーバを用意することをお勧めします。
- **推奨構成（AIコンポーネント専用サーバ）**：CPU16コア、空きメモリ64GB、空きディスク領域100GB。
- **最低構成（OrangeBIプロジェクトと共用）**：CPU8コア、空きメモリ16GB、空きディスク領域80GB。
- Data Agentコンポーネントサーバの時刻およびタイムゾーンは、他のプロジェクトサーバと完全に一致している必要があり、時刻の誤差は5秒以内でなければなりません。
- 必要なポートを開放してください：{{PRODUCT_FINEAI}}（7666）、意味解析小規模モデル（8666）、{{PRODUCT_FINEAI}} Redis（6679）。

### 3. Data Agent イメージの準備とアップロード

Data Agentのイメージはクラウドリポジトリから直接取得できないため、手動でリポジトリにプッシュする必要があります。

1. 公式サイトまたは関連チャネルから{{PRODUCT_FINEAI}}コンポーネントと{{PRODUCT_FINECHATBI}}意味解析小規模モデルのコンポーネントイメージを取得します。
2. 運用プラットフォームにログインし、デプロイ情報をエクスポートしてresourcesフォルダのパスを確認します。
<!-- VISUAL_PENDING
visual_id: upload-export-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 運用プラットフォームでデプロイ情報をエクスポートし、リソースディレクトリパスを確認する操作を示します。
-->
3. ダウンロードした2つのイメージパッケージ（.tar.gz）をサーバのresourcesフォルダにアップロードします。
<!-- VISUAL_PENDING
visual_id: upload-folder-001
role: screenshot
locale_sensitivity: none
brand_sensitivity: none
purpose: イメージファイルをサーバのresourcesフォルダにアップロードする操作を示します。
-->
4. 運用プラットフォームの「メンテナンスセンター > イメージ管理」で「イメージのロード」をクリックし、アップロードしたイメージをリポジトリにプッシュします。
<!-- VISUAL_PENDING
visual_id: load-image-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 運用プラットフォームでアップロードしたイメージファイルをロードする操作を示します。
-->
5. 新しいイメージのバージョン番号を確認して記録し、「アップデート/アップグレード > デプロイリスト > 手動変更」で対応するAIコンポーネントのバージョン番号をイメージ管理のものと完全に一致するように修正します。
<!-- VISUAL_PENDING
visual_id: image-version-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: イメージ管理でプッシュされた新しいイメージのバージョン番号を確認する操作を示します。
-->
<!-- VISUAL_PENDING
visual_id: update-version-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 運用プラットフォームでAIコンポーネントのデプロイバージョン番号を手動で変更する操作を示します。
-->
6. イメージリポジトリにv20.3.0-6.2.17以上のバージョンのredisイメージが存在することを確認します。
<!-- VISUAL_PENDING
visual_id: check-redis-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: イメージ管理でredisのイメージバージョンを確認する操作を示します。
-->

### 4. コンポーネントのデプロイ

1. 運用プラットフォームの「メンテナンス > コンポーネント管理」で「コンポーネントの追加」をクリックし、「ビジネスサービス > AI」を選択します。
<!-- VISUAL_PENDING
visual_id: add-component-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 運用プラットフォームでビジネスサービスコンポーネントを追加する操作画面を示します。
-->
2. ノード情報を入力し、要件を満たすAIコンポーネントサーバを追加します。
<!-- VISUAL_PENDING
visual_id: add-node-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 新規ノードの追加画面とディスク要件を示します。
-->
<!-- VISUAL_PENDING
visual_id: select-node-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: ノードを選択してリソースを確認する画面を示します。
-->
3. 各AIコンポーネントのポート設定を確認・調整します。また、{{PRODUCT_FINEAI}} Redisコンポーネントのパスワードはデフォルトでランダム生成され、デプロイ成功後は変更できないため、必ずデプロイ前にパスワードを変更してください。設定完了後、「デプロイ開始」をクリックします。
<!-- VISUAL_PENDING
visual_id: component-config-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: Data Agent各コンポーネントのホストポートとパスワードを設定する操作を示します。
-->

### 5. ElasticSearch コンポーネントのアップグレードと設定

1. ElasticSearchコンポーネントがv20.4.5-8.17.3以上のバージョンであり、「running」状態であることを確認します。
<!-- VISUAL_PENDING
visual_id: check-es-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 運用プラットフォームでElasticSearchコンポーネントのバージョンと実行状態を確認する操作を示します。
-->
2. 開発者モードを通じてElasticSearchコンポーネントの環境変数をカスタマイズし、INSTALL_FINE_PLUGINの値をyesに変更します。
<!-- VISUAL_PENDING
visual_id: env-es-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 開発者モードでElasticSearchの環境変数を変更する操作を示します。
-->

### 6. Data Agent プラグインのインストールと接続テスト

1. OrangeBIの「システム管理 > プラグイン管理 > アプリストア」で「ローカルからインストール」をクリックし、ダウンロードしたData Agentプラグインのインストールパッケージをアップロードします。
<!-- VISUAL_PENDING
visual_id: install-plugin-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: FineBIプラグイン管理でローカルからData Agentプラグインをインストールする操作を示します。
-->
2. Emon Corp営業担当に連絡してData Agentのライセンスを取得し、インストールします。
3. プラグインのインストールとライセンス付与が完了すると、OrangeBIの右上に「Data Agent」ボタンが表示されます。
<!-- VISUAL_PENDING
visual_id: check-success-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: Data Agentボタンが表示され、設定が成功したことを確認する画面を示します。
-->
4. 「Data Agent管理バックエンド > オープンインテグレーション > その他」にアクセスし、バックエンドアドレスにOrangeBIアドレスを追加して「接続テスト」をクリックし、通信が正常であることを確認します。
<!-- VISUAL_PENDING
visual_id: test-connection-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: バックエンドアドレスを追加し、接続テストをクリックする操作を示します。
-->
5. 「Data Agent管理バックエンド > モデル」にアクセスし、追加した対象の大規模言語モデルに対して接続テストを実施します。
<!-- VISUAL_PENDING
visual_id: test-model-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: モデル管理ページで接続テストをクリックし、モデルが利用可能であることを確認する操作を示します。
-->

💡 ヒント:
従来の{{PRODUCT_FINECHATBI}}コンポーネントをData Agentにアップグレードする場合は、まず最新のAIイメージパッケージをリポジトリにプッシュし、「コンポーネント管理」からアップグレードを行うことでスムーズに移行できます。
<!-- VISUAL_PENDING
visual_id: component-update-001
role: diagram
locale_sensitivity: high
brand_sensitivity: none
purpose: 運用プラットフォームで従来の{{PRODUCT_FINECHATBI}}コンポーネントをアップグレードする操作を示します。
-->

## 大規模言語モデルの接続トラブルシューティング

### 1. 前置チェック

大規模言語モデルのパラメータや並行処理能力が推奨要件を満たしているか確認します。また、{{PRODUCT_FINEAI}}プラグインとOrangeBIプラットフォームの通信テスト、および大規模言語モデルの接続テストが完了していることを確認します。

### 2. 接続テスト失敗

大規模言語モデルの接続テストが失敗した場合、ブラウザの開発者ツール（F12）を開き、testリクエストのレスポンスにあるerror_messageフィールドを確認してください。これにより、OrangeBIが{{PRODUCT_FINEAI}}に接続できないのか、{{PRODUCT_FINEAI}}がOrangeBIに接続できないのかを特定できます。
<!-- VISUAL_PENDING
visual_id: connection-test-fail-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: F12開発者ツールでtestリクエストのレスポンスを確認する手順を示します。
-->

### 3. 応答なし、またはタイムアウト

Emonが正常に応答しない、またはリクエストがタイムアウトする場合は、通常ネットワーク通信に問題があります。{{PRODUCT_FINEAI}}は直接大規模言語モデルと通信できますが、BI-Webは{{PRODUCT_FINEAI}}と双方向で通信する必要があります。
- {{PRODUCT_FINEAI}}ノードが正常に実行されているか確認します。
- 接続テストが失敗する場合は、F12のerror_messageを確認して切断箇所を特定してください。

### 4. 最初の通信でエラーになり、2回目は正常

この現象は、現在の大規模言語モデルがtool_callをサポートしていないことが原因です。Emonはtool_callに依存しているため、モデルがサポートしていない場合は別のモデルに変更する必要があります。
- tool_callを含むcurlコマンドでテストし、エラーになるか確認します。
- tool_callを含まないcurlコマンドでテストし、正常に応答するか確認します。

### 5. リクエストが 422 ステータスコードを返す

デプロイされた大規模言語モデルがOpenAIのインターフェースプロトコル仕様に準拠していない可能性があります。インターフェースのログを取得し、開発担当者に調査を依頼してください。

### 6. system content フィールドのエラー

一部の大規模言語モデルはsystem contentの形式として文字列（string）のみをサポートしています。現在使用しているモデルに形式の制限があるか確認し、必要に応じてリクエスト形式を調整してください。

### 7. Azure OpenAI の接続エラー

Azureはresponses API形式のエンドポイントをサポートしていないため、接続テストが失敗することがあります。エンドポイントをbase URL形式に変更することで接続可能になります。

### 8. ai-server-error エラー

大規模言語モデルのコンテキストの長さが不足しています。モデルのコンテキスト長が最低要件である128Kを満たしているか確認してください。

### 9. Azure モデルの応答異常または中断

Azureモデルにはデフォルトでコンテンツの安全性をチェックするメカニズムがあり、特定のキーワードをトリガーすると応答が中断されます。拒否キーワードを避けるように質問内容を変更してください。

### 10. モデルへのアクセス不可

モデルサービスの負荷が高すぎることが原因です。しばらく待ってから再試行してください。また、推奨モデルの並行処理とパフォーマンスのリファレンスを参照し、モデルの負荷状況を評価してください。

### 11. 残高不足によるエラー

大規模言語モデルの利用料金が未払い、または残高が不足しています。チャージ後に再度お試しください。

## よくある質問

### 底層の行データ制限（PostgreSQL）

直接接続モードでPostgreSQLデータベースに接続する場合、基盤となる100万行のデータ制限がトリガーされることがあります。
- OrangeBIの「システム管理 > BIパラメータ > データアクセス制限」を確認し、設定値が低すぎないか確認します。
- データアクセスの制限値を増やしてください。
<!-- VISUAL_PENDING
visual_id: row-limit-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 100万行のデータ制限がトリガーされた際のエラーメッセージを示します。
-->
<!-- VISUAL_PENDING
visual_id: row-limit-002
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: システム管理でデータアクセス制限を引き上げる設定箇所を示します。
-->

### レポート関連スキルのトークン消費量

「AI固定レポート」スキルを使用してプロンプトを入力し、中程度の長さのレポートを出力する場合、約80万〜200万トークンが消費されます。


