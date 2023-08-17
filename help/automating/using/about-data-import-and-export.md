---
title: 關於資料匯入和匯出
description: 瞭解使用Adobe Campaign匯入和匯出資料的各種方式。
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

根據您的業務需求，您有數種方式可使用Adobe Campaign匯入和匯出資料：

* **封裝**：套件是XML檔案，可讓您將設定和資料集從Adobe Campaign執行個體匯出並匯入至另一個執行個體。 系統更新也會透過套件匯入來執行。
* **清單**：所有清單畫面都可以設定，且顯示的資料會匯出至個別檔案。
* **工作流程**：從檔案匯入資料，並用來更新資料庫或傳送電子郵件。 您也可以選取要匯出到檔案中的資料。 工作流程是自動進行定期更新的最佳方式，例如設定檔匯入。

   * **[!UICONTROL Load file]** 活動可讓您匯入單一結構化格式的資料，以便在 Adobe Campaign 中使用此資料。會暫時匯入資料，而另一個活動必須將它完全整合在 Adobe Campaign 資料庫中。有關如何使用此活動的詳細資訊，請參閱 [本節](../../automating/using/load-file.md).
   * **[!UICONTROL Transfer file]** 活動可讓您接收或傳送檔案、測試 Adobe Campaign 中是否有檔案或列出檔案。您可在「 」之前使用此活動 **[!UICONTROL Load file]** 以備您需要從外部來源擷取檔案時使用。 有關如何使用此活動的詳細資訊，請參閱 [本節](../../automating/using/transfer-file.md).

在設計匯入流程時，最佳實務是使用您可以根據需求調整的工作流程範本。 有關如何設定工作流程範本以匯入資料的詳細資訊，請參閱 [此使用案例](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign也提供簡單的方式來執行定期匯入，包括設計 **匯入範本**. 匯入範本是專用工作流程範本，可透過專用畫面使用。 設計完成後，執行匯入的使用者只需上傳檔案，即可在簡化的檢視中匯入。

**相關主題**：

* [使用匯入範本匯入資料](../../automating/using/importing-data-with-import-templates.md)
* [定義匯入範本](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [管理套件](../../automating/using/managing-packages.md)
