---
title: 早期發行說明
description: 早期發行說明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 3f9adbf4e8c9066b1954a1443654d82ee7b53fea
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 20%

---


# 早期發行說明 {#e-new-release}

本頁面說明下一版Campaign Standard中包含的改善和修正。

>[!CAUTION]
>
> 在預備環境升級日期前，此內容可能會有所變更，恕不另行通知。 請參閱[發行計劃頁面](../../rn/using/release-planning.md)以瞭解更多資訊。

## 發行版本 22.3 – 2022 年 9 月 {#e-rn-2022}


### 改善{#e-rn-improvements}

**協助功能**

Campaign Standard22.3隨附協助工具修正和改良功能，可方便使用者導覽及充分運用Adobe Campaign。

這些功能在有限可用性中發行，僅向一組客戶推出。 若要在您的促銷活動環境中啟用這些改善，請連絡您的Adobe代表。

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### 安全性更新{#e-rn-security}

此版本隨附下列安全性升級：Apache Tomcat已從v7.0升級至v8.0。

### 修正{#e-rn-fixes}

* 修正排程報表在排程計時前一小時觸發的問題。 (CAMP-51502)
* 修正「傳送」控制面板中「傳送」指標與「傳送記錄檔」(nms:broadLogRcp)不符的問題。 (CAMP-51127)
* 修正無法透過ACS Connector(Prime Offering)擴充自訂資源的問題。 (CAMP-51033)
* 改善隱私權要求回應的發佈程式，以避免延遲。 (CAMP-50613)