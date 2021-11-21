---
title: 關於資料匯入和匯出
description: 了解使用Adobe Campaign匯入和匯出資料的不同方式。
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

根據您的業務需求，您有數種方式可透過Adobe Campaign匯入和匯出資料：

* **套件**:套件是XML檔案，可讓您從Adobe Campaign執行個體將設定和資料集匯出和匯入至另一個執行個體。 系統更新也通過包導入執行。
* **清單**:所有清單畫面皆可設定，且顯示的資料可匯出為個別檔案。
* **工作流程**:從檔案匯入資料，並使用它更新資料庫或傳送電子郵件。 您也可以選取要在檔案中匯出的資料。 工作流程是自動執行定期更新（例如設定檔匯入）的最佳方式。

   * **[!UICONTROL Load file]** 活動可讓您匯入單一結構化格式的資料，以便在 Adobe Campaign 中使用此資料。會暫時匯入資料，而另一個活動必須將它完全整合在 Adobe Campaign 資料庫中。有關如何使用此活動的詳細資訊，請參閱 [本節](../../automating/using/load-file.md).
   * **[!UICONTROL Transfer file]** 活動可讓您接收或傳送檔案、測試 Adobe Campaign 中是否有檔案或列出檔案。您可以在 **[!UICONTROL Load file]** 以備您需要從外部來源擷取檔案時使用。 有關如何使用此活動的詳細資訊，請參閱 [本節](../../automating/using/transfer-file.md).

在設計匯入程式時，最佳實務是使用工作流程範本，以便根據您的需求進行調整。 有關如何設定工作流模板以導入資料的詳細資訊，請參閱 [此使用案例](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign也提供簡化的方式來執行一般匯入，包括設計 **匯入範本**. 匯入範本是專用的工作流程範本，可透過專用畫面使用。 設計後，執行匯入的使用者只需上傳檔案，即可以簡化檢視匯入。

**相關主題**：

* [使用匯入範本匯入資料](../../automating/using/importing-data-with-import-templates.md)
* [定義匯入範本](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [管理套件](../../automating/using/managing-packages.md)
