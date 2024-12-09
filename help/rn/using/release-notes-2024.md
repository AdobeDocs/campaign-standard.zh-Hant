---
title: 發行說明 2024 年
description: 本頁列出 2024 年的所有 Adobe Campaign Standard 版本。
feature: Overview
role: User
level: Beginner
source-git-commit: c70e3058f75ba2b11a8311628198e5c02d489964
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 100%

---

# 發行說明 2024 年 {#release-notes-2024}

## 版本 24.1 - 2024 年冬季發布內容 {#winter-24}

### 功能改進 {#e-rn-improvements}

* **Android 推播通知** - Adobe Campaign Standard 24.1 使用 HTTP v1 API 傳送 Android 推播通知訊息，以確保與即將推出的 FCM 變更相容。 若要了解詳細資訊，請參閱[此技術說明](../../administration/using/push-technote.md)。

* **iOS 推播通知** - Adobe Campaign Standard 24.1 現在支援 iOS 推播通知的 p8 驗證憑證。您的實作必須經過調整，才能啟用這些變更。 若要了解詳細資訊，請參閱[此技術說明](../../administration/using/push-technote.md)。

* **一鍵式清單取消訂閱** - Google 和 Yahoo! 於 2024 年 6 月 1 日起使用要求寄件者遵守一鍵式清單取消訂閱規範。Campaign 現在可立即支援此功能。若要了解詳細資訊，請參閱[本章節](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters)。

* **基礎結構** - Postgres 資料庫已從 11.22 版升級至 12.17 版。

* **CTA 追蹤** - 當使用者開啟並按一下個人化 URL 時，系統現在會追蹤已解析的個人化 URL，而非編碼的個人化 URL。 預設情況下，不會啟用此選項。 若要在您的 Campaign 執行個體啟用此功能，請聯絡您的 Adobe 代表。

* **個人化欄位下拉式清單** - 在 Adobe Experience Manager 建立交易式電子郵件訊息範本時，您現在可以從下拉式清單選取個人化欄位。 預設情況下，不會啟用此選項。 若要在您的 Campaign 執行個體啟用此功能，請聯絡您的 Adobe 代表。

### 修正 {#e-rn-fixes}

* 修正無法在 30 天後從隔離區移除已退回電子郵件地址的問題。 (CAMP-52977)
* 修正傳送警報工作流程因下列錯誤而停止的問題：`division by zero`。(CAMP-49786)

