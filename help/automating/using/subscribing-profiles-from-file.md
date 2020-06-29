---
title: 將配置檔案從檔案預訂到特定服務
description: 此使用案例說明如何匯入包含描述檔的檔案，並將其訂閱至現有服務。
page-status-flag: never-activated
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---


# 在匯入檔案後將描述檔訂閱至特定服務 {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

此示例說明如何導入包含配置檔案的檔案並將其預訂到現有服務。 匯入檔案後，必須進行協調，以便將匯入的資料識別為描述檔。 為確保檔案不包含任何重複項，將對資料執行重複資料消除活動。

工作流程如下：

![](assets/subscription_activity_example1.png)

* 「載 [入檔案](../../automating/using/load-file.md) 」(Load file)活動載入配置檔案並定義導入列的結構。

   在此範例中，載入的檔案是。csv格式，並包含下列資料：

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

* 「協 [調](../../automating/using/reconciliation.md) 」活動會將檔案中的資料識別為屬於Adobe Campaign資料庫的描述檔維度。 僅配置 **[!UICONTROL Identification]** 了頁籤。 它會根據描述檔的電子郵件地址識別檔案資料。

   ![](assets/subscription_activity_example3.png)

* 根據臨 [時資源(](../../automating/using/deduplication.md) 由協調產生 **)的電子郵件欄位** ，重複資料消除可識別任何重複資料。 如果從檔案匯入的資料包含任何重複項目，服務的訂閱將會失敗。

   ![](assets/subscription_activity_example5.png)

* 「訂 [閱服務](../../automating/using/subscription-services.md) 」活動可讓您選擇描述檔必須訂閱的服務、與訂閱日期對應的欄位，以及訂閱的來源。

   ![](assets/subscription_activity_example4.png)
