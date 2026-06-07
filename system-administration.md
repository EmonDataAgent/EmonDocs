---
page_id: system-administration
title: "系統設定與權限管理"
locale: zh-TW
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
generated_at: "2026-06-04T08:05:05+08:00"
---
<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-07T08:31:49Z
source_master: data/dora/locale/zh-TW/pages/system-administration.md
-->

# 系統設定與權限管理

## 使用者與權限分配

超級管理員可透過『管理后台』的『用户管理』與『权限管理』，集中設定平台內所有使用者的角色與權限。

### 管理所有使用者

在『管理后台』>『用户管理』>『所有用户』中，您可以查看、搜尋並管理全平台的使用者。

<!-- VISUAL_PENDING
visual_id: all-users-01
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
purpose: 展示所有用户页面的入口及列表视图
placement_hint: 段落 anchor 2.1 设置入口
source_original_url: ""
source_local_path: "data/dora/assets/1779370282OF3C.png"
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
    a
  wo
  一
  oR
  nw
  =
  /1 >
caption_zh_TW: "所有使用者页面的入口及列表視圖"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: all-users-06
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示使用条件过滤搜索用户
placement_hint: 段落 anchor 2.6 搜索用户
source_original_url: ""
source_local_path: "data/dora/assets/1779370681J2Bp.png"
ocr_text: |
  < Data Agent
  ® Agent
  技能
  S 数据
  © 模型
  © Agent监管
  > 开放集成
  2 用户管理
  O 权限管理
  用户管理
  所有用户 用户类型
  1IM用户映射
  | OQ 搜索用户名/姓名             |
  全部
  立|
  用户名                  姓名           EAS
  查看用户
  开发用户
  未分配
  超级管理员
  admin-test                           admin-test                           -
  admin-test2                         admin-test2                         -
  admin-test3                         admin-test3                         -
  Anya                                     an                                  ‘or -
  Aria                                       Aria.Han                               -
caption_zh_TW: "使用条件篩選搜尋使用者"
rebuild_spec: null
-->

1. 點選『添加用户』以建立新使用者，必須填寫使用者名稱、姓名與密碼，並指定其使用者類型（『查看用户』、『开发用户』或『未分配』）。在此建立的使用者會自動同步至 FineBI 平台。

<!-- VISUAL_PENDING
visual_id: all-users-02
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示添加用户时的必填和选填字段
placement_hint: 段落 anchor 2.2 添加用户
source_original_url: ""
source_local_path: "data/dora/assets/1779370374NSAU.png"
ocr_text: |
  添加用户
  用户名*
  请输入
  姓名*
  请输入
  密码*
  请输入密码
  邮箱
  请输入
  手机号码
  中国大陆 +86         Y | | 请输入
  用户类型*
  5| 查看用户         开发用户
caption_zh_TW: "新增使用者时的必填和選填欄位"
rebuild_spec: null
-->

2. 針對既有使用者，可編輯其姓名、電子郵件、手機號碼與類型，或點選『重置密码』。使用者名稱在建立後無法修改。

<!-- VISUAL_PENDING
visual_id: all-users-03
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示编辑用户弹窗中的可修改项
placement_hint: 段落 anchor 2.3 编辑用户
source_original_url: ""
source_local_path: "data/dora/assets/1779370512U797.png"
ocr_text: |
  邮箱
  请输入
  手机号码
  中国大陆 +86         Y | | 请输入
  用户类型*
  查看用户 > FRAP
caption_zh_TW: "編輯使用者對話方塊中的可修改项"
rebuild_spec: null
-->

3. 您可隨時『禁用』使用者，禁用後使用者將無法登入 Dora 平台。此為暫時措施，資料將保留於系統中且可隨時『启用』。若確定不再需要，可選擇刪除，刪除後資料將無法恢復。

<!-- VISUAL_PENDING
visual_id: all-users-04
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
purpose: 展示列表中用户状态为禁用或启用
placement_hint: 段落 anchor 2.4 禁用与启用
source_original_url: ""
source_local_path: "data/dora/assets/17793705729JgG.png"
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
caption_zh_TW: "列表中使用者狀態为禁用或啟用"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: all-users-05
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示删除用户时的二次确认对话框
placement_hint: 段落 anchor 2.5 删除用户
source_original_url: ""
source_local_path: "data/dora/assets/1779370627ZvAs.png"
ocr_text: |
  确定删除?
  删除后不可恢复，确认删除用户“Aria"吗?
caption_zh_TW: "刪除使用者时的二次確認對話方塊"
rebuild_spec: null
-->

使用者在 Dora 中的資料權限，會直接繼承其在 FineBI 平台的設定。

