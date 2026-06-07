---
page_id: getting-started
title: "Emonクイックスタート"
locale: ja-JP
sourced_from_kus:
  - dora.platform.intro
  - finereport.agent.workspace.intro
  - finereport.agent.workspace.dora_general_agent
  - finereport.agent.workspace.expert_agent
  - finereport.agent.workspace.admin_backend
  - dora.getting_started.use_agent.overview
  - dora.getting_started.use_agent.select_and_new_chat
  - dora.getting_started.use_agent.dialogue_interaction
  - dora.getting_started.use_agent.dialogue_correction
  - dora.getting_started.use_agent.session_operations
  - dora.getting_started.use_agent.workspace
generated_at: "2026-06-07T17:28:15+08:00"
---
<!-- RENDERED
brand: emon
brand_display_name: Emon
locale: ja-JP
rendered_at: 2026-06-07T09:39:36Z
source_master: data/dora/locale/ja-JP/pages/getting-started.md
-->

# Emonクイックスタート

## プラットフォーム概要

Emonはエンタープライズレベルのデータインテリジェントエージェント（Data Agent）プラットフォームであり、エンタープライズレベルのデータセキュリティ基盤とAgentオーケストレーションエンジン機能を備えています。Emonはタスクの複雑さに応じて自動的に「思考」（次の行動を計画）し、「行動」（対応するスキルを呼び出す）することで、さまざまな業務シナリオにおけるデータ分析、レポート作成、アラート、プッシュ通知など、全プロセスのクローズドループを実現できます。主にデータアナリストおよびデータレポートに関心のある企業管理者向けであり、データ分析のハードルを下げ、分析効率を向上させ、業務のセルフサービス化を支援することをコアバリューとしています。財務、運用、販売などのさまざまな業務部門向けに専用のAgentアシスタントを作成し、データ機能の再利用と蓄積を実現できます。

データ照会AgentはEmonの最も基本的なコア機能です。ユーザが自然言語の対話を通じて直接業務データを照会することをサポートします。ユーザの質問に含まれる重要な情報（意図のインテリジェント解析）を自動的に認識し、正確な結果を返し、マルチシナリオでの照会をサポートします。

