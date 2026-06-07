---
page_id: skill-orchestration
title: スキルオーケストレーションガイド
locale: ja-JP
sourced_from_kus:
  - dora.agent.skills.intro
  - dora.skill_management.custom_skills
  - finereport.skills.chart-visualization
  - finereport.skill.data_query_analysis_comparison
  - finereport.skill.fr_report_query
  - finereport.skills.dashboard-retrieval
  - dora.skill.dialog_subscription
  - dora.skill.ai-fixed-report
  - dora.skill.pptx_template.overview
  - dora.skill.pptx_template.preprocessing_rules
  - dora.skill.pptx_template.setup_and_global_config
  - dora.skill.pptx_template.page_config
  - dora.skill.pptx_template.reupload
  - dora.skills.report-generation-comparison.concept
  - dora.skills.report-generation-comparison.procedure
generated_at: '2026-06-07T00:00:00Z'
---
<!-- RENDERED
brand: emon
brand_display_name: Emon
locale: ja-JP
rendered_at: 2026-06-07T09:39:36Z
source_master: data/dora/locale/ja-JP/pages/skill-orchestration.md
-->

スキルはData AgentにおいてAgentが呼び出すための中核となる機能単位です。Agentはさまざまなスキルを選択して設定することで、多様なデータ分析や処理タスクを実現し、異なるシナリオにおける使用ニーズを満たします。

## スキルの概要とカスタマイズ

現在、共用可能な20種類の公式スキルが組み込まれており、Agentの能力に応じて必要に応じて選択できます。公式スキルには、データ照会と分析、データ可視化、レポート生成、研究と分析（コンサルティング分析、詳細調査など）、コンテンツ作成（ニュースレター、創作インスピレーションなど）、コード能力（コードドキュメント、Webデザインレビューなど）、会話と対話、メタ能力とガバナンス（スキル発見、スキル作成など）などのタイプが含まれます。

<!-- VISUAL_PENDING
visual_id: skills-official-list
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 公式スキルリストの表示
placement_hint: 事实“目前已内置 20 种可公用的官方技能”
source:
  original_url: ""
  local_path: data/dora/assets/1778566629OJ4F.png
  content_hash: dummy
  ocr_text: |
    < Data Agent
    @ Agent     gg   我的“| Q 搜索名称/描述
    ELS                                      全部                      18
    令 数据                                                    数据查询与分析                 4
    数据可视化       1
    @ 模型
    报告生成                    4
    @ Agent监管                                      研究与分析                    2
    内容创作                    2
  caption_zh_cn: ""
referenced_facts:
  - 官方技能包含：数据查询与分析、数据可视化、报告生成、研究与分析、内容创作、代码能力、对话与交互、元能力与治理等类型
production_method: recreate
suggested_ui_text_mapping:
  "Agent": "Agent"
  "我的": "私の"
  "搜索名称/描述": "名前/説明を検索"
  "全部": "すべて"
  "数据": "データ"
  "数据查询与分析": "データ照会と分析"
  "数据可视化": "データ可視化"
  "模型": "モデル"
  "报告生成": "レポート生成"
  "Agent监管": "Agent管理"
  "研究与分析": "研究と分析"
  "内容创作": "コンテンツ作成"
-->

### カスタムスキル

Emonプラットフォームは、テンセント（腾讯）SkillHubスキルのインポート、またはスキルパッケージのアップロードの2つの方法で独自の専用スキルをすばやくカスタマイズできます。プラットフォームはスキルパッケージの設定を自動的に解析し、直接使用可能なスキルを生成します。

カスタムスキルの使用シナリオは、企業、チーム、または個人のスキルを必要に応じてカスタマイズし、Agentがニーズにより適したコンテンツを出力できるようにすることです。

<!-- VISUAL_PENDING
visual_id: custom-skill-entrance
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: カスタムスキル管理のエントリポイント表示
placement_hint: 2.1 设置入口
source:
  original_url: ""
  local_path: data/dora/assets/1779872532wAHz.png
  content_hash: dummy
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts: []
production_method: recreate
suggested_ui_text_mapping: {}
-->

