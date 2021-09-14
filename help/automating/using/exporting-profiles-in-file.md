---
title: 在外部檔案中匯出設定檔
description: 此使用案例顯示如何以外部檔案的形式匯出設定檔清單，以便在Adobe Campaign外部使用資料。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 68%

---

# 在外部檔案中匯出設定檔 {#exporting-profiles-external-file}

以下範例說明如何在活動 **[!UICONTROL Extract file]** 之後設定 **[!UICONTROL Query]** 活動。

此工作流程的目的是以外部檔案格式匯出設定檔清單，以便在 Adobe Campaign 外部使用資料。

1. 將[擷取檔案](../../automating/using/extract-file.md)活動拖放至工作流程中，並將其置於[Query](../../automating/using/query.md)活動之後。

   在此範例中，會對年齡介於 18 至 30 歲的所有設定檔執行查詢。

1. 開啟&#x200B;**[!UICONTROL Extract file]**&#x200B;活動以進行編輯。
1. 為輸出檔案命名。
1. 新增輸出欄。

   在此範例中，會新增設定檔的電子郵件、年齡、出生日期、名字和姓氏作為輸出欄。

   ![](assets/wkf_data_export6.png)

1. 按一下 **[!UICONTROL File structure]** 索引標籤以定義：

   * CSV 輸出格式

      ![](assets/wkf_data_export7.png)

   * 日期格式

      ![](assets/wkf_data_export9.png)

1. 確認您的活動。
1. 在&#x200B;**[!UICONTROL Extract file]**&#x200B;活動之後拖放[傳輸檔案](../../automating/using/transfer-file.md)活動，以復原外部帳戶上的擷取檔案。
1. 開啟活動並選取 **[!UICONTROL File upload]** 動作。

   ![](assets/wkf_data_export11.png)

1. 選取外部帳戶，然後輸入伺服器上資料夾的路徑。

   ![](assets/wkf_data_export12.png)

1. 確認您的活動並儲存您的工作流程。
1. 啟動工作流程。

   當工作流程已正確執行時，擷取的檔案便可在外部帳戶上使用。
