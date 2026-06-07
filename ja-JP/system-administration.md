---
page_id: system-administration
title: "システム設定と権限管理"
locale: ja-JP
sourced_from_kus:
  - dora.user-management.all-users.reference
  - dora.user-management.user-types.concept
  - dora.permission-management.permission-assignment.reference
  - dora.agent-supervision.audit-logs.concept
  - finereport.agent.scheduled_tasks.concept
  - finereport.agent.scheduled_tasks.setup
  - dora.monitor.scheduled_tasks.overview
  - dora.monitor.scheduled_tasks.view_execution
  - dora.monitor.scheduled_tasks.view_session
  - dora.data_management.data
  - finereport.user_management.im_mapping
  - dora.admin.usage_overview
generated_at: 2026-06-07T17:28:15+08:00
---
<!-- RENDERED
brand: emon
brand_display_name: Emon
locale: ja-JP
rendered_at: 2026-06-07T09:39:36Z
source_master: data/dora/locale/ja-JP/pages/system-administration.md
-->

本ページでは、Emonプラットフォームのシステム管理者向け機能について説明します。
ユーザの管理、権限の割り当て、定期タスク、監査ログ、データ管理、IMユーザマッピングの概要と設定方法を学びます。

## 1. ユーザと権限の割り当て

### ユーザタイプの管理

プラットフォーム内のすべてのユーザは、スーパー管理者、開発ユーザ、閲覧ユーザ、未割り当ての4タイプに分類されます。
「ユーザタイプ」ページでは、役割ごとにユーザを表示し、ユーザタイプを一括で割り当てられます。

- **スーパー管理者**: プラットフォームの最高権限を持つ役割です。すべてのユーザとモジュール設定を管理できます。プラットフォームに組み込まれており、変更はできません。
- **開発ユーザ**: プラットフォームの設定と管理を行う役割です。Agentの作成、公開、およびモデル、Agent管理、オープン統合の管理が可能です。
- **閲覧ユーザ**: プラットフォームの一般利用者です。Agentとの対話や公開されたAgentの閲覧が可能ですが、バックエンドの設定権限はありません。
- **未割り当て**: プラットフォームの操作権限を持たないユーザです。

開発ユーザ、閲覧ユーザ、未割り当ての各タイプは、相互に変更可能です。

スーパー管理者として「管理バックエンド>ユーザ管理>ユーザタイプ」タブにアクセスします。
ここでプラットフォーム内の全ユーザのユーザタイプを表示および編集できます。
表内の複数のユーザにチェックを入れ、表上部のボタンをクリックすると、ユーザタイプを一括で割り当てられます。
また、右側の検索ボックスで「ユーザ名」または「氏名」によるあいまい検索が可能です。

<!-- VISUAL_PENDING
visual_id: user-types-01
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1779370786RN8n.png
  ocr_text: |
  < Data Agent
  ® Agent
  Z 技能
  S 数据
  © 模型
  © Agent监管
  > 开放集成
  | 2 用户管理                   |
  O 权限管理
  用户管理  2)
  所有用户 | 用户类型
  未分配
  查看用户
  开发用户
  超级管理员
  1IM用户映射
  已选择 0 个用户，分配为: ， 未分配
  用户名
  1111
  Anya
  Aria
  lance
  Irm-designer
  sit
  sl4
  查看用户
  姓名
  23
  an'                                   om
  Aria.Han
  lance
  Irm-designer
  sit
  sl4
  OQ 搜索用户名/姓名
  
-->

### すべてのユーザの管理

「すべてのユーザ」ページでは、プラットフォーム内の全ユーザ情報を集中的に管理します。
このページでは、検索とフィルタリング、新規ユーザの追加、情報の編集、ユーザの無効化や削除が可能です。
ページ上部の検索ボックスとドロップダウンを使用して、ユーザをすばやく特定できます。

手動で追加されたユーザは、自動的にOrangeBIプラットフォームに同期されます。
ユーザの追加には、ユーザ名、氏名、パスワードの入力が必須です。
また、ユーザタイプ（閲覧ユーザ、開発ユーザ、未割り当て）も同時に設定できます。

ユーザ作成後、ユーザ名の変更はできません。氏名、メールアドレス、電話番号、ユーザタイプは編集可能です。
パスワードは平文で表示されませんが、「パスワードのリセット」ボタンで再設定できます。

