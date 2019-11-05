---
title: 訂閱服務
description: 「訂閱服務」活動可讓您將設定檔大量擷取，並訂閱至服務或取消訂閱服務。
page-status-flag: 從未激活
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 資料管理活動
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 訂閱服務{#subscription-services}

## 說明 {#description}

![](assets/wf_subscription.png)

此活 **[!UICONTROL Subscription Services]** 動可讓您大量擷取描述檔，並將其訂閱至服務或取消訂閱服務。

>[!CAUTION]
>
>當在工作流環境中管理訂閱時，訂閱或取消訂閱的設定檔不會收到服務屬性中定義的不同確認電子郵件。

## 使用內容 {#context-of-use}

此活 **[!UICONTROL Subscription Services]** 動是唯一可讓多個描述檔在單一動作中訂閱或取消訂閱服務的Adobe Campaign功能。

在執行定位或匯入含有已識別資料的檔案後，您可以使用此活動。

如果通過專用列在檔案中指定，則此活動還允許您選擇要執行該操作的操作（訂閱或取消訂閱）和服務。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Subscription Services]** 至工作流程。
1. 在匯入後進行其他定位活動（例如查詢或協調）之後進行連接。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 使用 **[!UICONTROL Service]** 下列其中一個選項，選擇您要管理其訂閱的選項：

   * **[!UICONTROL Select a specific service]**:手動選擇服務。
   * **[!UICONTROL Select services from the inbound transition]**:服務在入站過渡中指定。 例如，您可以匯入指定每行所管理之服務的檔案。 如果您選擇此選項，請確定資料與服務資源之間已預先建立連結，如本 **範例所示**[](#example--updating-multiple-subscription-statuses-from-a-file)。

      然後，對每個記錄動態地選擇要對其執行操作的服務。

1. 使用 **[!UICONTROL Operation type]** 下列選項之一選擇要執行的：

   * **[!UICONTROL Select a specific operation type]**:手動選擇是否要選擇或 **[!UICONTROL Subscribe]** 配置 **[!UICONTROL Unsubscribe]** 式。
   * **[!UICONTROL Select an operation type from a path of inbound transition]**:選擇入站資料的列，指定對每個記錄執行的操作。

      在此列中，必須將操作指定為布爾或整數。 使 **用** 0取消訂閱記錄， **使用** 1訂閱。

      如果導入檔案中包含的值不符合上述要求，您仍可以使用活動中可用的 [Remapping of values](../../automating/using/load-file.md#column-format) (重新映射值 **[!UICONTROL Load file]** )選項

1. 如果入站資料包含與服務配置檔案的預訂日期對應的列，請選擇該列。 您可以將其保留為空白，但在執行工作流程時未設定訂閱日期。
1. 定義訂閱的來源。 您可以勾選選項，將其設為傳入資料的其中一個欄位，或設為您選擇的常數 **[!UICONTROL Set a constant as origin]** 值。 您可以將其保留為空，但在運行工作流時未設定原點。
1. 如有需要，您可以產生出站轉場。 此轉換包含與傳入活動中完全相同的資料。
1. 確認活動的設定並儲存工作流程。

   現在可以執行了。 一旦執行，您就可以檢視已訂閱或取消訂閱服務的描述檔，以瞭解服務的詳細資訊。

## 範例：在匯入檔案後將描述檔訂閱至特定服務 {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

此示例說明如何導入包含配置檔案的檔案並將其預訂到現有服務。 匯入檔案後，必須進行協調，以便將匯入的資料識別為描述檔。 為確保檔案不包含任何重複項，將對資料執行重複資料消除活動。

工作流程如下：

![](assets/subscription_activity_example1.png)

* 活 **[!UICONTROL Load file]** 動載入配置檔案並定義導入列的結構。

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

* 活 **[!UICONTROL Reconciliation]** 動會將檔案中的資料識別為屬於Adobe Campaign資料庫的描述檔維度。 僅配置 **[!UICONTROL Identification]** 了頁籤。 它會根據描述檔的電子郵件地址識別檔案資料。

   ![](assets/subscription_activity_example3.png)

* 基 **[!UICONTROL Deduplication]** 於臨時資 **源** （由協調產生）的電子郵件欄位識別任何重複項。 如果從檔案匯入的資料包含任何重複項目，服務的訂閱將會失敗。

   ![](assets/subscription_activity_example5.png)

* 活 **[!UICONTROL Subscription Services]** 動可讓您選擇必須訂閱描述檔的服務、與訂閱日期對應的欄位，以及訂閱的來源。

   ![](assets/subscription_activity_example4.png)

## 範例：從檔案更新多個訂閱狀態 {#example--updating-multiple-subscription-statuses-from-a-file}

此示例說明如何導入包含配置檔案的檔案，以及如何將其預訂更新為檔案中指定的多個服務。 匯入檔案後，必須進行協調，以便將匯入的資料識別為具有服務連結的描述檔。 為確保檔案不包含任何重複項，將對資料執行重複資料消除活動。

工作流程如下：

![](assets/subscription_activity_example1.png)

* 活 **[!UICONTROL Load file]** 動載入配置檔案並定義導入列的結構。

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

   如您所注意的，此操作在檔案中指定為「sub」或「不明嫌犯」。 系統需要一個 **布爾** 或 **** 整數值來識別要執行的操作：「0」取消訂閱，「1」取消訂閱。 為符合此要求，在「操作」列的詳細資訊中執行值的重新映射。

   ![](assets/subscription_example_remapping.png)

   如果您的檔案已使用"0"和"1"來識別作業，則不需要重新對應這些值。 請只確定該列在頁籤中被處 **理為布爾****或整數****[!UICONTROL Column definition]** 。

* 活 **[!UICONTROL Reconciliation]** 動會將檔案中的資料識別為屬於Adobe Campaign資料庫的描述檔維度。 透過標 **[!UICONTROL Identification]** 簽，檔案的 **電子郵件欄位會與描述檔資** 源的電子郵件欄位相符 **** 。

   ![](assets/subscription_activity_example3.png)

   在標 **[!UICONTROL Relations]** 簽中，使用服務資源建立連結，以便 **識別檔案** 的服務欄位。 在此示例中，值與服務資 **源的名稱** 欄位匹配。

   ![](assets/subscription_example_service_relation.png)

* 基 **[!UICONTROL Deduplication]** 於臨時資 **源** （由協調產生）的電子郵件欄位來標識重複項。 務必消除重複項，因為服務的訂閱將在出現重複項時失敗。

   ![](assets/subscription_activity_example5.png)

* A標 **[!UICONTROL Subscription Services]** 識要更新的服務是來自轉場，透過活動中建立的連結 **[!UICONTROL Reconciliation]** 進行。

   該 **[!UICONTROL Operation type]** 檔案被標識為來自 **檔案** 的操作欄位。 此處只能選擇布爾或整數欄位。 如果包含要執行的操作的檔案列未出現在清單中，請確保您已正確設定活動中的列格式，如本例前面所述 **[!UICONTROL Load file]** 。

   ![](assets/subscription_activity_example_from_file.png)

