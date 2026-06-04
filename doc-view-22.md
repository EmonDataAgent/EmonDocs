<!-- RENDERED
brand: native
brand_display_name: FineReport
locale: zh-TW
rendered_at: 2026-06-04T07:24:15Z
source_master: data/dora/locale/zh-TW/pages/doc-view-22.md
-->
---
page_id: doc-view-22
title: 部署 Data Agent 操作指南
locale: zh-TW
sourced_from_kus:
  - dora.deployment.data_agent.overview
  - dora.deployment.data_agent.new_install
  - dora.deployment.data_agent.upgrade_install
  - dora.deployment.data_agent.upgrade
  - dora.deployment.data_agent.upgrade_elasticsearch
  - dora.deployment.data_agent.connection_test
generated_at: "2026-06-03"
---

# 部署 Data Agent 操作指南

本文講解如何在 FineBI 專案中部署與啟用 Data Agent。

## 1. 概述與使用前提

FineBI 與 Data Agent 需要按順序部署，因此使用者需要先使用維運平台部署好 FineBI。

- **部署維運平台**
  FineBI 和 Data Agent 均依賴維運平台部署，因此使用者需要提前部署好維運平台。
  - **如尚未部署維運平台：**
    請參考文檔部署最新版維運平台。內網環境請務必使用全量版離線安裝包部署，否則無法獲取 FineBI 相關元件映像檔。
  - **如已部署維運平台：**
    請確保維運平台在 V2.26.0 及以上，建議升級到最新版本。

- **部署 FineBI**
  使用者需要先使用維運平台部署好 FineBI，再對 FineBI 新增 Data Agent。
  - **如尚未部署 FineBI：**
    1. 準備 FineBI 部署環境（確認伺服器配置、網路以及掛載目錄）。
    2. 部署最新版 FineBI 專案。
  - **如已部署 FineBI：**
    請確保 FineBI 部署方式為「維運平台部署」，不支援非維運平台部署。
    版本須在 7.0.7 及以上，建議直接升級到最新版本。因為後續提供的映像檔均為最新 Data Agent 映像檔，不同版本適配不同版本的 AI 映像檔。如為歷史版本，請聯絡客服獲取對應版本。

<!-- AUTHOR_NOTE: "FineAI", "FineChatBI", "Data Agent" 未列入 tokenization-rules，保留原樣 -->

## 2. 全新部署 Data Agent

針對未部署使用過 FineChatBI 的 FineBI 工程。部署前請確認您的維運平台和 FineBI 專案符合上述使用前提。

### 2.1 準備 Data Agent 元件伺服器

由於 Data Agent 所需資源較多，建議為其單獨準備一台伺服器。

- **推薦配置：** CPU 16 核、可用記憶體 64G、可用磁碟 100G，AI 元件獨占伺服器。
- **最低配置：** CPU 8 核、可用記憶體 16G、可用磁碟 80G，AI 元件與 FineBI 共用伺服器。請在部署完 BI 後確認伺服器有相關閒置資源再著手部署。

**基礎要求：**
- **時間與時區一致：** Data Agent 伺服器與專案其他伺服器時間相差不能超過 5 秒，且時區必須完全一致，否則可能導致定時任務錯誤、資料不一致。
- **內網互通：** 伺服器間需內網互通或開放連接埠，內網延遲 < 1ms。
- **環境限制：** 不建議使用虛擬機。不支援 Kubernetes（K8S）環境，請為 Data Agent 準備非 K8S 環境。

**作業系統要求：**
- **類型與架構：** Linux，支援 X86_64 或 ARM。
- **核心：** 3.10 及以上。
- **軟體推薦：** 推薦 Ubuntu 22。支援 Ubuntu 18.04.4 及以上（不支援 20.04）、CentOS 7.3~7.9、RedHat 7.6 及以上、Rocky Linux 8.8~9.4。使用 Ubuntu 時，請注意預設 root 使用者可能並非超級管理員。

**硬體配置細節：**
- **CPU：** 推薦 Intel Xeon Gold 6338 等高效能處理器，主頻 2.5GHz 及以上。
- **磁碟效能：** 最低要求為固態硬碟（SSD）。
- **掛載目錄：** 必須設定重新啟動自動掛載，且不能是共享路徑。禁止直接使用 `/`、`/usr`、`/root`、`/usr/local`。
- **命令列與權限：** 需安裝 `tar` 和 `sed` 命令。使用者需透過 ssh 連線（密碼無英文單引號），且必須具備 sudo 權限（優先推薦使用 root 超管）。

