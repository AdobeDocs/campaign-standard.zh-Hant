---
title: 關於資料匯入和匯出
description: 瞭解使用Adobe Campaign匯入和匯出資料的各種方式。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 12%

---

# 關於資料匯入和匯出{#about-data-import-and-export}

根據您的業務需求，您有數種方式可使用Adobe Campaign匯入和匯出資料：

* **套件**：套件是XML檔案，可讓您從Adobe Campaign執行個體匯出及匯入組態和資料集至另一個執行個體。 系統更新也會透過套件匯入來執行。
* **清單**：可以設定所有清單畫面，並將顯示的資料匯出到個別檔案中。
* **工作流程**：從檔案匯入資料，並使用它來更新資料庫或傳送電子郵件。 您也可以選取要匯出到檔案中的資料。 工作流程是自動進行定期更新的最佳方式，例如設定檔匯入。

   * **[!UICONTROL Load file]** 活動可讓您匯入單一結構化格式的資料，以便在 Adobe Campaign 中使用此資料。資料會暫時匯入，而另一個活動必須將它完全整合在Adobe Campaign資料庫中。 有關如何使用此活動的詳細資訊，請參閱[本節](../../automating/using/load-file.md)。
   * **[!UICONTROL Transfer file]**&#x200B;活動可讓您接收或傳送檔案、測試是否有檔案存在，或列出Adobe Campaign中的檔案。 如果您需要從外部來源擷取檔案，可在&#x200B;**[!UICONTROL Load file]**&#x200B;之前使用此活動。 有關如何使用此活動的詳細資訊，請參閱[本節](../../automating/using/transfer-file.md)。

在設計匯入流程時，最佳實務是使用您可以根據需求調整的工作流程範本。 有關如何設定工作流程範本以匯入資料的詳細資訊，請參閱[此使用案例](../../automating/using/creating-import-workflow-templates.md)。

Adobe Campaign也提供簡單的方式來執行一般匯入，包括設計&#x200B;**匯入範本**。 匯入範本是專用工作流程範本，可透過專用畫面使用。 設計完成後，執行匯入的使用者只需上傳檔案，即可在簡化的檢視中匯入。

**相關主題**：

* [使用匯入範本匯入資料](../../automating/using/importing-data-with-import-templates.md)
* [定義匯入範本](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [管理套件](../../automating/using/managing-packages.md)
