---
title: 調解
seo-title: 調解
description: 調解
seo-description: 「調解」活動可讓您將未識別的資料連結至現有資源。
page-status-flag: 從未啓動
uuid: 7884db8c-1717-4724-be15-3b0 b32 cc071
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 資料管理活動
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: 協調，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Reconciliation{#reconciliation}

## Description {#description}

![](assets/reconciliation.png)

**[!UICONTROL Reconciliation]** 活動可讓您將未識別的資料連結至現有資源。

## Context of use {#context-of-use}

**[!UICONTROL Reconciliation]** 此活動主要用於「資料管理」用途，並隱含兩種不同的使用案例：

* Adding relations: a **[!UICONTROL Links]** tab allows you to add links between the inbound data and several other Adobe Campaign database dimensions.

   例如，包含購買資料的檔案也可能包含識別購買產品以及購買者的資訊。Two additional dimensions (besides that of **Purchases**) are therefore concerned by the file data: the **Products** and **Profiles** dimensions. Relations then need to be created between these and the **Purchases** dimension (refer to the following example).

   定義關係時，會將欄新增至傳入的資料，以參考連結維度的外鍵。

   >[!NOTE]
   >
   >此操作表示連結維度的資料已在資料庫中。例如，如果您匯入一個購買檔案，顯示購買了哪些產品、在哪個時間、哪個用戶端等等，以及用戶端都必須已存在於資料庫中。

* Data identification: an **[!UICONTROL Identification]** tab allows you to simply link inbound data to columns of an existing dimension in the Adobe Campaign database. 活動後，資料會被識別為屬於已定義維度。

   例如，您可以執行儲存觀眾、資料庫更新等動作。

For example, the **[!UICONTROL Reconciliation]** activity can be placed after a load data activity with the aim of importing non-standard data into the database.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Reconciliation]** activity into your workflow, following a transition containing a population whose targeting dimension does not directly come from Adobe Campaign. For more on this, referr to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to define links between the inbound data and other database dimensions, go to the **[!UICONTROL Links]** tab.

   視需要新增多個關係。對於每個關係，請先選取連結維度，然後在連結詳細資料中指定對應的欄位。

1. If you would like to simply identify the inbound data, go to the **[!UICONTROL Identification]** tab and check the **[!UICONTROL Identify the document from the working data]** box.

   選取您要協調傳入資料的定位維度。

   新增協調准則，將傳入的轉換記錄連結至選定的定位維度記錄。如果指定幾個准則，則必須進行所有驗證，才能讓所有資料之間的連結生效。

   Choose the **[!UICONTROL Processing unidentified source lines]** mode:

   * **[!UICONTROL Ignore them]**：只有可識別的資料才會保留在活動的對外轉場中。
   * **[!UICONTROL Keep in the outbound population]**：傳入過渡的所有資料都會保留在活動的對外轉移中。

1. 確認活動的設定並儲存工作流程。

## Example 1: Relation definition {#example-1--relation-definition}

下列範例顯示使用檔案購買資料更新資料庫的工作流程。購買資料包含其他維度的資料參照元素，例如用戶端電子郵件和產品代碼。

>[!NOTE]
>
>The **Transactions** and **Products** resources used in this example do not exist in the Adobe Campaign database by default. They were therefore created beforehand using the [Custom resources](../../developing/using/data-model-concepts.md) function. 對應至匯入檔案中的電子郵件地址以及產品的描述檔，會預先載入資料庫中。

工作流程由下列活動組成：

![](assets/reconciliation_example1.png)

* **[!UICONTROL Load file]** 活動，會載入並偵測檔案要匯入的資料。匯入的檔案包含下列資料：

   * 交易日期
   * 用戶端電子郵件地址
   * 購買的產品代碼
   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* A **[!UICONTROL Reconciliation]** activity to bind purchasing data to database profiles as well as products. 因此，必須定義檔案資料和描述檔表格以及產品表格之間的關係。This configuration is carried out in the activity's **[!UICONTROL Relations]** tab:

   * Relation with the **Profiles**: the file's **client** column is linked to the **email** field of the **Profiles** dimension.
   * Relation with the **Products**: the file's **product** column is linked to the **productCode** field of the **Profiles** dimension.
   欄會新增至傳入的資料，以參照連結維度的外鍵。

   ![](assets/reconciliation_example3.png)

* **[!UICONTROL Update data]** 活動可讓您使用匯入的資料定義要更新的資料庫欄位。As the data was already identified as belonging to the **Transactions** dimension in the previous activity, here you can use the **[!UICONTROL Directly using the targeting dimension]** identification option.

   By using the option that automatically detects fields to update, the links configured in the previous activity (to profiles and products) are added to the list of **[!UICONTROL Fields to update]**. 您也必須確定對應至交易日期的欄位已正確新增至此清單。

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## Example 2: Identification {#example-2--identification}

下列範例示範從包含新客戶的匯入檔案直接建立個人檔案的工作流程。它由下列活動組成：

![](assets/identification_example2.png)

* **[!UICONTROL Load file]** 活動，會載入並偵測檔案要匯入的資料。匯入的檔案包含下列資料：

   ```
   lastname;firstname;email;dateofbirth
   jackman;megan;megan.jackman@testmail.com;07/08/1975
   phillips;edward;phillips@testmail.com;09/03/1986
   weaver;justin;justin_w@testmail.com;11/15/1990
   martin;babeth;babeth_martin@testmail.net;11/25/1964
   reese;richard;rreese@testmail.com;02/08/1987
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
   grimes;daryl;daryl_890@testmail.com;12/06/1979
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
   ```

* **[!UICONTROL Reconciliation]** 活動，會將載入檔案的每欄連結至描述檔維度欄。無法識別檔案記錄(遺失資料、不相容資料類型等)會被忽略，以保留最終觀眾資料的完整性。

   ![](assets/identification_example1.png)

* **[!UICONTROL Save audience]** 活動，可儲存個人檔案的觀眾。

   ![](assets/identification_example3.png)

