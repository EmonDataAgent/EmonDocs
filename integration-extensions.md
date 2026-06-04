<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/integration-extensions.md
-->
---
page_id: integration-extensions
title: 整合與第三方擴充
locale: zh-TW
sourced_from_kus:
  - dora.integration.openclaw
  - finereport.integration.external-mcp
  - dora.wecom.app_integration
  - finereport.skills.im-integration
generated_at: 2026-06-04T08:05:05+08:00
---

## 開放整合 (OpenClaw 與 MCP)

Dora 支援對接外部 AI 平台（如 OpenClaw）與外部 MCP（Model Context Protocol）服務，開放 API 對接能力。透過整合，可將分析產生的圖表或報表定時推播給負責人閱覽，並實現自動發佈 Agent 與查詢歷史對話等功能。此外，外接 MCP 可讓 Agent 呼叫外部工具與獲取外部資料，實現功能的彈性擴充與生態整合。

### OpenClaw 整合設定
1. 進入『后台地址』，新增對應的 FineBI 地址。
2. 點選『连接测试』，以確保 <!-- AUTHOR_NOTE: FineAI -->FineAI 外掛與 FineBI 平台互通且版本一致。
<VISUAL_PENDING
  id="integration-002"
  ku_id="dora.integration.openclaw"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="high"
  production_method="screenshot_re-capture"
>
  <description>展示在其他頁面新增 FineBI 後台地址並進行連線測試。</description>
  <caption_proposal>連線測試</caption_proposal>
</VISUAL_PENDING>

3. 在『Key 管理』頁面中，勾選一個或多個可存取 OpenClaw 的介面權限，以產生新的存取 Key。
<VISUAL_PENDING
  id="key-001"
  ku_id="dora.integration.openclaw"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="high"
  production_method="screenshot_re-capture"
>
  <description>展示在 Key 管理頁面建立包含介面權限的新 Key。</description>
  <caption_proposal>產生存取 Key</caption_proposal>
</VISUAL_PENDING>

<VISUAL_PENDING
  id="key-002"
  ku_id="dora.integration.openclaw"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="high"
  production_method="screenshot_re-capture"
>
  <description>展示產生的 OpenClaw 存取 Key 列表。</description>
  <caption_proposal>Key 管理列表</caption_proposal>
</VISUAL_PENDING>

4. 按照介面提示，依序完成『发送安装对话』、『发送集成对话』與『检查集成状态』等操作，即可完成 Dora 與 OpenClaw 的整合對接。
<VISUAL_PENDING
  id="openclaw-001"
  ku_id="dora.integration.openclaw"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="high"
  production_method="screenshot_re-capture"
>
  <description>展示整合 OpenClaw 的介面與操作步驟。</description>
  <caption_proposal>整合 OpenClaw</caption_proposal>
</VISUAL_PENDING>


### 外接 MCP 服務
外接 MCP 功能用於管理 Agent 可使用的外部 MCP 服務。所有已啟用的 MCP 服務都會自動下發給所有 Agent，停用後 Agent 將無法呼叫該服務，請在停用前評估影響範圍。

**通訊協定選擇：**
新增 MCP 服務時，支援 HTTP、SSE、STDIO 三種傳輸方式，需根據外部 MCP 服務的實際協定進行選擇，協定不符將導致連線失敗。
- **HTTP**：適用於標準 REST API 形式的 MCP 服務，透過 HTTP 請求與回應進行互動。
- **SSE**：適用於需要伺服器主動推播資料的場景，如即時資料流、狀態更新。
- **STDIO**：適用於本機處理程序形式的 MCP 服務，透過標準輸入輸出流進行通訊。

**設定步驟：**
1. 以管理員身分，進入『管理后台』>『开放集成』>『外接 MCP』。
2. 點選右上角的『添加 MCP』按鈕，開啟配置視窗。
<VISUAL_PENDING
  id="ext-mcp-001"
  ku_id="finereport.integration.external-mcp"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示在管理後台新增外部 MCP 服務時彈出的配置視窗介面。</description>
  <caption_proposal>設定入口</caption_proposal>
</VISUAL_PENDING>

3. 根據 MCP 服務的實際情況，填寫名稱、傳輸方式、描述、URL 以及請求頭，並選擇啟用狀態。建議名稱不要包含中文字元，相關中文說明可填寫於描述中。
4. 若 MCP 知識庫需基於 FineBI 使用者進行驗證，且 MCP 伺服器支援從請求標頭中獲取使用者名稱，可於『请求头 (JSON 对象)』中配置 `{"fine_username": "${fine_username}"}`。
5. 點選『确定』儲存配置，服務將加入至列表中。
<VISUAL_PENDING
  id="ext-mcp-002"
  ku_id="finereport.integration.external-mcp"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>以配置 12306 MCP 為例，展示在配置視窗中填寫各項參數的效果。</description>
  <caption_proposal>儲存配置並生效</caption_proposal>
