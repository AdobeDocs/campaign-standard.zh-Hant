---
solution: Campaign Standard
product: campaign
title: 讀取對象
description: 「讀取對象」活動可讓您擷取現有對象，並套用其他篩選條件加以改良。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: 工作流程
role: 資料架構師
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 86%

---


# 讀取對象{#read-audience}

## 說明 {#description}

![](assets/prefill.png)

**[!UICONTROL Read audience]** 活動可讓您擷取現有的對象，並套用其他篩選條件來調整對象。

## 使用內容 {#context-of-use}

**[!UICONTROL Read audience]** 活動是 **[!UICONTROL Query]** 活動的簡單版本，專為您只需要選取現有對象的情況而設計。

**相關主題**

* [使用案例：結合兩個精美受眾](../../automating/using/union-on-two-refined-audiences.md)
* [使用案例：協調檔案對象與資料庫](../../automating/using/reconcile-file-audience-with-database.md)

## 設定 {#configuration}

1. 將活動 **[!UICONTROL Read audience]** 拖曳至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 選取您要從 **[!UICONTROL Properties]** 索引標籤擷取的對象。

   您可以擷取下列類型的對象：**[!UICONTROL List]**、**[!UICONTROL Query]**、**[!UICONTROL File]** 及 **[!UICONTROL Experience Cloud]**。如需對象類型的詳細資訊，請參閱[對象](../../audiences/using/about-audiences.md)文件。

   **[!UICONTROL Use a dynamic audience]** 選項可讓您根據工作流程的事件變數定義要定位的對象名稱。有關詳細資訊，請參閱[本頁](../../automating/using/customizing-workflow-external-parameters.md)部分。

   ![](assets/readaudience_activity1.png)

1. 如果您想要將其他篩選套用至選取的對象，請透過活動的 **[!UICONTROL Source filtering]** 索引標籤新增條件。

   有關建立篩選條件的詳細資訊，請參閱[建立查詢](../../automating/using/editing-queries.md#creating-queries)文件。

1. 確認活動的設定並儲存工作流程。
