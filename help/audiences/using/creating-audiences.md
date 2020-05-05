---
title: 建立閱聽眾
description: 瞭解如何在Adobe Campaign中建立觀眾。
page-status-flag: never-activated
uuid: fe99b31b-a949-4832-b0e6-2b36d1c8be80
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: df8bdcfb-be5e-4044-bc26-aa3466accbbe
context-tags: readAudience,main;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# 建立閱聽眾{#creating-audiences}

## 建立查詢對象 {#creating-query-audiences}

本節說明如何建立查 **詢對象** 。 您也可以從匯入檔案或在工作流程中鎖定目標來建立 [對象](../../automating/using/get-started-workflows.md)。

從對象清單中，您可以對Adobe Campaign設定檔執行查詢或匯入Adobe Experience Cloud對象，以建立對象。

1. 透過標籤或卡片前往對 **[!UICONTROL Audiences]** 像清單。

   ![](assets/audiences_query_1.png)

1. 選 **[!UICONTROL Create]** 取以存取畫面以建立新觀眾。

   ![](assets/audiences_query.png)

1. 為您的觀眾命名。 觀眾標籤會用於觀眾清單和查詢工具的浮動視窗中。
1. 選擇對 **[!UICONTROL Query]** 像類型： 由查詢定義的觀眾在每次進一步使用時被重新計算。

   ![](assets/audience_type_selection.png)

