---
title: 根據工作流程區段建立報表
seo-title: 根據工作流程區段建立報表
description: 根據工作流程區段建立報表
seo-description: 瞭解如何根據報表中的工作流程細分，檢查交付是否成功。
page-status-flag: 從未啓動
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: benst
products: SG_ CAMPAIGN/STANDARD
audience: 報告功能
content-type: reference
topic-tags: 自訂報表
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36e04227f300d28d2c48da440ddab3ccf9281168

---


# Creating a report based on workflow segments{#creating-a-report-workflow-segment}

建立工作流程並將其篩選為不同目標對象後，您可以根據此定位工作流程中定義的區段，測量行銷促銷活動的效率。
若要在您的報表中定位這些區段：

* [步驟1：更新具有區段的自訂資源](#step-1--update-profiles-custom-resource-segments)
* [步驟2：建立含區段的工作流程](#step-2--create-a-workflow-segments)
* [步驟3：建立動態報表以篩選區段](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>必須接受動態報告使用合約，才能開始收集這些資料。
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Step 1: Update Profiles custom resource with segments{#step-1--update-profiles-custom-resource-segments}

Before reporting on your segment code, you need to update your **[!UICONTROL Profiles]** custom resource for your segment codes to be stored.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]**, then select the **[!UICONTROL Profile (profile)]** resource.
1. In the **[!UICONTROL Sending logs extension]** menu from the **[!UICONTROL Data structure]** tab, check **[!UICONTROL Add segment code]** to allow storage of your segment codes from targeting workflows and to send it to dynamic reporting.

   **[!UICONTROL Segment code]** 然後可在報表 **[!UICONTROL Profile]** 的維度區段中使用。

   ![](assets/report_segment_4.png)

1. 儲存自訂資源。

1. 您現在需要發佈自訂資源。
From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button. For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

您現在可以開始使用區段代碼建立工作流程。

Note that segment codes will be collected as soon as you enable the segment code in the **[!UICONTROL Sending logs extension]**.

## Step 2: Create a workflow with segments {#step-2--create-a-workflow-segments}

[!NOTE]
>如果電子郵件傳送的輸入轉換為空，則預設會新增先前轉場的區段代碼。

您首先需要建立具有不同目標人群的工作流程。在這裡，我們想要傳送一封會根據觀眾年齡而個人化的電子郵件：一次提供20到30年的個人檔案，另一份則適用於30到40歲的個人檔案。

1. 建立工作流程。For more details on how to create your workflow, refer to this [page](../../automating/using/building-a-workflow.md).

1. **[!UICONTROL Query]** 從浮動視窗拖曳並將活動拖曳至工作區中，以新增活動。

1. 從20到40歲的目標設定檔，將其細分為更明確的人口族群。

   ![](assets/report_segment_1.png)

1. Add a **[!UICONTROL Segmentation]** activity to split your query results into two targeted populations. For more on segmentation, refer to this [page](../../automating/using/targeting-data.md#segmenting-data).

1. Double click the **[!UICONTROL Segmentation]** activity to configure it. Edit the first segment by clicking **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Query profiles between the age of 20 to 30 and click **[!UICONTROL Confirm]** when done.

   ![](assets/report_segment_8.png)

1. Click **[!UICONTROL Add an element]** to create your second segment and configure it as described in the steps above to target profiles between the age of 30 to 40.

1. Edit the **[!UICONTROL Segment code]** for each population to be passed on through dynamic reporting.

   >[!NOTE]
   >此步驟是強制的，否則您將無法瞭解要報告的區段。

   ![](assets/report_segment_9.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity after your segments.

   ![](assets/report_segment_3.png)

1. 根據不同目標人口，個人化您的交付。For more on email creation, refer to this [page](../../designing/using/about-email-content-design.md).

1. 儲存工作流程。

1. Click **[!UICONTROL Start]** when your workflow is ready.

您現在可以存取報表來追蹤區段代碼。

## Step 3: Create a dynamic report to filter segments {#step-3--create-a-dynamic-report-filter-segments}

將傳送與工作流程傳送後，您可以使用工作流程中的區段代碼來劃分報表。

1. From the **[!UICONTROL Reports]** tab, select an out-of-the-box report or click the **[!UICONTROL Create new project]** button to start one from scratch.

   ![](assets/custom_profile_18.png)
1. Drag and drop the **[!UICONTROL Delivery]** dimension to your freeform table.

   ![](assets/report_segment_5.png)

1. Drag and drop different metrics to your table such as the **[!UICONTROL Open]** and **[!UICONTROL Click]** metrics to start filtering your data.
1. **[!UICONTROL Dimensions]** 在類別中，按一下 **[!UICONTROL Profile]** 維度，然後拖放工作流程中的 **[!UICONTROL Segment code]** 維度，以測量您的電子郵件傳送是否成功，根據目標人口而定。

   ![](assets/report_segment_6.png)

1. 視需要拖放工作區中的視覺化。

   ![](assets/report_segment_10.png)
