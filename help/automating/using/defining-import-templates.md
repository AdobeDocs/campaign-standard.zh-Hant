---
title: 定義匯入範本
seo-title: 定義匯入範本
description: 定義匯入範本
seo-description: 匯入範本可減少需要的設定，以及更快速匯入資料。
page-status-flag: 從未啓動
uuid: 651eb57c-adac-4e3 e-b454-b39 aea1 f0484
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 匯入-匯出資料
discoiquuid: 85d13147-fb31-446a-8476-f112 c841 fb82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Defining import templates{#defining-import-templates}

匯入範本可讓管理員預先定義一定數目的技術匯入設定。然後可以將這些範本提供給標準使用者執行並上傳檔案。

An import template is defined by the functional administrator and can be managed under the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Import templates]** menu.

![](assets/import_template_list.png)

有三個預設的唯讀範本可供使用：

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**：此範本可做為新匯入的基礎，用來更新直效郵件的四分位數和傳送記錄檔。範本的工作流程包含下列活動：
* **[!UICONTROL Import data]**：此範本可做為新匯入的基礎，將資料從檔案插入資料庫中。此範本的工作流程包含下列活動：

   * **[!UICONTROL Load file]**：此活動可讓您上傳Adobe Campaign伺服器上的檔案。
   * **[!UICONTROL Update data]**：此活動可讓您從資料庫中的檔案插入資料。

* **[!UICONTROL Import list]**：此範本可做為新匯入的基礎，以便從檔案中的資料建立 **清單** 類型觀眾。此範本的工作流程包含下列活動：

   * **[!UICONTROL Load file]**：此活動可讓您上傳Adobe Campaign伺服器上的檔案。
   * **[!UICONTROL Reconciliation]**：此活動可讓您將定位維度連結至匯入的資料。This then allows you to create a **List** type audience. If the targeting dimension of the imported data is not known, the audience is **File** type. See [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**：此活動可讓您儲存以 **清單** 類型對象的形式匯入的資料。已儲存對象的名稱對應至由使用者匯入的檔案名稱，並會新增指定匯入日期和時間的字尾。例如：'profiles_20150406_151448'。

這些預設範本為唯讀，不會顯示給標準使用者。若要建立可供使用者使用的範本，請遵循下列步驟：

1. 複製預設範本。複製的範本包含三個標籤：

   * **[!UICONTROL Properties]**：匯入範本的一般參數。此標籤可讓您啓用範本並上傳範例檔案。
   * **[!UICONTROL Workflow]**：匯入工作流程。此標籤可讓您定義工作流程活動。在簡化的匯入作業期間，無法顯示這些活動。
   * **[!UICONTROL Executed imports]**：使用此範本進行的匯入清單。您可以檢視使用此範本進行的每個匯入的狀態、詳細資料和結果。您可以從此清單直接存取工作流程(以透明方式進行)。

1. From the **[!UICONTROL Properties]** tab, rename the template and add a description. 當範本可用時，使用者就可以檢視說明。

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. 您可以在這裡豐富預設的工作流程，根據您的需求新增活動。

   For more on how to configure the workflow activities, refer to the use case describe in this section: [Example: Import workflow template](../../automating/using/importing-data.md#example--import-workflow-template). 此使用案例可協助您設定工作流程，以便重新使用Adobe Campaign資料庫中CRM中的描述檔。

1. 儲存範本，以便正確考量工作流程的設定。
1. Upload a sample file from the **[!UICONTROL Properties]** tab. 上傳的檔案只能有日後匯入或範例資料所需的欄。範例檔案中的資料可讓您在定義工作流程後測試簡化的匯入。

   ![](assets/import_template_sample.png)

   然後，此範例檔案將供使用者使用範本進行匯入。他們將可下載至電腦，例如將它填入資料以匯入。新增範例檔案時請務必考慮這一點。

1. 儲存範本。現在會考量範例檔。At any moment you can download it to your computer to check the content, or modify it by checking the **[!UICONTROL Drop a new sample file]** option.

   ![](assets/simplified_import_model2.png)

1. Go back to the **[!UICONTROL Workflow]** tab and open the **[!UICONTROL Load file]** activity to check and adjust the column configuration of the sample file that was uploaded at the previous step.
1. 啓動工作流程以測試匯入。The sample file uploaded at step **5** has to contain data.

   然後，樣本檔案的資料就會如實匯入。請確定使用的資料是小型且虛構的，以確保您的資料庫不受影響。

1. 前往工作流程執行記錄，在動作列中可用。如果遇到錯誤，請檢查活動是否正確設定。

   ![](assets/simplified_import_model3.png)

1. **[!UICONTROL Properties]** 在標籤中，將其 **[!UICONTROL Import template status]** 設定為 **[!UICONTROL Available]**，然後儲存範本。To stop using this template, you can set the **[!UICONTROL Import template status]** to **[!UICONTROL Archived]**.

The template workflow can be modified by re-uploading the sample file and checking the **[!UICONTROL Load file]** configuration.

現在可供使用者使用匯入範本，並可用來上傳檔案。

**相關主題：**

* [工作流程](../../automating/using/discovering-workflows.md)
* [匯入資料](../../automating/using/importing-data.md)
* [範例：匯入工作流程範本](../../automating/using/importing-data.md#example--import-workflow-template)

