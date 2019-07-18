---
title: Union
seo-title: Union
description: Union
seo-description: 歐盟活動可讓您將多個活動的結果重新整理為單一目標。
page-status-flag: 從未啓動
uuid: fafc3ce9-2212-4403-8754-cfbb28 ba6 e26
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
discoiquuid: 99a8c3a5-4d90-4db-aa37-1d0 a84719 cf6
context-tags: 聯合組織，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Union{#union}

## Description {#description}

![](assets/union.png)

**[!UICONTROL Union]** 活動可讓您將多個活動的結果重新群組為單一目標。

>[!NOTE]
>
>這些集不一定需要統一。

## Context of use {#context-of-use}

**[!UICONTROL Union]** 活動可用來在執行分段、定義觀眾或在準備訊息目標時，結合傳入的轉場次數。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Union]** activity into your workflow.
1. 將它連接至之前的其他活動，例如查詢。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]** to define how duplicates are from the confrontation between inbound populations are handled:

   * **[!UICONTROL Keys only]**：這是預設模式。當來自不同傳入轉場的元素具有相同的索引鍵時，活動只會保留一個元素。只有在傳入的人口族群統一時，才可使用此選項。
   * **[!UICONTROL All shared columns]**：資料會根據傳入轉場的所有欄進行協調。因此，您必須選取要保留在重復情況下的主要集。如果傳入的人口目標維度不同，則可使用此選項。
   * **[!UICONTROL A selection of columns]**：選取此選項，可定義將套用資料協調的欄清單。您必須先選取主要設定(包含來源資料)，然後選取要用於加入的欄。

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If you would like to limit the size of the final population, check the **[!UICONTROL Limit size of generated population]** box. The size can be specified in the **[!UICONTROL Maximum number of records]** field.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the calculated population.
1. 確認活動的設定並儲存工作流程。

## Example {#example}

以下範例顯示兩個查詢活動的結果，其目標是從Adobe Campaign資料庫的Adobe Campaign資料庫到年齡介於34到40歲之間的重新群組描述檔。結果包含兩個查詢的所有描述檔，或設定期間所指定的最大記錄數(如果適用)。

![](assets/wkf_union_example.png)