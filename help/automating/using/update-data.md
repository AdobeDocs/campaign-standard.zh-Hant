---
title: 更新資料
seo-title: 更新資料
description: 更新資料
seo-description: 「更新資料活動」可讓您對資料庫中的欄位執行大量更新。
page-status-flag: 從未啓動
uuid: 1dc55db5-afd-4688-b673-adfb8 c1338 b5
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 資料管理活動
discoiquuid: 4db83c95-4b75-4a16-8df-bd8940431 fa9
context-tags: 作者，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Update data{#update-data}

## Description {#description}

![](assets/data_update.png)

**[!UICONTROL Update data]** 活動可讓您對資料庫中的欄位執行大量更新。

## Context of use {#context-of-use}

**您可以在匯入檔案後使用更新資料** 活動，將資料插入Adobe Campaign資料庫中。有幾個選項可讓您個人化資料。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Operation type]** to be carried out:

   * **[!UICONTROL Insert or update]**：插入資料，或在資料庫中已存在記錄時加以更新。
   * **[!UICONTROL Insert only]**：僅插入資料。已存在的記錄不會更新。如果定義協調准則，則只會新增未協調的記錄。

      Check the **[!UICONTROL Generate an outbound transition for rejects]** box if the data imported contains certain records that already exist in the database to avoid any possible errors.

   * **[!UICONTROL Update]**：更新已存在於資料庫中的記錄資料。
   * **[!UICONTROL Delete]**：刪除資料。
   >[!NOTE]
   >
   >**[!UICONTROL Batch size]** 欄位可讓您定義要上載資料的最大批次大小。

1. In the **[!UICONTROL Identification]** tab, specify how to identify the records in the database:

   * **[!UICONTROL Using the targeting dimension]**：選取 **[!UICONTROL Dimension to update]** 然後指定 **[!UICONTROL Keys for finding records]**。For more this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * If the data entered matches an existing targeting dimension, select the **[!UICONTROL Using one or more links]** option. Then select the **[!UICONTROL Dimension to update]**.
   如果選取的作業類型需要更新，您必須使用協調金鑰。

1. **[!UICONTROL Fields to update]** 在標籤中，指定將套用更新的欄位，並視需要新增條件，以便進行此更新。To do this, use the **[!UICONTROL Taken into account if]** column. 條件會以清單順序逐一套用。使用右側的箭頭，變更更新順序。您可以多次使用相同的目的地欄位。

   You can automatically link fields using the ![](assets/wkf_magic_wand-24px.png) button. 自動連結會偵測相同名稱的欄位。

   **[!UICONTROL Insert or update]** 在類型操作期間，您可以個別選取要套用至每個欄位的作業。To do this, select the value you would like in the **[!UICONTROL Operation]** column.

   >[!NOTE]
   >
   >**管理更新：** 執行更新資料活動時，會自動更新 **[!UICONTROL lastModified]**&#x200B;和 **[!UICONTROL modifiedBy]****[!UICONTROL created]****[!UICONTROL createdBy]** 欄位，除非在欄位更新表格上明確執行其組態。更新僅在偵測到至少一個差異的記錄上執行。如果值相同，則不會進行更新。

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.

   If you have selected **[!UICONTROL Insert only]** and the data imported may contain records that are already present in the database, check the **[!UICONTROL Generate an outbound transition for the rejects]** box to avoid any possible errors.

1. 確認活動的設定並儲存工作流程。

## Example {#example}

The following activity shows the configuration of an **[!UICONTROL Update data]** activity following a **[!UICONTROL Load file]** activity. 此工作流程的目的是要使用從檔案復原的資料，新增或更新描述檔至Adobe Campaign資料庫。使用的協調金鑰是電子郵件地址。

The file loaded is a **.txt** format file containing the following example data:

```
lastname;firstname;email;birthdate
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

**[!UICONTROL Update data]** 活動的設定如下：

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

