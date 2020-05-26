---
title: 關於資料匯入和匯出
description: 瞭解使用Adobe Campaign匯入和匯出資料的不同方式。
page-status-flag: never-activated
uuid: f6810364-555c-4b72-8a9c-4ae2fcb2ba63
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 31215773-6c0c-48f1-9101-da0ea2a366da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0deabe17442b679a340a4497945837b83b4c9207
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 6%

---


# 關於資料匯入和匯出{#about-data-import-and-export}

根據您的業務需求，您有數種方式可以透過Adobe Campaign匯入和匯出資料：

* **套件**: 套件是XML檔案，可讓您從Adobe Campaign例項匯出和匯入組態和資料集至另一個。 系統更新也通過包導入來執行。
* **清單**: 可以配置所有清單螢幕，並將顯示的資料導出到單獨的檔案中。
* **工作流程**: 從檔案匯入資料，並使用它來更新資料庫或傳送電子郵件。 您也可以選取要在檔案中匯出的資料。 工作流程是自動化定期更新（例如描述檔匯入）的最佳方式。

   * 此活 **[!UICONTROL Load file]** 動可讓您匯入單一結構化格式的資料，以便在Adobe Campaign中使用此資料。 資料會暫時匯入，而另一個活動必須將它完全整合在Adobe Campaign資料庫中。 有關如何使用此活動的詳細資訊，請參 [閱本節](../../automating/using/load-file.md)。
   * 此活 **[!UICONTROL Transfer file]** 動可讓您接收或傳送檔案、測試Adobe Campaign中是否有檔案或列出檔案。 您可以在前使用此活動，以 **[!UICONTROL Load file]** 防需要從外部源中檢索檔案。 有關如何使用此活動的詳細資訊，請參 [閱本節](../../automating/using/transfer-file.md)。

在設計匯入程式時，最好使用可配合需求調整的工作流程範本。 如需如何設定工作流程範本以匯入資料的詳細資訊，請參閱 [此使用案例](../../automating/using/creating-import-workflow-templates.md)。

Adobe Campaign也提供簡化的方式來執行定期匯入，包括設計匯入 **範本**。 匯入範本是專用的工作流程範本，可透過專用螢幕取得。 設計完成後，執行匯入的使用者只需上傳檔案即可在簡化檢視中匯入。

**相關主題**:

* [使用匯入範本匯入資料](../../automating/using/importing-data-with-import-templates.md)
* [定義匯入範本](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [管理套件](../../automating/using/managing-packages.md)