<!-- VISUAL_PENDING
visual_id: all-users-01
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1779370282OF3C.png
  ocr_text: |
  < Data Agent                         用户管理
  加 Agent           2 所有用户 | 用户类型 IMAP BRST
  Q 搜索用户名/姓名                   全部                   v                                                                                         + 添加用户
  O 技能
  用户名                  姓名                     邮箱                              手机号码                用户类型                操作
  S 数据
  -                                 -                          超级管理员             分 禁用 w
  © 模型                                                                                              -                                    -                            开发用户                 QO 禁用 wW
  admin-test              admin-test              -                                 -                          超级管理员             QO 禁用 首
  © Agent监管
  admin-test2             admin-test2             -                                 -                          超级管理员             QO 禁用 首
  > 开放集成
  1)                          admin-test3             admin-test3             -                                 -                          超级管理员             QO 禁用 首
  2 用户管理                                 Anya                    an               aa.col -                                 -                          开发用户                分 禁用 wt
  加 权限管理                        Aria               Aria.Han            -                        -                   开发用户           QO 禁用 首
  Jacqueline              jac                lgka -                                 -                          查看用户                QO 禁用 首
  lance                    lance                    21              |.com             19         22              FRAP                CO 禁用 WwW
  Irm-designer             Irm-designer             -                                 -                          开发用户                QO 禁用 wW
  Irm-viewer               Irm-viewer               -                                 -                          查看用户                QO 禁用 首
  -                                 -                          查看用户                QO 禁用 首
  Mercy                   mk                 kea -                                 -                          查看用户                QO 禁用 人阁
  \
  a
  wo
  一
  oR
  nw
  =
  /1 >
  
-->

ユーザを無効化すると、そのユーザはEmonにログインできなくなります。
これは一時的な措置であり、いつでも有効化して元の権限を復元できます。
ユーザの削除は元に戻せない操作であり、データは完全に削除されます。
削除操作の前に、そのユーザが不要であることを必ず確認してください。

<!-- VISUAL_PENDING
visual_id: all-users-04
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/17793705729JgG.png
  ocr_text: |
  < Data Agent                                 用户管理
  所有用户 用户类型 ”1M用户映射
  ® Agent
  ET      2      -
  O 技能
  用户名                  姓名                     邮箱                              手机号码                用户类型                操作
  S 数据
  -                                 -                          超级管理员             分 禁用 w
  © 模型                                                                                              -                                    -                            开发用户                 QO 禁用 wW
  admin-test              admin-test              -                                 -                          超级管理员             QO 禁用 首
  © Agent监管
  admin-test2             admin-test2             -                                 -                          超级管理员             QO 禁用 首
  > 开放集成
  admin-test3             admin-test3             -                                 -                          超级管理员             QO 禁用 首
  2 用户管理                                 Anya                    anya               cor -                                 -                          FRAP                QO | 禁用 |
  -一
  © 权限管理                        Aria               Aria.Han            -                        -                   开发用户           QO | 启用 | 首
  Jacqueline              jaca                jka -                                 -                          查看用户                QO 禁用 首
  lance                    lance                    21               com             1¢          2              FRAP                CO 禁用 WwW
  Irm-designer                      Irm-designer                      -                                                         -                                             开发用户                           QO 禁用 wW
  
-->

プラットフォームのユーザデータ権限は、そのユーザがOrangeBIで持つすべてのデータ権限を直接継承します。

### 権限の割り当て

「権限管理」ページでは、ユーザごとにAgentのフロントエンド使用権限と管理バックエンド権限を設定します。
スーパー管理者は「管理バックエンド>権限管理」にアクセスし、全ユーザに権限を割り当てられます。
左側のユーザリストからユーザ名をクリックすると、右側のパネルで権限を設定できます。

<!-- VISUAL_PENDING
visual_id: perm-assignment-01
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1779370062LB1M.png
  ocr_text: |
  < Data Agent
  @® Agent
  Z 技能
  S 数据
  © 模型
  © Agent监管
  > 开放集成
  fo]  ae
  & 用户 a)
  权限管理
  Q 搜索名称
  > = 查看用户 18
  ” @ 开发用户7
  = 23(1111)
  “= anya.li1 @ingka.ikea.com(Anya)
  == Aria.Han(Aria)
  “= lance(lance)
  “= Irm-designer(Irm-designer)
  =: sl1(slt)
  =: sl4(sl4)
  Agent前台使用 。” 管理后台
  Q 搜索名称
  Agent名称
  Dora-通用智能体
  Irm测试
  sl1fJagent1
  未命名Agent_34
  test11
  O 权限管理
  未命名Agent_38
  未命名Agent_39
  模板报告测试Dylan
  连锁经营分析测试
  使用权限
  6 6 8
  
