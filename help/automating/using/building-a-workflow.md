---
title: 建立工作流程
description: 本節詳細說明建立新工作流程的主要原則和最佳實務。
page-status-flag: never-activated
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: workflow,wizard;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# 建立工作流程{#building-a-workflow}

本節詳細說明建立新工作流程的主要原則和最佳實務：

* 建立工作流程。
* 新增和連結活動。
* 設定活動。

## 建立工作流程 {#creating-a-workflow}

您可以從方案、促銷活動或行銷活動清單建立工作流程。

建立行銷活動在「建立行銷活動」一 [節中有詳細說明](../../start/using/marketing-activities.md#creating-a-marketing-activity) 。

1. 當您開始建立工作流程類型行銷活動後，請選取您要使用的範本。

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >每個行銷活動預設提供數種類型。 這些功能可讓您根據需求預先設定特定參數。 如需詳細資訊，請參閱「管 [理範本](../../start/using/marketing-activity-templates.md) 」一節。

1. 輸入工作流的常規屬性。

   ![](assets/workflow_creation_2.png)

   您可以在「標籤」欄位中輸 **入名稱** ，並修改ID。 活動名稱及其ID會顯示在介面中，但訊息收件者無法看到這些名稱。

   >[!NOTE]
   >
   >您可以從行銷活動清單中建立父促銷活動的工作流程。 您可以選取已建立的促銷活動，將此工作流程連結至促銷活動。

   您可以新增使用者可在促銷活動內容中看到的說明。

   由於若未以預期方式執行，可讓工作流程更容易找到並疑難排解，Adobe建議您為工作流程指定適當的名稱和標籤：填寫工作流程的說明欄位，匯總要執行的程式，讓運算子輕鬆瞭解。

1. 確認建立活動，然後會顯示該活動的控制面板。 有關詳細資訊，請參閱「工作 [流介面](../../automating/using/workflow-interface.md) 」部分。

**相關主題：**

[建立工作流程](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-workflow-feature-video-use.html) 影片

## 新增和連結活動 {#adding-and-linking-activities}

您現在必須定義各種活動，並將它們在圖中連結在一起。

>[!NOTE]
>
>如果浮動視窗未顯示，請按一下工具列的第一個按鈕以顯示它。

活動會依浮動視窗不同區段中的類別分組。

* 第一節包含定位活動。
* 第二節包括執行活動，主要用於協調其他活動。
* 第三節包含可用來在不同頻道傳送訊息的活動。 本節中的活動可能會因您實例上啟用的渠道而異。
* 第四節包含檔案操縱和資料管理活動。

要建立圖：

1. 將活動從浮動視窗拖曳並拖曳至圖中，以新增活動。

   例如，在圖中 **新增** 「開始」活動，然 **後新增「電子郵件傳送** 」活動。

1. 將「開始」活動轉場拖曳至「電子郵 **件傳送** 」活動，將活動連結 **在一起** 。

   >[!NOTE]
   >
   >您可以將新活動放置在上一個活動的轉換結束時，自動將活動連結至上一個活動。

1. 新增您需要的活動，並將它們連結在一起，以完成您的工作流程。

   >[!NOTE]
   >
   >您也可以複製並貼上現有活動，以複製現有活動。 如此，您就可保留原本定義的設定。 有關詳細資訊，請參閱複製 [工作流活動](../../automating/using/workflow-interface.md#duplicating-workflow-activities)。

將工作流程活動連結在一起後，您就可以使用您選擇的標籤，個人化 **它們** 之間的轉場。 若要這麼做，請連按兩下轉場以存取其屬性。

此外， **[!UICONTROL Targeting]**活動**[!UICONTROL Data management (ETL)]** 可讓您定義其 **對外轉場的區** 段代碼。 然後，您可以根據這些區段代碼建立報表，以評估行銷促銷活動的效率。 如需詳細資訊，請參閱[本小節](../../reporting/using/creating-a-report-workflow-segment.md)。

**工作流程使用案例：**

* [使用案例：建立每週一次的電子郵件傳送](../../automating/using/workflow-weekly-offer.md)
* [使用案例：建立依位置分段的傳送](../../automating/using/workflow-segmentation-location.md)
* [使用案例：建立具備輔助功能的傳送](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重新定位傳送新傳送給非開啟者的工作流程](../../automating/using/workflow-cross-channel-retargeting.md)

## 設定活動 {#configuring-activities}

依預設，活動未設定，如果未設定，則無法正確處理資料。 每個活動包含幾個頁籤，用於管理特定配置和活動通用選項，如出站轉場、標籤等。

1. 請確定所有活動皆已正確連線。 某些活動需要檢測傳入資料的結構或性質，以提供正確的配置選項。
1. 連按兩下某個活動或選取該活動，然後按一 **[!UICONTROL Edit]**下內容相關動作以開啟其設定視窗。
1. 編輯活動的標籤。
1. 定義處理資料所需的所有不同選項。 請參閱本檔案中活動的特定章節，瞭解每個活動的可能選項。
1. 保存活動，然後對工作流的每個活動重複這些操作。
1. 儲存工作流程。
