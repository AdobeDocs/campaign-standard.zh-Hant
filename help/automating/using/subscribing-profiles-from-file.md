---
solution: Campaign Standard
product: campaign
title: 從檔案訂閱設定檔至特定服務
description: 此使用案例說明如何匯入包含描述檔的檔案，並將其訂閱至現有服務。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 53%

---


# 在導入檔案{#subscribing-profiles-to-a-specific-service-after-importing-a-file}後將配置檔案預訂到特定服務

此範例說明如何匯入包含設定檔的檔案並將其訂閱至現有服務中。匯入檔案後，必須進行調解，以便將匯入的資料識別為設定檔。為確保檔案不包含任何重複項目，將對資料執行重複資料刪除活動。

工作流程如下：

![](assets/subscription_activity_example1.png)

* [載入檔案](../../automating/using/load-file.md)活動會載入描述檔，並定義匯入欄的結構。

   在此範例中，載入檔案為 .csv 格式，並包含以下資料：

   ```
   lastname;firstname;email;birthdate;subdate
   jackman;megan;megan.jackman@testmail.com;07/08/1975;10/08/2017
   phillips;edward;phillips@testmail.com;09/03/1986;10/08/2017
   weaver;justin;justin_w@testmail.com;11/15/1990;10/08/2017
   martin;babeth;babeth_martin@testmail.net;11/25/1964;10/08/2017
   reese;richard;rreese@testmail.com;02/08/1987;11/08/2017
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;11/08/2017
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;11/08/2017
   grimes;daryl;daryl_890@testmail.com;12/06/1979;12/08/2017
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;12/08/2017
   ```

   ![](assets/subscription_activity_example2.png)

* [協調](../../automating/using/reconciliation.md)活動將來自檔案的資料標識為屬於Adobe Campaign資料庫的配置檔案維。 僅設定 **[!UICONTROL Identification]** 索引標籤。它會根據描述檔的電子郵件地址識別檔案資料。

   ![](assets/subscription_activity_example3.png)

* 基於臨時資源（由協調產生）的&#x200B;**email**&#x200B;欄位的[重複資料消除](../../automating/using/deduplication.md)標識任何重複項。 如果從檔案匯入的資料包含任何重複項目，所有資料服務的訂閱將會失敗。

   ![](assets/subscription_activity_example5.png)

* [訂閱服務](../../automating/using/subscription-services.md)活動可讓您選擇必須訂閱描述檔的服務、與訂閱日期對應的欄位，以及訂閱的來源。

   ![](assets/subscription_activity_example4.png)
