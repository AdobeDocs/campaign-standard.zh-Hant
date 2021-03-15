---
solution: Campaign Standard
product: campaign
title: 關於資料匯入和匯出
description: 瞭解使用Adobe Campaign匯入和匯出資料的不同方式。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: 工作流程
role: 資料架構師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 24%

---


# 關於資料匯入和匯出{#about-data-import-and-export}

根據您的業務需求，您有數種方式可匯入和匯出Adobe Campaign的資料：

* **套件**:軟體包是XML檔案，允許您將配置和資料集從Adobe Campaign實例導出和導入到另一個實例。系統更新也通過包導入來執行。
* **清單**:可以配置所有清單螢幕，並將顯示的資料導出到單獨的檔案中。
* **工作流程**:從檔案匯入資料，並使用它來更新資料庫或傳送電子郵件。您也可以選取要在檔案中匯出的資料。 工作流程是自動化定期更新（例如描述檔匯入）的最佳方式。

   * **[!UICONTROL Load file]** 活動可讓您匯入單一結構化格式的資料，以便在 Adobe Campaign 中使用此資料。會暫時匯入資料，而另一個活動必須將它完全整合在 Adobe Campaign 資料庫中。有關如何使用此活動的詳細資訊，請參閱[本節](../../automating/using/load-file.md)。
   * **[!UICONTROL Transfer file]** 活動可讓您接收或傳送檔案、測試 Adobe Campaign 中是否有檔案或列出檔案。您可以在&#x200B;**[!UICONTROL Load file]**&#x200B;之前使用此活動，以備需要從外部源中檢索檔案時使用。 有關如何使用此活動的詳細資訊，請參閱[本節](../../automating/using/transfer-file.md)。

在設計匯入程式時，最好使用可配合需求調整的工作流程範本。 有關如何設定工作流模板以導入資料的詳細資訊，請參閱[此使用案例](../../automating/using/creating-import-workflow-templates.md)。

Adobe Campaign也提供簡化的方式來執行常規導入，包括設計&#x200B;**導入模板**。 匯入範本是專用的工作流程範本，可透過專用螢幕取得。 設計完成後，執行匯入的使用者只需上傳檔案即可在簡化檢視中匯入。

**相關主題**：

* [使用匯入範本匯入資料](../../automating/using/importing-data-with-import-templates.md)
* [定義匯入範本](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [管理套件](../../automating/using/managing-packages.md)
