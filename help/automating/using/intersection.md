---
title: 交集
description: 「交叉點」活動允許您僅保留活動中不同傳入人口族群的共同元素。
page-status-flag: never-activated
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# 交集{#intersection}

## 說明 {#description}

![](assets/intersection.png)

此活 **[!UICONTROL Intersection]** 動可讓您僅保留活動中不同傳入人口族群的共同元素。

## 使用內容 {#context-of-use}

活動 **[!UICONTROL Intersection]** 通常用於對入站轉變中的人口族群進行額外過濾。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Intersection]** 至工作流程。
1. 將其連接到前面的其他活動，如查詢。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 選擇 **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: 預設模式。 當來自不同傳入轉場的元素具有相同索引鍵時，活動只會保留一個元素。
   * **[!UICONTROL All shared columns]**: 資料會根據與傳入轉場共用的欄進行調節。 因此，您必須選擇作為比較基礎的主集。 如果傳入人口族群定位維度不同，則可使用此選項。
   * **[!UICONTROL A selection of columns]**: 選擇此選項可定義將應用資料協調的列清單。 首先必須選擇主集（包含源資料的主集），然後指定用於聯接的欄位。

1. 如果您 **[!UICONTROL Use common additional data only]** 只想保留所有傳入轉場中的其他資料，請勾選此方塊。
1. 如有需要，請管理活動的 [轉場](../../automating/using/activity-properties.md) ，以存取出站人口的進階選項。
1. 確認活動的設定並儲存工作流程。

## Example {#example}

以下示例顯示兩個查詢活動之間的交集。 此處用來查看Adobe Campaign資料庫，並擷取年齡介於18到27歲之間的個人檔案，以及分別提供電子郵件地址的個人檔案。

![](assets/wkf_intersection_example.png)

