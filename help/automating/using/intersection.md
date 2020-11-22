---
solution: Campaign Standard
product: campaign
title: 交集
description: 「交集」活動可讓您僅保留活動中不同入站母體的共同元素。
audience: automating
content-type: reference
topic-tags: targeting-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 100%

---


# 交集{#intersection}

## 說明 {#description}

![](assets/intersection.png)

**[!UICONTROL Intersection]**　活動可讓您僅保留活動中不同入站母體的共同元素。

## 使用內容 {#context-of-use}

**[!UICONTROL Intersection]** 活動通常用於對入站轉變中的母體進行額外篩選。

## 設定 {#configuration}

1. 將 **[!UICONTROL Intersection]** 活動拖放至工作流程中。
1. 將其連接到其前面的其他活動，例如查詢。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 選取 **[!UICONTROL Reconciliation type]**：

   * **[!UICONTROL Keys only]**：預設模式。當來自不同入站轉變的元素具有相同索引鍵時，活動只會保留一個元素。
   * **[!UICONTROL All shared columns]**：資料會根據與入站轉變共用的欄進行調節。因此，您必須選取作為比較基礎的主集。如果入站母體目標定位維度不同，則可使用此選項。
   * **[!UICONTROL A selection of columns]**：選取此選項可定義將套用資料協調的欄清單。首先，必須選取主集（包含來源資料的主集），然後指定用於加入的欄位。

1. 如果您只想保留所有入站轉變中的其他資料，請核取　**[!UICONTROL Use common additional data only]**　方塊。
1. 如有需要，請管理活動的[轉變](../../automating/using/activity-properties.md)，以存取輸出母體的進階選項。
1. 確認活動的設定並儲存工作流程。

## 範例 {#example}

以下範例會顯示兩個查詢活動之間的交集。此處用於查看　Adobe Campaign　資料庫，以及擷取年齡介於　18　到　27　歲之間的設定檔，以及分別提供電子郵件地址的設定檔。

![](assets/wkf_intersection_example.png)