-->

プラットフォームでは以下の2種類の権限を割り当てられます。

- **Agentフロントエンド使用**: そのユーザがAgentを使用できるかどうかを制御します。
- **管理バックエンド**: 開発ユーザに対して、バックエンドの各モジュールの操作権限を設定します。
  - **Agentモジュール**: 個人開発権限(自身のAgentの作成・編集・削除)、管理権限(Agentの公開)。
  - **モデルモジュール**: 個人開発権限(個人用モデルの追加・削除)、管理権限(共通モデルの追加・削除)。
  - **Agent管理モジュール**: 個人開発権限(管理権限を持つAgentの管理データを表示)。管理権限はありません。
  - **オープン統合モジュール**: 個人開発権限(オープン統合ページの表示と使用)。管理権限はありません。

閲覧ユーザに対しては、管理バックエンド権限の設定はサポートされていません。

<!-- VISUAL_PENDING
visual_id: perm-assignment-03
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/177996718770JF.png
  ocr_text: |
  < Data Agent
  ® Agent
  0 技能
  S 数据
  ORH
  回 Agent监管
  D> 开放集成
  & 用户管理
  人 权限管理
  权限管理
  Q 搜索名称
  > 查看用户
  "” FRAP
  2 kyle(2)
  A almond(almond)
  A Aria(Aria)
  Agent前台使用 ”管理后台
  Q 搜索权限资源
  Agent
  权限资源
  Agent
  权限资源
  模型
  Agent监管
  开放集成
  ©
  个人开发权限
  ©
  公共管理权限
  ©
  
-->

ユーザがAgentでアクセスできるデータ範囲は、OrangeBIでのデータディレクトリ権限に依存します。
開発者は「管理バックエンド>データ」で、自身が権限を持つデータリソースのみを追加できます。
OrangeBIでデータソースの権限を持たない場合、Agentでもそのデータを照会できません。
ただし、アップロードされたローカルのExcelデータソースなどはデータ権限の制限を受けません。

## 2. 定期タスクと監査ログ

### 定期タスクの設定

定期タスクはAgentの自動化機能の中核モジュールです。
設定済みのAgentに対して、定期的にトリガーされるバックエンドタスクを追加できます。
ユーザが質問しなくても、データの集計や異常の事前警告などの操作を自動で実行します。
結果は複数のチャネルを通じて対象ユーザにプッシュ送信されます。
営業担当者へのリスク事前警告や、定期的な統計レポートの自動生成に適しています。

<!-- VISUAL_PENDING
visual_id: agent-scheduled-task-effect
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/17793271106tJ1.png
  ocr_text: |
  编辑定时任务
  
  定时任务名称;
  江苏省销售额预和
  
  任务提示词
  
  坦询江苏省2024年的总销售额，判断是否小于120万元【1200000元) 。如果江苏省2024年
  销售额小于120万元，则甬改预警任务; 如果销售额大于等于120万元或数据为室，则不能
  发，不发送任何内容.
  
  定时执行频率
  
  加 | 江苏省销售额预警 Osa
  
  生成江苏省销售数据异常预警通知，具体要求如下: 1、标题: 【严重/中度/轻度预警] 江苏省销售数据异常通
  
  知。严重程度判定规则: 销售额低于50万元为严重预警，50-90万元为中度预警，90-120万元为轻度预警。2、
  
  内容必须包含以下四个部分: - 销售额情况和现状: 说明江苏省2024年实际销售额数值及与120万元阔值的差距
  - 关键数据对比: 与120万元目标的偏差百分比、同比变化情况等
  
  A Henne
  
  ，坦看其他 14 个步骤
  加 展示文件
  
  /ont /user-data/output
  
  省销售数据异常预区通知,nd
  
  我来为您生成江苏省销售数据异常预警通知。首先需要查询江苏省2024年的销售数据，然后根据间值判定预警等级。
  数据源已加载，模型已选中。现在开始解析查询并获     2024年和2023年的销售额数据
  
  解析成功，无歧义。现在获取NL2DSL上下文并生成DSL查询。
  
  现在生成DSL坦询江苏省2023年和2024年的销售额数据 (用于同比对比) 。
  
  数据已获取成功。江苏省2024年销售额约为 105.10万元，2023年约为 102.87万元。根据闭值判定: 105.10万元落在 90-120万元区间，属于轻
  ame.
  
  现在生成预警通知。
  
  数据计算完成，现在生成预警通知文件-
  
  预警通知已生成完毕。以下是核心结论
  
  预警等级判定: 轻度预警
  
  江苏省2024年销售额为 105.10万元，落在90-120万元区间，触发轻度预警。具体数据:
  
  与120万元阔值差距: 14.9057, (HH 12.42%
  同比2023年 【102.87万元) : 仅增长 2.17%，增速微弱
  + 虽未触及中度或严重预警线，但距离正常水平仍有了明显缺口，增长及 YE
  
  预警通知文件已保存至输出目录，包含四个完整板块: 销售额现状、关键数据对比、影响分析、处理建议。
  
  ems 人
  
  在此输入任何您想查询或分析的问题
  
  内容均由AI生成，仅供参考
