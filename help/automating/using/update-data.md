---
title: 更新資料
description: 「更新」資料活動允許您對資料庫中的欄位執行成批更新。
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
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 0%

---


# 更新資料{#update-data}

## 說明 {#description}

![](assets/data_update.png)

此活 **[!UICONTROL Update data]** 動允許您對資料庫中的欄位執行成批更新。

## 使用內容 {#context-of-use}

匯 **入檔案後** ，可使用「更新資料」活動，以便將已復原的資料插入Adobe Campaign資料庫。 幾個選項可讓您個人化更新資料。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Update data]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 指定 **[!UICONTROL Operation type]** 要執行的：

   * **[!UICONTROL Insert or update]**: 插入資料或更新資料（如果資料庫中已存在記錄）。
   * **[!UICONTROL Insert only]**: 僅插入資料。 不更新已存在的記錄。 如果定義了協調標準，則只添加未協調的記錄。

      如果匯入 **[!UICONTROL Generate an outbound transition for rejects]** 的資料包含資料庫中已存在的某些記錄，請核取此方塊，以避免可能的錯誤。

   * **[!UICONTROL Update]**: 更新僅存在於資料庫中的記錄的資料。
   * **[!UICONTROL Delete]**: 刪除資料。
   >[!NOTE]
   >
   >欄位 **[!UICONTROL Batch size]** 可讓您定義要上傳之資料的最大批次大小。

1. 在頁籤 **[!UICONTROL Identification]** 中，指定如何標識資料庫中的記錄：

   * **[!UICONTROL Using the targeting dimension]**: 選取 **[!UICONTROL Dimension to update]** ，然後指定 **[!UICONTROL Keys for finding records]**。 如需詳細資訊，請參閱「定 [位維度和資源」](../../automating/using/query.md#targeting-dimensions-and-resources)。
   * 如果輸入的資料符合現有的定位維度，請選取 **[!UICONTROL Using one or more links]** 選項。 然後選擇 **[!UICONTROL Dimension to update]**。
   如果所選操作類型需要更新，則必須使用協調密鑰。

1. 在標 **[!UICONTROL Fields to update]** 簽中，指定要套用更新的欄位，並視需要新增條件，以執行此更新。 若要這麼做，請使用 **[!UICONTROL Taken into account if]** 欄。 條件會依清單順序逐一套用。 使用右邊的箭頭來變更更新順序。 您可以多次使用相同的目標欄位。

   您可以使用按鈕自動連結欄 ![](assets/wkf_magic_wand-24px.png) 位。 自動連結會偵測同名的欄位。

   在文字操 **[!UICONTROL Insert or update]** 作期間，您可以單獨選擇要應用於每個欄位的操作。 若要這麼做，請在欄中選取您要的 **[!UICONTROL Operation]** 值。

   >[!NOTE]
   >
   >**管理更新** ：在執行更新資料活 **[!UICONTROL lastModified]****[!UICONTROL modifiedBy]****[!UICONTROL created]****[!UICONTROL createdBy]** 動時，除非在欄位更新表格上明確執行其設定，否則會自動更新、和欄位。 只對已檢測到至少一個差的記錄執行更新。 如果值相同，則不會執行更新。

1. 如有需要，請管理活動的 [轉場](../../automating/using/activity-properties.md) ，以存取出站人口的進階選項。

   如果您已選擇並 **[!UICONTROL Insert only]** 且導入的資料可能包含資料庫中已存在的記錄，請選中該框以 **[!UICONTROL Generate an outbound transition for the rejects]** 避免出現任何可能的錯誤。

1. 確認活動的設定並儲存工作流程。

## Example {#example}

以下活動顯示活動後 **[!UICONTROL Update data]** 的活動配 **[!UICONTROL Load file]** 置。 此工作流程的目的，是使用從檔案中復原的資料，將描述檔新增或更新至Adobe Campaign資料庫。 使用的協調金鑰是電子郵件地址。

載入的檔案為 **.txt格式檔案** ，包含下列範例資料：

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

活動 **[!UICONTROL Update data]** 的配置如下：

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

