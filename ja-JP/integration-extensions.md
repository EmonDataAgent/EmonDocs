---
page_id: integration-extensions
title: "Emon統合とサードパーティ拡張"
locale: ja-JP
sourced_from_kus:
  - dora.integration.openclaw
  - finereport.integration.external-mcp
  - dora.wecom.app_integration
  - finereport.skills.im-integration
generated_at: "2026-06-07T17:28:15+08:00"
---
<!-- RENDERED
brand: emon
brand_display_name: Emon
locale: ja-JP
rendered_at: 2026-06-07T09:39:36Z
source_master: data/dora/locale/ja-JP/pages/integration-extensions.md
-->

# 統合とサードパーティ拡張

このページでは、Emonプラットフォームを外部のAIプラットフォームやMCP (Model Context Protocol) サービス、および企業向けメッセージングアプリ（IM）と統合する方法について説明します。

## オープン統合 (OpenClawとMCP)

Data Agent（<!-- AUTHOR_NOTE: Data Agentは製品内用語として保持しています -->）は、OpenClawなどの外部AIプラットフォームとの連携、およびMCPを通じた機能拡張をサポートしており、APIの接続機能を開放しています。

### 外部AIプラットフォーム（OpenClaw）の統合

外部のAIプラットフォームと連携することで、Data Agentが分析・生成したチャートやレポートをスケジュールに沿って担当者に自動プッシュしたり、Agentの自動公開、履歴セッションの自動照会などを実現できます。

**統合手順：**
1. **プラットフォームの連携**: 画面の指示に従い、「インストール対話の送信」>「統合対話の送信」>「統合状態の確認」の順に操作し、Data AgentとOpenClawの統合を完了させます。
2. **アクセスキーの生成**: 「Key管理」ページで、OpenClawからアクセス可能なAPI権限（Agent公開やセッション照会など）にチェックを入れ、新しいOpenClawアクセスキーを生成します。
3. **バックエンドアドレスの設定**: Data Agentプラットフォームのデプロイ後、「バックエンドアドレス（后台地址）」に対応するOrangeBIのアドレスを追加します。
4. **接続テスト**: 追加後、「接続テスト」をクリックし、FineAIプラグインとOrangeBIプラットフォーム間で通信が正常に行われ、バージョンが一致していることを確認します。

### 外部MCPサービスの設定

外部MCP機能を使用すると、Agentが外部ツールを呼び出したり、外部データを取得したりできるようになり、機能の柔軟な拡張とエコシステムの統合が可能になります。有効化されたすべてのMCPサービスは、自動的にAgentに配信されます。

**MCPの追加と設定手順：**
1. 管理者として、「管理バックエンド > オープン統合 > 外部MCP」にアクセスします。
2. ページ右上の「MCPの追加」をクリックします。
3. 外部MCPサービスの仕様に合わせて以下の情報を入力します：
   - **名称**: 日本語や全角文字を含めないことを推奨します（説明は「記述」欄に記載してください）。
   - **伝送方式（伝送プロトコル）**: HTTP（標準的なREST API用）、SSE（サーバからのデータプッシュ、リアルタイムストリーミング用）、STDIO（ローカルプロセス用）から、外部サービスに適合するものを選択します。不一致の場合、接続に失敗します。
   - **URL**: 対象のサービスURL。
   - **リクエストヘッダー**: 認証などのヘッダー情報をJSON形式で入力します。※ MCPサーバがOrangeBIのユーザ名による認証をサポートしている場合、`{"fine_username": "${fine_username}"}`のように設定できます。
   - **状態**: 有効 / 無効 を選択します。
4. 「OK」をクリックして設定を保存します。

> **注意**:
> * 同種のMCPや、Emonの組み込みスキルと重複する能力を追加しないでください。誤検知や呼び出し精度の低下を招く恐れがあります。
> * サービスを「無効」にすると、Agentから該当機能が直ちに呼び出せなくなります。影響範囲を事前に評価してから無効化してください。
> * 対象のMCPが見つからない場合は、伝送プロトコルが正しいか、MCPの有効期限が切れていないか、URLアドレスが正しいかを順に確認してください。

