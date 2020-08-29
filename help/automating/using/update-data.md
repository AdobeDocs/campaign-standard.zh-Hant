---
title: 更新資料
description: 「更新」資料活動可讓您對資料庫中的欄位執行成批更新。
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 96%

---


# 更新資料{#update-data}

## 說明 {#description}

![](assets/data_update.png)

活動 **[!UICONTROL Update data]** 可讓您對資料庫中的欄位執行大量更新。

## 使用內容 {#context-of-use}

匯入檔案之後，可使用&#x200B;**更新資料**&#x200B;活動，以便將已復原的資料插入 Adobe Campaign 資料庫。數個選項可讓您個人化更新資料。

**相關主題：**

* [使用案例：根據檔案更新資料](../../automating/using/update-database-file.md)
* [根據自動檔案下載更新資料](../../automating/using/update-data-automatic-download.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Update data]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 指定要執行的 **[!UICONTROL Operation type]**：

   * **[!UICONTROL Insert or update]**：插入資料或更新資料（如果記錄已存在於資料庫中）。
   * **[!UICONTROL Insert only]**：僅插入資料。不更新已存在的記錄。如果已定義調解標準，則僅會新增未調解的記錄。

      如果匯入的資料包含資料庫中已存在的特定記錄，請核取此 **[!UICONTROL Generate an outbound transition for rejects]** 方塊，以避免任何可能的錯誤。

   * **[!UICONTROL Update]**：更新僅存在於資料庫中記錄的資料。
   * **[!UICONTROL Delete]**：刪除資料。

   >[!NOTE]
   >
   >**[!UICONTROL Batch size]** 欄位可讓您定義要上傳之資料的最大批次大小。

1. 在 **[!UICONTROL Identification]** 索引標籤中，指定如何識別資料庫中的記錄：

   * **[!UICONTROL Using the targeting dimension]**：選取 **[!UICONTROL Dimension to update]**，然後指定 **[!UICONTROL Keys for finding records]**。如需詳細資訊，請參閱[定位維度和資源](../../automating/using/query.md#targeting-dimensions-and-resources)。
   * 如果輸入的資料符合現有的定位維度，請選取 **[!UICONTROL Using one or more links]** 選項。然後選取 **[!UICONTROL Dimension to update]**。

   如果所選取的作業類型需要更新，則必須使用調解金鑰。

1. 在&#x200B;**[!UICONTROL Fields to update]** 索引標籤中，指定要套用更新的欄位，並視需要新增條件，以執行此更新。要執行此操作，請使用 **[!UICONTROL Taken into account if]** 欄。條件會依清單順序逐一套用。使用右邊的箭頭以變更更新順序。您可以多次使用相同的目的地欄位。

   您可以使用 ![](assets/wkf_magic_wand-24px.png) 按鈕自動連結欄位。自動連結會偵測具有相同名稱的欄位。

   在 **[!UICONTROL Insert or update]** 類型作業期間，您可以個別選取要對每個欄位套用的作業。要執行此操作，請在 **[!UICONTROL Operation]** 欄中選取您需要的值。

   >[!NOTE]
   >
   >**管理更新**：在執行更新資料活動時，除非在欄位更新表格上明確執行其設定，否則會自動更新 **[!UICONTROL lastModified]**、**[!UICONTROL modifiedBy]**、**[!UICONTROL created]**、**[!UICONTROL createdBy]**。只會對至少偵測到一個差異的記錄執行更新。如果值相同，則不會執行更新。

1. 如有需要，請管理活動的[轉變](../../automating/using/activity-properties.md)，以存取輸出母體的進階選項。

   如果您已選取 **[!UICONTROL Insert only]**，而且匯入的資料可能包含資料庫中已存在的記錄，請核取 **[!UICONTROL Generate an outbound transition for the rejects]** 方塊，以避免出現任何可能的錯誤。

1. 確認活動的設定並儲存工作流程。
