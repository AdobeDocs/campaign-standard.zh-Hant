---
title: 儲存對象
description: 「儲存對象」活動可讓您更新現有的對象，或是從工作流程中的母體運算上游建立新的對象。
page-status-flag: never-activated
uuid: 8babb173-fa59-44a7-a2a5-49f45ba6bf99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 1f6bb048-7abd-499b-a4b0-187f9492dc47
context-tags: saveAudience,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '803'
ht-degree: 100%

---


# 儲存對象{#save-audience}

## 說明 {#description}

![](assets/save_audience.png)

**[!UICONTROL Save audience]** 活動可讓您更新現有的對象，或是從工作流程中的母體運算上游建立新的對象。從此活動建立或更新的對象是&#x200B;**清單**&#x200B;或&#x200B;**檔案**&#x200B;對象。它們會新增至應用程式對象清單，並可透過 **[!UICONTROL Audiences]** 功能表使用。

>[!NOTE]
>
>如果對象是透過 **[!UICONTROL Save audience]** 活動建立並且富含其他資料，您將無法使用這些資料來個人化獨立傳送。它們只能從在工作流程中執行的傳送中使用。

此活動也可讓您將設定檔匯出為 Adobe Experience Cloud 對象/區段。如此一來，您便可在其他 Adobe Experience Cloud 解決方案中利用這些對象。如需共用對象的詳細資訊，請參閱[使用 Campaign 及 People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)。

## 使用內容 {#context-of-use}

**[!UICONTROL Save audience]** 活動主要用於將母體族群轉換為可重複使用的對象，讓母體族群可繼續在相同工作流程中運算。

## 設定 {#configuration}

1. 將活動 **[!UICONTROL Save audience]** 拖曳至工作流程中。
1. 在其他目標定位活動（例如查詢、交叉點、聯合或排除）之後進行連接。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 選取要執行的動作：

   * **[!UICONTROL Update an existing audience]**：選取現有對象，然後選取更新類型：

      * **[!UICONTROL Replace audience content with new data]**：會取代整個對象內容。遺失舊資料。僅保留儲存對象活動之入站轉變的資料。
      * **[!UICONTROL Complete audience with new data]**：保留舊的對象資料，並新增儲存對象活動入站轉變的資料。
   * **[!UICONTROL Create then update an audience]**：輸入對象名稱並選取更新類型。如果對象尚未存在，則會建立對象。若已存在，則會根據所選模式更新：

      * **[!UICONTROL Replace audience content with new data]**：會取代整個對象內容。遺失舊資料。僅保留儲存對象活動之入站轉變的資料。

         警告：此選項會清除已更新對象的對象類型和目標定位維度。

      * **[!UICONTROL Complete audience with new data]**：保留舊的對象資料，並新增儲存對象活動入站轉變的資料。

         警告：如果更新對象的對象類型或目標維度與工作流程的目前設定不相容，此選項會造成錯誤。例如，您無法使用來自查詢的設定檔以完成檔案類型對象。
   * **[!UICONTROL Create a new audience]**：輸入要建立的對象名稱。建立對象的時間和日期會自動新增至對象名稱。如此一來，每次執行工作流程時，對象都會是唯一的。
   * **[!UICONTROL Share in Adobe Experience Cloud]**：如果您有目標設定檔，而且您想要將對象匯出至 Adobe Experience Cloud，請選取此選項，然後選取現有的共用對象或建立新對象。

      同時選取與對象中所含資料之資源相對應的 **[!UICONTROL Shared Data source]**，以便在 Adobe Experience Cloud 中正確調解資料。

      使用此選項，共用的對象不會新增至 **[!UICONTROL Audiences]** 功能表中可用的 Adobe Campaign 對象清單。

      >[!NOTE]
      >
      >只有在管理員已設定 Adobe Experience Cloud 的共用對象功能時，才可使用此選項。如需詳細資訊，請參閱[使用 Campaign 及 People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)。
   更新期間儲存或可用的對象類型會視工作流程上游的活動而定。

   如果對象的目標定位維度在儲存時未知（例如，如果來自匯入的檔案），則會建立或更新對象為 **[!UICONTROL File]** 類型觀眾。

   如果儲存時已定義儲存對象的目標定位維度（例如，如果來自定位、查詢後等），則會將對象儲存或更新為 **[!UICONTROL List]** 類型對象。

   之後著，儲存的對象內容便可在對象的詳細資料檢視中使用，您可從 **[!UICONTROL Audiences]** 功能表存取該內容。此檢視中可用的欄會與工作流程儲存對象活動之入站轉變的欄相對應。例如：匯入檔案的欄、從查詢新增的其他資料。

1. 確認活動的設定並儲存工作流程。

## 範例 {#example}

此範例中定義的工作流程會顯示定期的對象更新，以利目標定位：

* 會使用 **[!UICONTROL Scheduler]** 每月自動執行一次。
* 您可以使用 **[!UICONTROL Query]**，將所有訂閱的設定檔復原到可用的不同應用程式服務。
* **[!UICONTROL Save audience]** 活動會刪除自上次工作流程執行以來從服務取消訂閱的設定檔，並新增新訂閱的設定檔，以更新對象。

![](assets/save_audience_example_1.png)

**[!UICONTROL Save audience]** 活動的設定如下：

![](assets/save_audience_example_2.png)

