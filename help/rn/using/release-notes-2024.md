---
title: 發行說明2024年
description: 本頁列出 2024 年的所有 Adobe Campaign Standard 版本。
feature: Overview
role: User
level: Beginner
exl-id: 26616ecc-a009-485c-b13d-d4e0c23969f2
TQID: https://experienceleague.adobe.com/L1RnV5WNdVWVn8oRUtFp4BDW-GzuP6xWZXpFYgupbQs
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
  - id: cbcf4d90-26be-46e2-b16a-aebc529dc41e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 516
ht-degree: 93%

---

# 發行說明2024年 {#release-notes-2024}


## 版本 24.2 - 2024 夏季版 {#summer-24}

### 改進 {#summer-24-rn-improvements}

**移轉至 OAuth 伺服器對伺服器認證**

自此版本開始，Adobe 已棄用服務帳戶 (JWT) 認證，Campaign 與 Adobe 解決方案和應用程式的輸出整合現在需依賴 OAuth 伺服器對伺服器認證。 Adobe 會針對您的傳出整合執行 JWT 到 OAuth 的移轉，例如 Campaign-Analytics 整合或 Experience Cloud 觸發器整合。

如果您已實作與Campaign的傳入整合，而且正在使用[Campaign API](../../api/using/get-started-apis.md)，您必須移轉您的技術帳戶，如[本檔案](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}所詳述。 現有的服務帳戶 (JWT) 認證將於 **2025 年 1 月 27 日**&#x200B;停止運作。

### 修正 {#summer-24-rn-fixes}

* 已修正造成工作流程排程器早於排程時間啟動的問題。 (CAMP-55412)
* 已修正在交易型推播通知中複製自訂欄位時發生錯誤的問題。 (CAMP-54459)
* 已修正影響應用程式內傳訊時間與日期排程器可用性的問題。 (CAMP-54495)
* 已修正使用自訂追蹤別名功能時，整個連結為動態，導致追蹤無法運作的問題。 (CAMP-56044)
* 已修正使用搜尋尋找特定範本時，導致顯示有限範本數的問題。 (CAMP-55273)
* 已新增下列語言至首選語言下拉式清單：en_kz (英文 — 哈薩克語) 與 en_ua (英文 — 烏克蘭語)。 (CAMP-55336)
* 已修正造成時間調整按鈕在排程器設定無法運作的問題。 (CAMP-53602)
* 已修正排程器設定中時間調整列的幾個使用者介面問題。 (CAMP-55291)


## 版本 24.1 - 2024 年冬季發布內容 {#winter-24}

### 功能改進 {#e-rn-improvements}

* **Android 推播通知** - Adobe Campaign Standard 24.1 使用 HTTP v1 API 傳送 Android 推播通知訊息，以確保與即將推出的 FCM 變更相容。 若要了解詳細資訊，請參閱[此技術說明](../../administration/using/push-technote.md)。

* **iOS 推播通知** - Adobe Campaign Standard 24.1 現在支援 iOS 推播通知的 p8 驗證憑證。 您的實作必須經過調整，才能啟用這些變更。 若要了解詳細資訊，請參閱[此技術說明](../../administration/using/push-technote.md)。

* **一鍵式清單取消訂閱** - Google 和 Yahoo! 於 2024 年 6 月 1 日起使用 要求寄件者遵守一鍵式清單取消訂閱規範。 Campaign 現在可立即支援此功能。 若要了解詳細資訊，請參閱[本章節](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters)。

* **基礎結構** - Postgres 資料庫已從 11.22 版升級至 12.17 版。

* **CTA 追蹤** - 當使用者開啟並按一下個人化 URL 時，系統現在會追蹤已解析的個人化 URL，而非編碼的個人化 URL。 預設情況下，不會啟用此選項。 若要在您的 Campaign 執行個體啟用此功能，請聯絡您的 Adobe 代表。

* **個人化欄位下拉式清單** - 在 Adobe Experience Manager 建立交易式電子郵件訊息範本時，您現在可以從下拉式清單選取個人化欄位。 預設情況下，不會啟用此選項。 若要在您的 Campaign 執行個體啟用此功能，請聯絡您的 Adobe 代表。

### 修正 {#e-rn-fixes}

* 修正無法在 30 天後從隔離區移除已退回電子郵件地址的問題。 (CAMP-52977)
* 修正傳送警報工作流程因下列錯誤而停止的問題：`division by zero`。 (CAMP-49786)