-->

タスクの作成は、管理バックエンドまたはフロントエンド（Agent使用画面）から設定可能です。
空白からの新規作成、または推奨テンプレートの使用から選択できます。
現在、「営業週報」と「データ事前警告」の2種類のシナリオテンプレートが提供されています。

タスク設定項目には以下の内容が含まれます。

- **タスク名**: 目的を明確に表現する名前。
- **タスクプロンプト**: Agentがタスクを実行する際の完全な指示。
- **定期実行頻度**: タスクを自動実行する周期と特定の時間点。
- **通知先ユーザ**: 結果のプッシュ対象となるユーザ。
- **プッシュチャネル**: 実行結果のプッシュチャネル。現在プラットフォーム、企業WeChat（企業微信）に対応しています。

タスクの実行には「対話サブスクリプション」スキルが依存するため、Agentにスキルを追加しておく必要があります。

### 定期タスクの管理と監査ログ

Agent管理の「定期タスク」ページでは、Agentにおけるタスクの実行履歴や起動状態などを一元的に確認できます。
タスクの開始・停止、内容の編集、削除がサポートされています。
実行履歴ボタンをクリックすると、タスク専用の実行履歴詳細ページに移動します。
通知先ユーザやプッシュチャネルを条件に履歴データをすばやく検索できます。

<!-- VISUAL_PENDING
visual_id: view-execution-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1779367415Hr6r.png
  ocr_text: |
  < Data Agent
  Agent监管
  Agent
  定时任务
  提示词
  执行频率
  推送渠道
  任务来源
  触达用户
  
-->

監査ログは、スーパー管理者に対してプラットフォームの全モジュールにおける操作履歴を提供します。
Agent、データディレクトリ、分析テーマ、LLMモデルの設定、外部MCPの連携などの操作を追跡します。
これにより、異常な操作行為の特定や変更問題のトラブルシューティングが可能です。
監査ログ一覧は時間降順で表示され、時間範囲や操作者名でフィルタリングできます。
モジュールのフィルタリングオプションには、Agent、データ、モデル、オープン統合が含まれます。

リストには以下のフィールドが含まれます。
操作時間、操作者、モジュール、オブジェクトタイプ、オブジェクト名、操作、結果。
結果フィールドは操作の成功・失敗を記録し、異常操作の迅速な識別に役立ちます。

