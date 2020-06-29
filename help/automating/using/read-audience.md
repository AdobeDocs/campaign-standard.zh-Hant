---
title: 讀取閱聽眾
description: 「讀取對象」活動可讓您擷取現有對象，並套用其他篩選條件以加以調整。
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 1%

---


# 讀取閱聽眾{#read-audience}

## 說明 {#description}

![](assets/prefill.png)

此活 **[!UICONTROL Read audience]** 動可讓您擷取現有的觀眾，並套用其他篩選條件來調整觀眾。

## 使用內容 {#context-of-use}

此活 **[!UICONTROL Read audience]** 動是活動的簡單版本，專 **[!UICONTROL Query]** 為您只需要選取現有對象的情況而設計。

**相關主題**

* [使用案例： 結合兩個精美受眾](../../automating/using/union-on-two-refined-audiences.md)
* [使用案例： 協調檔案對象與資料庫](../../automating/using/reconcile-file-audience-with-database.md)

## 配置 {#configuration}

1. 將活動 **[!UICONTROL Read audience]** 拖放至工作流程中。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 選取您要從標籤擷取的對 **[!UICONTROL Properties]** 像。

   您可以擷取下列類型的觀眾： **[!UICONTROL List]**、 **[!UICONTROL Query]**&#x200B;和 **[!UICONTROL File]****[!UICONTROL Experience Cloud]**。 如需觀眾類型的詳細資訊，請參閱「觀眾 [」檔案](../../audiences/using/about-audiences.md) 。

   選 **[!UICONTROL Use a dynamic audience]** 項可讓您根據工作流程的事件變數定義要定位的對象名稱。 如需詳細資訊，請參閱「使用事件變 [數自訂活動](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 」一節。

   ![](assets/readaudience_activity1.png)

1. 如果您想要將其他篩選套用至選取的對象，請透過活動的標 **[!UICONTROL Source filtering]** 簽新增條件。

   有關建立篩選條件的詳細資訊，請參閱「創 [建查詢](../../automating/using/editing-queries.md#creating-queries) 」文檔。

1. 確認活動的設定並儲存工作流程。
