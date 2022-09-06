---
title: 最新版本
description: 本頁詳細說明最新 Campaign Standard 版本的內容
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 93f1a6cb0727859f3c3f645366a9d2dc25795a79
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 最新版本{#latest-release}

![控制面板](assets/do-not-localize/cp-icon.png) **新控制面板版本**。 [深入瞭解](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hant){target=&quot;_blank&quot;}.


## 版本22.3 - 2022年秋冬 {#sept-22}

### 改善{#rn-improvements}

**協助功能**

Campaign Standard22.3隨附協助工具修正和改良功能，可方便使用者導覽及充分運用Adobe Campaign。

這些功能在有限可用性中發行，僅向一組客戶推出。 若要在您的促銷活動環境中啟用這些改善，請連絡您的Adobe代表。

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### 安全性更新{#rn-security}

此版本隨附下列安全性升級：Apache Tomcat已從v7.0升級至v8.0。

### 修正{#e-rn-fixes}

* 修正排程報表在排程計時前一小時觸發的問題。 (CAMP-51502)
* 修正「傳送」控制面板中「傳送」指標與「傳送記錄檔」(nms:broadLogRcp)不符的問題。 (CAMP-51127)
* 修正無法透過ACS Connector(Prime Offering)擴充自訂資源的問題。 (CAMP-51033)
* 改善隱私權要求回應的發佈程式，以避免延遲。 (CAMP-50613)

