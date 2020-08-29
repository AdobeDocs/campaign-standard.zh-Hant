---
title: 訂閱服務
description: 「訂閱服務」活動可讓您大量擷取設定檔，並訂閱至服務或取消訂閱服務。
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
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 98%

---


# 訂閱服務 {#subscription-services}

## 說明 {#description}

![](assets/wf_subscription.png)

**[!UICONTROL Subscription Services]** 活動可讓您大量擷取設定檔，並將其訂閱至服務或取消訂閱服務。

>[!CAUTION]
>
>當在工作流程內容中管理訂閱時，訂閱或取消訂閱的設定檔不會接收服務屬性中定義的不同確認電子郵件。

## 使用內容 {#context-of-use}

**[!UICONTROL Subscription Services]** 活動是唯一允許多個設定檔在單一動作中訂閱或取消訂閱服務的 Adobe Campaign 功能。

在執行目標定位或匯入含有已識別資料的檔案後，您可以使用此活動。

如果透過專用欄在檔案中指定，則此活動可讓您選取該動作（訂閱或取消訂閱）及要在其執行動作服務。

**相關主題：**

* [使用案例：從檔案更新多個訂閱狀態](../../automating/using/updating-subscriptions-from-file.md)
* [使用案例：將配置檔案從檔案預訂到特定服務](../../automating/using/subscribing-profiles-from-file.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Subscription Services]** 活動拖放至工作流程中。
1. 在匯入其他目標定位活動（如查詢或調解）之後進行連接。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 使用以下其中一個選項，選取您要為其管理訂閱的 **[!UICONTROL Service]**：

   * **[!UICONTROL Select a specific service]**：手動選取服務。
   * **[!UICONTROL Select services from the inbound transition]**：服務會在輸入轉變中指定。例如，您可以匯入指定每行所管理之服務的檔案。如果您選取此選項，請確定資料與&#x200B;**服務**&#x200B;資源之間已預先建立連結，如[本範例](#example--updating-multiple-subscription-statuses-from-a-file)所示。

      然後為每個記錄動態選取要對其執行操作的服務。

1. 使用下列選項之一，選取 **[!UICONTROL Operation type]** 所要執行的：

   * **[!UICONTROL Select a specific operation type]**：手動選取是否要選取 **[!UICONTROL Subscribe]** 或 **[!UICONTROL Unsubscribe]** 設定檔。
   * **[!UICONTROL Select an operation type from a path of inbound transition]**：選取輸入資料之欄，並指定為每個記錄執行的操作。

      在此欄中，必須將操作指定為布林值或整數。使用 **0** 以取消訂閱記錄，並使用 **1** 開始訂閱。

      如果導入檔案中包含的值不符合上述要求，您仍然可以使用活動中可用的 [Remapping of values](../../automating/using/load-file.md#column-format) **[!UICONTROL Load file]** 選項。

1. 如果輸入資料包含與服務設定檔訂閱之日期對應的欄，請選取此欄。您可以將其保留為空白，但在執行工作流程時未設定訂閱日期。
1. 定義訂閱的來源。您可以核取 **[!UICONTROL Set a constant as origin]** 選項，將其設為輸入資料的其中一個欄位，或設為您選取的常數值。您可以將其保留為空白，但在執行工作流程時未設定來源。
1. 如有需要，您可以產生輸出轉變。此轉變包含與輸入活動中完全相同的資料。
1. 確認活動的設定並儲存工作流程。

   現已準備就緒而可執行。一旦執行後，您即可以在服務的詳細資訊中檢視已訂閱或取消訂閱服務的設定檔。

## 範例：匯入檔案後將設定檔訂閱至特定的服務 {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

此範例說明如何匯入包含設定檔的檔案並將其訂閱至現有服務中。匯入檔案後，必須進行調解，以便將匯入的資料識別為設定檔。為確保檔案不包含任何重複項目，將對資料執行重複資料刪除活動。

工作流程如下：

![](assets/subscription_activity_example1.png)

* **[!UICONTROL Load file]** 活動載入設定檔檔案並定義匯入欄之結構。

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

* **[!UICONTROL Reconciliation]** 活動會將檔案中的資料識別為屬於 Adobe Campaign 資料庫的設定檔維度。僅設定 **[!UICONTROL Identification]** 索引標籤。它會根據描述檔的電子郵件地址識別檔案資料。

   ![](assets/subscription_activity_example3.png)

* **[!UICONTROL Deduplication]** 是以臨時資源的 **email** 為基礎（調解後產生的結果）的電子郵件欄位識別任何重複項目。如果從檔案匯入的資料包含任何重複項目，所有資料服務的訂閱將會失敗。

   ![](assets/subscription_activity_example5.png)

* **[!UICONTROL Subscription Services]** 活動可讓您選取必須訂閱設定檔的服務、與訂閱日期對應之欄位，以及訂閱的來源。

   ![](assets/subscription_activity_example4.png)

## 範例：從檔案 {#example--updating-multiple-subscription-statuses-from-a-file} 更新多個訂閱狀態

此範例說明如何匯入包含設定檔的檔案，以及如何將其訂閱更新為檔案中指定的多個服務。匯入檔案後，必須進行調解，以便將匯入的資料識別為具有服務連結的描述檔。為確保檔案不包含任何重複項目，將對資料執行重複資料刪除活動。

工作流程如下：

![](assets/subscription_activity_example1.png)

* **[!UICONTROL Load file]** 活動載入設定檔檔案並定義匯入欄之結構。

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

* **[!UICONTROL Reconciliation]** 活動會將檔案中的資料識別為屬於 Adobe Campaign 資料庫的設定檔維度。透過 **[!UICONTROL Identification]** 索引標籤，檔案的 **email** 欄位與設定檔資源的 **email** 欄位相符。

   ![](assets/subscription_activity_example3.png)

   在 **[!UICONTROL Relations]** 索引標籤中，使用服務資源所建立之連結，以便識別檔案的 **service** 欄位。在此範例中，值與服務資源的 **name** 欄位相符。

   ![](assets/subscription_example_service_relation.png)

* **[!UICONTROL Deduplication]** 是以臨時資源的 **email** 為基礎（調解後產生的結果）的電子郵件欄位識別重複項目。消除重複項目非常重要，因為所有資料的服務訂閱將會在出現重複項目時失敗。

   ![](assets/subscription_activity_example5.png)

* **[!UICONTROL Subscription Services]** 識別要更新的服務是來自此轉變，透過 **[!UICONTROL Reconciliation]** 活動中所建立的連結進行。

   將 **[!UICONTROL Operation type]** 識別為來自檔案的 **operation** 欄位。此處只能選取 Boolean 或 Integer 欄位。如果檔案中包含要執行的操作欄未出現在清單中，請確保您已正確設定 **[!UICONTROL Load file]** 活動中的欄格式，如本範例前面所述 。

   ![](assets/subscription_activity_example_from_file.png)

