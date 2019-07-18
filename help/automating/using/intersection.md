---
title: 十字路口
seo-title: 十字路口
description: 十字路口
seo-description: 「相交」活動可讓您僅保留活動中不同傳入人口族群常用的元素。
page-status-flag: 從未啓動
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3 dec8 e43 f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Intersection{#intersection}

## Description {#description}

![](assets/intersection.png)

**[!UICONTROL Intersection]** 活動可讓您僅保留活動中不同傳入人口族群常用的元素。

## Context of use {#context-of-use}

**[!UICONTROL Intersection]** 此活動通常用於對傳入的轉場進行其他篩選。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Intersection]** activity into your workflow.
1. 將它連接至之前的其他活動，例如查詢。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**：預設模式。當來自不同傳入轉場的元素具有相同的索引鍵時，活動只會保留一個元素。
   * **[!UICONTROL All shared columns]**：資料會根據傳入轉場的常見欄來協調。因此，您必須選擇做為比較基礎的主要集。如果傳入的人口目標維度不同，則可使用此選項。
   * **[!UICONTROL A selection of columns]**：選取此選項，可定義將套用資料協調的欄清單。您必須先選取主要集(其中包含來源資料的資料)，然後指定要用於加入的欄位。

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. 確認活動的設定並儲存工作流程。

## Example {#example}

下列範例顯示兩個查詢活動之間的相交情形。此處用於Adobe Campaign資料庫，並擷取在18到27歲之間的描述檔，以及分別提供電子郵件地址的個人檔案。

![](assets/wkf_intersection_example.png)