<!-- VISUAL_PENDING
visual_id: audit-logs-01
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1778577191huCE.png
  ocr_text: |
  < Data Agent
  ® Agent
  Z 技能
  S 数据
  加 模型
  加 Agent监管
  > 开放集成
  o: 用户管理
  Agent监管
  © 刷新
  使用概览 ”会话记录 。 监管日志
  监管日志                                                                     无限制                ~ 无限制
  1)       全部模块                                       Y Agent                                                         创建                                               v          Q 搜索对象名称
  搜索操作者名称                            v
  操作时间                                    操作者                                  模块                           对象类型                              对象名称                                         操作                           结果
  2026-05-12 15:07:53             1                                         Agent                      Agent                                 未命名Agent_01                             创建                         成功
  (2    2026-05-12 11:58:09           1                                 Agent                  Agent                          未命名Agent_44                      创建                    成功
  2026-05-12 11:10:15             1                                        Agent                      Agent                                未命名Agent_31                            创建                        成功
  2026-05-11 19:52:34             1                                         Agent                      Agent                                 未命名Agent_31                             创建                         成功
  
-->

## 3. データとアカウントのマッピング

### データモジュール

データモジュールは、Agentに分析素材を提供するコア機能です。
照会や分析の対象となる業務データはすべてここで管理・設定されます。
現在、OrangeBIの分析テーマ、ダッシュボード、およびExcelファイルのインポートに対応しています。

「管理バックエンド>データ」にアクセスすると、左側のディレクトリツリーでデータの管理が可能です。
フォルダやデータ資産の名称変更、移動、削除などの操作がサポートされています。
リスト上部のフィルタアイコンをクリックすると、すべて、FRBI分析テーマ、FRBIダッシュボードの分類でデータを絞り込めます。

<!-- VISUAL_PENDING
visual_id: data-module-demo
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1775120078hwWU.png
  ocr_text: |
  < Data Agent                    RES                                 +
  oS 连锁经营分析-多时间 OC
  88 Agent                       Q 搜索名称                   了
  商品销售明细.…     图 O 共23条                              Q 字段搜引
  ” © 全部数据
  Z 技能                       鲜BzB               7     商品信息维度表    T 商品编码           T 商品类别           T 商品名称
  心 测试数据集                                                  47DFCFOA-87A5-42BD-BCA... 饮料                         纯悦550ml矿物质水
  S 数据                           Els                  加      门店信息维度表
  A3E1185B-5B4E-497E-B5B6... 饮料                                                  RSS 280M
  > 连锁经营分析-多时间
  Eb 知识库                       o 连鲁经营分析           7                   8C56F4E3-B518-44B7-8080... 调料                太太乐40g鸡精调味料
  J                      fo SERNIRERS     1      .                 6B38CB04-702F-4F3B-9DF9... 调料              多力葵花油500ml
  © 模型                          > 连锁经营分析多模型
  作 连锁经营分析-sql直连          co                            AE451BC0-8615-4F8C-8126... SB                       丽芝士散装系列
  @ Agent监管                         S 连锁经营分析-直连         本                        BE2DA7FO-1E24-4729-BED... 。 零食                    嘉士利115g威化饼
  > 连锁经 z营FILE >》        区                         G2CF9CFA-1E86-4960-B7C... 2                     三全960g奶香馒头
  & 外高桥                       全                              CBB40A41-178E-44F7-BD5... ER                         格力高55g草莓味百奇
  5B7ECC92-0FCC-4F40-98F... 2B                                    金冠森香颂夹心蛋糕系列
  7D6DCE09-0F 1F-4052-B28A... 零食                                    盐津铺子散装系列
  77DA67A0-ED8C-4FB3-8E0... 零食                                   养乐多100ml\"5乳酸菌
  OA88662D-AEF2-4756-BASA... 零食                                         德芙巧克力
  67E818C0-3E49-4010-A453-...         :                                                      德芮巧克力180g
  E5EA2E2A-DC19-4D47-BF0.…      品                 家之寅圆形24夹晒架
  31995BCC-72AA-413B-9B2...                         BRE 1 500g SEER
  BC639DE8-B503-437C-9B6...            品                                 微爽日用245mm
  E5BBD85B-DOBE-4C5F-A71.…                                               FAX 1000MIA AA
  59F35931-24BA-46DC-9551...                                              本地小白菜
  12EF7049-C847-4A7F-A5B4.…                                                                西红柿
  SDDCE422-6782-43D2-9AC...                                                      西域香妃蜜瓜
  共23条                                                                                                    <
  
-->

データ資産の削除は関連するAgentに影響を与え、復元できないため注意してください。
データ資産を追加するには、「+」をクリックしてExcelファイルをアップロードするか、分析テーマなどをインポートします。

<!-- VISUAL_PENDING
visual_id: data-add-analysis-subject
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1775721163cFvc.png
  ocr_text: |
  < Data Agent                     数据名
  88 Agent                        Q 搜索名称
  © 全部数据
  CO 技能
  四 B2B                                                        3]
  S 数据                            Bye
  & 知识                       ox  添加分析主题
  识
  © HH                     GE hams: RAR
  S| 我的分析
  G##
  @ Agent监管                           Q 搜索名称
  Lo Ba
  回 Agent联接                    ox      we 协作给我的
  o%         G@ Beau
  >A        入 demo数据
  四 PC     mS 国金风控报告 (勿动)
  BR         we 测试文件夹
  四连         Ge 小One分析报告
  ，国国         we 壳牌B2B报告                                                 请选择分析主题预览
  马连         &@ 客户数据
  > GM      @ 问答历史记录
  > ae         & 连锁经营分析
  四 Be        1 nami
  4        已选择分析主题: 0 个
  On
  GF
  > fj Be
  