<!-- VISUAL_PENDING
visual_id: platform-agent-qa
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: rebuild
purpose: 展示问数类Agent的交互界面
placement_hint: 事实“问数类Agent是Dora最基础的核心能力”
source:
  original_url: ""
  local_path: data/dora/assets/1779940749EDR2.png
  content_hash: dummy
  ocr_text: |
    OQ > 行政考勤数据助手
    Q MX
    (So定时任务
    历史会话
    3月谁请假总时长超过3天? 哪个…
    3月第1周有多少领导不在岗? 请…
    高管们3月第1周出差情况?
    ‘Up ”行政考勤数据助
    高管们3月第1周出差情况?
    哪个部门公出最为频繁?
    18! 我是你的考勤/公出查询小助手，专门帮你分析公出和请假数据
    领导公出的主要目的地和事由集…
    哪个部门公出最为频繁?                                                                            公出查询            请假查询            综合查询
    生产部门3月的行程安排?                                * 高管们3月第1周出差情况?
  caption_zh_cn: ""
referenced_facts: []
rebuild_spec: null
-->

レポートAgentは、照会結果に基づいて構造化された分析レポートを自動的にオーケストレーションして出力することをサポートし、企業管理者のデータ報告およびレビューのニーズを満たします。データの自動統合、構造化された出力、およびさまざまな業務に対するシナリオの適応といった利点を備えています。

<!-- VISUAL_PENDING
visual_id: platform-agent-report
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: rebuild
purpose: 展示报告类Agent的交互界面
placement_hint: 事实“报告类Agent支持基于查询结果，自动编排并输出结构化分析报告”
source:
  original_url: ""
  local_path: data/dora/assets/1779940713dmXo.png
  content_hash: dummy
  ocr_text: |
    OQ & 供应链经营分析师
    Q MX
    (So定时任务
    历史会话
    请根据你可以查询数据和能力，…
    各运营中心的业务量与效率对比…
    各运营中心的业务量与效率对比…
    各承运人的毛利排名及盈利情况…
    2025年各月供应链收入与成本趋…
    帮有我生成你自己的agent简介吧.….
    公司整体收入成本趋势如何? 是…
    各运营中心供应链收入分月完成…
    上海口岸供应链收入分月完成情…
    供应链收入激励构成是什么，各…
    A  admin(admin)          =: 管理后台
    q
    AL供应链经营分析师
    我是供应链经营分析师，专注于供应链与项目分类数据查询、多维度经营分析及可视化图表生成，助您用一句话快速获取业务洞察。
    推荐问题
    + 各运营中心的业务量与效率对比如何?
    + 各承运人的毛利排名及盈利情况怎样?
    * 2025年各月供应链收入与成本趋势如何?
  caption_zh_cn: ""
referenced_facts: []
rebuild_spec: null
-->

## ワークスペースの概要

ワークベンチ（Emonプラットフォームのホームページ）では、従業員がさまざまなデータ分析を処理するための適切なAgentをすばやく選択できます。ユーザは「販売データ照会Agent」や「レポート分析Agent」などを選択して作業を支援できます。開発ユーザまたは管理者はさまざまな種類のAgentを作成し、ワークベンチに公開して従業員に提供できます。

Emon汎用AgentはEmon Corp Emonプラットフォームに組み込まれた汎用Agentであり、プラットフォームのすべてのスキルが統合されています。管理者はEmon用のモデル、スケジュールされたタスク、およびIM連携を設定できます。閲覧ユーザはワークベンチで直接Emonと対話できます。

<!-- VISUAL_PENDING
visual_id: dora-general-agent
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: rebuild
purpose: 展示工作台上内置的Dora通用智能体对话入口。
placement_hint: 段落2. Dora通用智能体
source:
  original_url: data/dora/assets/1778580342v74K.png
  local_path: data/dora/assets/1778580342v74K.png
  content_hash: dummy
  ocr_text: |
    Data Agent
    =
    UR DARE Z| |
    [s, Ke Dora，全能助手随时待命
    我可以帮你 数据分析
    COCO探索更多专家 ^
  caption_zh_cn: null
referenced_facts: []
rebuild_spec: null
-->

ワークベンチで「さらに専門家を探す」をクリックすると、専門家Agentリストで名前または説明を使用してターゲットAgentをすばやく検索できます。ターゲットのAgentカードをクリックして会話画面に入ります。

<!-- VISUAL_PENDING
visual_id: expert-agent-list
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: rebuild
purpose: 展示专家Agent列表页及搜索、选择卡片的操作界面。
placement_hint: 段落3. 专家Agent
source:
  original_url: data/dora/assets/1778580878YQNH.png
  local_path: data/dora/assets/1778580878YQNH.png
  content_hash: dummy
  ocr_text: |
    Data Agent
    iis, Ezz Dora，全能助手随时待命
    我可以帮你
    在此
    生成PPT
    COO探索更多专家 ^
    s四1
    Data Agent
    专家Agent                                                  Q搜索名称
    a检索test jeremy                       a部门考勤助手a星火人才画像
    二20200512                         ileit: 20200000                            (eit: 20200u10
    Data Agent查看部门成员出勤数据                         星火人才画像
    人aexest
    aR: 2028/05/12
    a               02
    IEAM: 2026/0408,
    QQ BPH BBOVen
    BMIRAR: 2026/0421
    潜量分析报告
    A          CMO报告-Dylan
    sBIIRAH: 2026/03/30
    生成壳牌PCMO报告
    QR REMEAELARAGent
    BMI: 2026/08/08
    最分析报告Agent by zhuoyang
    人afies
    BIR: 2026/04/00
    析问数
    LA HS四coral
    BMH: 2026/03/90
    专家
    A               4
    iE: 2026/04/00
    QR Fittest
    EMM: 2026/05/12
    Data Agent
    QR omtittitagent
    BiGiRE: 2026/0429
    Data Agent
    au
    BENE: 2026/04/08
    hoky-test
  caption_zh_cn: null
referenced_facts: []
rebuild_spec: null
-->

また、左下の管理バックエンドアイコンボタンや「作成に進む」ボタンから管理バックエンドに入り、スキル、データ、ナレッジベース、モデルを設定し、必要なAgentを作成できます。

<!-- VISUAL_PENDING
visual_id: admin-backend-icon
role: icon
locale_sensitivity: none
brand_sensitivity: none
production_method: reuse
purpose: 管理后台入口图标。
placement_hint: 段落4. 管理后台
source:
  original_url: data/dora/assets/1775187625laDS.png
  local_path: data/dora/assets/1775187625laDS.png
  content_hash: dummy
  ocr_text: ""
  caption_zh_cn: null
referenced_facts: []
rebuild_spec: null
-->
<!-- VISUAL_PENDING
visual_id: admin-backend-entry
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: rebuild
purpose: 展示从工作台进入管理后台的入口按钮位置。
placement_hint: 段落4. 管理后台
source:
  original_url: data/dora/assets/1778580953ZE6g.png
  local_path: data/dora/assets/1778580953ZE6g.png
  content_hash: dummy
  ocr_text: |
    Ea  Jah
    Data Agent
    专家Agent
    检索test jeremy
    人
    最近编辑: ”2026/05/12
    Data Agent
    alex test
    a
    最近编辑: §~— 2026/05/12
    Aa             02
    最近编辑: 2026/04/08
    潜量分析报告Dylan
    人
    最近编辑: ”2026/04/21
    潜量分析报告
    a壳牌PCMO报告-Dylan
    最近编辑: ”2026/03/30
    生成壳牌PCMO报告
    部门考勤助手
    A最近编辑: ”2026/04/03
    查看部门成员出勤数据
    A     B2B市场潜量洞察Agent
    eee
    最近编辑: ”2026/04/08
    潜量分析报告Agent by zhuoyang
    /09
    自动化test
    AA最近编辑: ”2026/04/09
    连锁经营分析问数
    报告生成-coral
    人ees
    最近编辑: ”2026/03/30
    周报生成专家
    Q搜索名称/描述
    星火人才画像
    A最近编辑: ”2026/04/10
    星火人才画像
    a              is
    最近编辑: ~— 2026/04/09
    不可加test
    人na
    最近编辑: ”2026/05/12
    Data Agent
    Jeremy.LiMitagent
    ae
    最近编辑: § — 2026/04/23
    Data Agent
    a     hoky
    最近编辑: 2026/04/03
    hoky-test
  caption_zh_cn: null
referenced_facts: []
rebuild_spec: null
-->

## 最初の会話を始める

Data Agentワークベンチは、Agentベースのインテリジェントな会話入口を提供します。ユーザは構成済みのAgentを直接選択し、自然言語の会話を通じてデータ照会、ナレッジ検索、および分析レポートの作成などのタスクをすばやく完了できます。使用シナリオには、日常的なデータ照会、複数ターンの対話分析、および過去の対話の振り返りが含まれます。

<!-- VISUAL_PENDING
visual_id: overview-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: rebuild
purpose: 展示通过对话向Agent提问并获取业务数据的结果
placement_hint: 0
source:
  original_url: data/dora/assets/1775113297y5CC.png
  local_path: data/dora/assets/1775113297y5CC.png
  content_hash: sha1
  ocr_text: |
    Data Agent
    连锁经营分析
  caption_zh_cn: ""
referenced_facts: []
rebuild_spec: "チャットボックスを強調表示する"
-->
<!-- VISUAL_PENDING
visual_id: overview-002
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: rebuild
purpose: 展示多轮对话中对Agent进行连续追问的效果
placement_hint: 0
source:
  original_url: data/dora/assets/1775114053v1NN.png
  local_path: data/dora/assets/1775114053v1NN.png
  content_hash: sha1
  ocr_text: |
    其中华东区域Top3省份是哪些
  caption_zh_cn: ""
referenced_facts: []
rebuild_spec: null
-->

### Agentの選択と新しいチャットの作成

公開されたすべてのAgentは、ワークベンチにカード形式で表示されます。上部の検索ボックスを使用してターゲットAgentをすばやく見つけることができます。Data Agentにログインした後、ターゲットAgentカードをクリックして、そのAgentの会話画面に入ります。

<!-- VISUAL_PENDING
visual_id: select-agent-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: rebuild
purpose: 展示Data Agent工作台中已发布的Agent卡片及搜索框位置
placement_hint: 1
source:
  original_url: data/dora/assets/177504025810dD.png
  local_path: data/dora/assets/177504025810dD.png
  content_hash: sha1
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts:
  - 在工作台以卡片形式展示所有已发布的Agent，通过顶部搜索框可快速定位目标Agent。
rebuild_spec: null
-->

過去の会話履歴は左側のパネルに表示されます。クリックすると履歴に入り、未完了の分析を続行できます。新しい分析タスクを開始するには、左側の「新しいチャット」ボタンをクリックして現在の会話コンテキストをクリアし、新しい会話を開始します。

<!-- VISUAL_PENDING
visual_id: new-chat-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: rebuild
purpose: 展示对话界面左侧的「新聊天」按钮及历史对话记录
placement_hint: 2
source:
  original_url: data/dora/assets/1775040310sT2r.png
  local_path: data/dora/assets/1775040310sT2r.png
  content_hash: sha1
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts:
  - 历史对话记录显示在左侧面板，单击可进入历史对话，继续未完成的分析。
rebuild_spec: null
-->

> [!WARNING]
> 毎回「新しいチャット」をクリックすると独立した会話コンテキストが開始され、Agentは前回の会話の内容を記憶しません。連続した追加質問は同じ会話内で完了してください。

### 会話とインタラクション

画面中央の入力ボックスに質問を入力し、送信ボタンをクリックする（またはEnterキーを押す）と質問が送信されます。Agentは質問の意図を自動的に解析し、対応するスキルを呼び出して、会話エリアに結果を返します。さらに分析が必要な場合は、同じ会話内で追加質問を続けることができます。

<!-- VISUAL_PENDING
visual_id: dialog-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: rebuild
purpose: 展示输入问题并发送的界面操作
placement_hint: 1
source:
  original_url: data/dora/assets/17750404833i8q.png
  local_path: data/dora/assets/17750404833i8q.png
  content_hash: sha1
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts: []
rebuild_spec: null
-->
<!-- VISUAL_PENDING
visual_id: dialog-002
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: rebuild
purpose: 展示Agent分析并返回结果的过程
placement_hint: 1
source:
  original_url: data/dora/assets/1775040878VXQd.png
  local_path: data/dora/assets/1775040878VXQd.png
  content_hash: sha1
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts:
  - Agent会自动解析问题意图，调用对应技能，并在对话区域内返回结果。
rebuild_spec: null
-->
<!-- VISUAL_PENDING
visual_id: dialog-003
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: rebuild
purpose: 展示在对话中继续追问的交互过程
placement_hint: 2
source:
  original_url: data/dora/assets/1775041014A0kl.png
  local_path: data/dora/assets/1775041014A0kl.png
  content_hash: sha1
  ocr_text: |
    B2B市场潜量洞察Agent
    东区的top10的客户
  caption_zh_cn: ""
referenced_facts: []
rebuild_spec: null
-->

### 会話の修正

Agentの出力内容に誤りがあるか、期待通りでない場合（回答のズレ）、ユーザは直接異議、修正要求、または指示戦略の調整を行うことができます。Agentは自動的に振り返り、適切な結果を再生成します。

<!-- VISUAL_PENDING
visual_id: correct-002
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: rebuild
purpose: 展示Agent回复偏差时用户提出修正要求并由Agent重新生成结果的效果
placement_hint: 0
source:
  original_url: data/dora/assets/1778297767OLBK.png
  local_path: data/dora/assets/1778297767OLBK.png
  content_hash: sha1
  ocr_text: |
    快捷支付章节中，本年新增快捷支付绑卡户数的单位是万户，把报告中该部分的单位补齐
    已完成修正
  caption_zh_cn: ""
referenced_facts:
  - 用户可直接提出异议、修正要求或调整指令策略，Agent将自动复盘反思并重新生成合规结果。
rebuild_spec: null
-->

ユーザの入力した質問に誤りがあり、Agentが既に応答生成プロセスに入っている場合（質問の誤り）、ユーザは会話ボックスに簡潔で正しい質問を直接再送信できます。Agentは元のタスクを自動的に中断し、最新の正しい質問に基づいて再応答します。

<!-- VISUAL_PENDING
visual_id: correct-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: rebuild
purpose: 展示用户提问有误时直接补发修正指令中断重新应答的效果
placement_hint: 0
source:
  original_url: data/dora/assets/1778297521yCz2.png
  local_path: data/dora/assets/1778297521yCz2.png
  content_hash: sha1
  ocr_text: |
    不对，看张敏的
    星火计划人才画像 — 张敏
  caption_zh_cn: ""
referenced_facts:
  - 用户可在对话框直接补发精简正确的问题内容；Agent将自动中断原有任务，按最新正确问题重新应答。
rebuild_spec: null
-->

### 会話の操作と共有

Agentが内容を出力した後、ユーザは下部にある「いいね（高評価）」および「低評価」アイコンをクリックして、会話の品質をリアルタイムで評価できます。Agentに関連付けられたデータ、ナレッジ、スキルなどが調整された場合、またはネットワークの問題により内容が正しく出力されなかった場合は、再生成アイコンをクリックして再生成できます。

<!-- VISUAL_PENDING
visual_id: session-op-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: rebuild
purpose: 展示在会话气泡下方进行点赞或点踩评价的位置
placement_hint: 1
source:
  original_url: data/dora/assets/1775789484884p.png
  local_path: data/dora/assets/1775789484884p.png
  content_hash: sha1
  ocr_text: |
    成本额、销售额
  caption_zh_cn: ""
referenced_facts:
  - Agent输出内容后，用户可以点击下方的点赞和点踩图标，实时对会话质量做出评价。
rebuild_spec: null
-->
<!-- VISUAL_PENDING
visual_id: session-op-002
role: icon
locale_sensitivity: none
brand_sensitivity: none
production_method: reuse
purpose: 展示重新生成按钮的图标样式
placement_hint: 2
source:
  original_url: data/dora/assets/1775789646L1dt.png
  local_path: data/dora/assets/1775789646L1dt.png
  content_hash: sha1
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts: []
rebuild_spec: null
-->
<!-- VISUAL_PENDING
visual_id: session-op-003
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: rebuild
purpose: 展示点击重新生成按钮的效果
placement_hint: 2
source:
  original_url: data/dora/assets/1775789695fELl.png
  local_path: data/dora/assets/1775789695fELl.png
  content_hash: sha1
  ocr_text: ""
  caption_zh_cn: ""
referenced_facts: []
rebuild_spec: null
-->

会話の共有はスナップショット形式で行われ、最終出力結果のみが共有され、Agentの思考および分析プロセスは共有されません。複数の会話内容を選択し、リンクを介してプラットフォーム内の他のユーザと共有して閲覧することができます。

<!-- VISUAL_PENDING
visual_id: session-op-004
role: decorative
locale_sensitivity: unknown
brand_sensitivity: unknown
production_method: rebuild
purpose: 动图演示如何多选会话内容并通过链接分享
placement_hint: 3
source:
  original_url: data/dora/assets/1779874156893854.gif
  local_path: data/dora/assets/1779874156893854.gif
  content_hash: sha1
  ocr_text: ""
  caption_zh_cn: "0407迭代43.gif"
referenced_facts: []
rebuild_spec: null
-->

### ワークスペースでの結果確認

レポート生成Agentがタスクを完了すると、会話ボックスの右上に「ワークスペース」の入口が自動的に表示され、Agentタスクプロセス中に生成されたファイルと最終レポートファイルがまとめて保存されます。

ワークスペースでサポートされる操作項目は、レポートタイプ（MarkDown、HTML、PPT）によって異なります。すべてのタイプのレポートで、出力ファイルの切り替え、表示モード（ソースコード/ビジュアル）の切り替え、および新しいページで開くことがサポートされています。コンテンツのコピーはMarkDownおよびHTMLレポートでのみサポートされており、PPTレポートではサポートされていません。MarkDownレポートはMarkDown形式でのみダウンロード可能であり、HTMLレポートはHTML形式でのみダウンロード可能です。PPTレポートでは、元のPPT、PDF、ページZIP、および現在のページのダウンロードも追加でサポートされています。

<!-- VISUAL_PENDING
visual_id: workspace-overview
role: screenshot
locale_sensitivity: unknown
brand_sensitivity: unknown
production_method: rebuild
purpose: 展示『工作区』界面的截图
placement_hint: 段落：ワークスペースでの結果確認
source:
  original_url: ""
  local_path: ""
  content_hash: dummy
  ocr_text: "(原图无 OCR 文字)"
  caption_zh_cn: ""
referenced_facts: []
rebuild_spec: "ワークスペースの入口位置を強調表示する"
-->
<!-- NEEDS_VISUAL_REVIEW -->