### 設定使用者類型

平台內的使用者分為四種類型：
- **超級管理員**：平台最高權限角色，可管理所有使用者與模組，為內建角色，不可修改。
- **開發用戶**：平台配置與管理角色，可建立、編輯、發佈 Agent，並管理模型、監管與開放整合等模組。可與查看用戶、未分配用戶互轉。
- **查看用戶**：一般使用者，僅能與 Agent 對話及查看已發佈的 Agent，無後台配置權限。可與開發用戶、未分配用戶互轉。
- **未分配**：無任何平台操作權限。可與開發用戶、查看用戶互轉。

在『管理后台』>『用户管理』>『用户类型』頁籤中，可透過搜尋框尋找特定使用者，或勾選多個使用者並點選上方按鈕，批次指派使用者類型。

<!-- VISUAL_PENDING
visual_id: user-types-01
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
purpose: 展示用户类型页面的入口及分类列表
placement_hint: 段落 anchor 2.1 设置入口
source_original_url: ""
source_local_path: "data/dora/assets/1779370786RN8n.png"
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
caption_zh_TW: "使用者類型页面的入口及分類列表"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: user-types-02
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 动图演示如何勾选并批量分配用户类型
placement_hint: 段落 anchor 2.3 批量分配用户类型
source_original_url: ""
source_local_path: "data/dora/assets/1779849745751543.gif"
ocr_text: |
  (原圖無 OCR 文字)
caption_zh_TW: "動圖展示如何勾选并批次分配使用者類型"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: user-types-03
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 动图演示使用搜索框模糊匹配用户名或姓名
placement_hint: 段落 anchor 2.4 搜索用户
source_original_url: ""
source_local_path: "data/dora/assets/1779849858391709.gif"
ocr_text: |
  (原圖無 OCR 文字)
caption_zh_TW: "動圖展示使用搜尋框模糊對應使用者名或姓名"
rebuild_spec: null
-->

### 權限分配

在『管理后台』>『权限管理』中，可為指定使用者設定更細緻的操作權限：