-->

左側のディレクトリで分析テーマやダッシュボードをクリックすると、右側でプレビューが表示されます。
分析テーマのプレビューでは、データ明細のページング表示やフィールド検索がサポートされています。
ダッシュボードのプレビューでは、ダッシュボード全体が表示されます。
また、ダッシュボードの別名保存、エクスポート、適応、パフォーマンス分析、指標情報の確認、フィルタ照会などの操作も可能です。

<!-- VISUAL_PENDING
visual_id: data-preview-analysis
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1775130451wYMp.png
  ocr_text: |
  < Data Agent
  88 Agent
  O 技能
  多 数据
  E ARE
  @ 模型
  @ Agent监管
  数据吕
  oS ”连锁经营分析-多时间 今
  Q 搜索名称           了
  商品销售明细.…
  + = 全部数据
  £8 B2B                                时商品信息维度表
  Ce             门店信息维度表
  > 连锁经营分析-多时间
  & BWBE Oi
  > 连锁经营分析多模型
  > 连锁经营分析-sq|直连
  > 连锁经营分析-直连
  连锁经营分析-双模型
  查看字段信息
  转 回   共23条
  T 商品编码
  47DFCFOA-87A5-42BD-BCA...
  A3E1185B-5B4E-497E-BSB6...
  8C56F4E3-B51B-44B7-8080...
  6B38CB04-702F-4F3B-9DF9...
  AE451BC0-8615-4F8C-8126...
  BE2DA7F0-1E24-4729-BED...
  62CF9CFA-1E86-4960-B7C...
  CBB40A41-178E-44F7-BDS...
  5B7ECC92-0FCC-4F40-98F...
  7D6DCE09-0F 1F-4052-B28A...
  77DA67A0-ED8C-4FB3-8E0...
  0A88662D-AEF2-4756-BAQA...
  67E818C0-3E49-4010-A453-...
  ES5EA2E2A-DC19-4D47-BF0...
  31995BCC-72AA-413B-9B2...
  BC639DE8-B503-437C-9B6...
  ESBBD85B-DOBE-4C5F-A71...
  59F35931-24BA-46DC-9551...
  12EF7049-C847-4A7F-ASB4...
  SDDCE422-6782-43D2-9AC...
  共23条
  T 商品类别
  饮料
  饮料
  调料
  零食
  零食
  零食
  零食
  零食
  生鲜
  生鲜
  生鲜
  分页
  语义信息
  支持字段搜索
  T 商品名称
  纯悦550ml矿物质水
  HERS 280M
  太太乐40g鸡精调味料
  多力葵花油500ml
  丽芝士散装系列
  嘉士利115g威化饼
  三全960g奶香馒头
  格力高55g草莓味百奇
  金冠森香颁夹心蛋糕系列
  盐津铺子散装系列
  养乐多100ml*5乳酸菌
  德芙巧克力
  (RIGHT 180g
  家之富圆形24夹栖架
  雕牌1500g洗洁精
  微爽日用245mm，
  球柔1000ml去局洗发露
  本地小白菜
  西红柿
  西域香妃密瓜
  查看
  
-->

「フィールド」タブでは、フィールドタイプの確認や数値形式の設定が可能です。
指標属性として、以下の3つを設定できます。
- **累積可能指標**: 指標値をすべての次元で直接加算して集計できる指標。
- **半累積指標**: 特定の次元では直接加算できず、特殊な集計方法が必要な指標。
- **不可累積指標**: どの次元でも直接加算して集計できない指標。

<!-- VISUAL_PENDING
visual_id: data-fields-info
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1775720658juGz.png
  ocr_text: |
  < Data Agent
  ee
  8 Agent
  S 数据
   知识库
  钙 模型
  @ Agent监管
  数据虽
  Q 搜索名称
  vy = 全部数据
  & B2B
  从 测试数据集
  从 连锁经营分析-多时间
  > 连锁经营分析
  o 连锁经营分析多模型
  > 连锁经营分析-sq|直连
  > 连锁经营分析-直连
  从 连锁经营分析-双模型
  商品销售明细.…
  门店信息维度表
  语义信息
  回@-         rom
  =}
  a        AHA AA)            日期(年月日)
  T 文本     门店编码              门店编码
  T 文本     单据编码              单据编码
  T 文本     商品编码              商品编码              6
  Be                 =                        7
  4 )  数据格式 。 指标属性
  # 数值       一一                             +3
  4 mM    数字        百分比       g
  数量单位      万                  v
  einem      元
  FAH      . @
  示例               2.000万元
  取消        确定
  