1. 管理者として「管理バックエンド>スキル」画面にアクセスします。
2. 「公共」または「私の」タブを選択します。（「公共」タブでアップロードしたスキルは全ユーザーが確認および使用でき、「私の」タブでアップロードしたスキルは作成者本人のみが確認および使用できます。）
3. 右上の「+ スキル」をクリックし、作成方法（テンセントSkillHubスキルのインポート、またはスキルパッケージのアップロード）を選択します。
4. テンセントSkillHubスキルをインポートする場合、スキル詳細画面のURL、または単一の`.zip`スキルパッケージへのURLを入力してインポートします。
5. スキルパッケージをアップロードする場合、準備したローカルの独自スキルパッケージ、またはEmonプラットフォームで生成したスキルパッケージをアップロードします。
   > 💡 ヒント
   > 「Emon汎用スマートAgent」を使用し、会話の中でスキル要件を入力すると、完全なスキルパッケージを自動生成できます。スキルパッケージは`.zip`形式で50MB以下である必要があり、ルートディレクトリに`SKILL.md`を含める必要があります。
6. 生成されたスキルコンテンツのプレビューカードで解析に誤りがないことを確認した後、「OK」をクリックして作成を完了します。

> ℹ お知らせ
> - スキルコンテンツはオンライン編集できません。変更する場合は再アップロードしてください。
> - スキルの使用権限はアップロードしたタブによって決まり、作成後は変更できません。
> - 公共スキルは全員に表示されるため、機密情報をアップロードしないでください。
> - スキルを削除する前に、そのスキルに依存しているAgentがないことを確認してください。

<!-- VISUAL_PENDING
visual_id: custom-skill-management
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: スキル管理操作メニューの表示
placement_hint: 3. 技能管理
source:
  original_url: ""
  local_path: data/dora/assets/1779873095xBHL.png
  content_hash: dummy
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts: []
production_method: recreate
suggested_ui_text_mapping: {}
-->

## データ照会とグラフ分析スキル

データソースごとにAgentに単一の専用データ照会分析スキルを割り当てることをお勧めします。これにより、無効な検索を回避し、実行速度を向上させてトークン消費を削減できます。

データ照会と分析には、ダッシュボード検索、データ分析、ORレポート照会、分析テーマデータ照会の4種類のスキルが含まれます。スキル間の違いは以下の通りです。

| スキル名 | 説明 | 適用シナリオ |
| --- | --- | --- |
| **ダッシュボード検索** | 紐付け済みのダッシュボード内で資産データを検索し、指標の照会、トレンド分析、比較集計などの質問に回答します。 | 看板のデータ確認や看板分析シナリオ |
| **データ分析** | Excel/CSV形式のデータソースをアップロード後、データの確認、分析、集計、エクスポートを行います。 | ローカルファイル（Excel/CSV）の直接分析 |
| **ORレポート照会** | OrangeReportプラットフォームと連携し、レポートの検索、プレビュー、データ分析、パラメータ調整をサポートします。 | 手動で探すことなくORレポートデータを利用 |
| **分析テーマデータ照会** | 追加済みのOrangeBI分析テーマデータソースやExcelデータソースに対して、自然言語によるデータ照会をサポートします。 | 構造化されたデータ結果の自然言語による取得 |

### ダッシュボード検索スキル

会話内でダッシュボードのグラフや指標に対して直接質問し、数値、ランキング、前年比・環比などのデータを取得したり、レポート生成時に主要指標とトレンドの変化を自動的に集計し、構造化された分析レポートを出力したりできます。

> ⚠ 警告
> 使用する前に、ElasticSearchコンポーネントがv20.4.5-8.17.3以上にアップグレードされ、`running`状態であることを確認してください。また、開発者モードを使用して、ElasticSearchコンポーネントの環境変数`INSTALL_FINE_PLUGIN`の値を`yes`に設定する必要があります。

1. ElasticSearchのバージョンと状態を確認し、環境変数`INSTALL_FINE_PLUGIN`を`yes`に設定します。
2. Data Agentプラットフォームでダッシュボードのデータ確認・分析用のAgentを作成し、検索対象のダッシュボードデータを追加します。
3. 「Agent設定画面>スキル」で、「ダッシュボード検索」スキルを選択して追加します。
4. データ境界をロックするために、スキルが検索可能なダッシュボードの範囲を限定します。
   > 💡 ヒント
   > 検索範囲が狭すぎるとデータが返されず、広すぎると無関係なデータの干渉やトークン消費の増加につながります。
