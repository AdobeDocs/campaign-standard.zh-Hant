---
title: 最新發行說明
description: 本頁詳細說明最新 Campaign Standard 版本的內容
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c1f64589578c144a9b8eb879684f27834efaf8d8
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---


# 最新發行說明 {#latest-release}

<!--
## Release notes {#e-new-release}


This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).

-->

## 版本 25.2 - 2025 夏季版本 {#summer-25}

### 安全性修正 {#summer-25-security}

* 此版本提供安全性修正。
* 此版本附帶以下安全性升級：PostgreSQL 14.18，從 CentOS 移轉到 Rocky 用於 Azure 執行個體。

### 其他修正 {#summer-25-fixes}

* 改善處理序列耗竭的程式，以提升系統可靠性。 (CAMP-57281)
* 一般產品穩定更新。 (CAMP-57339)
* 改進的動態報告具有更好的穩健性並減少了資料不符項目。(CAMP-58157)
* 修正下拉式功能表未正確繞排文字的問題。 (CAMP-57360)
* 更新了報告功能以防止使用者查詢超過 2 年的資料。(CAMP-59262)

## 發行版本 25.1.2 {#25.1.2}

### 安全性修正 {#25.1.2-security}

* 此版本提供安全性修正。
* 此版本隨附下列安全性升級：Apache Tomcat 已升級至 v10.1.36。

### 其他修正 {#25.1.2-fixes}

* 修正權杖剖析問題，此問題可能阻止使用者透過 IMS 登入。(CAMP-57337)
* 改善自動序列 ID 產生機制，以提升系統可靠性。(CAMP-57281)

## 版本 25.1 - 2025 年冬季發布內容 {#winter-25}

### 安全性修正 {#winter-25-security}

* 此版本提供安全性修正。
* 此版本隨附下列安全性升級：Apache Tomcat 已升級至 v10.1.33。

### 其他修正 {#winter-25-fixes}


* 修正訂閱摘要畫面中的「資料結構描述」URL (CAMP-56168、CAMP-56296)
* 當使用&#x200B;**要立即傳送的訊息**&#x200B;選項時，修正略過疲勞規則的問題 (CAMP-56866、CAMP-57033)
* 修正範本重複的問題 (CAMP-56340)
* 修正在 Adobe Experience Manager 範本中使用動態 URL 時的追蹤回歸 (CAMP-51932)
* 修正計費流程的效能問題 (CAMP-56796)
* 修正 JSSP 網頁上 `>` 字元的 HTML 編碼問題 (CAMP-56497)
* 修正動態報告中使用 **在選取的列顯示** 選項的問題 (CAMP-55895)

