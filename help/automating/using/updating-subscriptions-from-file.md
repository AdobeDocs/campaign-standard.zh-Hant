---
title: 從檔案更新多個訂閱狀態
description: 此使用案例顯示如何匯入包含設定檔的檔案，並將其訂閱更新為檔案中指定的多項服務。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2e98561a-97fd-483a-a547-c4e6d33993dc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 77%

---

# 從檔案更新多個訂閱狀態 {#updating-multiple-subscription-statuses-from-a-file}

此範例說明如何匯入包含設定檔的檔案，以及如何將其訂閱更新為檔案中指定的多個服務。匯入檔案後，必須進行調和，以便將匯入的資料識別為具有服務連結的描述檔。為確保檔案不包含任何重複項目，將對資料執行重複資料刪除活動。

工作流程如下：

![](assets/subscription_activity_example1.png)

* A [載入檔案](../../automating/using/load-file.md) 活動載入設定檔檔案並定義匯入欄的結構。

  在此範例中，載入檔案為 .csv 格式，並包含以下資料：

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

  如您所注意的，此操作在檔案中指定為 &quot;sub&quot; 或 &quot;unsub&quot;。此系統需要一個 **Boolean** 或 **Integer** 整數值來識別要執行的操作：&quot;0&quot; 為取消訂閱與 &quot;1&quot; 為訂閱。為符合此要求，在 &quot;operation&quot; 欄的詳細資訊中執行值的重新映射。

  ![](assets/subscription_example_remapping.png)

  如果您的檔案已使用 &quot;0&quot; 及 &quot;1&quot; 來識別此操作，則不需要重新映射這些值。僅確定在 **[!UICONTROL Column definition]** 索引標籤中將此欄處理為 **Boolean** 或 **Integer**。

* A [調解](../../automating/using/reconciliation.md) 活動會將檔案中的資料識別為屬於Adobe Campaign資料庫的設定檔維度。 透過 **[!UICONTROL Identification]** 索引標籤，檔案的 **email** 欄位與設定檔資源的 **email** 欄位相符。

  ![](assets/subscription_activity_example3.png)

  在 **[!UICONTROL Relations]** 索引標籤中，使用服務資源所建立之連結，以便識別檔案的 **service** 欄位。在此範例中，值與服務資源的 **name** 欄位相符。

  ![](assets/subscription_example_service_relation.png)

* A [重複資料刪除](../../automating/using/deduplication.md) 根據 **電子郵件** 臨時資源的欄位（調解後產生的結果）會識別重複專案。 消除重複項目非常重要，因為所有資料的服務訂閱將會在出現重複項目時失敗。

  ![](assets/subscription_activity_example5.png)

* A [訂閱服務](../../automating/using/subscription-services.md) 活動會將要更新的服務識別為來自此轉變，透過中建立的連結進行 **[!UICONTROL Reconciliation]** 活動。

  將 **[!UICONTROL Operation type]** 識別為來自檔案的 **operation** 欄位。此處只能選取 Boolean 或 Integer 欄位。如果檔案中包含要執行的操作欄未出現在清單中，請確保您已正確設定 **[!UICONTROL Load file]** 活動中的欄格式，如本範例前面所述 。

  ![](assets/subscription_activity_example_from_file.png)
