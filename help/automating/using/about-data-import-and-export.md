---
title: 關於資料匯入和匯出
description: 瞭解與Adobe Campaign進行資料導入和導出的不同方法。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 24%

---

# 關於資料匯入和匯出{#about-data-import-and-export}

根據您的業務需要，您有多種方法可以與Adobe Campaign進行資料導入和導出：

* **包**:包是XML檔案，允許您將配置和資料集從Adobe Campaign實例導出並導入到另一個實例。 系統更新也通過包導入執行。
* **清單**:可以配置所有清單螢幕，並將顯示的資料導出到單獨的檔案中。
* **工作流**:從檔案導入資料，然後使用它更新資料庫或發送電子郵件。 也可以選擇要在檔案中導出的資料。 工作流是自動執行常規更新（如配置檔案導入）的最佳方法。

   * **[!UICONTROL Load file]** 活動可讓您匯入單一結構化格式的資料，以便在 Adobe Campaign 中使用此資料。會暫時匯入資料，而另一個活動必須將它完全整合在 Adobe Campaign 資料庫中。有關如何使用此活動的詳細資訊，請參閱 [此部分](../../automating/using/load-file.md)。
   * **[!UICONTROL Transfer file]** 活動可讓您接收或傳送檔案、測試 Adobe Campaign 中是否有檔案或列出檔案。您可以在 **[!UICONTROL Load file]** 以防您需要從外部源檢索檔案。 有關如何使用此活動的詳細資訊，請參閱 [此部分](../../automating/using/transfer-file.md)。

在設計導入流程時，最好使用可以根據需要調整的工作流模板。 有關如何設定工作流模板以導入資料的詳細資訊，請參閱 [此使用案例](../../automating/using/creating-import-workflow-templates.md)。

Adobe Campaign還提供了簡化的常規進口方法，包括設計 **導入模板**。 導入模板是通過專用螢幕提供的專用工作流模板。 一旦設計好，執行導入的用戶只需上載要在簡化視圖中導入的檔案。

**相關主題**：

* [使用匯入範本匯入資料](../../automating/using/importing-data-with-import-templates.md)
* [定義匯入範本](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [管理套件](../../automating/using/managing-packages.md)