**連接埠與網路連通：**
確保預設的容器對應連接埠未被佔用（FineAI：7666；FineChatBI 語義解析小模型：8666；FineAI Redis：6679）。
- **FineAI (fine-ai)：** BI 專案的內網閘道與每個 bi-web 需能存取。
- **語義解析小模型 (fine-chat-bi-parser)：** BI 專案的每個 bi-web 需能存取。
- **FineAI Redis (fine-ai-redis)：** 語義解析小模型與 FineAI 需能存取。

### 2.2 準備 Data Agent 映像檔與外掛

Data Agent 映像檔無法直接從雲端倉庫提取，需手動推送。

1. 下載 FineAI 元件映像檔和 FineChatBI 語義解析小模型元件映像檔（如為 ARM 架構，請聯絡客服獲取）。
2. 在維運平台「維運平台管理 > 維運元件」匯出部署資訊。前往伺服器匯出檔案 `logs` 的同級目錄 `resources` 內，將映像檔上傳至此資料夾。
3. 在維運平台「維護中心 > 映像檔管理」點選「載入映像檔」。
4. 載入後，在部署列表手動修改元件映像檔版本號，確保與映像檔管理中一致。
5. 確保倉庫中存在 v20.3.0-6.2.17 及以上版本的 redis 映像檔。

### 2.3 部署 Data Agent 元件

1. 登入維運平台，進入對應的 FineBI 專案，點選「維護 > 元件管理」。
2. 點選「新增元件」，選擇「業務服務 > AI」。
3. （選做）若使用新伺服器，點選「新增節點」，填寫內網 IP、連接埠（預設 22）、具備 sudo 權限的使用者名，以及掛載路徑（預設 `~/data`）。
4. 選擇要部署的節點（低於最低配置的節點將灰化不可選）。
5. 調整連接埠並**務必修改 FineAI Redis 的密碼**。
6. 點選「開始部署」。

### 2.4 配置與授權

1. 下載 Data Agent 外掛。
2. 進入 FineBI 系統管理，透過本地安裝 Data Agent 外掛。
3. 聯絡客服或銷售獲取 Data Agent 授權並進行認證安裝。
4. 部署完成後，FineBI 右上角會出現「Data Agent」按鈕，即代表配置成功。

## 3. 升級部署 Data Agent

針對**曾經部署過** FineChatBI 的 FineBI 工程。優先建議使用未部署過的新專案，否則請自行檢查舊資料的相容性。

1. 登入 FineBI 系統管理，卸載原有的 FineChatBI 外掛。
2. 參考 [2.2 節準備 Data Agent 映像檔與外掛](#22-準備-data-agent-映像檔與外掛)，將最新版映像檔推送至倉庫並修改版本號。
3. 在維運平台「元件管理」將原 FineChatBI 元件升級至 Data Agent 元件版本。
4. 進入 FineBI 系統管理，本地安裝最新的 Data Agent 外掛。
5. 獲取並安裝 Data Agent 授權，確認右上角出現「Data Agent」按鈕。

## 4. 後續維護與升級

### 4.1 升級 Data Agent
1. 請先將 FineBI 專案升級到最新版。
2. 將最新的 AI 映像檔包推送到維運平台倉庫。
3. 在維運平台「維護 > 元件管理」中找到待更新的 AI 元件，點選「更新」。
4. 升級完成後，在 FineBI 中將 Data Agent 外掛也升級到最新。

### 4.2 升級 ElasticSearch 元件
1. 確保升級 ElasticSearch 元件至 v20.4.5-8.17.3 及以上版本，並處於 running 狀態。
2. 透過開發者模式，自訂 ElasticSearch 元件的環境變數，將 `INSTALL_FINE_PLUGIN` 的值修改為 `yes`。

## 5. 連線測試

在正式使用 Data Agent 平台前，管理員需進行測試。

1. **平台連線測試：** 
   前往「Data Agent 管理後台 > 開放整合 > 其他」，新增目前部署 Data Agent 的 FineBI 位址並點選「連線測試」。
2. **模型連線測試：** 
   前往「Data Agent 管理後台 > 模型」，對已新增的目標模型進行連線測試，確保大模型為可用狀態。

<!-- 本頁已依品牌規則處理 5 條過濾項 -->
