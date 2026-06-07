---
page_id: doc-view-52
title: "Dora 企業微信機器人應用對接"
locale: zh-TW
sourced_from_kus:
  - dora.user-management.wecom-robot-integration
generated_at: "2026-06-03T22:48:20+08:00"
---
<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-07T08:31:49Z
source_master: data/dora/locale/zh-TW/pages/doc-view-52.md
-->

# Dora 企業微信機器人應用對接

本文檔提供 Dora 平台對接企業微信機器人的前置操作流程。請務必按順序完成操作，否則系統將無法正確對接企業微信使用者名稱或 ID。

## 前提條件

在進行對接前，您需要滿足以下條件：
1. 必須擁有企業微信管理後台的權限。
2. 已為 Dora 服務配置網域。
3. 已取得 Dora 服務的出口 IP（用於配置企業微信的可信 IP）。

## 操作步驟

### 1. 建立企業微信自建應用

1. **登入管理後台**：由企業微信管理員登入企業微信管理後台，進入『應用管理 > 應用 > 自建』，建立應用。
2. **設定應用資訊**：設定應用標誌（Logo）、應用名稱與可見範圍。建議可見範圍選擇全員，或必須包含企業中使用機器人的使用者與部門。

### 2. 設定 API 接收與參數配置

1. **進入 API 接收配置頁**：完成自建應用建立後，系統會自動跳轉至應用配置詳情頁。請在『功能 > 接收訊息』中點選『設定 API 接收』，進入接收訊息伺服器配置頁。
2. **取得 URL**：請參考以下規則取得 URL（範例：`https://www.example.com/decision/external/api/im/config/wecom/callback`）：
   ```shell
   https://{Dora 服務網域}/{BI 服務後綴}/external/api/im/config/wecom/callback
   ```
3. **產生憑證參數**：點選『隨機獲取』，系統會自動產生 Token 與 EncodingAESKey。
   > [!WARNING]
   > 產生 Token 與 EncodingAESKey 後，請先不要點選保存，必須先前往 Dora 管理後台填寫這兩項資訊。

### 3. Dora 後台對接與保存 API 接收

1. **Dora 後台配置應用對接**：以超級管理員身分進入『Dora 管理後台 > 使用者管理 > IM 使用者映射』，點選應用對接的配置按鈕，將上一步取得的 Token 與 EncodingAESKey 填入對話方塊中，並點選『下一步』。
2. **保存 API 接收**：回到企業微信後台，儲存先前的 API 接收配置。

### 4. 配置可信 IP 與認證憑證

1. **配置企業可信 IP**：回到自建應用配置詳情頁，前往『開發者介面 > 企業可信 IP』中點選『配置』。在對話方塊中新增 Dora 服務的出口 IP 位址，點選『確認』以完成白名單配置。
2. **取得企業微信 CorpSecret**：前往『自建應用 > 配置詳情頁 > Secret』，點選『查看』並記錄 CorpSecret。
3. **取得企業微信 CorpId**：前往『我的企業 > 企業資訊』，向下拉動頁面並記錄企業 ID（CorpId）。
4. **完成憑證新增**：回到『Dora 管理後台 > 使用者管理 > IM 使用者映射』，繼續先前的配置對話方塊流程，填入剛才取得的 CorpSecret 與 CorpId。點選『測試連接並保存』，若頁面提示『已配置』，即代表配置成功。


