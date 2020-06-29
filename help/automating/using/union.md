---
title: 聯集
description: 「聯合」活動允許您將多個活動的結果重新組合到單個目標中。
page-status-flag: never-activated
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: union,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 1%

---


# 聯集{#union}

## 說明 {#description}

![](assets/union.png)

此活 **[!UICONTROL Union]** 動可讓您將多個活動的結果重新群組至單一目標。

>[!NOTE]
>
>這些集合不一定需要是同質的。

## 使用內容 {#context-of-use}

當執 **[!UICONTROL Union]** 行分段、定義對象或準備訊息目標時，活動可用來結合傳入轉場中的人口族群。

**相關主題：**

* [使用案例： 結合兩個精美受眾](../../automating/using/union-on-two-refined-audiences.md)

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Union]** 到工作流程中。
1. 將其連接到前面的其他活動，如查詢。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 選擇以 **[!UICONTROL Reconciliation type]** 定義如何處理傳入人口族群對抗中重複項：

   * **[!UICONTROL Keys only]**: 這是預設模式。 當來自不同傳入轉場的元素具有相同索引鍵時，活動只會保留一個元素。 只有傳入的人口族群是同質的，才能使用此選項。
   * **[!UICONTROL All shared columns]**: 資料會根據所有與傳入轉場共用的欄進行協調。 因此，您必須選擇在出現重複時保留的主集。 如果傳入人口族群定位維度不同，則可使用此選項。
   * **[!UICONTROL A selection of columns]**: 選擇此選項可定義將應用資料協調的列清單。 首先必須選擇主集（包含源資料的主集），然後選擇用於聯接的列。

1. 如果您 **[!UICONTROL Use common additional data only]** 只想保留所有傳入轉場中的其他資料，請勾選此方塊。
1. 如果要限制最終人口的大小，請選中該 **[!UICONTROL Limit size of generated population]** 框。 可在欄位中指定大 **[!UICONTROL Maximum number of records]** 小。
1. 如有需要，請管理活動的 [轉場](../../automating/using/activity-properties.md) ，以存取計算人口的進階選項。
1. 確認活動的設定並儲存工作流程。

## Example {#example}

下列範例顯示兩個查詢活動的結果，這些活動旨在從18到27歲的Adobe Campaign資料庫重新群組設定檔，以及34到40歲的資料。 結果包含兩個查詢的所有配置檔案或在配置期間指定的最大記錄數（如果適用）。

![](assets/wkf_union_example.png)