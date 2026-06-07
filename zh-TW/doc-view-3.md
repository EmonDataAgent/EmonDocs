---
page_id: doc-view-3
title: "Dora V0.6 更新日誌"
locale: zh-TW
sourced_from_kus:
  - dora.release_notes.v0_6
generated_at: "2026-06-03T22:05:00+08:00"
---
<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-07T08:31:49Z
source_master: data/dora/locale/zh-TW/pages/doc-view-3.md
-->

## 1. 版本說明

| 發布日期 | 適配 FineBI 版本 | 組件鏡像 |
| --- | --- | --- |
| 2026-05-28 | V7.0 及以上 | - FineAI 組件鏡像：升級至 v2026.0.6.0.0<br>- FineChatBl 語義解析小模型組件鏡像：升級至 0.6.0 |

## 2. 構建流程

### 2.1 Dora 通用智能體

在 Dora 工作台首頁設定「Dora 通用智能體」，該能力已整合平台全量技能。管理員可依需求設定關聯模型與 IM 對接服務；使用者進入工作台即可直接和 Dora 發起對話互動，降低使用門檻並提升互動便利性。

### 2.2 支援大模型配置

超級管理員或開發使用者可在「管理後台 > 模型」中為企業或個人新增可用的大模型，滿足不同業務場景下的智慧分析需求。

詳細資訊請參閱：[推薦大模型](https://help.fanruan.com/finereport/doc-view-26.html) 與 [模型資源配置](https://help.fanruan.com/finereport/doc-view-28.html)。

### 2.3 支援對接多種資料源

支援透過「管理後台 > 數據」模組新增以下三種資料源，使用者可靈活接入各類資料，為 Agent 提供更豐富的分析素材：
- Excel 檔案
- FineBI 分析主題
- FineBI 儀表板

詳細資訊請參閱：[數據](https://help.fanruan.com/finereport/doc-view-9.html)。

### 2.4 官方發布多種技能

平台目前共發布 20 種官方技能，涵蓋資料查詢分析、視覺化、報告產生與技能建立等場景。

詳細資訊請參閱：[技能介紹](https://help.fanruan.com/finereport/doc-view-19.html)。

### 2.5 支援使用者自訂技能

支援透過匯入 SkillHub 技能與上傳技能包兩種方式快速自訂技能。平台會自動解析技能包配置並產生可直接使用的技能，降低技能開發門檻。

詳細資訊請參閱：[自訂技能](https://help.fanruan.com/finereport/doc-view-8.html)。

### 2.6 支援建立封裝 Agent

開發使用者可自選模型與技能，構建企業、團隊或個人專屬 Agent。支援依需求客製化智慧助手，滿足差異化的業務場景。

詳細資訊請參閱：[封裝 Agent](https://help.fanruan.com/finereport/doc-view-17.html)。

### 2.7 Agent 支援多種發布方式

支援以下三種發布方式，靈活適配內外部不同使用場景：
- **工作台**：發布至 Dora 工作台，使用者可在工作台中搜尋並使用 Agent，適用於組織內發布。
- **獨立 URL**：將 Agent 產生獨立連結，使用者可透過專屬 URL 快速存取，適用於對外分享。
- **FineBI 平台**：將 Agent 發布至「FineBI 平台 > 目錄」下的一個或多個資源；使用者存取對應目錄資源時，可透過頁面側邊欄快速發起 Agent 會話。

詳細資訊請參閱：[發布 Agent](https://help.fanruan.com/finereport/doc-view-4.html#1716014be1852469)。

### 2.8 Agent 支援配置 MCP

若管理員在「管理後台 > 開放集成 > 外接MCP」中完成 MCP 新增，建立 Agent 時可直接選擇一個或多個外部 MCP，實現更多資料與技能工具的呼叫，擴展 Agent 能力邊界。

詳細資訊請參閱：[封裝 Agent - MCP](https://help.fanruan.com/finereport/doc-view-17.html#70df4d6a4ffac247)。

### 2.9 Agent 支援設定定時任務

Agent 支援設定定時任務，可透過後台配置頁或前台使用頁兩種入口設定。可實現報告定期推播、資料異常預警等自動化操作，提升 Agent 主動服務能力。

詳細資訊請參閱：[定時任務](https://help.fanruan.com/finereport/doc-view-29.html)。

### 2.10 Agent 支援對接企業微信

支援將 Agent 與企業微信機器人綁定，方便使用者在企業微信中呼叫 Agent 能力，提升協作效率。支援以下互動方式：
- 單聊場景：直接與機器人發起會話，會話歷史保留，支援多輪會話。
- 群聊場景：在群聊中 @機器人，並發送問題，支援多輪會話。

詳細資訊請參閱：[IM 工具對接](https://help.fanruan.com/finereport/doc-view-38.html)。

### 2.11 定時任務支援企業微信推播

Agent 定時任務可對接企業微信，自動將任務執行結果推播至指定群組或個人，賦能日報、週報、月報推播與資料預警等場景，實現任務結果即時同步，提升資訊傳遞效率。

## 3. 高級功能

### 3.1 支援監管 Agent 記錄

「管理後台 > Agent監管」支援以下四大監管模組，超級管理員可全面掌握 Agent 執行狀況，保障系統合規與安全：
- **使用概覽**：全局監控 Agent 執行狀態與使用狀況。
- **會話記錄**：追溯 Agent 互動日誌、對話過程、執行結果與資源消耗。
- **定時任務**：統一檢視 Agent 中定時任務的推播管道、任務來源、執行記錄與啟動狀態等資訊。
- **監管日誌**：為超級管理員提供全平台所有模組的操作行為稽核。

詳細資訊請參閱：[使用概覽](https://help.fanruan.com/finereport/doc-view-6.html)、[會話記錄](https://help.fanruan.com/finereport/doc-view-11.html)、[定時任務](https://help.fanruan.com/finereport/doc-view-46.html) 與 [監管日誌](https://help.fanruan.com/finereport/doc-view-40.html)。

### 3.2 支援整合 OpenClaw

支援對接 OpenClaw 並開放 API 對接介面，幫助企業實現更複雜的自動化分析需求，進一步拓展系統整合能力。

詳細資訊請參閱：[開放集成介紹](https://help.fanruan.com/finereport/doc-view-20.html)。

## 4. 平台管理

### 4.1 支援使用者管理與權限分配

超級管理員可檢視、編輯與新增 Dora 平台使用者，並根據使用者類型分配對應權限，實現細粒度的權限分級控制。

詳細資訊請參閱：[所有使用者](https://help.fanruan.com/finereport/doc-view-43.html)、[使用者類型](https://help.fanruan.com/finereport/doc-view-44.html) 與 [權限分配](https://help.fanruan.com/finereport/doc-view-45.html)。

### 4.2 支援映射企業微信使用者

為支援使用者在企業微信中透過機器人對話 Agent，超級管理員需將企業微信使用者 ID 與 Dora 平台使用者名稱進行關係映射匹配，確保身分互通。

詳細資訊請參閱：[IM 使用者映射](https://help.fanruan.com/finereport/doc-view-30.html)。