</VISUAL_PENDING>


> **注意事項**：不建議新增同類 MCP 或與 Dora 自有技能重複的能力，以免造成誤觸發或呼叫不準確。若找不到對應 MCP，可依序檢查傳輸方式是否正確、MCP 是否過期以及 URL 地址是否正確。

## 企業通訊軟體串接 (企業微信等)

對接 IM 工具是 Agent 跨平台觸達的能力模組，支援將智能體與第三方即時通訊工具的機器人綁定，目前主要支援對接企業微信機器人。
在單聊場景下，使用者可與 Dora 機器人建立單聊對話，適合個人的日常資料查詢；在群聊場景下，使用者可透過 @ 機器人發起資料查詢或報表產生，適合團隊協作。

機器人支援多輪對話與上下文保留，會基於前文語境給出連貫回答，且回覆支援富文字訊息卡片，可包含關鍵數字與簡潔圖表。
<VISUAL_PENDING
  id="im-integ-001"
  ku_id="finereport.skills.im-integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>演示在企業微信群聊中 @Dora 機器人進行多輪問答對話的實際效果。</description>
  <caption_proposal>對話效果展示</caption_proposal>
</VISUAL_PENDING>

### 前置作業：企業微信應用對接
在對接前，請確保您擁有企業微信管理後台權限、已為 Dora 服務配置網域，且已取得其出口 IP（用於企業微信可信 IP 配置）。請務必依序完成下列步驟，否則無法對接企業微信使用者名稱或 ID。

1. **建立應用程式**：企業微信管理員登入企業微信管理後台，進入『应用管理』>『应用』>『自建』，建立應用程式。
<VISUAL_PENDING
  id="wecom-app-create"
  ku_id="dora.wecom.app_integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示在企業微信後台建立自建應用的入口。</description>
  <caption_proposal>建立應用程式</caption_proposal>
</VISUAL_PENDING>

2. 設定應用程式 Logo、名稱與可見範圍。可見範圍需包含企業中使用機器人的使用者與部門，建議選擇全體人員。
<VISUAL_PENDING
  id="wecom-app-info"
  ku_id="dora.wecom.app_integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="high"
  production_method="screenshot_re-capture"
>
  <description>展示自建應用基本資訊及可見範圍設定介面。</description>
  <caption_proposal>設定基本資訊</caption_proposal>
</VISUAL_PENDING>

3. **獲取通訊參數**：完成後進入應用配置詳情頁，在『功能』>『接收消息』中點選『设置API接收』，進入伺服器配置頁。
<VISUAL_PENDING
  id="wecom-api-receive-entrance"
  ku_id="dora.wecom.app_integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示 API 接收訊息配置入口。</description>
  <caption_proposal>API 接收配置</caption_proposal>
</VISUAL_PENDING>

   - 參考規則 `https://{dora服務網域}/{BI服務後綴}/external/api/im/config/wecom/callback` 獲取 URL。
   - 點選隨機獲取，系統會自動產生 Token 與 EncodingAESKey（產生後請先不要點選儲存）。
<VISUAL_PENDING
  id="wecom-api-server-config"
  ku_id="dora.wecom.app_integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示接收訊息伺服器 URL、Token 與 EncodingAESKey 的配置介面。</description>
  <caption_proposal>獲取通訊參數</caption_proposal>
</VISUAL_PENDING>

4. **平台綁定**：以超級管理員身分進入 Dora『管理后台』>『用户管理』>『IM 用户映射』。點選應用對接配置，填入 Token 與 EncodingAESKey 並進行下一步。在此處您也必須完成平台與 IM 工具之間的使用者映射。
<VISUAL_PENDING
  id="dora-admin-im-mapping"
  ku_id="dora.wecom.app_integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="high"
  production_method="screenshot_re-capture"
>
  <description>展示 Dora 後台填入 Token 與 EncodingAESKey 的彈窗介面。</description>
  <caption_proposal>填寫應用資訊</caption_proposal>
</VISUAL_PENDING>
<VISUAL_PENDING
  id="im-integ-002"
  ku_id="finereport.skills.im-integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="medium"
  production_method="screenshot_re-capture"
>
  <description>展示在 Data Agent 管理後台完成平台使用者與企業微信使用者映射的介面。</description>
  <caption_proposal>IM 用戶映射</caption_proposal>
</VISUAL_PENDING>


