---
title: 在外部檔案中匯出設定檔
description: 此使用案例說明如何匯出外部檔案格式的描述檔清單，以便在Adobe Campaign外部使用資料。
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 在外部檔案中匯出設定檔 {#exporting-profiles-external-file}

以下範例說明如何在活動 **[!UICONTROL Extract file]** 之後設定 **[!UICONTROL Query]** 活動。

此工作流程的目的是以外部檔案格式匯出設定檔清單，以便在 Adobe Campaign 外部使用資料。

1. Drag and drop an [Extract file](../../automating/using/extract-file.md) activity into your workflow and place it after the [Query](../../automating/using/query.md) activity.

   在此範例中，會對年齡介於 18 至 30 歲的所有設定檔執行查詢。

1. Open the **[!UICONTROL Extract file]** activity to edit it.
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
1. Drag and drop a [Transfer file](../../automating/using/transfer-file.md) activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. 開啟活動並選取 **[!UICONTROL File upload]** 動作。

   ![](assets/wkf_data_export11.png)

1. 選取外部帳戶，然後輸入伺服器上資料夾的路徑。

   ![](assets/wkf_data_export12.png)

1. 確認您的活動並儲存您的工作流程。
1. 啟動工作流程。

   當工作流程已正確執行時，擷取的檔案便可在外部帳戶上使用。
