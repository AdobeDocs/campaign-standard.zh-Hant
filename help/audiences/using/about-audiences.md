---
title: 關於閱聽眾
description: 瞭解如何從查詢、清單或檔案建立觀眾，以及如何從Adobe Experience cloud匯入觀眾。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# 關於閱聽眾{#about-audiences}

對象是根據規則和屬性的設定檔清單。

Adobe Campaign可讓您使用查詢手動建立觀眾，或自動使用專用的工作流程。 您也可以使用來自Adobe Experience cloud的共用觀眾。 所有觀眾都會重新分組成清單，可透過Adobe Campaign首頁 **[!UICONTROL Audiences]**的資訊卡或連結存**[!UICONTROL Audiences]** 取。

![](assets/audience_1.png)

您可以在Adobe Campaign中控制不同的觀眾類型。 對象類型與建立對象的方式相對應：

* **[!UICONTROL Query]**:指出觀眾是從觀眾清單[中](../../automating/using/editing-queries.md#about-query-editor)，從Adobe Campaign資料庫的資料查詢建立。 在每次進一步使用時重新計算由查詢定義的對象。
* **[!UICONTROL List]**:指出對象是固定的設定檔清單。 這些清單是在工作[流程中建立](../../automating/using/discovering-workflows.md)，在此工作流程中儲存對象時會知道資料維度。 例如，在定位活動(尤其是**[!UICONTROL Query]** )後或協調從檔案匯入的資料後。
* **[!UICONTROL File]**:指出觀眾是直接從檔案匯入工[作流程建立](../../automating/using/load-file.md)，且儲存觀眾時資料維度未知。
* **[!UICONTROL Experience Cloud]**:指出觀眾是從Adobe Experience cloud匯入的。 只有已設定觀眾共用功能時，才可使用此選項。 如需詳細資訊，請[參閱「從Adobe Experience cloud匯入觀眾」](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)。

![](assets/audience_type_selection.png)