5. 使用シナリオに応じて、公開チャネルを選択し、Agentをエンドユーザーに公開します。
   - **ワークスペース**：Data Agentプラットフォーム内部ユーザーの日常的な分析用
   - **独立URL**：ログイン不要で外部と共有可能
   - **OrangeBIプラットフォーム**：OrangeBIのサイドバーからAgentを呼び出して利用可能

<!-- VISUAL_PENDING
visual_id: dash-retrieval-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
purpose: FineBIプラットフォームでのダッシュボード検索Agentの会話画面
placement_hint: 效果演示
source:
  original_url: ""
  local_path: data/dora/assets/1779776241767583.gif
  content_hash: dummy
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts:
  - "在看板查数场景下，可针对已绑定仪表板中的图表与指标，直接提问获取数值、排名、同比环比等数据。"
production_method: recreate
suggested_ui_text_mapping: {}
-->

<!-- VISUAL_PENDING
visual_id: dash-retrieval-006
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: ダッシュボード検索スキルの範囲設定
placement_hint: 5
source:
  original_url: ""
  local_path: data/dora/assets/1779181645GS21.png
  content_hash: dummy
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts:
  - "配置仪表板检索技能时，需限定技能可检索的仪表板范围以锁定数据边界。"
production_method: recreate
suggested_ui_text_mapping: {}
-->

### ORレポート照会スキル

このスキルを使用すると、手動でレポートを探すことなく、会話の中で直接質問するだけでORプロジェクト内のレポートデータを呼び出すことができます。

レポートの検索とプレビューシナリオでは、自然言語の説明によって対象のレポートをすばやく特定し、コンテンツをプレビューできます。データ分析シナリオでは、レポート内のデータの指標照会、トレンド分析、比較集計をサポートします。

> ℹ お知らせ
> スキルを設定する前に、対象のORプロジェクトで「OR検索プラグイン」のインストールとテンプレート検索設定を完了する必要があります。

1. **プラグインのインストール**：ORでOR検索プラグインをインストールします。プラグインの圧縮パッケージは解凍せず、そのままインストールしてください。
2. **モデル設定**：ORで「管理システム>テンプレート検索>モデル設定」にアクセスし、大規模言語モデルとベクトルモデルを設定します。「テストして接続」をクリックしてモデルが利用可能であることを確認します。
3. **テンプレート設定**：ORで「管理システム>テンプレート検索>テンプレート設定」にアクセスし、メタデータを生成するためのテンプレートを設定します。
4. Data Agentプラットフォームで、分析用のカプセル化Agent設定画面にアクセスします。
5. 「Agent設定画面>スキル」で、「ORレポート照会」スキルをクリックして追加します。
6. 接続設定で、ドロップダウンリストから以前に作成したORプロジェクト接続を選択します。以前に作成したORプロジェクト接続は自動的に記録されるため、ドロップダウンリストから選択して再利用できます。履歴がない場合は、「新しい接続」をクリックし、カスタムの接続名とORサーバアドレスを入力して接続を作成します。

<!-- VISUAL_PENDING
visual_id: fr-query-plugin-install
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: FR検索プラグインインストールの成功プロンプト
placement_hint: 2.1 使用前准备
source:
  original_url: ""
  local_path: data/dora/assets/1779862842IDJp.png
  content_hash: dummy
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts:
  - "在配置技能前，需在目标 FR 工程中完成「FR检索插件」安装"
production_method: recreate
suggested_ui_text_mapping: {}
-->

<!-- VISUAL_PENDING
visual_id: fr-query-model-config
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: FRテンプレート検索でのモデル設定画面
placement_hint: 2.1 使用前准备
source:
  original_url: ""
  local_path: data/dora/assets/1779184208nUDh.png
  content_hash: dummy
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts:
  - 点击「管理系统>模板检索>模型配置」配置大语言模型与向量模型
production_method: recreate
suggested_ui_text_mapping: {}
-->

### グラフ可視化スキル

