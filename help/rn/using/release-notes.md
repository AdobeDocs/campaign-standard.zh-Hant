---
title: 最新發行說明
description: 本頁詳細說明最新 Campaign Standard 版本的內容
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c2d2f3843801d108f007fea52a76e41abe16d76c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 76%

---


# 最新發行說明 {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## 早期發行說明 {#e-new-release}

本章節介紹了下一個 Campaign Standard 版本中包含的改善及變動。

>[!CAUTION]
>
>在階段環境升級日期前，此內容可能會有所變更，恕不另行通知。 請參閱[發行計劃頁面](../../rn/using/release-planning.md)以瞭解更多資訊。

### 版本 25.1 - 2025 年冬季發布內容 {#winter-25}

#### 安全性修正 {#winter-25-security}

* 此版本提供安全性修正。
* 此版本隨附下列安全性升級：Apache Tomcat已升級至v10.1.33。

#### 其他修正 {#winter-25-fixes}

* 修正範本重複的問題(CAMP-56340)
* 修正在Adobe Experience Manager範本中使用動態URL時的追蹤回歸(CAMP-51932)
* 修正計費流程的效能問題(CAMP-56796)
* 修正JSSP網頁上`>`字元的HTML編碼問題(CAMP-56497)
* 修正動態報告中使用&#x200B;**在選取的列上顯示**&#x200B;選項的問題(CAMP-55895)


## 版本24.2 - 2024年夏季版本(LA) {#summer-24}

### 改進 {#summer-24-rn-improvements}

**移轉至 OAuth 伺服器對伺服器認證**

自此版本開始，Adobe 已棄用服務帳戶 (JWT) 認證，Campaign 與 Adobe 解決方案和應用程式的輸出整合現在需依賴 OAuth 伺服器對伺服器認證。 Adobe 會針對您的傳出整合執行 JWT 到 OAuth 的移轉，例如 Campaign-Analytics 整合或 Experience Cloud 觸發器整合。

如果您已傳入 Campaign 傳入整合，而且正在使用 [Campaign API](../../api/using/get-started-apis.md)，您必須移轉您的技術帳戶，如[本文件](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}所詳述。 現有的服務帳戶 (JWT) 認證將於 **2025 年 1 月 27 日**&#x200B;停止運作。

### 修正 {#summer-24-rn-fixes}

* 已修正造成工作流程排程器早於排程時間啟動的問題。 (CAMP-55412)
* 已修正在交易型推播通知中複製自訂欄位時發生錯誤的問題。(CAMP-54459)
* 已修正影響應用程式內傳訊時間與日期排程器可用性的問題。 (CAMP-54495)
* 已修正使用自訂追蹤別名功能時，整個連結為動態，導致追蹤無法運作的問題。 (CAMP-56044)
* 已修正使用搜尋尋找特定範本時，導致顯示有限範本數的問題。 (CAMP-55273)
* 已新增下列語言至首選語言下拉式清單：en_kz (英文 — 哈薩克語) 與 en_ua (英文 — 烏克蘭語)。 (CAMP-55336)
* 已修正造成時間調整按鈕在排程器設定無法運作的問題。 (CAMP-53602)
* 已修正排程器設定中時間調整列的幾個使用者介面問題。 (CAMP-55291)