1. 然後，選 **[!UICONTROL Targeting dimension]** 取您要用來篩選客戶的項目。 每個對象都由單一定位維度組成。 例如，您無法建立由設定檔、測試設定檔和訂閱者組成的觀眾。 For more on targeting dimensions, refer to [this page](../../automating/using/query.md#targeting-dimensions-and-resources).
1. 建立查詢以定義觀眾人口。 請參閱有關編輯查詢 [的章節](../../automating/using/editing-queries.md)。
1. 按一下按 **[!UICONTROL Create]** 鈕以儲存您的觀眾。

>[!NOTE]
>
>您可以新增說明給此對象，並透過圖示定義存取授 **[!UICONTROL Edit properties]** 權。

## 建立清單對象 {#creating-list-audiences}

本節說明在工作流程中定 **位後** ，如何建立清單對象。 您也可以將檔案匯入工作流程 [中](../../automating/using/get-started-workflows.md) ，或透過功能表的查詢來建立 **[!UICONTROL Audiences]** 觀眾。

若要建立 **清單** (List)對象，步驟如下：

1. 在「行銷活 **動」標籤中** ，按一下「 **建立** 」，然後選 **取「工作流程**」。

   ![](assets/audiences_list_1.png)

1. 拖放，然後設定定位活動，讓您選取具有已知維度的 **人口** 。 可用活動的清單及其設定會在「定位活動」區 [段中詳](../../automating/using/about-targeting-activities.md) 細說明。

   您可以使用活 **[!UICONTROL Query]** 動，或在使用活動識別匯入 **[!UICONTROL Load file]** 的資料維度之前， **[!UICONTROL Reconciliation]** 使用活動匯入資料。 在此，我們希望鎖定訂閱體育電子報並進行活動的收 **[!UICONTROL Query]** 件者。

   ![](assets/audiences_list_2.png)

1. 定位後，將活動拖放至 **[!UICONTROL Save audience]** 工作流程中。 例如，您可以選擇建 **[!UICONTROL Create or update an audience]**&#x200B;立，然後使用新資料自動更新觀眾。 在這種情況下，請在工作 **[!UICONTROL Scheduler]** 流程的開頭添加活動。

   如需設定此活動的詳細資訊，請參閱「儲存 [觀眾](../../automating/using/save-audience.md) 」區段。

   ![](assets/audiences_list_3.png)

1. 儲存並啟動工作流程。

   當定位 **[!UICONTROL Save audience]** 對象與已知維度之後放置時，透過此活動建立的對象為「清 **單** 」對象。

   接著，儲存的觀眾內容便可在觀眾的詳細檢視中取得，而觀眾的詳細檢視可透過觀眾清單存取。 此視圖中可用的列對應於工作流保存活動的入站轉換的列。 例如： 匯入的檔案欄、從查詢新增的其他資料。

   ![](assets/audiences_list_4.png)

## 建立檔案對象 {#creating-file-audiences}

本節詳細說明如何將檔案匯 **入工作流程** ，以建立檔案對象。 您也可以從工作流程中的定位活動 [或從功能表](../../automating/using/get-started-workflows.md) ，透過查詢建立 **[!UICONTROL Audiences]** 對象。

若要建立 **檔案** (File)對象，步驟如下：

1. 在「行銷活 **動」標籤中** ，按一下「 **建立** 」，然後選 **取「工作流程**」。
1. 拖放，然後設定活 **[!UICONTROL Load file]** 動，可讓您在執行工作流程時匯入具有未 **知維** 度的人口。 有關配置此活動的詳細資訊，請參閱「 [載入檔案](../../automating/using/load-file.md) 」部分。

   ![](assets/audience_files_1.png)

1. 在活動後拖 **[!UICONTROL Save audience]** 放活 **[!UICONTROL Load file]** 動。 如需設定此活動的詳細資訊，請參閱「儲存 [觀眾](../../automating/using/save-audience.md) 」區段。
1. 儲存並啟動工作流程。

   ![](assets/audience_files_2.png)

   當匯 **[!UICONTROL Save audience]** 入後置入時，資料維度為未知，透過此活動建立的對象為檔案 **對象** 。

   接著，儲存的觀眾內容便可在觀眾的詳細檢視中取得，而觀眾的詳細檢視可透過觀眾清單存取。 此視圖中可用的列對應於工作流保存活動的入站轉換的列。 例如： 讀入檔案的欄、從查詢新增的其他資料。

   ![](assets/audience_files_3.png)

## 建立Experience Cloud觀眾 {#creating-experience-cloud-audiences}

Adobe Campaign可讓您與Adobe Experience Cloud共用和交換受眾。 Experience Cloud類 **型的觀眾會透過技術工作流程，直接從People核心服務匯入****[!UICONTROL Import shared audience]** Adobe Campaign。

與 **Adobe Campaign中查詢個人檔案的** Query類型對象不同， **Experience Cloud** Audience是由訪客ID清單所組成。

為了讓此整合發揮作用，您必須先進行設定。 如需有關設定以及如何使用People核心服務匯入或匯出觀眾的詳細資訊，請參閱下 [節](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)。

![](assets/audience_peoplecore.png)

## 編輯觀眾 {#editing-audiences}

根據對象類型，有不同的編輯對象方式：

* 若要編輯 **查詢對象** ，請透過功能表或Adobe Campaign首頁 **[!UICONTROL Audiences]****[!UICONTROL Audiences]** 的資訊卡，移至對象清單。

   開啟相關的受眾。 您可以編輯先前建立之觀眾的所有元素。

   >[!CAUTION]
   >
   >如果您變更 **[!UICONTROL Filtering dimension]** 查詢中的規則，先前已定義的規則將會遺失。

* 若要編輯 **清單** 或檔案 **對象** ，請編輯從中建立該對象的工作流程，並修改 **[!UICONTROL Save audience]** 活動。 啟動工作流程，以便修改對象。
* 若要編輯 **Experience Cloud觀眾** ，請參閱「使用 [人員核心服務匯入／匯出觀眾](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) 」區段。

## 刪除觀眾 {#deleting-audiences}

有兩種方式可刪除一或多個對象。 首先，您可以新增到期日給對象

若要這麼做：

1. 存取您的觀眾。
1. 按一下 ![](assets/edit_darkgrey-24px.png) 按鈕以存取您對象的設定。

   ![](assets/audience_delete_2.png)

1. 在欄位 **[!UICONTROL Expires on]** 中，新增到期日給您的觀眾。

   ![](assets/audience_delete_3.png)

1. 按一 **[!UICONTROL Confirm]** 下 **[!UICONTROL Save]**。

您的到期日現在已設定好。 一旦到達此日期，您的對象就會自動刪除。

或者，如果您需要刪除對象，您只需選取一或多個對象，然後按一下按 **[!UICONTROL Delete element]** 鈕。

![](assets/audience_delete_1.png)