グラフ可視化機能は、上流のデータ照会結果とユーザーのグラフ作成の要望を組み合わせて、Echartsグラフなどの可視化グラフを自動的に生成します。レポート生成やデータの確認・分析などのシナリオで、Agentが分析してプレビュー可能なグラフを出力する必要がある場合に使用できます。

> ℹ お知らせ
> 地図生成機能を使用するにはネットワーク接続が必要です。ローカル環境で展開するユーザーは、`antv-studio.alipay.com`と`mdn.alipayobjects.com`の2つのドメインをアクセス許可リストに追加する必要があります。

1. Data Agentプラットフォームで、データ確認・分析用のAgentを準備します。
2. 「Agent設定画面>スキル」で、「グラフ可視化」および「分析テーマデータ照会」スキルを選択して追加します。
3. Agentを公開すると、会話の中でグラフ可視化の効果を体験できます。

## レポート生成とサブスクリプション配信スキル

### 報告生成類スキル

報告生成には、以下の5つのスキルタイプが含まれます。スキル間の違いは以下の通りです。

| スキル名 | 説明 | 適用シナリオ |
| --- | --- | --- |
| **htmlレポート** | テキストコンテンツや分析結論に基づいて、プレビュー可能なHTMLレポートを動的に生成します。 | フォーマット制限のないオープンなレポート生成 |
| **テンプレートからのhtmlレポート作成** | アップロードされたHTMLテンプレートと構造化データソース（Excel/CSV）に基づいてカスタマイズされたHTMLレポートを生成します。 | 固定フォーマットの制約があるレポート生成 |
| **PPTレポート** | ドキュメント、アウトライン、テーマなどの入力に基づいて構造化されたPPTを生成します。 | 販売や業務報告用のPPT資料の迅速な生成 |
| **PPTXテンプレート入力** | プレ処理済みのPPTテンプレート、AIプロンプト、ダッシュボードデータのバインディングにより標準化されたPPTレポートを生成します。 | 固定のPPTフォーマットでの標準化されたレポート |
| **AI固定レポート** | 事前設定されたレポートアウトラインと関連データソースに基づきデータを統合し、標準化された分析レポートを生成します。 | 通用まとめ、要因分析、比較分析などの標準化レポート |

1. レポート生成用のAgentを準備します。
2. 「Agent設定画面>スキル」で、「レポート生成」分類内の適切なスキルを追加します。
3. 「AI固定レポート」および「PPTXテンプレート入力」スキルを追加する場合は、スキルの詳細な設定を行う必要があります。

### AI固定レポートスキル

AI固定レポートスキルは、通用まとめレポート、要因分析レポート、比較分析レポートなどの生成に通常使用されます。ローカルレポートテンプレートをアップロードして、固定レイアウトのハードコードレポートを生成することもサポートしています。

1. 経営分析レポート生成用のAgentを作成し、適切なモデルとデータを設定します。
2. Agentに「ダッシュボードレポート生成」スキルを追加します。
3. テンプレート選択画面で、レポートテンプレートの作成方法（空白からの新規作成、組み込みテンプレートからの新規作成、ローカルレポートテンプレートのアップロード）を選択します。現在アップロードはdocx形式のファイルのみをサポートしています。
4. 左側の利用可能なデータ領域に「全体」データまたは「章ごと」データを追加し、データフィルタ条件を設定します（フィルタ条件は自然言語による記述をサポートしています）。全体データはドキュメント全体で共通して使用でき、章ごとデータは右側の該当章に対して独立して設定されます。
5. 右側のコンテンツ編集領域で、構造化されたコンテンツとプロンプトをMarkDown形式で編集します。
   > 💡 ヒント
   > 【】をプレースホルダ（例：【地域】、【年度】）として使用し、利用可能なデータ領域のダッシュボードに含まれるグラフやテーブル、添付ファイルを挿入できます。全画面プロンプトを挿入して、ドキュメントの分析フレームワーク、出力基準、文体を統一することもできます。
6. レポート生成後、添付ファイルはクリックしてダウンロード可能です。

### PPTXテンプレート入力スキル

金融や販売などの業界で、固定テンプレートに依存して標準化されたPPTレポートをバッチ生成する業務シナリオに適用され、PPT作成の効率を大幅に向上させることができます。

**PPTテンプレートの前処理規範**