-->

「意味情報」ボタンをクリックすると、フィールドごとにビジネス用語を追加できます。
これにより、自然言語認識の精度が向上します。
意味情報のインポートやエクスポートもサポートされています。
設定後「検出して保存」をクリックすると自動的に認識が有効になります。

<!-- VISUAL_PENDING
visual_id: data-semantics-page
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/177513122772VJ.png
  ocr_text: |
  < Data Agent
  ee
  8 Agent
  O 技能
  S 数据
  E> 知识库
  钙 模型
  @ Agent监管
  数据虽
  Q 搜索名称
  vy = 全部数据
  号B2B
  ta SSP kite Ae
  语义信息
  Q 搜索对象业务用语
  暂无预览数据
  共5000条
  字段名
  日期年月日)
  字段别名
  BRAGA A)
  添加业务用语
  取消
  导入
  险测并保存
  
-->

データのリアルタイム性を確保するため、定期的な自動リフレッシュ頻度を設定できます。
更新設定画面で頻度と起点時間を設定することでデータの正確性を維持できます。
起点時間を設定しない場合、デフォルトで毎時00分にリフレッシュが実行されます。
パフォーマンスの低下を防ぐため、業務要件に合わせて設定してください。

<!-- VISUAL_PENDING
visual_id: data-refresh-config
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1775131905OxOM.png
  ocr_text: |
  <“ Data Agent
  68 Agent
  O 技能
  S 数据
  知识库
  加 模型
  @ Agent监管
  十
  S 。 连锁经营分析-sql直连 信
  | Q 搜索名称                             v
  时sql-商品销售.…         时 四 共5000条
  ” = 全部数据
  LB B2B                   be     & sql-商品信息…      首 日期年月B) 了 门店编码
  2023-08-14 00:... D010214
  es Mir:       te                     see              »
  & 测试数据集                           sql-门店信息.…
  _                                                                 2023-11-19 00:...  D010311
  数据预加载刷新
  2022-09-03 00:...  D010311
  定期自动加载刷新数据，可以确保Agent使用数据的准确性
  2023-11-28 00:...  D010223
  分析主题        个                                    6           2022-10-28 00:...  D010173
  2022-03-01 00:...  D010173
  上次刷新: 2026-04-02 11:41:45
  2024-10-16 00:... D010275
  自动刷新频率                                                               2024-01-09 00:...  D010103
  个 每 al - 动加载刷新一次                  2022-11-10 00:.，， D010106
  _                                                                             2022-04-06 00:...  D010186
  计时起点
  © [seorem oooeoo meres
  2022-08-25 00:...  D010318
  >
  个    2024-05-30 00:...  DO10310
  BUS [ESN 2025-04-21 00:...  Dot0248
  }                                                                !      ]
  2022-06-04 00:...  D010318
  2022-01-16 00:...  D010318
  T 单据编码
  SMDHN180001.
  SMDGZ1800015
  SMDGZ1800043
  SMDSH1800001
  SMDCD180003.
  SMDCD180004.
  SMDWH18000..
  SM8011802003:
  SM8011803009(
  SMDCD180007.
  SMDGZ1800097
  SMDGZ1800114
  SMDGZ1800125
  SMDSH1800207
  SMDGZ1800155
  SMDGZ1800170
  
-->

### IMユーザマッピング

IMユーザマッピングは、サードパーティのIMプラットフォームとEmonのユーザを紐付ける機能です。
これにより、定期タスクの通知先を正確に特定できます。
現在、企業WeChat（企業微信）の連携に対応しています。

「管理バックエンド>ユーザ管理>IMユーザマッピング」タブから「編集」をクリックして設定します。
企業WeChatの管理バックエンドでアプリケーション連携を完了した後、マッチング方式を選択します。

- **ユーザ名/IDマッチング**: システムが自動で両端のユーザ名/IDをマッチングします。
- **カスタムマッチング**: インポートテンプレートを使用し、対応関係を記入したExcelをアップロードします。

<!-- VISUAL_PENDING
visual_id: im-mapping-app-docking
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/17799662782hsX.png
  ocr_text: |
  < Data Agent
  
  ® Agent
  
  技能
  
  S 数据
  
  © 模型
  
  钙 Agent监管
  
  > 开放集成
  
  O 权限管理
  
  用户管理
  所有用户 mew | wae QO
  
  © 企业微信机器人                                                                                                                                                                                     保存
  
  © 请先在企业微信和创建"应用?并填入相关信息，否则系统无法对接企业微信用户名/ID 帮助文档
  
  应用对接*                    配置    (3
  
  映射方式                          户名/ID匹配 OBER
  
  用户映射                   十 添加映射                                                                                    个 上传用户映射表     人 清空
  企业微信用户名                                                                             Data Agent 用户名
  SI                                                   a      o      2                       v                           i
  x                                                   a      o      ti                       v                           i
  k                                                   分      eo      1                        Vv                           1
  s)                                                   分      所>      pl                       Vv                          w
  w                                                   Q      o      alt                      v                          全
-->

> ⚠ 警告
> 一括アップロード用のマッピング表は、テンプレートの形式に厳密に従って記入する必要があります。列名や形式が不規則な場合、解析に失敗します。

アップロード成功後も、手動でData Agentのユーザ名を変更することが可能です。

## 4. プラットフォーム利用状況の概要

Agent管理の「利用状況の概要」モジュールは、稼働状態と使用状況を監視するダッシュボードです。

全体概要では、Agentの数、使用回数、使用人数をリアルタイムで確認できます。
時間別のフィルタリング（当日、過去7日間、過去30日間、全期間、カスタム）に対応しています。
これにより、さまざまなサイクルにおける利用トレンドを柔軟に分析できます。

<!-- VISUAL_PENDING
visual_id: usage-overview-demo
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1779950407qITY.png
  ocr_text: |
  < Data Agent
  Agent监管
  @ Agent                                 使用概览”| 会话记录 ”定时任务 BEAD
  QZ 技能                                 全局概览                                                                                                                                                近30天    Vv
  S 数据                                         21%                                        >           3,476 2%                                 @           2A                                          e
                                                                                                                       -
  Agent 数量                                                                   Agent 使用次数                                                             Agent 使用人数
  O 模型       @
  加 Agent监                                 使用次数排行                                                                                                                                                      近30天 OV
  办 开放集成                                        Agent名称                                                                                                                                                                     使用次数
  2 用户管理                                 启”Dora-通用智能体                                                                                                                                                     1.252
  & ”财务单据费用查询助手                                                                                                                                                 501
  © 权限管理
  & ”全国市场潜量洞察报告员                                                                                                                                               298
  4 美妆品牌市场分析师                                                                                                                                                   272
  5 行政考勤数据助手                                                                                                                                                      215
  
-->

「使用回数ランキング」では、使用頻度上位5つのAgentが降順で表示されます。
価値の高いAgentを特定したり、使用頻度の低いAgentの最適化の評価に役立てられます。

<!-- VISUAL_PENDING
visual_id: usage-overview-ranking
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
production_method: recreate_in_target_locale_ui
source:
  local_path: data/dora/assets/1779950665FdRS.png
  ocr_text: |
  < Data Agent
  ® Agent
  技能
  S 数据
  © 模型
  加 Agent监
  > 开放集成
  & APSE
  O 权限管理
  Agent监管
  使用概览 ”会话记录 定时任务 ”监管日志
  全局概览
  21个
  Agent 数量
  使用次数排行
  Agent名称
  @ ”Dora-通用智能体
  2) OS ”财务单据费用查询助手
  & ”全国市场潜量洞察报告员
  4 ，”美妆品牌市场分析师
  5 ”行政考勤数据助手
  ad
  3,476次
  Agent 使用次数
  @
  2A
  Agent 使用人数
  近30天         Vv
  1)  近30天     Vv
  使用次数
  1,252
  501
  298
  272
  215
  
-->

<!-- 本頁已依品牌規則處理 6 條過濾項 -->