<!-- VISUAL_PENDING
visual_id: perm-assignment-01
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
purpose: 展示权限管理页面的入口及初始状态
placement_hint: 段落 anchor 2.1 设置入口
source_original_url: ""
source_local_path: "data/dora/assets/1779370062LB1M.png"
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
caption_zh_TW: "權限管理页面的入口及初始狀態"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: perm-assignment-02
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示点击左侧用户后右侧面板展示权限配置内容
placement_hint: 段落 anchor 2.2 选择用户
source_original_url: ""
source_local_path: "data/dora/assets/1779370126nYeV.png"
ocr_text: |
  权限管理
  用户列表
  OQ 搜索用户名/姓名
  > mS AARP 21
  . ee |)
  y
  ,;
  o
  2
  a
       =» coral(coral)                                  |
  =     “nico(nico)
  = nico3(nico2)
  => no(no)
  = press_test_17(press_test_17)
  = press_test_20(press_test_20)
  = shuju(shuju)
  = sla(si2)
  = tina(tina)
  = tomorrow(tomorrow)
  coral(coral)
  暂无内容
  Agent前台使用 管理后台   (2
  搜索名称
  Agent名称
  Dora-通用智能体
  kyle定时任务测试
  检索test_jeremy
  门店经营预警521
  连锁经营分析
  数据查询与分析类
  时分秒测试
  从模板创建html报告
  压测agent_1
  报告-图表插入测试-Dylan
  报告附件测试
  共109条
  使用权限
  6
  6668686666886
  /6
caption_zh_TW: "点击左侧使用者后右侧面板權限設定內容"
rebuild_spec: null
-->

| 權限類型 | 模組 | 權限說明 |
| :--- | :--- | :--- |
| **Agent 前台使用** | 前台對話介面 | 控制使用者是否能在前台使用指定的 Agent。 |
| **管理后台**（僅『开发用户』） | Agent 模組 | 『个人开发权限』：可建立、編輯、刪除自己的 Agent。<br>『公共管理权限』：可發佈 Agent。 |
| | 模型模組 | 『个人开发权限』：可增刪供個人使用的模型。<br>『公共管理权限』：可增刪公共模型。 |
| | Agent 監管模組 | 『个人开发权限』：可查看自己具備管理權限的 Agent 監管資料。<br>『公共管理权限』：此模組無管理權限。 |
| | 開放整合模組 | 『个人开发权限』：可查看和使用開放整合頁面。<br>『公共管理权限』：此模組無管理權限。 |

<!-- VISUAL_PENDING
visual_id: perm-assignment-03
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
purpose: 展示管理后台各模块的个人开发权限和管理权限配置
placement_hint: 段落 anchor 2.3 平台权限分配
source_original_url: ""
source_local_path: "data/dora/assets/177996718770JF.png"
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
caption_zh_TW: "管理後台各模組的個人開發權限和管理權限設定"
rebuild_spec: null
-->

在 Agent 查詢資料時，使用者能存取的資料範圍完全取決於其在 FineBI 的權限。若使用者在 FineBI 缺少某資料源的權限，則無法在 Agent 中查詢該資料。開發人員在新增資料資源時，也只能加入自己在 FineBI 已獲授權的資料。上傳的本機 Excel 檔案不受此資料權限限制。

## 排程任務與監管日誌

### 排程任務
排程任務（定時任務）讓 Agent 具備自動化能力，可依設定週期主動執行資料彙整、報告生成或異常預警，並透過多種管道推播給指定使用者，實現從被動問答到主動服務的升級。

<!-- VISUAL_PENDING
visual_id: agent-scheduled-task-effect
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示销售场景中定时推送销售风险预警的实际对话与预警通知效果
placement_hint: 段落「效果演示」
source_original_url: ""
source_local_path: "data/dora/assets/17793271106tJ1.png"
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
caption_zh_TW: "銷售場景中排程推送銷售風險預警的實際对话与预警通知效果"
rebuild_spec: null
-->

您可從『管理后台』（Agent 配置頁面）或前台對話介面的『定时任务』進入設定：

<!-- VISUAL_PENDING
visual_id: agent-scheduled-task-backend
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
purpose: 展示在管理后台中定时任务的配置入口
placement_hint: 段落「2.1.1 管理后台（Agent 配置页面）」
source_original_url: ""
source_local_path: "data/dora/assets/1779327326c9fy.png"
ocr_text: |
  © @& Ws smeseR 人 cee tHe
  封装Agent
  
  Ub BRERM
  
  位 ”分析主题数据查询
  
  (© 智能PPT
  
  (ES 代理金融业务发展通报报告生成技能
  
  全新闻通讯
  
  位 ”仪表板检索
  
  >» MCP.
  
  + 定时任务
  
  > 对接IM工具
  
  会话体验
  
  多轮对话
  
  最近保存; 2026/5/17 1640-18 全部用户可而 。 | 保存 | | 取消发布 发布
  
  预览 当前为测试环境                                                                                                                                           重置对话
  
  添加定时任务
  
  | 推荐模板
  
  经营周报任务
  定期汇总经营关键指标，自动生成并推送周报分析内容
  
  数据预警任务
  监控关键指标变化，在触发条件后自动推送预警信息
  
  站
caption_zh_TW: "在管理後台中定时任务的設定入口"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: agent-scheduled-task-frontend
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在前台用户界面中定时任务的菜单入口
placement_hint: 段落「2.1.2 前台（Agent 使用界面）」
source_original_url: ""
source_local_path: "data/dora/assets/1779327477IwRO.png"
ocr_text: |
  OQ & 江苏-连锁经营分析        O 定时任务                                                                         需要管理该 Agent 的所有定时任务? 前往 TAgentitey 7
  Q 新聊天
  QQ 搜索                   全部任务来源   Y ”全部推送渠道   Y
  [定时任务                    1)
  历史会话
  
  添加定时任务
  
  经营周报任务
  定期汇总经营关键指标，自动生成并
  
  数据预警任务
  监控关键指标变化，在触发条件后自动推送预警信息
  
  1         = 管理后台
caption_zh_TW: "在前台使用者介面中定时任务的選單入口"
rebuild_spec: null
-->

1. 點選『添加定时任务』，可選擇『从空白开始』或使用內建的推薦範本（如經營周報、資料預警）。

<!-- VISUAL_PENDING
visual_id: agent-scheduled-task-blank
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示从空白新建定时任务的配置表单
placement_hint: 段落「2.2.1 从空白新建」
source_original_url: ""
source_local_path: "data/dora/assets/1779327573ZlB3.png"
ocr_text: |
  添加定时任务
  
  定时任务名称*
  如: 门店销售分析日报
  
  任务提示词”
  请输入执行的任务和需要满足的条件，如: 当销售额低于100时，发送门店销售分析报告
  
  定时执行频率*
  
  OWS
caption_zh_TW: "从空白建立定时任务的設定表單"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: agent-scheduled-task-template
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示提供的新建定时任务推荐模板卡片
placement_hint: 段落「2.2.2 从模板新建」
source_original_url: ""
source_local_path: "data/dora/assets/1779328717KgiC.png"
ocr_text: |
  添加定时任务
  
  十
  从空白开始
  
  经营周报任务
  定期汇总经营关键指标，自动生成并推送周报分析内容
  
  数据预警任务
  监控关键指标变化，在触发条件后自动推送预警
caption_zh_TW: "提供的建立定时任务推薦範本卡片"
rebuild_spec: null
-->

2. 設定任務名稱、執行頻率，並編寫任務提示詞（應包含任務目標、核心規則與輸出要求）。
3. 指定觸達使用者與推播管道（目前支援平台通知與通訊軟體，若使用企業微信需先完成對接）。必須至少勾選一個管道，否則結果無法送達。

請確認 Agent 已開啟『对话订阅』技能，排程任務才能正常執行。從後台建立的任務會標記為『Agent內配置』，從前台建立則為『我添加的』。

<!-- VISUAL_PENDING
visual_id: agent-scheduled-task-tags
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示定时任务列表中不同来源标签的区别
placement_hint: 段落「3. 注意事项」
source_original_url: ""
source_local_path: "data/dora/assets/1779363159DdGv.png"
ocr_text: |
  江苏省销售关预区| 2fig |                                            ab eu@®
  
  查询江苏省2024年的总销售额，判断是否小于120万元 (1200000元) 。如果江苏省2024年销售额小于120万元，则和触发预警任务， 如果销售额大于等于120万…
  
  每天 11:44                                                                                      全
  
   销售日报| Acorn |                                                                     G &O
  
  查询去年今天各省份的销售额，并分析后输出一份销售分析日报。
  每天 10:32                                                                                                                                                                                    全
caption_zh_TW: "定时任务列表中不同來源標籤的區別"
rebuild_spec: null
-->

### 排程任務監管

管理員可在『管理后台』>『Agent监管』>『定时任务』中統一監控全平台的排程任務運作狀況：

- **查看任務詳情**：列表呈現任務提示詞、執行頻率、推播管道、任務來源與觸達使用者，並支援啟動、關閉、編輯或刪除任務。
- **執行紀錄**：點選『执行记录』查看歷史資料，可依推播管道與使用者進行篩選。

<!-- VISUAL_PENDING
visual_id: view-execution-001
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示在定时任务列表中点击查看执行记录的位置
placement_hint: 1
source_original_url: "data/dora/assets/1779367415Hr6r.png"
source_local_path: "data/dora/assets/1779367415Hr6r.png"
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
caption_zh_TW: "在定时任务列表中点击查看執行紀錄的位置"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: view-execution-002
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示执行记录详情页的筛选区域和列表信息
placement_hint: 2
source_original_url: "data/dora/assets/1779368250FtrU.png"
source_local_path: "data/dora/assets/1779368250FtrU.png"
ocr_text: |
  Agent监管
  全部任务来源
  全部推送渠道
  执行记录
caption_zh_TW: "執行紀錄詳情页的筛选區域和列表資訊"
rebuild_spec: null
-->

- **會話紀錄**：在執行紀錄中點選單筆歷史紀錄的查看按鈕，並選定觸達使用者，系統將跳轉至對應的會話紀錄區塊。

<!-- VISUAL_PENDING
visual_id: view-session-001
role: decorative
locale_sensitivity: medium
brand_sensitivity: medium
purpose: 动图演示如何跳转至会话记录板块
placement_hint: 2
source_original_url: "data/dora/assets/1779776604531159.gif"
source_local_path: "data/dora/assets/1779776604531159.gif"
ocr_text: |
  (原圖無 OCR 文字)
caption_zh_TW: "動圖展示如何跳轉至會話紀錄區塊"
rebuild_spec: null
-->

### 監管日誌

『Agent监管』模組下的『监管日志』記錄了全平台所有模組（如 Agent、資料、模型、開放整合等）的新增、編輯、測試與刪除等操作行為，確保平台操作可追溯。管理員可依時間範圍與操作者名稱進行篩選，快速定位並排查異常。

<!-- VISUAL_PENDING
visual_id: audit-logs-01
role: screenshot
locale_sensitivity: high
brand_sensitivity: medium
purpose: 展示监管日志界面的列表及筛选字段
placement_hint: 段落 anchor 2. 日志查看与筛选
source_original_url: ""
source_local_path: "data/dora/assets/1778577191huCE.png"
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
caption_zh_TW: "監管日誌介面的列表及筛选欄位"
rebuild_spec: null
-->

## 資料與帳號映射

### 管理資料資產

『管理后台』>『数据』模組是為 Agent 提供分析素材的核心樞紐。目前支援匯入 FineBI 的分析主題與儀表板，以及上傳本機的 Excel 檔案（.xls、.xlsx、.csv）。

<!-- VISUAL_PENDING
visual_id: data-module-demo
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示添加数据资产后的整体界面效果
placement_hint: 1.3 效果演示
source_original_url: ""
source_local_path: "data/dora/assets/1775120078hwWU.png"
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
  77DA67A0-ED8C-4FB3-8E0... 零食                                   养乐多100ml"5乳酸菌
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
caption_zh_TW: "新增資料資產后的整體介面效果"
rebuild_spec: null
-->

- **新增資料資產**：點選『+』，可選擇『上传文件』、『分析主题』或『仪表板』。

<!-- VISUAL_PENDING
visual_id: data-upload-file-gif
role: decorative
locale_sensitivity: medium
brand_sensitivity: medium
purpose: 动图展示上传Excel文件的过程
placement_hint: 3.1 上传文件
source_original_url: ""
source_local_path: "data/dora/assets/1779788276215511.gif"
ocr_text: |
  (原圖無 OCR 文字)
caption_zh_TW: "动图上傳Excel文件的過程"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: data-add-analysis-subject
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示添加分析主题的弹窗及右侧字段结构预览
placement_hint: 3.2 添加分析主题
source_original_url: ""
source_local_path: "data/dora/assets/1775721163cFvc.png"
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
caption_zh_TW: "新增分析主題的對話方塊及右侧欄位結構預覽"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: data-add-dashboard
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示添加仪表板的弹窗及右侧仪表板内容预览
placement_hint: 3.3 添加仪表板
source_original_url: ""
source_local_path: "data/dora/assets/1775721171dZIE.png"
ocr_text: |
  < Data Agent
  88 Agent
  O 技能
  S 数据
  & 知识
  加 模型
  @ Agent监管
  @ Agent联接
  数据 吕
  Q 搜索名称
  © 全部数据
  四 B2B
  Bytes
  Ge
  > GM
  > BB
  ® Bz
  66
  GF
  > G@ Be
  告agent测试
  金风控日报 (勿动)
  已选择仪表板: 0 个
  =
  请选择仪表板预
  ay
caption_zh_TW: "新增儀表板的對話方塊及右侧儀表板內容預覽"
rebuild_spec: null
-->

- **目錄管理**：左側目錄樹提供資料夾分組功能，可透過篩選圖示依資料來源過濾，並支援重新命名、移動與刪除。根目錄『全部数据』不可修改。刪除資料夾或資產會影響相關的 Agent 且無法恢復。

<!-- VISUAL_PENDING
visual_id: data-directory-tree
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示左侧数据目录树和搜索框
placement_hint: 2.1 查看与筛选数据
source_original_url: ""
source_local_path: "data/dora/assets/1775120230yiKq.png"
ocr_text: |
  <“ Data Agent
  88 Agent
  Z 技能
  S 数据
  © 知识库
  钙 模型
  @ Agent监管
  数据虽   1)        +
     y
  y = 全部数据
  做 连锁经营分析-多时间
  从 连锁经营分析
  从 连锁经营分析多模型
  从 连锁经营分析-sql直连
  自动化test
  从 连锁经营分析-lIm3.2
  GB 连锁经营分析-Dylan
  从 连锁门店销售数据分析
  请选择左侧数据源
caption_zh_TW: "左侧数据目錄樹和搜尋框"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: data-directory-filter
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示数据目录的筛选分类下拉框
placement_hint: 2.1 查看与筛选数据
source_original_url: ""
source_local_path: "data/dora/assets/1775120341Gsg6.png"
ocr_text: |
  +t
  Data Agent
  88 Agent
  六
  技能
  数据
  知识库
  © 2 4
  模型
  目
  Agent监管
  数据吕
  Q 搜索名称                 |v |e
  + = 全部数据       全部 。FRBI分析主题。FRBI仪表板 | @
  GB B2B          =
  & 测试数据集
  从 连锁经营分析-多时间
  党 连锁经营分析-sql直连
  > 连锁经营分析-直连
  从 连锁经营分析-双模型
  & 外高桥
caption_zh_TW: "数据目录的筛选分類下拉選單"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: data-directory-manage
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示对文件夹和数据资产的重命名、移动和删除操作菜单
placement_hint: 2.2 目录管理
source_original_url: ""
source_local_path: "data/dora/assets/1775120430g5N8.png"
ocr_text: |
  <“ Data Agent                   BUTE cS                              +
  88 Agent                       Q 搜索名称                   Y
  y ™ 全部数据
  Z 技能                            BoB
  S 数据 Wit ES
  从 连锁经营分析-多时间
  S 连锁经营分析
  © 模型                                   > 连锁经营分析多模型
  & 连锁经营分析-sql直连
  Eb 知识库
  Agent监管                              心 连锁经营分析-直连
  > 连锁经营分析-双模型
caption_zh_TW: "对文件夹和資料資產的重新命名、移動和刪除操作選單"
rebuild_spec: null
-->

- **資料預覽與設定**：點選分析主題或儀表板，可在右側預覽資料明細或完整畫面（Excel 檔暫不支援預覽）。切換至『字段』頁籤，可設定數值格式與指標屬性：
  - **可累加**：指標值在所有維度上皆可直接相加彙總。
  - **半累加**：指標值在部分維度（如時間維度）上無法直接相加。
  - **不可累加**：指標值在任何維度上皆不可直接相加。

<!-- VISUAL_PENDING
visual_id: data-preview-analysis
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示分析主题类数据资产的明细与字段预览
placement_hint: 4.1 数据预览
source_original_url: ""
source_local_path: "data/dora/assets/1775130451wYMp.png"
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
caption_zh_TW: "分析主題类資料資產的明細与欄位預覽"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: data-preview-dashboard
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示仪表板类数据资产的完整预览效果
placement_hint: 4.1 数据预览
source_original_url: ""
source_local_path: "data/dora/assets/1775130389myJs.png"
ocr_text: |
  < Data Agent
  ee
  88 Agent
  O 技能
  S 数据
  fe)
  &
  [oF
  3
  By
  bu
  SUR S
  Q 搜索名称
  "” = 全部数据
  & B2B
  从 测试数据集
  © 连锁经营分析-多时间
  从 连锁经营分析-sq|直连
  从 连锁经营分析-直连
  [8B B2B候
  区域年份数据
  - 东区            = 2025                    2023                                                    ‘
  = 北区            = 2025                    2023
  一 南区            = 2025                    2023
  = 2025                                           2023
  区域省份数据
  一 上海市                                                  = 2025                                                                         74,9336
  云南省                                   = 2025                                                   25.7514
  内蒙古自治区                                          - 2025                                                                     30,128.€
  北京市                                                                          2025                                                                                                     202,912.5
  吉林省                                                                          2025                                                                                                       14,766.
  四川省                                                     2025                                                                         47,229.€
  天津市                                                                          2025                                                                                                       21,059.
  宁夏回族自治区                                                               2025                                                                                                        9,346.
  1v
  区域省市数据
  SS
  一 七台河市                             = 2025                   2023
  一 三亚市                         = 2025                2023
  = 2025                                       2023
caption_zh_TW: "儀表板类資料資產的完整預覽效果"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: data-fields-info
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示字段信息标签页及数值格式、指标类型的设置
placement_hint: 4.2 字段信息查看
source_original_url: ""
source_local_path: "data/dora/assets/1775720658juGz.png"
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
caption_zh_TW: "欄位資訊標籤页及數值格式、指標類型的設定"
rebuild_spec: null
-->

- **語意資訊配置**：點選『语义信息』可為欄位設定業務上的同義詞（例如將「銷售額」對應至「營收」），以提升 Agent 的語意辨識準確率，並支援批次匯入與匯出。點選『检测并保存』後即可生效。語意資訊配置僅對當前資料資產生效，不同資料資產需獨立維護。

<!-- VISUAL_PENDING
visual_id: data-semantics-page
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示语义信息配置页面的列表
placement_hint: 4.3 语义信息配置
source_original_url: ""
source_local_path: "data/dora/assets/177513122772VJ.png"
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
caption_zh_TW: "語意資訊設定页面的列表"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: data-semantics-gif
role: decorative
locale_sensitivity: medium
brand_sensitivity: medium
purpose: 动图展示批量导入/导出业务用语的过程
placement_hint: 4.3 语义信息配置
source_original_url: ""
source_local_path: "data/dora/assets/1779776387910068.gif"
ocr_text: |
  (原圖無 OCR 文字)
caption_zh_TW: "动图批次匯入/匯出業務用語的過程"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: data-semantics-add
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示添加业务用语并检测保存的效果
placement_hint: 4.3 语义信息配置
source_original_url: ""
source_local_path: "data/dora/assets/1775131505LKNt.png"
ocr_text: |
  语义信息
  对象类型                对象                                                          业务用语
  字段                       销售额
caption_zh_TW: "新增業務用語并檢測儲存的效果"
rebuild_spec: null
-->

- **資料預先載入刷新**：設定自動刷新頻率與計時起點，確保 Agent 查詢時的資料即時性。建議依據業務需求合理設定，避免過度刷新影響效能。

<!-- VISUAL_PENDING
visual_id: data-refresh-icon
role: icon
locale_sensitivity: none
brand_sensitivity: none
purpose: 展示数据刷新配置的入口图标
placement_hint: 5. 数据刷新配置
source_original_url: ""
source_local_path: "data/dora/assets/1775131565Nztk.png"
ocr_text: |
  (原圖無 OCR 文字)
caption_zh_TW: "数据預先載入刷新設定的入口圖示"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: data-refresh-config
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示数据预加载刷新的频率与计时起点配置面板
placement_hint: 5. 数据刷新配置
source_original_url: ""
source_local_path: "data/dora/assets/1775131905OxOM.png"
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
caption_zh_TW: "数据预加载預先載入刷新的頻率与計時起點設定面板"
rebuild_spec: null
-->

### IM 帳號映射

為確保排程任務的訊息能準確推播至第三方通訊軟體，需設定 IM 帳號映射，建立使用者對應關係：

<!-- VISUAL_PENDING
visual_id: im-mapping-entry
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示 IM 用户映射配置入口及支持的 IM 平台列表
placement_hint: 段落「2.1 设置入口」
source_original_url: ""
source_local_path: "data/dora/assets/1779966197X8yy.png"
ocr_text: |
  < Data Agent
  ® Agent
  Z 技能
  S 数据
  © Agent监管
  > 开放集成
  用户管理
  所有用户 用户类型
  企业微信
  1IM用户映射
  用户名/ID匹配”已匹配用户数: 0
  2 用户管理
  O 权限管理
  GE
caption_zh_TW: "IM 使用者映射設定入口及支援的 IM 平台列表"
rebuild_spec: null
-->

1. 進入『管理后台』>『用户管理』>『IM用户映射』，點選目標平台（如企業微信）的『编辑』以完成應用程式對接。

<!-- VISUAL_PENDING
visual_id: im-mapping-app-docking
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示企业微信应用对接配置和映射方式选择界面
placement_hint: 段落「2.2 应用对接」
source_original_url: ""
source_local_path: "data/dora/assets/17799662782hsX.png"
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
  用户映射                   十 添加映射                                                                                    个
  上传用户映射表     人 清空
  企业微信用户名                                                                             Data
  Agent 用户名
  SI                                                   a      o      2                       v                           i
  x                                                   a      o      ti                       v                           i
  k                                                   分      eo      1                        Vv                           1
  s)                                                   分      所>      pl                       Vv                          w
  w                                                   Q      o      alt                      v                          全
caption_zh_TW: "企業微信應用對接設定和映射方式選擇介面"
rebuild_spec: null
-->

2. 若雙方平台的使用者名稱或 ID 一致，可選擇『用户名/ID匹配』讓系統自動連結並即時生效。

<!-- VISUAL_PENDING
visual_id: im-mapping-auto-match
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示选择「用户名/ID匹配」选项的配置状态
placement_hint: 段落「方式一：用户名/ID 匹配」
source_original_url: ""
source_local_path: "data/dora/assets/1778573300Ylxa.png"
ocr_text: |
  < Data Agent
  ® Agent
  Z 技能
  S 数据
  加 模型
  四 Agent上监管
  > 开放集成
  失 用户管理
  用户管理
  IMFAP BRST
  <= 企业微信机器人
  映射方式
  © 用户名/ID匹配
  自定义匹配
caption_zh_TW: "選擇「使用者名/ID對應」选项的設定狀態"
rebuild_spec: null
-->

3. 若名稱不一致，請選擇『自定义匹配』，下載匯入範本並上傳對應表（僅支援 .xls、.xlsx）。系統會自動解析並呈現對應結果，您也可再次手動修改對應的使用者。

<!-- VISUAL_PENDING
visual_id: im-mapping-upload-dialog
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示批量上传用户映射表及下载模板的对话框
placement_hint: 段落「方式二：自定义匹配」- 步骤1
source_original_url: ""
source_local_path: "data/dora/assets/1778573874Rox6.png"
ocr_text: |
  上传用户映射表                                         x
  上传文件                                                                                  山
  下载导入模板
  十
  点击或拖搜上传文件
  支持 .xls、.xlsx 格式
caption_zh_TW: "批次上傳使用者映射表及下載範本的對話方塊"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: im-mapping-upload-success
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示映射表上传成功后解析出的用户名对应列表
placement_hint: 段落「方式二：自定义匹配」- 步骤2
source_original_url: ""
source_local_path: "data/dora/assets/1778574779BRZ0.png"
ocr_text: |
  < Data Agent
  ® Agent
  Z 技能
  S 数据
  加 模型
  四 Agent上监管
  > 开放集成
  a 用户管理
  用户管理
  IMFAP BRST
  <= 企业微信机器人
  映射方式
  用户映射
  用户名/ID匹配 © 自定义匹配
  上传用户映射表
  企业微信用户名
  ZhangZhuoYang
  获取用户
  Data Agent 用户名
  10条/页       Vv
  aR
caption_zh_TW: "映射表上傳成功后解析出的使用者名对应列表"
rebuild_spec: null
-->

<!-- VISUAL_PENDING
visual_id: im-mapping-manual-edit
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示在自定义匹配下手动修改对应的 Data Agent 用户名
placement_hint: 段落「方式二：自定义匹配」- 步骤3
source_original_url: ""
source_local_path: "data/dora/assets/1778574834BQFI.png"
ocr_text: |
  用户管理
  IMFAP BRST
  <= 企业微信机器人
  映射方式
  用户映射
  用户名/ID匹配 © 自定义匹配
  上传用户映射表
  企业微信用户名
  ZhangZhuoYang
  10条/页       Vv
  aR
  获取用户
  Data Agent 用户名
  Coral
  demo
  INT
  john
  no
  shuju
  sit
caption_zh_TW: "在自訂對應下手动修改对应的 Data Agent 使用者名"
rebuild_spec: null
-->

## 平台使用量概覽

透過『管理后台』>『Agent监管』>『使用概览』，超級管理員能即時掌握平台的整體營運狀態：

<!-- VISUAL_PENDING
visual_id: usage-overview-demo
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示使用概览页面的整体效果
placement_hint: 1.3 效果演示
source_original_url: ""
source_local_path: "data/dora/assets/1779950407qITY.png"
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
caption_zh_TW: "使用概覽页面的整體效果"
rebuild_spec: null
-->

- **核心指標**：查看平台內已建立的 Agent 總數、總使用次數以及獨立使用人數。

<!-- VISUAL_PENDING
visual_id: usage-overview-metrics
role: screenshot
locale_sensitivity: high
brand_sensitivity: none
purpose: 展示全局概览的核心指标卡片
placement_hint: 2.1 核心指标
source_original_url: ""
source_local_path: "data/dora/assets/17799504677VoE.png"
ocr_text: |
  < Data Agent
  Agent监管
  @/enes) seca exes ness
  ® Agent
  CG 技能                                 全局概览                                                                                                                                                近30天    Vv
  S 数据                           3)     217                                  =         3,476 ix                             @          2A                                    e
  =                                  :                                                                                                             =
  Agent 数量                                                                   Agent 使用次数                                                             Agent 使用人数
  © 模型      @
  四 Agent监                              使用次数排行                                                                                                                                           近30天 OV
  > 开放集成                                     Agent名称                                                                                                                                                        使用次数
  2 用户管理                              Gi ”Dora-通用智能体                                                                                                                                          1,252
  OS ”财务单据费用查询助手                                                                                                                                       501
  © 权限管理
  & 全国市场潜量洞察报告员                                                                                                                                     298
  4 美妆品牌市场分析师                                                                                                                                         272
  5 ”行政考勤数据助手                                                                                                                                           215