## 企業向けメッセージングアプリの統合 (企業微信など)

IM（インスタントメッセージング）ツールの連携は、AgentをサードパーティのIMボットとバインドし、クロスプラットフォームでの対話を可能にする機能です。現在、企業微信（WeCom）のボット連携をサポートしており、今後はDingTalkやFeishuへの対応を予定しています。

IMツールと連携することで、シングルチャットでの個人的なデータ照会や、グループチャット内でAgentをメンション（@）してのチーム連携が可能になります。ボットの応答はリッチテキストメッセージカードに対応し、主要な数値や簡易的なグラフ（棒グラフ、折れ線グラフなど）を表示できます。また、複数回のやり取り（マルチターン対話）をサポートしており、コンテキストは常に保持されるため、ボットはこれまでの文脈を踏まえて一貫性のある回答を提供します。

連携は大きく分けて、「アプリケーションの構築とマッピング」および「ボットの作成と紐付け」の2段階で行います。

### 前提条件
* 企業微信の管理バックエンド権限を持っていること。
* Emonサービス用のドメイン名が設定されていること。
* Emonサービスの外部公開IP（出口IP）を把握していること（企業微信の信頼できるIP構成に使用します）。

### 1. アプリケーションの構築とユーザマッピング

プラットフォームとIMツール間でユーザをマッピングするために、企業微信側で自社開発アプリ（自建应用）を作成します。※この手順を順番通りに完了しないと、システムで企業微信のユーザ名/IDを照合できません。

1. **アプリの作成**: 企業微信の管理者として管理バックエンドにログインし、「アプリ管理 > アプリ > 自社開発（自建）」から新しいアプリを作成します。ロゴ、名称、および可視範囲を設定します（可視範囲にはロボットを使用するメンバー/部門を含め、全社を選択することを推奨します）。
2. **API受信の設定（一時取得）**: アプリの構成詳細ページ「機能 > メッセージ受信」から「API受信の設定」を開きます。受信URL（例: `https://{ドメイン名}/{BIサービスサフィックス}/external/api/im/config/wecom/callback`）を入力し、TokenとEncodingAESKeyの「ランダム取得」をクリックします。**※この時点ではまだ企業微信側で保存しないでください。**
3. **IMユーザマッピング**: 特権管理者としてEmonの「管理バックエンド > ユーザ管理 > IMユーザマッピング」に移動します。アプリ連携の構成ボタンをクリックし、先ほど取得したTokenとEncodingAESKeyを入力して「次へ」をクリックし、マッピングを完了させます。
4. **API受信の保存**: 企業微信のバックエンドに戻り、API受信設定を「保存」します。
5. **信頼できるIPの設定**: 企業微信アプリの構成ページ内、「開発者インターフェース > 企業の信頼できるIP」で「構成」をクリックし、Emonサービスの外部公開IPアドレスを追加して確定し、ホワイトリストの構成を完了します。
6. **Secretと企業IDの取得**:
   - アプリの構成ページ内「Secret」の表示をクリックし、`CorpSecret`を取得します。
   - 「マイエンタープライズ（我的企业） > 企業情報」ページ下部にスクロールし、`企業ID (CorpId)`を取得します。
7. **連携の完了**: Emonの管理バックエンドの画面に戻り、`CorpSecret`と`CorpId`を入力して「接続テストして保存」をクリックします。「構成済み」と表示されれば設定完了です。

### 2. スマートボットの作成と紐付け

1. **ボットの作成**: 最新版の企業微信で「連絡先 > スマートボット」を開き、Emonプラットフォームへの接続用スマートボットを「手動作成（手动创建）」します。
2. **APIモードへの切り替え**: ボットの作成ページを最下部までスクロールし、「APIモードで作成」に切り替えます。
3. **接続方法の設定**: ボットの名称と利用可能なメンバーを設定します。API構成にて「長接続を使用（使用长连接）」を選択し、`Bot ID`をコピーし、`Secret`を取得します。
4. **Agentへの登録**: Data Agentプラットフォームの「Agent構成ページ > IMツールの連携」から「企業微信ボット」の追加を選択し、コピーした`Bot ID`と`Secret`を入力します。
5. **テスト**: 設定完了後、企業微信上でボット宛にテストメッセージを送信し、インタラクションが正常に機能するか検証します。

