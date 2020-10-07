---
title: 根據自動檔案下載更新資料
description: '以下範例顯示透過傳輸檔案活動自動下載的載入檔案活動的結果，之後會進行更新資料活動。 '
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 根據自動檔案下載更新資料 {#updating-data-automatic-file-download}

載入檔案活動主要從傳輸檔案活動中建構資料，以便將其整合到現有資料中。

以下範例顯示透過傳輸檔案活動自動下載的載入檔案活動的結果，之後會進行更新資料活動。此工作流程旨在以新的設定檔擴充 Adobe Campaign 資料庫，或使用從匯入檔案中復原的資料更新現有的設定檔。

![](assets/load_file_workflow_ex1.png)

若要建立工作流程，請依照下列步驟進行：

1. 將[傳輸檔案](../../automating/using/transfer-file.md)活動拖放至您的工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 以某種方式配置活動，以便恢復您要的檔案。 在 **[!UICONTROL Protocol]** 索引標籤中，選取 **SFTP**。
1. 選取 **Use connection parameters defined in an external account** 選項。
1. 輸入外部帳戶的名稱。
1. 輸入&#x200B;**遠端伺服器上的檔案路徑**。

   ![](assets/wkf_file_transfer_07.png)

1. 確認您的活動。
1. Drag and drop a [Load file](../../automating/using/load-file.md) activity into your workflow and place it after the **[!UICONTROL Transfer file]** activity.
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 在 **[!UICONTROL Execution]** 索引標籤的 **[!UICONTROL File to load]** 區段中，核取 **[!UICONTROL Use the file specified in the inbound transition]** 選項。

   ![](assets/wkf_file_loading8.png)

1. 依照先前指定的內容來設定您的活動。
1. Drag and drop an [Update data](../../automating/using/update-data.md) activity into your workflow and place it after the **[!UICONTROL Load file]** activity, then configure it.

工作流程開始之後，會擷取上傳檔案的資料，然後用於擴充 Adobe Campaign 資料庫。