caption_zh_TW: "全域概覽的核心指標卡片"
rebuild_spec: null
-->

- **時間維度篩選**：支援切換至當天、近 7 天、近 30 天（預設）、所有週期或自訂時間範圍。

<!-- VISUAL_PENDING
visual_id: usage-overview-time-filter
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示时间维度筛选下拉框
placement_hint: 2.2 时间维度筛选
source_original_url: ""
source_local_path: "data/dora/assets/1779950516NGt6.png"
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
  OS ”财务单据费用查询助手
  & ”全国市场潜量洞察报告员
  4 ，”美妆品牌市场分析师
  5 ”行政考勤数据助手
  ad
  3,476 次
  Agent 使用次数
  @
  2A
  Agent 使用人数
  近30天 A
  SS]
  当天
  近7天
  |  近30天
  所有周期
  自定义
  ES |
  近30天         v
  使用次数
  1,252
  501
  298
  272
  215
caption_zh_TW: "時間維度筛选下拉選單"
rebuild_spec: null
-->

- **排行分析**：依據使用次數或 Token 消耗量列出前五名 Agent，協助管理員識別高價值業務場景，或評估低頻 Agent 是否需要最佳化。

<!-- VISUAL_PENDING
visual_id: usage-overview-ranking
role: screenshot
locale_sensitivity: high
brand_sensitivity: high
purpose: 展示使用次数排行列表
placement_hint: 3.使用次数排行
source_original_url: ""
source_local_path: "data/dora/assets/1779950665FdRS.png"
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
caption_zh_TW: "使用次數排行列表"
rebuild_spec: null
-->

<!-- 本頁已依品牌規則處理 2 條過濾項 -->
