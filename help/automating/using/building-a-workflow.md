---
title: 建立工作流程
seo-title: 建立工作流程
description: 建立工作流程
seo-description: 本節詳細說明建立新工作流程的主要原則和最佳做法。
page-status-flag: 從未啓動
uuid: 11374f64-40da-937b-937b-09f419250f4c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 工作流程一般運作
discoiquuid: c26fcp0e-19d5-4bd5-b7 d6-2d22 ce92 ad90
context-tags: workflow，wizard；工作流程，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# 建立工作流程{#building-a-workflow}

本節詳細說明建立新工作流程的主要原則和最佳做法：

* 建立工作流程。
* 新增和連結活動。
* 設定活動。

## 建立工作流程 {#creating-a-workflow}

您可以從程式、促銷活動或行銷活動清單建立工作流程。

建立行銷活動會詳細說明 [「建立行銷活動](../../start/using/marketing-activities.md#creating-a-marketing-activity) 」區段。

1. 開始建立工作流程類型行銷活動後，選取您要使用的範本。

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >每個行銷活動依預設提供數種類型。這些可讓您根據需求預先設定某些參數。如需詳細資訊，請參閱 [「管理範本](../../start/using/about-templates.md) 」區段。

1. 輸入工作流程的一般屬性。

   ![](assets/workflow_creation_2.png)

   您可以在「Label」( **標籤)** 欄位中輸入名稱，然後修改ID。活動名稱及其ID會出現在介面中，但訊息收件者看不到這些項目。

   >[!NOTE]
   >
   >您可以從行銷活動清單中建立父促銷活動的工作流程。您可以選取已建立的促銷活動，將此工作流程連結至促銷活動。

   您可以新增使用者在促銷活動內容中看到的說明。

   由於它可讓他們更容易找到並疑難排解無法依預期方式執行的工作，Adobe建議您提供適當的名稱和標籤：填寫工作流程的說明欄位，以摘要執行的程序，讓操作員輕鬆瞭解此程序。

1. 確認建立活動，然後顯示該活動的控制面板。如需詳細資訊，請參閱 [「工作流程」介面](../../automating/using/workflow-interface.md) 區段。

**相關主題：**

[建立工作流程](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-workflow-feature-video-use.html) 影片

## 新增和連結活動 {#adding-and-linking-activities}

您現在必須定義各種活動，並將它們連結在圖表中。

>[!NOTE]
>
>如果未顯示浮動視窗，請按一下工具列的第一個按鈕以顯示它。

活動會依照浮動視窗不同區段內的類別分組。

* 第一節包含定位活動。
* 第二節包含執行活動，主要用於協調其他活動。
* 第三個區段包含可用來在不同頻道傳送訊息的活動。本節中的活動可能視您執行個體啓用的頻道而有所不同。
* 第四節包含檔案控制和資料管理活動。

若要建立圖表：

1. 將活動從浮動視窗拖曳至圖表中，以新增活動。

   例如，新增 **「開始** 」活動，然後在圖表上新增 **電子郵件傳送** 活動。

1. 拖曳 **「開始** 」活動轉換並將其拖放 **至電子郵件傳送** 活動，將活動連結在一起。

   >[!NOTE]
   >
   >您可以在舊版活動結束時放置新活動，將活動自動連結至前一個活動。

1. 新增您需要的活動，並將它們連結在一起以完成工作流程。

   >[!NOTE]
   >
   >您也可以複製現有活動，複製現有活動。如此，您就可以保留原本定義的設定。如需詳細資訊，請參閱 [複製工作流程活動](../../automating/using/workflow-interface.md#duplicating-workflow-activities)。

在連結您的工作流程活動後，您可以使用您選擇的 **標籤** 個人化它們之間的轉場效果。若要這麼做，請按兩下轉場以存取其屬性。

此外 **[!UICONTROL Targeting]****[!UICONTROL Data management (ETL)]** ，活動也可讓您為其傳出轉場定義 **區段代碼** 。然後您可以根據這些區段代碼建立報表，以測量行銷活動的效率。For more on this, refer to [this section](../../reporting/using/creating-a-report-workflow-segment.md).

**工作流程使用案例：**

* [使用案例：建立一次一次的電子郵件傳送](../../automating/using/workflow-weekly-offer.md)
* [使用案例：建立在位置上分段的傳送](../../automating/using/workflow-segmentation-location.md)
* [使用案例：建立具有輔助功能的傳送](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重新定位工作流程，將新傳送傳送至非opervers](../../automating/using/workflow-cross-channel-retargeting.md)

## 設定活動 {#configuring-activities}

依預設，未設定活動，且如果未設定資料，則不會正確處理資料。每個活動包含數個標籤，可管理特定組態和活動一般選項，例如傳出轉場、標籤等。

1. 確定所有活動都已正確連線。有些活動需要偵測傳入資料的結構或性質，以提供正確的配置選項。
1. 按兩下活動或選取該活動，然後按一下 **[!UICONTROL Edit]** 內容相關動作，開啓其設定視窗。
1. 編輯活動的標籤。
1. 定義處理資料所需的所有不同選項。請參閱本文件中的活動特定章節，以瞭解每個活動的可能選項。
1. 儲存活動並針對工作流程的每個活動重復這些作業。
1. 儲存工作流程。
