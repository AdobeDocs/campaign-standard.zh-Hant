---
title: 最新版本
description: 本頁詳細說明最新 Campaign Standard 版本的內容
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 9291eb06c35b1d06c0a992fa64a460215477f57e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 38%

---


# 最新版本{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## 版本 24.1 - 2024 年冬季發布內容 {#winter-24}

### 功能改進 {#e-rn-improvements}

* **Android推播通知** - Adobe Campaign Standard 24.1使用HTTP v1 API傳送Android推播通知訊息，以確保與即將推出的FCM變更相容。 若要了解詳細資訊，請參閱[此技術說明](../../administration/using/push-technote.md)。

* **iOS推播通知** - Adobe Campaign Standard 24.1現在支援iOS推播通知的p8驗證憑證。 您的實作必須經過調整，才能啟用這些變更。 若要了解詳細資訊，請參閱[此技術說明](../../administration/using/push-technote.md)。

**一鍵式清單 — 取消訂閱**  — 自2024年6月1日起，Google和Yahoo！ 要求寄件者遵守一鍵式清單取消訂閱規範。Campaign 現在可立即支援此功能。若要了解詳細資訊，請參閱[本章節](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters)。

* **基礎架構** - Postgres資料庫已從11.22版升級至12.17版。

* **CTA追蹤**  — 當使用者開啟並按一下個人化URL時，系統現在會追蹤已解析的個人化URL，而非編碼的個人化URL。 預設不會啟用此變更。 若要在您的Campaign執行個體上啟用此功能，請聯絡您的Adobe代表。

* **個人化欄位下拉式清單**  — 在Adobe Experience Manager中建立交易式電子郵件訊息範本時，您現在可以從下拉式清單中選取個人化欄位。 預設不會啟用此變更。 若要在您的Campaign執行個體上啟用此功能，請聯絡您的Adobe代表。

### 修正 {#e-rn-fixes}

* 修正無法在 30 天後從隔離區移除已退回電子郵件地址的問題。 (CAMP-52977)
* 修正傳送警報工作流程因下列錯誤而停止的問題：`division by zero`。(CAMP-49786)