- 純粋なテキストコンテンツは`{{内容名}}`（例：`{{今月のまとめ}}`）の形式を使用し、純粋な数値コンテンツは`{{データソース}}`（例：`{{売上高}}`）の形式を使用することをお勧めします。システムが識別できない曖昧なフォーマット（xxxxなど）は避けてください。
- テキストと数値の混合表現（例：`{{売上高}}円`、`{{地域}}市場分析`）もサポートされています。
- テンプレート内の画像プレースホルダは自動的に認識されるため、特別なマークは不要です。
- テンプレートは、全体構造を明確にし、すべてのプレースホルダを一意にするために`.pptx`形式で保存する必要があります。

**設定手順**

1. Emonプラットフォームで標準化されたPPTレポート生成用のAgentを準備し、「Agent設定画面>スキル」で「PPTXテンプレート入力」スキルを選択して追加します。
2. 「テンプレートのアップロード」をクリックし、前処理済みの`.pptx`ファイルをアップロードします。アップロード後、テンプレートが自動的に解析され、ページ数、コンポーネント数、置換可能数、バインディング数が表示されます。
3. **グローバル設定**：「グローバル設定」タブでグローバルフィルタ条件を追加します。これは、バインドされたダッシュボードにのみ適用されます。
4. **ページごとの設定**：「ページごとの設定」タブで、各ページのテキストと画像プレースホルダの生成ルールとデータソースをそれぞれ設定します。
   - **テキストプレースホルダの設定**：左側で対象のPPTページを選択し、右側のコンポーネントの下の「プロンプト」入力ボックスに生成指示を入力します（数値を含むテキストタイプの場合、実際の数値を取得するために、先に「利用可能なデータ」にダッシュボードコンポーネントを追加する必要があります）。プロンプトは具体的であるほど良く、分析の次元、トーン、長さなどを明確に指定します。
   - **画像プレースホルダの設定**：ページの画像プレースホルダ領域を選択し、対応するダッシュボードとコンポーネントを関連付けます。独立したフィルタ条件を設定することも可能です。
5. **テンプレートの再アップロード**：テンプレートを変更して再アップロードすると、自動的に新旧バージョンの違いを比較し、不一致の項目をすべてリストアップします。古いプレースホルダに対応する新しい位置を選択して、元の設定が失われないようにすることができます。新しいテンプレートのページ数が多い場合、「新規ページのみ表示」機能をオンにしてすばやく設定できます。

<!-- VISUAL_PENDING
visual_id: pptx-setup-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: Agentの基本設定画面でのPPTXスキルの追加
placement_hint: 1
source:
  original_url: data/dora/assets/1779955547kBcP.png
  local_path: data/dora/assets/1779955547kBcP.png
  content_hash: sha1
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts:
  - "在 Dora 平台上，准备一个用于生成标准化 PPT 报告的 Agent。"
production_method: recreate
suggested_ui_text_mapping: {}
-->

<!-- VISUAL_PENDING
visual_id: pptx-setup-003
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: PPTXテンプレートの解析情報インターフェイス
placement_hint: 3
source:
  original_url: data/dora/assets/1779955631hE7w.png
  local_path: data/dora/assets/1779955631hE7w.png
  content_hash: sha1
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts:
  - "上传模板文件后，Dora 将自动解析模板，并展示页数、组件数、可替换数以及绑定数。"
production_method: recreate
suggested_ui_text_mapping: {}
-->

### 会話サブスクリプションスキル

会話サブスクリプションスキルは、ユーザー自身のスケジュールされたタスクを管理するために使用されます。ユーザーがスケジュールされたタスクを作成、照会、変更、閉じる、開始、または削除する場合に呼び出すことができます。日次レポートの定期プッシュ配信やデータアラートのプッシュ配信などのシナリオで必要になります。

1. Data Agentプラットフォームで、スケジュールタスクを設定してデータやレポートのプッシュ配信を行うAgentを準備します。
2. 「Agent設定画面>スキル」で、「会話サブスクリプション」スキルを選択して追加します。
3. 適切なスケジュールタスク（営業週報タスクやデータアラートタスクなど）を追加します。

<!-- 本頁已依品牌規則處理 1 條過濾項 -->
