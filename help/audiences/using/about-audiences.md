---
solution: Campaign Standard
product: campaign
title: 關於閱聽眾
description: 瞭解如何從查詢、清單或檔案建立閱聽眾，以及如何從　Adobe Experience Cloud　匯入閱聽眾。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: 受眾
role: 業務從業人員
level: 初學者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 90%

---


# 關於閱聽眾{#about-audiences}

閱聽眾是根據規則和屬性的設定檔清單。

Adobe Campaign　可讓您使用查詢手動建立閱聽眾，或自動使用專用的工作流程。您也可以使用來自　Adobe Experience Cloud　的共用閱聽眾。會將所有閱聽眾重新分組成清單，可透過　Adobe Campaign　首頁的 **[!UICONTROL Audiences]** 資訊卡或連結 **[!UICONTROL Audiences]**　進行存取。

![](assets/audience_1.png)

您可以在　Adobe Campaign　中控制不同的閱聽眾類型。閱聽眾類型與建立閱聽眾的方式相對應：

* **[!UICONTROL Query]**:表示觀眾是使用Adobe Campaign資料庫 [](../../automating/using/editing-queries.md#about-query-editor) 的查詢資料透過觀眾清單建立的。在每次進一步使用時重新計算由查詢定義的閱聽眾。
* **[!UICONTROL List]**：指出閱聽眾是固定的設定檔清單。這些清單會在[工作流程](../../automating/using/get-started-workflows.md)中建立，而且在儲存閱聽眾時會知道資料維度。例如，在目標定位活動（尤其是 **[!UICONTROL Query]**）之後，或是協調從檔案匯入的資料之後。
* **[!UICONTROL File]**：指出閱聽眾是從[檔案匯入](../../automating/using/load-file.md)工作流程直接建立，而且在儲存閱聽眾時不會知道資料維度。
* **[!UICONTROL Experience Cloud]**：指出閱聽眾是從　Adobe Experience Cloud　匯入。只有已設定閱聽眾共用功能時，才可使用此選項。如需詳細資訊，請參閱[從　Adobe Experience Cloud　匯入閱聽眾](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)。

![](assets/audience_type_selection.png)
