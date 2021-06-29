---
solution: Campaign Standard
product: campaign
title: 根據工作流程細分建立報告
description: 了解如何根據報表中的工作流程區段來檢查傳送是否成功。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: 報告
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: c001aaba50bdce8d949acc6daf74f3c7738bd117
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# 根據工作流程細分建立報告{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**只能將目標定位為電子郵件和簡訊傳送。

建立工作流程並將母體篩選為不同的目標對象後，您可以根據此目標工作流程中定義的區段來評估行銷活動的效率。
若要在報表中定位這些區段：

* [步驟1:使用區段更新設定檔自訂資源](#step-1--update-profiles-custom-resource-segments)
* [步驟2:使用區段建立工作流程](#step-2--create-a-workflow-segments)
* [步驟3:建立動態報表以篩選區段](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>必須接受動態報告使用協定，才能開始收集這些資料。
>
>有關此協定的詳細資訊，請參閱此[page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 步驟1:使用區段更新設定檔自訂資源{#step-1--update-profiles-custom-resource-segments}

在報告區段代碼之前，您需要更新要儲存的區段代碼的&#x200B;**[!UICONTROL Profiles]**&#x200B;自訂資源。

1. 從進階功能表，透過Adobe Campaign標誌，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**，然後選取&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;資源。
1. 在&#x200B;**[!UICONTROL Data structure]**&#x200B;標籤的&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;功能表中，勾選&#x200B;**[!UICONTROL Add segment code]**&#x200B;以允許從目標工作流程儲存區段代碼並將其傳送至動態報告。

   然後，**[!UICONTROL Segment code]**&#x200B;將可在報表的&#x200B;**[!UICONTROL Profile]**&#x200B;維度區段中使用。

   ![](assets/report_segment_4.png)

1. 儲存自訂資源。

1. 您現在需要發佈自訂資源。
從高級菜單中，選擇**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**。

   ![](assets/custom_profile_7.png)

1. 按一下&#x200B;**[!UICONTROL Prepare publication]**，然後準備完成時，按一下&#x200B;**[!UICONTROL Publish]**&#x200B;按鈕。 如需自訂資源的詳細資訊，請參閱此[page](../../developing/using/updating-the-database-structure.md)。

您現在可以開始使用區段代碼建立工作流程。

請注意，當您在&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;中啟用區段代碼時，系統會立即收集區段代碼。

## 步驟2:使用區段建立工作流程 {#step-2--create-a-workflow-segments}

>[!NOTE]
>如果電子郵件傳送的輸入轉變為空，依預設會新增前一個轉變的區段代碼。

您首先需要建立具有不同目標母體的工作流程。 在此，我們想要傳送根據對象年齡而個人化的電子郵件：一個為20至30歲的設定檔傳送，另一個為30至40歲的設定檔傳送。

1. 建立工作流程。 有關如何建立工作流的詳細資訊，請參閱此[page](../../automating/using/building-a-workflow.md)。

1. 將&#x200B;**[!UICONTROL Query]**&#x200B;活動從浮動視窗拖曳並拖曳至工作區，即可新增該活動。

1. 將20到40歲的設定檔定位，以後再將其細分為目標更明確的人口。

   ![](assets/report_segment_1.png)

1. 新增&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動，將查詢結果分割為兩個目標母體。 如需分段的詳細資訊，請參閱此[page](../../automating/using/segmentation.md)。

1. 連按兩下&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動以進行設定。 按一下&#x200B;**[!UICONTROL Edit properties]**&#x200B;編輯第一個區段。

   ![](assets/report_segment_7.png)

1. 在20到30歲之間查詢設定檔，然後在完成時按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/report_segment_8.png)

1. 按一下&#x200B;**[!UICONTROL Add an element]**&#x200B;以建立您的第二個區段，並依照上述步驟所述進行設定，以定位年齡介於30到40歲之間的設定檔。

1. 編輯要透過動態報告傳遞之每個母體的&#x200B;**[!UICONTROL Segment code]**。

   >[!NOTE]
   >此步驟為必要步驟，否則您將無法了解要報告的區段。

   ![](assets/report_segment_9.png)

1. 在您的區段之後拖放&#x200B;**[!UICONTROL Email delivery]**&#x200B;活動。

   ![](assets/report_segment_3.png)

1. 根據不同的目標母體個人化您的傳送。 如需建立電子郵件的詳細資訊，請參閱此[page](../../designing/using/designing-content-in-adobe-campaign.md)。

1. 儲存工作流程。

1. 當工作流準備就緒時，按一下&#x200B;**[!UICONTROL Start]**。

您現在可以存取報表來追蹤區段代碼。

## 步驟3:建立動態報表以篩選區段 {#step-3--create-a-dynamic-report-filter-segments}

在工作流程中傳送傳遞後，您可以使用工作流程中的區段代碼來劃分報表。

1. 從&#x200B;**[!UICONTROL Reports]**&#x200B;標籤中，選取現成報表，或按一下&#x200B;**[!UICONTROL Create new project]**&#x200B;按鈕從頭開始。

   ![](assets/custom_profile_18.png)
1. 將&#x200B;**[!UICONTROL Delivery]**&#x200B;維度拖放至自由表格。

   ![](assets/report_segment_5.png)

1. 將不同的量度拖放至表格，例如&#x200B;**[!UICONTROL Open]**&#x200B;和&#x200B;**[!UICONTROL Click]**&#x200B;量度，以開始篩選資料。
1. 在&#x200B;**[!UICONTROL Dimensions]**&#x200B;類別中，按一下&#x200B;**[!UICONTROL Profile]**&#x200B;維度，然後拖放&#x200B;**[!UICONTROL Segment code]**&#x200B;維度至工作流程的傳送，以根據目標母體測量電子郵件傳送的成功。

   ![](assets/report_segment_6.png)

1. 視需要在工作區中拖放視覺效果。

   ![](assets/report_segment_10.png)
