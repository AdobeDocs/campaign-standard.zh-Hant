---
solution: Campaign Standard
product: campaign
title: 根據工作流程細分建立報告
description: 瞭解如何根據報表中工作流程的區段來檢查傳送是否成功。
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 2%

---


# 根據工作流程細分建立報告{#creating-a-report-workflow-segment}

在建立工作流程並將人口篩選到不同的目標對象後，您可以根據此目標工作流程中定義的區段來評估行銷宣傳的效率。
若要定位報表中的這些區段：

* [步驟1:使用區段更新描述檔自訂資源](#step-1--update-profiles-custom-resource-segments)
* [步驟2:建立含區段的工作流程](#step-2--create-a-workflow-segments)
* [步驟3:建立動態報表以篩選區段](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>必須接受動態報告使用協定，才能開始收集這些資料。
>如需本合約的詳細資訊，請參閱此[頁面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 步驟1:使用區段{#step-1--update-profiles-custom-resource-segments}更新描述檔自訂資源

在報告區段代碼之前，您必須更新&#x200B;**[!UICONTROL Profiles]**&#x200B;自訂資源，以儲存區段代碼。

1. 從進階功能表，透過Adobe Campaign標誌，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**，然後選取&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;資源。
1. 在&#x200B;**[!UICONTROL Data structure]**&#x200B;標籤的&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;功能表中，勾選&#x200B;**[!UICONTROL Add segment code]**&#x200B;以允許從定位工作流程儲存區段代碼，並將它傳送至動態報表。

   然後，**[!UICONTROL Segment code]**&#x200B;將可在報表的&#x200B;**[!UICONTROL Profile]**&#x200B;維度區段中使用。

   ![](assets/report_segment_4.png)

1. 儲存自訂資源。

1. 您現在需要發佈自訂資源。
從高級菜單中，選擇**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**。

   ![](assets/custom_profile_7.png)

1. 按一下&#x200B;**[!UICONTROL Prepare publication]** ，然後在準備完成時按一下&#x200B;**[!UICONTROL Publish]**&#x200B;按鈕。 有關自定義資源的詳細資訊，請參閱此[頁](../../developing/using/updating-the-database-structure.md)。

您現在可以開始使用區段代碼建立工作流程。

請注意，當您在&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;中啟用區段代碼時，系統會立即收集區段代碼。

## 步驟2:建立具有區段{#step-2--create-a-workflow-segments}的工作流程

>[!NOTE]
>如果電子郵件傳送的輸入轉場是空的，則預設會新增先前轉場的區段代碼。

您首先需要建立具有不同目標群體的工作流程。 在此，我們想要傳送會根據受眾年齡而個人化的電子郵件：一個是20到30歲的個人檔案，另一個是30到40歲的個人檔案。

1. 建立您的工作流程。 有關如何建立工作流的詳細資訊，請參閱此[頁](../../automating/using/building-a-workflow.md)。

1. 將&#x200B;**[!UICONTROL Query]**&#x200B;活動從浮動視窗拖曳並拖曳至工作區，以新增該活動。

1. 將20到40歲的個人檔案分成目標群體，以後再將其分成目標群體。

   ![](assets/report_segment_1.png)

1. 新增&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動，將查詢結果分割為兩個目標人口族群。 如需細分的詳細資訊，請參閱此[頁面](../../automating/using/segmentation.md)。

1. 連按兩下&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動以進行設定。 按一下&#x200B;**[!UICONTROL Edit properties]**&#x200B;以編輯第一個區段。

   ![](assets/report_segment_7.png)

1. 在20到30歲之間查詢描述檔，然後完成時按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/report_segment_8.png)

1. 按一下&#x200B;**[!UICONTROL Add an element]**&#x200B;以建立第二個區段，並依上述步驟進行設定，以定位30到40歲之間的描述檔。

1. 編輯每個人口的&#x200B;**[!UICONTROL Segment code]**，以便透過動態報表傳遞。

   >[!NOTE]
   >此步驟為必要步驟，否則您將無法瞭解要報告的區段。

   ![](assets/report_segment_9.png)

1. 將&#x200B;**[!UICONTROL Email delivery]**&#x200B;活動拖放在區段後面。

   ![](assets/report_segment_3.png)

1. 根據不同的目標人口，個人化您的遞送。 如需建立電子郵件的詳細資訊，請參閱此[頁面](../../designing/using/designing-content-in-adobe-campaign.md)。

1. 儲存工作流程。

1. 當您的工作流程準備就緒時，按一下&#x200B;**[!UICONTROL Start]**。

您現在可以存取報表來追蹤區段代碼。

## 步驟3:建立動態報表以篩選區段{#step-3--create-a-dynamic-report-filter-segments}

在傳送傳送至您的工作流程後，您可以使用工作流程中的區段代碼來劃分報表。

1. 從&#x200B;**[!UICONTROL Reports]**&#x200B;標籤中，選擇現成可用的報表，或按一下&#x200B;**[!UICONTROL Create new project]**&#x200B;按鈕從頭開始。

   ![](assets/custom_profile_18.png)
1. 將&#x200B;**[!UICONTROL Delivery]**&#x200B;維度拖放至自由表格。

   ![](assets/report_segment_5.png)

1. 將不同的量度拖放至表格，例如&#x200B;**[!UICONTROL Open]**&#x200B;和&#x200B;**[!UICONTROL Click]**&#x200B;量度，以開始篩選資料。
1. 在&#x200B;**[!UICONTROL Dimensions]**&#x200B;類別中，按一下&#x200B;**[!UICONTROL Profile]**&#x200B;維度，然後拖放工作流程傳送上的&#x200B;**[!UICONTROL Segment code]**&#x200B;維度，以根據目標人口族群來評估電子郵件傳送的成功。

   ![](assets/report_segment_6.png)

1. 視需要將視覺化拖放至您的工作區。

   ![](assets/report_segment_10.png)
