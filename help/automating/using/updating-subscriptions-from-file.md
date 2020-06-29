---
title: 從檔案更新多個訂閱狀態
description: 此使用案例說明如何匯入包含描述檔的檔案，並將其訂閱更新為檔案中指定的數項服務。
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
source-wordcount: '417'
ht-degree: 0%

---


# 從檔案更新多個訂閱狀態 {#updating-multiple-subscription-statuses-from-a-file}

此示例說明如何導入包含配置檔案的檔案，以及如何將其預訂更新為檔案中指定的多個服務。 匯入檔案後，必須進行協調，以便將匯入的資料識別為具有服務連結的描述檔。 為確保檔案不包含任何重複項，將對資料執行重複資料消除活動。

工作流程如下：

![](assets/subscription_activity_example1.png)

* 「載 [入檔案](../../automating/using/load-file.md) 」(Load file)活動載入配置檔案並定義導入列的結構。

   在此範例中，載入的檔案是。csv格式，並包含下列資料：

   ```
   lastname;firstname;email;birthdate;service;operation
   jackman;megan;megan.jackman@testmail.com;07/08/1975;SVC2;sub
   phillips;edward;phillips@testmail.com;09/03/1986;SVC3;unsub
   weaver;justin;justin_w@testmail.com;11/15/1990;SVC3;sub
   martin;babeth;babeth_martin@testmail.net;11/25/1964;SVC3;unsub
   reese;richard;rreese@testmail.com;02/08/1987;SVC3;sub
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;SVC3;sub
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;SVC4;sub
   grimes;daryl;daryl_890@testmail.com;12/06/1979;SVC3;unsub
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;SVC2;sub
   ```

   ![](assets/subscription_example_load_file.png)

   如您所注意的，此操作在檔案中指定為「sub」或「不明嫌犯」。 系統需要一個 **布爾** 或 **** 整數值來識別要執行的操作： 「0」取消訂閱，「1」取消訂閱。 為符合此要求，在「操作」列的詳細資訊中執行值的重新映射。

   ![](assets/subscription_example_remapping.png)

   如果您的檔案已使用&quot;0&quot;和&quot;1&quot;來識別作業，則不需要重新對應這些值。 請只確定該列在頁籤中被處 **理為布爾****或整數****[!UICONTROL Column definition]** 。

* 「協 [調](../../automating/using/reconciliation.md) 」活動會將檔案中的資料識別為屬於Adobe Campaign資料庫的描述檔維度。 透過標 **[!UICONTROL Identification]** 簽，檔案的 **電子郵件欄位與描述檔資** 源的電子郵件欄位相符 **** 。

   ![](assets/subscription_activity_example3.png)

   在標 **[!UICONTROL Relations]** 簽中，使用服務資源建立連結，以便 **識別檔案** 的服務欄位。 在此示例中，值與服務資 **源的名稱** 欄位匹配。

   ![](assets/subscription_example_service_relation.png)

* 根據臨 [時資源(](../../automating/using/deduplication.md) 由協調產生 **)的電子郵件欄位** ，重複資料消除可識別重複資料。 務必消除重複項，因為服務的訂閱將在出現重複項時失敗。

   ![](assets/subscription_activity_example5.png)

* 「訂 [閱服務](../../automating/using/subscription-services.md) 」活動會透過活動中建立的連結，將要更新的服務識別為來自轉場的 **[!UICONTROL Reconciliation]** 服務。

   該 **[!UICONTROL Operation type]** 檔案被標識為來自 **檔案** 的操作欄位。 此處只能選擇布爾或整數欄位。 如果包含要執行的操作的檔案列未出現在清單中，請確保您已正確設定活動中的列格式，如本例前面所述 **[!UICONTROL Load file]** 。

   ![](assets/subscription_activity_example_from_file.png)