> **注意**: Agent側に登録するBot IDとBot Secretは、企業微信側のボット構成情報と完全に一致している必要があります。不一致の場合は連携に失敗します。

<!-- VISUAL_PENDING
visuals:
  - visual_id: openclaw-001
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: high
    purpose: "展示集成OpenClaw的界面与操作步骤。"
    production_method: recreate
  - visual_id: key-001
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: high
    purpose: "展示在Key管理页面创建包含接口权限的新Key。"
    production_method: recreate
  - visual_id: key-002
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: high
    purpose: "展示生成的OpenClaw访问Key列表。"
    production_method: recreate
  - visual_id: integration-002
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: high
    purpose: "展示在其他页面添加FineBI后台地址并进行连接测试。"
    production_method: recreate
  - visual_id: ext-mcp-001
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示在管理后台添加外部MCP服务时弹出的配置窗口界面。"
    production_method: recreate
  - visual_id: ext-mcp-002
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "以配置12306 MCP为例，展示在配置窗口中填写名称、传输方式、URL及请求头的效果。"
    production_method: recreate
  - visual_id: wecom-app-create
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示在企业微信后台创建自建应用的入口"
    production_method: recreate
  - visual_id: wecom-app-info
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: high
    purpose: "展示自建应用基本信息及可见范围设置界面"
    production_method: recreate
  - visual_id: wecom-api-receive-entrance
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示API接收消息配置入口"
    production_method: recreate
  - visual_id: wecom-api-server-config
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示接收消息服务器URL、Token与EncodingAESKey的配置界面"
    production_method: recreate
  - visual_id: dora-admin-im-mapping
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: high
    purpose: "展示Dora后台填入Token与EncodingAESKey的弹窗界面"
    production_method: recreate
  - visual_id: wecom-api-save
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "提示在企业微信后台保存API接收配置"
    production_method: recreate
  - visual_id: wecom-trusted-ip
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示企业可信IP的配置入口界面"
    production_method: recreate
  - visual_id: wecom-corp-secret
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示获取CorpSecret的界面"
    production_method: recreate
  - visual_id: wecom-corp-id
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示获取企业ID的界面"
    production_method: recreate
  - visual_id: dora-admin-im-save
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: high
    purpose: "展示Dora后台添加CorpSecret与CorpId的界面"
    production_method: recreate
  - visual_id: im-integ-001
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "演示在企业微信群聊中 @Dora机器人进行多轮问答对话的实际效果。"
    production_method: recreate
  - visual_id: im-integ-002
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: medium
    purpose: "展示在Data Agent管理后台完成平台用户与企业微信用户映射的界面。"
    production_method: recreate
  - visual_id: im-integ-003
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: medium
    purpose: "展示在企业微信通讯录中添加并创建智能机器人的入口。"
    production_method: recreate
  - visual_id: im-integ-004
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示在企业微信中点击「手动创建」机器人的选项。"
    production_method: recreate
  - visual_id: im-integ-005
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示将机器人创建页面下拉至最下方以切换到API模式创建的入口。"
    production_method: recreate
  - visual_id: im-integ-006
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示在企业微信中配置机器人基本信息并获取长连接所需Bot ID与Secret的界面。"
    production_method: recreate
  - visual_id: im-integ-007
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "展示在Dora平台的Agent配置中添加企业微信机器人并输入授权信息的界面。"
    production_method: recreate
  - visual_id: im-integ-008
    role: screenshot
    locale_sensitivity: high
    brand_sensitivity: none
    purpose: "演示在企业微信中对配置完成的机器人发送测试消息以验证功能是否正常。"
    production_method: recreate
-->

<!-- 本頁已依品牌規則處理 1 條過濾項 -->
