---
title: 關於受眾
seo-title: 關於受眾
description: 關於受眾
seo-description: 瞭解如何從查詢、清單或檔案建立觀眾，以及如何從Adobe Experience Cloud匯入觀眾。
page-status-flag: 從未啓動
uuid: b399662-96ec-489e-b146-c8 c2 cb52 aa32
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受眾
content-type: reference
topic-tags: 管理觀眾
discoiquuid: 750d8d-67a5-4180-bfec-2a8 e3098 c812
context-tags: 觀眾，精靈；觀眾，概觀；傳送，觀眾，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# About audiences{#about-audiences}

對象是根據規則和屬性的設定檔清單。

Adobe Campaign可讓您使用查詢或使用專屬工作流程自動建立觀眾。您也可以從Adobe Experience Cloud使用共用受眾。All of the audiences are regrouped into a list that can be accessed via the **[!UICONTROL Audiences]** card on the Adobe Campaign home page or from the **[!UICONTROL Audiences]** link.

![](assets/audience_1.png)

您可以在Adobe Campaign中控制不同的對象類型。對象的類型對應至建立的方式：

* **[!UICONTROL Query]**：表示觀眾是從Adobe Campaign資料庫中 [的](../../automating/using/editing-queries.md#about-query-editor) 資料查詢建立的對象。由查詢定義的觀眾會在每次進一步使用時重新計算。
* **[!UICONTROL List]**：表示觀眾是固定的描述檔清單。These lists are created in a [workflow](../../automating/using/discovering-workflows.md), where the data dimension is known when saving the audience. For example, after targeting activities (especially **[!UICONTROL Query]** ) or after the reconciliation of data imported from a file.
* **[!UICONTROL File]**：表示觀眾是直接從 [檔案匯入](../../automating/using/load-file.md) 工作流程建立，且在儲存觀眾時，資料維度不明。
* **[!UICONTROL Experience Cloud]**：表示觀眾是從Adobe Experience Cloud匯入。只有在已設定觀眾共用功能時，才可使用此選項。For more information, see [Importing an audience from the Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)

