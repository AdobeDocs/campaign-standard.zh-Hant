---
title: 在外部檔案中導出配置檔案
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---


# 在外部檔案中導出配置檔案 {#exporting-profiles-external-file}

以下示例說明如何在活動後 **[!UICONTROL Extract file]** 配置活 **[!UICONTROL Query]** 動。

此工作流程的目的是匯出外部檔案格式的描述檔清單，以便在Adobe Campaign外使用資料。

1. 將「擷取檔案 [」活動拖放至](../../automating/using/extract-file.md) 「工作流程」中，並將其置於「查詢」 [活動之後](../../automating/using/query.md) 。

   在此範例中，查詢是對18到30歲的所有描述檔執行。

1. 開啟活 **[!UICONTROL Extract file]** 動以進行編輯。
1. 命名輸出檔案。
1. 新增輸出欄。

   在此範例中，會新增描述檔的電子郵件、年齡、出生日期、名字和姓氏作為輸出欄。

   ![](assets/wkf_data_export6.png)

1. 按一下標 **[!UICONTROL File structure]** 簽以定義：

   * CSV輸出格式

      ![](assets/wkf_data_export7.png)

   * 日期格式

      ![](assets/wkf_data_export9.png)

1. 確認您的活動。
1. 在活動後拖 [放Transfer檔案](../../automating/using/transfer-file.md) ，以恢 **[!UICONTROL Extract file]** 復外部帳戶上的提取檔案。
1. 開啟活動並選擇 **[!UICONTROL File upload]** 動作。

   ![](assets/wkf_data_export11.png)

1. 選擇外部帳戶，然後輸入伺服器上資料夾的路徑。

   ![](assets/wkf_data_export12.png)

1. 確認您的活動並儲存您的工作流程。
1. 啟動工作流程。

   當工作流程已正確執行時，擷取的檔案便可在外部帳戶上使用。
