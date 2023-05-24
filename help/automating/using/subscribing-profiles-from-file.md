---
title: 從檔案訂閱設定檔至特定服務
description: 此用例說明如何導入包含配置檔案的檔案並將其預訂到現有服務。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 06ae4a5c-f112-4aac-b776-437ac35a8f02
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 53%

---

# 在導入檔案後將配置檔案訂閱到特定服務 {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

此範例說明如何匯入包含設定檔的檔案並將其訂閱至現有服務中。匯入檔案後，必須進行調解，以便將匯入的資料識別為設定檔。為確保檔案不包含任何重複項目，將對資料執行重複資料刪除活動。

工作流程如下：

![](assets/subscription_activity_example1.png)

* A [載入檔案](../../automating/using/load-file.md) 活動載入配置檔案並定義導入列的結構。

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

* A [協調](../../automating/using/reconciliation.md) activity將檔案中的資料標識為屬於Adobe Campaign資料庫的配置檔案維。 僅設定 **[!UICONTROL Identification]** 索引標籤。它會根據描述檔的電子郵件地址識別檔案資料。

   ![](assets/subscription_activity_example3.png)

* A [重複資料消除](../../automating/using/deduplication.md) 基於 **電子郵件** 臨時資源的欄位（由對帳產生）標識任何重複項。 如果從檔案匯入的資料包含任何重複項目，所有資料服務的訂閱將會失敗。

   ![](assets/subscription_activity_example5.png)

* A [訂閱服務](../../automating/using/subscription-services.md) 活動允許您選擇配置檔案必須訂閱到的服務、與訂閱日期對應的欄位以及訂閱的來源。

   ![](assets/subscription_activity_example4.png)