5. **保存配置與白名單**：回到企業微信後台，保存 API 接收配置。接著前往自建應用配置詳情頁的『开发者接口』>『企业可信IP』點選『配置』，新增 Dora 服務的出口 IP 地址以完成白名單配置。
<VISUAL_PENDING
  id="wecom-api-save"
  ku_id="dora.wecom.app_integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>提示在企業微信後台保存 API 接收配置。</description>
  <caption_proposal>保存 API 接收</caption_proposal>
</VISUAL_PENDING>
<VISUAL_PENDING
  id="wecom-trusted-ip"
  ku_id="dora.wecom.app_integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示企業可信 IP 的配置入口介面。</description>
  <caption_proposal>配置可信 IP</caption_proposal>
</VISUAL_PENDING>

6. **獲取企業資訊與連線測試**：前往自建應用的『Secret』點選查看，獲取 CorpSecret。接著在『我的企业』>『企业信息』中，向下拉取得企業 ID。
<VISUAL_PENDING
  id="wecom-corp-secret"
  ku_id="dora.wecom.app_integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示獲取 CorpSecret 的介面。</description>
  <caption_proposal>獲取 CorpSecret</caption_proposal>
</VISUAL_PENDING>
<VISUAL_PENDING
  id="wecom-corp-id"
  ku_id="dora.wecom.app_integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示獲取企業 ID 的介面。</description>
  <caption_proposal>獲取企業 ID</caption_proposal>
</VISUAL_PENDING>

在 Dora 管理後台繼續下一步，填入取得的 CorpSecret 與 CorpId，點選『测试连接并保存』，若顯示「已配置」即代表成功。
<VISUAL_PENDING
  id="dora-admin-im-save"
  ku_id="dora.wecom.app_integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="high"
  production_method="screenshot_re-capture"
>
  <description>展示 Dora 後台新增 CorpSecret 與 CorpId 的介面。</description>
  <caption_proposal>測試並儲存配置</caption_proposal>
</VISUAL_PENDING>

### 建立機器人與 Agent 配置
前置作業完成後，需建立機器人並將其參數綁定至 Agent。

1. 進入企業微信的『通讯录』>『智能机器人』，選擇『手动创建』一個用於連接 Dora 平台的智能機器人。
<VISUAL_PENDING
  id="im-integ-003"
  ku_id="finereport.skills.im-integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="medium"
  production_method="screenshot_re-capture"
>
  <description>展示在企業微信通訊錄中建立智能機器人的入口。</description>
  <caption_proposal>建立智能機器人</caption_proposal>
</VISUAL_PENDING>
<VISUAL_PENDING
  id="im-integ-004"
  ku_id="finereport.skills.im-integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示在企業微信中點選手動建立機器人的選項。</description>
  <caption_proposal>手動建立</caption_proposal>
</VISUAL_PENDING>

2. 配置機器人名稱與可用成員後，將建立頁面拉至最下方，切換至「API 模式创建」。
<VISUAL_PENDING
  id="im-integ-005"
  ku_id="finereport.skills.im-integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示將機器人建立頁面向下拉至最下方以切換到 API 模式建立的入口。</description>
  <caption_proposal>切換 API 模式</caption_proposal>
</VISUAL_PENDING>

3. 在 API 配置中選擇使用長連接方式，複製 Bot ID 並獲取 Secret。
<VISUAL_PENDING
  id="im-integ-006"
  ku_id="finereport.skills.im-integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示在企業微信中配置機器人基本資訊並獲取 Bot ID 與 Secret 的介面。</description>
  <caption_proposal>獲取機器人參數</caption_proposal>
</VISUAL_PENDING>

4. 在 Dora 平台的『Agent 配置页面』>『对接 IM 工具』中，選擇添加「企业微信机器人」，填入前述 Bot ID 與 Bot Secret。
<VISUAL_PENDING
  id="im-integ-007"
  ku_id="finereport.skills.im-integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>展示在 Dora 平台的 Agent 配置中新增企業微信機器人並輸入授權資訊的介面。</description>
  <caption_proposal>填寫機器人資訊</caption_proposal>
</VISUAL_PENDING>

   > **注意事項**：Bot ID 與 Bot Secret 必須與企業微信機器人配置資訊完全一致，否則將導致對接失敗。

5. 配置完成後，請在企業微信中向機器人發送測試訊息，驗證互動是否正常。
<VISUAL_PENDING
  id="im-integ-008"
  ku_id="finereport.skills.im-integration"
  role="screenshot"
  locale_sensitivity="high"
  brand_sensitivity="none"
  production_method="screenshot_re-capture"
>
  <description>演示在企業微信中對配置完成的機器人發送測試訊息以驗證功能是否正常。</description>
  <caption_proposal>驗證機器人互動</caption_proposal>
</VISUAL_PENDING>

<!-- 本頁已依品牌規則處理 7 條過濾項 -->
