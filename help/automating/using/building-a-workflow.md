---
solution: Campaign Standard
product: campaign
title: 建立工作流程
description: 本節詳細說明建立新工作流程的主要原則和最佳實務。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,wizard;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 100%

---


# 建立工作流程{#building-a-workflow}

本節詳細說明建立新工作流程的主要原則和最佳實務。

## 工作流程作業原則{#workflow-operating-principles}

工作流是&#x200B;**可設定活動的序列**。每個活動在進程中都具有特定角色。每個活動的結果透過&#x200B;**轉變**（用箭頭表示）轉發到以下活動。

在一個活動和另一個活動之間交換的資料類型可能會影響以下活動的設定方式。例如，如果在電子郵件傳送活動之前建立了人口族群，則可當成相關電子郵件的目標。

您可以在執行工作流之前或之後開啟活動以檢查或編輯參數。

您可以開啟轉變來檢查在執行工作流程期間或之後傳送的資料是否正確。若要存取轉變的詳細檢視，您必須核取工作流程屬性 **[!UICONTROL Execution]** 區段中的 **[!UICONTROL Keep interim results]** 選項。

>[!CAUTION]
>
>此選項佔用了大量磁碟空間，設計旨在幫助您建構工作流程並確保正確的設定和行為。在生產執行個體中保留未核取的狀態。

![](assets/workflow_overview.png)


## 建立工作流程 {#creating-a-workflow}

您可以從方案、行銷活動或行銷活動清單建立工作流程。

建立行銷活動在[建立行銷活動](../../start/using/marketing-activities.md#creating-a-marketing-activity)區段中有詳細說明。

1. 當您開始建立工作流程類型行銷活動後，請選取您要使用的範本。

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >每個行銷活動預設提供數種類型。這些功能可讓您根據需求預先設定特定參數。如需詳細資訊，請參閱[詳細文件](../../start/using/marketing-activity-templates.md)。

1. 輸入工作流的一般屬性。

   ![](assets/workflow_creation_2.png)

   您可以在 **Label** 欄位中輸入名稱，並修改 ID。活動名稱及其ID會顯示在介面中，但訊息收件者無法看到這些名稱。

   >[!NOTE]
   >
   >您可以從行銷活動清單中建立父行銷活動的工作流程。您可以選取已建立的行銷活動，將此工作流程連結至行銷活動。

   您可以新增使用者可在行銷活動內容中看到的說明。

   由於若未以預期方式執行，可讓工作流程更容易找到並疑難排解，Adobe建議您為工作流程指定適當的名稱和標籤：填寫工作流程的說明欄位，彙總要執行的程式，讓運算子輕鬆瞭解。

1. 確認建立活動，然後會顯示該活動的控制面板。有關詳細資訊，請參閱[工作流程介面](../../automating/using/workflow-interface.md)區段。

1. 一旦工作流準備好進行設定後，您可以按一下 **[!UICONTROL Edit properties]** 按鈕來存取其他選項。例如，您可以定義特定時區，以便在工作流的所有活動中預設使用。依預設，工作流程的時區是為目前的促銷活動運算子定義的時區。

   ![](assets/workflow_properties.png)

**相關主題：**

* [建立工作流程](https://docs.adobe.com/content/help/zh-Hant/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.translate.html) 影片
* [工作流程屬性](../../automating/using/managing-execution-options.md)

## 新增和連結活動 {#adding-and-linking-activities}

您現在必須定義各種活動，並將它們在圖表中連結在一起。

>[!NOTE]
>
>如果浮動視窗未顯示，請按一下工具列的第一個按鈕以顯示它。

活動會依浮動視窗不同區段中的類別分組。

* 第一節包含定位[活動](../../automating/using/about-targeting-activities.md)
* 第二節包括執行[活動](../../automating/using/about-execution-activities.md)，主要用於協調其他活動。
* 第三個區段包含可用於在不同[通道](../../automating/using/about-channel-activities.md)傳送訊息的活動。本區段的活動可能會因您實例上啟用的通道而異。
* 第四個區段包含[檔案操縱和資料管理活動](../../automating/using/about-data-management-activities.md)。

要建立圖表：

1. 從浮動視窗拖曳活動並將之拖曳至圖中，以新增活動。

   例如，在圖表中新增&#x200B;**[開始](../../automating/using/start-and-end.md)**&#x200B;活動，之後新增&#x200B;**[電子郵件傳送](../../automating/using/email-delivery.md)**&#x200B;活動。

1. 將&#x200B;**開始**&#x200B;活動轉變拖曳至&#x200B;**電子郵件傳送**&#x200B;活動，將活動連結在一起。

   >[!NOTE]
   >
   >您可以將新活動放置在上一個活動的轉變結束時，自動將活動連結至上一個活動。

1. 新增您需要的活動，並將它們連結在一起，以完成您的工作流程。

   >[!NOTE]
   >
   >您也可以複製並貼上現有活動，以複製現有活動。如此，您就可保留原本定義的設定。有關詳細資訊，請參閱[重複工作流程活動](../../automating/using/workflow-interface.md#duplicating-workflow-activities)。

將工作流程活動連結在一起後，您就可以使用所選取的&#x200B;**標籤**，個人化它們之間的轉變。若要這麼做，請連按兩下轉變以存取其屬性。

此外， **[!UICONTROL Targeting]** 活動 **[!UICONTROL Data management (ETL)]** 可讓您定義其 **對外轉變的區** 段代碼。然後，您可以根據這些區段代碼建立報表，以評估行銷行銷活動的效率。如需詳細資訊，請參閱[本區段](../../reporting/using/creating-a-report-workflow-segment.md)。

**工作流程使用案例：**

* [使用案例：建立每週一次的電子郵件傳送](../../automating/using/workflow-weekly-offer.md)
* [使用案例：建立依位置分段的傳送](../../automating/using/workflow-segmentation-location.md)
* [使用案例：建立具備輔助功能的傳送](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重新定位傳送新傳送給非開啟者的工作流程](../../automating/using/workflow-cross-channel-retargeting.md)

## 設定活動 {#configuring-activities}

預設不會設定活動，如果未設定，則無法正確處理資料。每個活動包含幾個頁籤，用於管理特定設定和活動通用選項，如出站轉變、標籤等。

1. 請確定所有活動皆已正確連線。某些活動需要檢測傳入資料的結構或性質，以提供正確的設定選項。
1. 連按兩下某個活動或選取該活動，然後按一下 **[!UICONTROL Edit]** 內容相關動作以開啟其設定視窗。
1. 編輯活動的標籤。
1. 定義處理資料所需的所有不同選項。請參閱本檔案中活動的特定區段，瞭解每個活動的可能選項。
1. 保存活動，然後對工作流的每個活動重複這些操作。
1. 儲存工作流程。
