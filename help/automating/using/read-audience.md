---
title: 讀取客群
description: 「讀取客群」活動可讓您擷取現有客群，並套用其他篩選條件加以改良。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 9a77a2c7-cc1c-416f-8103-bb7d5c84a373
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 86%

---

# 讀取客群{#read-audience}

## 說明 {#description}

![](assets/prefill.png)

**[!UICONTROL Read audience]** 活動可讓您擷取現有的客群，並套用其他篩選條件來調整客群。

## 使用內容 {#context-of-use}

**[!UICONTROL Read audience]** 活動是 **[!UICONTROL Query]** 活動的簡單版本，專為您只需要選取現有客群的情況而設計。

**相關主題**

* [使用案例：聯合兩個完善的對象](../../automating/using/union-on-two-refined-audiences.md)
* [使用案例：使用資料庫調解檔案對象](../../automating/using/reconcile-file-audience-with-database.md)

## 設定 {#configuration}

1. 將活動 **[!UICONTROL Read audience]** 拖曳至工作流程中。
1. 選取活動，然後使用所顯示快速動作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 選取您要從 **[!UICONTROL Properties]** 索引標籤擷取的客群。

   您可以擷取下列類型的客群：**[!UICONTROL List]**、**[!UICONTROL Query]**、**[!UICONTROL File]** 及 **[!UICONTROL Experience Cloud]**。如需客群類型的詳細資訊，請參閱[客群](../../audiences/using/about-audiences.md)文件。

   **[!UICONTROL Use a dynamic audience]** 選項可讓您根據工作流程的事件變數定義要鎖定的客群名稱。如需詳細資訊，請參閱[此頁面](../../automating/using/customizing-workflow-external-parameters.md)區段。

   ![](assets/readaudience_activity1.png)

1. 如果您想要將其他篩選套用至選取的客群，請透過活動的 **[!UICONTROL Source filtering]** 索引標籤新增條件。

   有關建立篩選條件的詳細資訊，請參閱[建立查詢](../../automating/using/editing-queries.md#creating-queries)文件。

1. 確認活動的設定並儲存工作流程。
