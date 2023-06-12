---
title: 根據自動檔案下載更新資料
description: 以下範例顯示透過傳輸檔案活動自動下載的載入檔案活動的結果，之後會進行更新資料活動。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2b21cf45-1c40-4e0e-ae2c-28c9f73e1964
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 79%

---

# 根據自動檔案下載更新資料 {#updating-data-automatic-file-download}

載入檔案活動主要從傳輸檔案活動中建構資料，以便將其整合到現有資料中。

以下範例顯示透過傳輸檔案活動自動下載的載入檔案活動的結果，之後會進行更新資料活動。此工作流程旨在以新的設定檔擴充 Adobe Campaign 資料庫，或使用從匯入檔案中復原的資料更新現有的設定檔。

![](assets/load_file_workflow_ex1.png)

若要建立工作流程，請遵循下列步驟：

1. 將[傳輸檔案](../../automating/using/transfer-file.md)活動拖放至您的工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 以某種方式設定活動，以便它可以復原您想要的檔案。 在 **[!UICONTROL Protocol]** 索引標籤中，選取 **SFTP**。
1. 選取 **Use connection parameters defined in an external account** 選項。
1. 輸入外部帳戶的名稱。
1. 輸入&#x200B;**遠端伺服器上的檔案路徑**。

   ![](assets/wkf_file_transfer_07.png)

1. 確認您的活動。
1. 拖放 [載入檔案](../../automating/using/load-file.md) 活動放入您的工作流程中，並將其放在 **[!UICONTROL Transfer file]** 活動。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 在 **[!UICONTROL Execution]** 索引標籤的 **[!UICONTROL File to load]** 區段中，核取 **[!UICONTROL Use the file specified in the inbound transition]** 選項。

   ![](assets/wkf_file_loading8.png)

1. 依照先前指定的內容來設定您的活動。
1. 拖放 [更新資料](../../automating/using/update-data.md) 活動放入您的工作流程中，並將其放在 **[!UICONTROL Load file]** 活動，然後進行設定。

工作流程開始之後，會擷取上傳檔案的資料，然後用於擴充 Adobe Campaign 資料庫。
