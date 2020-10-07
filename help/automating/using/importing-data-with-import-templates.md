---
title: 使用匯入範本匯入資料
description: 瞭解如何收集資料以摘要您的 Campaign 資料庫。
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用匯入範本匯入資料{#importing-data-with-import-templates}

匯入資料可讓您收集資料，以摘要您的 Campaign 資料庫。

或者，使用[工作流程](../../automating/using/get-started-workflows.md)，Adobe Campaign 提供簡化的匯入功能，以便使用者管理管理員定義的特定匯入類型。

其工作原理如下：**管理員**&#x200B;定義，並管理匯入範本（請參閱[定義匯入範本](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)）。這些匯入範本將以簡化視圖提供給使用者，**[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]** 功能表下。

因此，這些使用者只需要選取要執行的匯入類型，並上傳包含要匯入資料的檔案。管理員定義的工作流程將對使用者透明地執行，使用者在匯入完成後可以存取匯入結果的詳細資訊。

>[!NOTE]
>
>具有 **[!UICONTROL GENERIC IMPORT (import)]** 與 **[!UICONTROL WORKFLOW (workflow)]** 角色的使用者可以管理匯入資料函式。有關角色的詳細資訊，請參閱[本區段](../../administration/using/list-of-roles.md)。

可以根據匯入的執行範本、其執行日期與執行狀態來篩選匯入。

1. 在匯入概述中，按一下 **[!UICONTROL Create]** 按鈕。精靈開啟。
1. 選取要執行的匯入類型。匯入類型與可用的匯入範本對應。
1. 如有必要，請將連結至範本的範例檔案下載至您的電腦，以檢視要匯入的檔案中預期的資料類型。
1. 下載包含要在精靈中匯入之資料的檔案。
1. 開始匯入。精靈將關閉，並帶您返回使用範本執行的匯入清單。
1. 重新整理您的頁面，並選取您剛執行的匯入，以檢視執行詳細資料。

   ![](assets/simplified_import1.png)

現在可以取得匯入執行的詳細資訊。已匯入的檔案以及包含已拒絕資料（未匯入的資料）的檔案都可以下載至您的電腦。

## 設定匯入範本 {#setting-up-import-templates}

匯入範本可讓管理員預先定義特定數量的技術匯入設定。之後，這些範本就可以提供給標準使用者執行和上傳檔案。

匯入範本由功能管理員定義，可在 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]** 功能表下管理。

![](assets/import_template_list.png)

有三種預設的唯讀範本可供使用：

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**：此範本可作為新匯入的基礎，以更新直接郵件的隔離和傳送記錄檔。範本的工作流程包含下列活動：
* **[!UICONTROL Import data]**：此範本可作為新匯入的基礎，以便將檔案的資料插入資料庫。此範本的工作流程包含下列活動：

   * **[!UICONTROL Load file]**：此活動可讓您在 Adobe Campaign 伺服器上傳檔案。
   * **[!UICONTROL Update data]**：此活動可讓您從資料庫中插入檔案中的資料。

* **[!UICONTROL Import list]**：此範本可做為新匯入的基礎，以便從檔案中的資料建立&#x200B;**清單**&#x200B;類型的對象。此範本的工作流程包含下列活動：

   * **[!UICONTROL Load file]**：此活動可讓您在 Adobe Campaign 伺服器上傳檔案。
   * **[!UICONTROL Reconciliation]**：此活動可讓您將定位維度連結至匯入的資料。之後，您就可以建立&#x200B;**清單**&#x200B;類型對象。如果匯入資料的目標維度不是已知的，則對象為&#x200B;**檔案**&#x200B;類型。請參閱[定位維度和資源](../../automating/using/query.md#targeting-dimensions-and-resources)。
   * **[!UICONTROL Save audience]**：此活動可讓您以&#x200B;**清單**&#x200B;類型對象的形式儲存匯入的資料。儲存的對象名稱與使用者匯入的檔案名稱相對應，並會新增一個字尾，指定匯入的日期和時間。例如：&#39;profiles_20150406_151448&#39;。

這些預設範本為唯讀範本，標準使用者無法看到內容。若要建立可供使用者使用的範本，請遵循下列步驟執行：

1. 複製預設範本。重複的範本包含三個索引標籤：

   * **[!UICONTROL Properties]**：匯入範本的常規參數。此索引標籤可讓您啟用範本並上傳範例檔案。
   * **[!UICONTROL Workflow]**：匯入工作流程。此索引標籤可讓您定義工作流活動。使用者執行的簡化匯入期間，不會看見這些活動。
   * **[!UICONTROL Executed imports]**：使用此範本執行的匯入清單。您可以檢視使用此範本執行之每個匯入的狀態、詳細資訊和結果。您可以從此清單直接存取工作流程（以對使用者而言透明的方式執行）。

1. 從 **[!UICONTROL Properties]** 索引標籤，重新命名範本並新增說明。當範本可供使用時，使用者將可檢視說明。

   ![](assets/simplified_import_model1.png)

1. 移至 **[!UICONTROL Workflow]** 索引標籤。您可以從此處，根據您的需求新增活動，讓預設提供的工作流程更佳豐富。

   如需如何設定工作流程活動的詳細資訊，請參閱本區段說明的使用案例：[範例：匯入工作流程範本](../../automating/using/creating-import-workflow-templates.md)。此使用案例可協助您設定一個工作流程，此工作流程可重複用於匯入來自 Adobe Campaign 資料庫中 CRM 之設定檔的工作流程。

1. 儲存您的範本，以便正確考慮工作流程的設定。
1. 從 **[!UICONTROL Properties]** 索引標籤上傳範例檔案。上傳的檔案只能有未來匯入或範例資料所需的欄。範例檔案中的資料可讓您在定義工作流程後，測試簡化的匯入。

   ![](assets/import_template_sample.png)

   之後，使用範本進行匯入的使用者將可使用此範例檔案。例如，他們可以將它下載至電腦，以填入要匯入的資料。在新增範例檔案時，請務必考量這一點。

1. 儲存範本。現在會考量範例檔案。您隨時可以將它下載至電腦以檢查內容，或透過 **[!UICONTROL Drop a new sample file]** 選項加以修改。

   ![](assets/simplified_import_model2.png)

1. 返回索引標籤 **[!UICONTROL Workflow]** 並開啟 **[!UICONTROL Load file]** 活動，以檢查並調整在上一步上載的範例檔案的欄設定。
1. 啟動工作流程以測試匯入。在步驟 **5** 上傳的範例檔案，必須包含資料。

   之後，會確實匯入範例檔案中的資料。請確定所使用的資料是小型且虛構的，以確保您的資料庫不會受損。

1. 移至工作流程執行記錄檔，這可在動作列中使用。如果發生錯誤，請檢查活動是否正確設定。

   ![](assets/simplified_import_model3.png)

1. 在 **[!UICONTROL Properties]** 索引標籤中，將 **[!UICONTROL Import template status]** 設定為 **[!UICONTROL Available]**，之後儲存範本。若要停止使用此範本，您可將 **[!UICONTROL Import template status]** 設定為 **[!UICONTROL Archived]**。

可透過重新上傳範例檔案並檢查 **[!UICONTROL Load file]** 設定來修改範本工作流程。

匯入範本現在可供使用者使用，並可用於上傳檔案。

**相關主題：**

* [工作流程](../../automating/using/get-started-workflows.md)
* [範例：匯入工作流程範本](../../automating/using/creating-import-workflow-templates.md)
