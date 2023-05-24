---
title: 根據工作流程細分建立報告
description: 瞭解如何根據報告中的工作流段檢查交付是否成功。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 2%

---

# 根據工作流程細分建立報告{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**只能針對電子郵件和簡訊發送。

在建立工作流並將人口篩選到不同的目標受眾之後，您可以根據此目標工作流中定義的段來衡量市場營銷活動的效率。
要在報表中瞄準這些段：

* [步驟1:使用段更新配置檔案自定義資源](#step-1--update-profiles-custom-resource-segments)
* [步驟2:建立具有段的工作流](#step-2--create-a-workflow-segments)
* [第3步：建立動態報告以篩選段](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>必須接受動態報告使用協定才能開始收集這些資料。
>
>有關此協定的詳細資訊，請參閱此 [頁](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 步驟1:使用段更新配置檔案自定義資源{#step-1--update-profiles-custom-resource-segments}

在報告段代碼之前，您需要更新 **[!UICONTROL Profiles]** 要儲存的段代碼的自定義資源。

1. 從高級菜單中，通過Adobe Campaign徽標選擇 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**，然後選擇 **[!UICONTROL Profile (profile)]** 資源。
1. 在 **[!UICONTROL Sending logs extension]** 的子菜單。 **[!UICONTROL Data structure]** 頁籤 **[!UICONTROL Add segment code]** 允許將段代碼從目標工作流中儲存，並將其發送到動態報告。

   的 **[!UICONTROL Segment code]** 將在 **[!UICONTROL Profile]** 維部分。

   ![](assets/report_segment_4.png)

1. 保存自定義資源。

1. 您現在需要發佈自定義資源。
從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**。

   ![](assets/custom_profile_7.png)

1. 按一下 **[!UICONTROL Prepare publication]** 然後，在準備完成後，按一下 **[!UICONTROL Publish]** 按鈕 有關自定義資源的詳細資訊，請參閱 [頁](../../developing/using/updating-the-database-structure.md)。

您現在可以開始使用段代碼建立工作流。

請注意，一旦在中啟用段代碼，系統將立即收集段代碼 **[!UICONTROL Sending logs extension]**。

## 步驟2:建立具有段的工作流 {#step-2--create-a-workflow-segments}

>[!NOTE]
>如果電子郵件傳遞的輸入轉換為空，則預設情況下將添加上一個轉換的段代碼。

您首先需要建立具有不同目標填充的工作流。 在此，我們希望發送一封根據受眾年齡而個性化的電子郵件：一個是20至30歲的檔案，另一個是30至40歲的檔案。

1. 建立工作流。 有關如何建立工作流的詳細資訊，請參閱此 [頁](../../automating/using/building-a-workflow.md)。

1. 添加 **[!UICONTROL Query]** 將其從元件面板中拖放到工作區中。

1. 20至40歲的目標資料，以後將其分類為目標群體。

   ![](assets/report_segment_1.png)

1. 添加 **[!UICONTROL Segmentation]** 活動，將查詢結果拆分為兩個目標總體。 有關細分的詳細資訊，請參閱此 [頁](../../automating/using/segmentation.md)。

1. 按兩下 **[!UICONTROL Segmentation]** 活動以配置它。 通過按一下 **[!UICONTROL Edit properties]**。

   ![](assets/report_segment_7.png)

1. 在20到30歲之間查詢配置檔案，然後按一下 **[!UICONTROL Confirm]** 完成。

   ![](assets/report_segment_8.png)

1. 按一下 **[!UICONTROL Add an element]** 建立第二段，並按照上面步驟中的說明將其配置為30到40歲之間的目標配置檔案。

1. 編輯 **[!UICONTROL Segment code]** 通過動態報告傳遞給每個人口。

   >[!NOTE]
   >此步驟是必需的，否則您將無法瞭解要報告的段。

   ![](assets/report_segment_9.png)

1. 拖放 **[!UICONTROL Email delivery]** 活動。

   ![](assets/report_segment_3.png)

1. 根據不同的目標群體個性化您的交貨。 有關建立電子郵件的詳細資訊，請參閱此 [頁](../../designing/using/designing-content-in-adobe-campaign.md)。

1. 儲存工作流程。

1. 按一下 **[!UICONTROL Start]** 工作流就緒。

您現在可以訪問報表以跟蹤段代碼。

## 第3步：建立動態報告以篩選段 {#step-3--create-a-dynamic-report-filter-segments}

在使用工作流發送交貨後，您可以使用工作流中的段代碼細分報表。

1. 從 **[!UICONTROL Reports]** 頁籤，選擇現成報告，或按一下 **[!UICONTROL Create new project]** 按鈕，從頭開始。

   ![](assets/custom_profile_18.png)
1. 拖放 **[!UICONTROL Delivery]** 的形式。

   ![](assets/report_segment_5.png)

1. 將不同的度量拖放到表中，如 **[!UICONTROL Open]** 和 **[!UICONTROL Click]** 開始篩選資料的度量。
1. 在 **[!UICONTROL Dimensions]** 的 **[!UICONTROL Profile]** 然後拖放 **[!UICONTROL Segment code]** 的維，以根據目標群體來衡量電子郵件傳遞的成功程度。

   ![](assets/report_segment_6.png)

1. 根據需要，在工作區中拖放可視化內容。

   ![](assets/report_segment_10.png)
