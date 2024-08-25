---
title: 儲存客群
description: 「儲存客群」活動可讓您更新現有的客群，或是從工作流程中的群體運算上游建立新的客群。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: saveAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c3f029d7-779e-47e7-a925-1e8f672da4dd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 99%

---

# 儲存客群{#save-audience}

## 說明 {#description}

![](assets/save_audience.png)

**[!UICONTROL Save audience]** 活動可讓您更新現有的客群，或是從工作流程中的母體運算上游建立新的客群。從此活動建立或更新的客群是&#x200B;**清單**&#x200B;或&#x200B;**檔案**&#x200B;客群。它們會新增至應用程式客群清單，並可透過 **[!UICONTROL Audiences]** 功能表使用。

>[!NOTE]
>
>如果客群是透過 **[!UICONTROL Save audience]** 活動建立並且富含其他資料，您將無法使用這些資料來個人化獨立傳送。它們只能從在工作流程中執行的傳送中使用。

此活動也可讓您將設定檔匯出為 Adobe Experience Cloud 客群/區段。如此一來，您便可在其他 Adobe Experience Cloud 解決方案中利用這些客群。如需共用客群的詳細資訊，請參閱[使用 Campaign 及 People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)。

## 使用內容 {#context-of-use}

**[!UICONTROL Save audience]** 活動主要用於將母體族群轉換為可重複使用的客群，讓母體族群可繼續在相同工作流程中運算。

## 設定 {#configuration}

1. 將活動 **[!UICONTROL Save audience]** 拖曳至工作流程中。
1. 在其他目標定位活動（例如查詢、交叉點、聯合或排除）之後進行連接。
1. 選取活動，然後使用所顯示快速動作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 選取要執行的動作：

   * **[!UICONTROL Update an existing audience]**：選取現有客群，然後選取更新類型：

      * **[!UICONTROL Replace audience content with new data]**：會取代整個客群內容。遺失舊資料。僅保留儲存客群活動之入站轉變的資料。
      * **[!UICONTROL Complete audience with new data]**：保留舊的客群資料，並新增儲存客群活動入站轉變的資料。

   * **[!UICONTROL Create then update an audience]**：輸入客群名稱並選取更新類型。如果客群尚未存在，則會建立客群。若已存在，則會根據所選模式更新：

      * **[!UICONTROL Replace audience content with new data]**：會取代整個客群內容。遺失舊資料。僅保留儲存客群活動之入站轉變的資料。

        警告：此選項會清除已更新客群的客群類型和目標維度。

      * **[!UICONTROL Complete audience with new data]**：保留舊的客群資料，並新增儲存客群活動入站轉變的資料。

        警告：如果更新客群的客群類型或目標維度與工作流程的目前設定不相容，此選項會造成錯誤。例如，您無法使用來自查詢的設定檔以完成檔案類型客群。

   * **[!UICONTROL Create a new audience]**：輸入要建立的客群名稱。建立客群的時間和日期會自動新增至客群名稱。如此一來，每次執行工作流程時，客群都會是唯一的。
   * **[!UICONTROL Share in Adobe Experience Cloud]**：如果您有目標輪廓，而且您想要將客群匯出至 Adobe Experience Cloud，請選取此選項，然後選取現有的共用客群或建立新客群。

     同時選取與客群中所含資料之資源相對應的 **[!UICONTROL Shared Data source]**，以便在 Adobe Experience Cloud 中正確調和資料。

     使用此選項，共用的客群不會新增至 **[!UICONTROL Audiences]** 功能表中可用的 Adobe Campaign 客群清單。

     >[!NOTE]
     >
     >只有在管理員已設定 Adobe Experience Cloud 的共用客群功能時，才可使用此選項。如需詳細資訊，請參閱[使用 Campaign 及 People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)。

   更新期間儲存或可用的客群類型會視工作流程上游的活動而定。

   如果客群的目標定位維度在儲存時未知 (例如，如果來自匯入的檔案)，則會建立或更新客群為 **[!UICONTROL File]** 類型客群。

   如果儲存時已定義儲存客群的目標維度 (例如，如果來自定位、查詢後等)，則會將客群儲存或更新為 **[!UICONTROL List]** 類型客群。

   之後著，儲存的客群內容便可在客群的詳細資料檢視中使用，您可從 **[!UICONTROL Audiences]** 功能表存取該內容。此檢視中可用的欄會與工作流程儲存客群活動之入站轉變的欄相對應。例如：匯入檔案的欄、從查詢新增的其他資料。

1. 確認活動的設定並儲存工作流程。

## 範例 {#example}

此範例中定義的工作流程會顯示定期的客群更新，以利目標定位：

* 會使用 **[!UICONTROL Scheduler]** 每月自動執行一次。
* 您可以使用 **[!UICONTROL Query]**，將所有訂閱的設定檔復原到可用的不同應用程式服務。
* **[!UICONTROL Save audience]** 活動會刪除自上次工作流程執行以來從服務取消訂閱的輪廓，並新增新訂閱的設定檔，以更新客群。

![](assets/save_audience_example_1.png)

**[!UICONTROL Save audience]** 活動的設定如下：

![](assets/save_audience_example_2.png)
