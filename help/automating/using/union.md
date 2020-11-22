---
solution: Campaign Standard
product: campaign
title: 聯集
description: 「聯集」活動可讓您將多個活動的結果重新分組到單一目標中。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: union,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 98%

---


# 聯集{#union}

## 說明 {#description}

![](assets/union.png)

**[!UICONTROL Union]** 活動可讓您將多個活動的結果重新群組至單一目標。

>[!NOTE]
>
>這些集不一定是要同質的。

## 使用內容 {#context-of-use}

例如，**[!UICONTROL Union]** 活動的作用是在執行分段、定義對象，或是準備訊息目標時，結合來自入站變動的母體。

**相關主題：**

* [使用案例：結合兩個精美受眾](../../automating/using/union-on-two-refined-audiences.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Union]** 活動拖放至工作流程中。
1. 將其連接到其前面的其他活動，例如查詢。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 選取 **[!UICONTROL Reconciliation type]** 以定義如何處理來自入站母體之間對抗的重複項目：

   * **[!UICONTROL Keys only]**：這是預設模式。當來自不同入站轉變的元素具有相同索引鍵時，活動只會保留一個元素。如果入站母體是同質的，則只能使用此選項。
   * **[!UICONTROL All shared columns]**：資料會根據與入站轉變共用的所有欄進行調節。因此，您必須選取在出現重複項目時要保留的主要集。如果入站母體目標定位維度不同，則可使用此選項。
   * **[!UICONTROL A selection of columns]**：選取此選項可定義將套用資料協調的欄清單。首先，必須選取主集（其中包含來源資料），然後指定用於加入的欄。

1. 如果您只想保留所有入站轉變中的其他資料，請核取　**[!UICONTROL Use common additional data only]**　方塊。
1. 如果您要限制最終母體的大小，請合取 **[!UICONTROL Limit size of generated population]** 方塊。可在　**[!UICONTROL Maximum number of records]**　欄位中指定大小。
1. 如有需要，請管理活動的[轉變](../../automating/using/activity-properties.md)，以存取計算母體的進階選項。
1. 確認活動的設定並儲存工作流程。

## 範例 {#example}

下列範例顯示兩個查詢活動的結果，其目的在於從 Adobe Campaign 資料庫重新分組設定檔（適用對象是　18 至 27 歲，以及 34 至 40 歲的人）。結果包含在設定期間指定的兩個查詢的所有設定檔，或是記錄數量上限（如果適用）。

![](assets/wkf_union_example.png)