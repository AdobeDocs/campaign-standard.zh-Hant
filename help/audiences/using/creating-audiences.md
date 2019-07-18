---
title: 建立觀眾
seo-title: 建立觀眾
description: 建立觀眾
seo-description: 瞭解如何在Adobe Campaign中建立受眾。
page-status-flag: 從未啓動
uuid: fe99b31b-a949-4832-b0 e6-2b36 d1 c8
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受眾
content-type: reference
topic-tags: 管理觀眾
discoiquuid: df8bdlbing-be5 e-4044-bc26-aa3466 accbe
context-tags: ReadAudience，main；觀眾，概觀；傳送，觀眾，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Creating audiences{#creating-audiences}

## Creating query audiences {#creating-query-audiences}

This section describes how to create a **Query** audience. You can also create audiences from importing a file or targeting in a [workflow](../../automating/using/discovering-workflows.md).

在觀眾清單中，您可以透過執行Adobe Campaign設定檔上的查詢或匯入Adobe Experience Cloud觀眾來建立觀眾。

1. Go to the audience list via the **[!UICONTROL Audiences]** tab or card.

   ![](assets/audiences_query_1.png)

1. Select **[!UICONTROL Create]** to access the screen to create a new audience.

   ![](assets/audiences_query.png)

1. 為您的觀眾命名。觀眾標籤會用於觀眾清單中，以及查詢工具的浮動視窗中。
1. Choose a **[!UICONTROL Query]** audience type: the audiences defined by a query are recomputed at each further use.

   ![](assets/audience_type_selection.png)

1. Then select the **[!UICONTROL Targeting dimension]** that you would like to use to filter your customers. 每個對象由單一定位維度組成。例如，您無法建立由這兩個描述檔組成的觀眾，測試設定檔和訂閱者。For more on targeting dimensions, refer to [this page](../../automating/using/query.md#targeting-dimensions-and-resources).
1. 建立查詢以定義觀眾人口。Refer to the section on [editing queries](../../automating/using/editing-queries.md).
1. Click the **[!UICONTROL Create]** button to save your audience.

>[!NOTE]
>
>You can add a description to this audience and define the access authorizations via the **[!UICONTROL Edit properties]** icon.

## Creating list audiences {#creating-list-audiences}

This section describes how to create a **List** audience after targeting in a workflow. You can also create audiences by importing a file into a [workflow](../../automating/using/discovering-workflows.md) or via a query from the **[!UICONTROL Audiences]** menu.

To create a **List** audience, the steps are as follows:

1. In the **Marketing activities** tab, click **Create** then select **Workflow**.

   ![](assets/audiences_list_1.png)

1. Drag and drop, and then configure the targeting activities which will allow you to select a population that has a **known** dimension. The list of available activities and their configuration are detailed in the [Targeting activities](../../automating/using/about-targeting-activities.md) section.

   You can use a **[!UICONTROL Query]** activity, or import data using a **[!UICONTROL Load file]** activity before using a **[!UICONTROL Reconciliation]** activity to identify the dimension of the data imported. Here, we want to target recipients who subscribed to the Sport Newsletter with a **[!UICONTROL Query]** activity .

   ![](assets/audiences_list_2.png)

1. After your targeting, drag and drop a **[!UICONTROL Save audience]** activity into your workflow. For example, you can chose to **[!UICONTROL Create or update an audience]**, this allows you to create then automatically update your audience with new data. In this case, add a **[!UICONTROL Scheduler]** activity at the beginning of your workflow.

   For more information on configuring this activity, refer to the [Save audience](../../automating/using/save-audience.md) section.

   ![](assets/audiences_list_3.png)

1. 儲存並開始工作流程。

   As the **[!UICONTROL Save audience]** is placed after a targeting with a known dimension, the audiences created via this activity are **List** audiences.

   然後，已儲存對象的內容便可用於讀者的詳細檢視，可透過觀眾清單存取。此檢視中可用的欄對應工作流程儲存活動的傳入轉變欄。例如：匯入的檔案欄，以及從查詢中新增的其他資料。

   ![](assets/audiences_list_4.png)

## Creating file audiences {#creating-file-audiences}

This section details how to create a **File** audience by importing a file into a workflow. You can also create audiences from a targeting activity in a [workflow](../../automating/using/discovering-workflows.md) or via a query from the **[!UICONTROL Audiences]** menu.

To create a **File** audience, the steps are as follows:

1. In the **Marketing activities** tab, click **Create** then select **Workflow**.
1. Drag and drop, and then configure a **[!UICONTROL Load file]** activity which will allow you to import a population that has an **unknown** dimension when the workflow is executed. For more information on configuring this activity, refer to the [Load file](../../automating/using/load-file.md) section.

   ![](assets/audience_files_1.png)

1. Drag and drop a **[!UICONTROL Save audience]** activity after the **[!UICONTROL Load file]** activity. For more information on configuring this activity, refer to the [Save audience](../../automating/using/save-audience.md) section.
1. 儲存並開始工作流程。

   ![](assets/audience_files_2.png)

   As the **[!UICONTROL Save audience]** is placed after an import, the data dimension is unknown and the audiences created via this activity are **File** audiences.

   然後，已儲存對象的內容便可用於讀者的詳細檢視，可透過觀眾清單存取。此檢視中可用的欄對應工作流程儲存活動的傳入轉變欄。例如：匯入檔案的欄，以及從查詢中新增的其他資料。

   ![](assets/audience_files_3.png)

## Creating Experience Cloud audiences {#creating-experience-cloud-audiences}

Adobe Campaign可讓您透過Adobe Experience Cloud分享和交換受眾。**Experience Cloud** 類型對象會透過 **[!UICONTROL Import shared audience]** 技術工作流程直接從People核心服務匯入Adobe Campaign。

Unlike **Query** type audience which will query profiles from Adobe Campaign, the **Experience Cloud** audience is composed of a list of Visitor IDs.

要讓此整合運作，您必須先進行設定。For more information on configuration and how to import or export audiences with People core service, refer to the following [section](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md).

![](assets/audience_peoplecore.png)

## Editing audiences {#editing-audiences}

根據對象類型編輯對象有不同的方式：

* To edit a **Query** audience, go to the list of audiences via the **[!UICONTROL Audiences]** menu, or the **[!UICONTROL Audiences]** card from the Adobe Campaign home page.

   開啓相關受眾。可以編輯先前建立之對象的所有元素。

   >[!CAUTION]
   >
   >If you change the **[!UICONTROL Filtering dimension]** in the query, the rules that have previously been defined will be lost.

* To edit a **List** or **File** audience, edit the workflow from which it was created and modify the **[!UICONTROL Save audience]** activity. 啓動工作流程，讓觀眾修改。
* To edit an **Experience Cloud** audience, refer to the [Importing/Exporting audiences with People core service](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) section.

## Deleting audiences {#deleting-audiences}

有兩種方法可刪除一或多個對象。首先，您可以為觀眾新增到期日

若要這麼做：

1. 存取您的其中一個觀眾。
1. Click the ![](assets/edit_darkgrey-24px.png) button to access your audience's configuration.

   ![](assets/audience_delete_2.png)

1. **[!UICONTROL Expires on]** 在欄位中，新增到期日給您的觀眾。

   ![](assets/audience_delete_3.png)

1. Click **[!UICONTROL Confirm]** then **[!UICONTROL Save]**.

您的到期日現在已設定。一旦達到此日期，您的觀眾將會自動刪除。

Or if you need to delete an audience, you can simply select one or several audiences then click the **[!UICONTROL Delete element]** button.

![](assets/audience_delete_1.png)

