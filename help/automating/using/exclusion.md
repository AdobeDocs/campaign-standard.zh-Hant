---
title: 排除
seo-title: 排除
description: 排除
seo-description: 排除活動可讓您根據特定條件排除同一人口中的元素。
page-status-flag: 從未啓動
uuid: b79e7f73-37a0-4ec3-ac5 a-5449dc1 b1 f22
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
discoiquuid: d5312fcd-43ad-428e-bde9-90f062 e9358 c
context-tags: exclusion，main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Exclusion{#exclusion}

## Description {#description}

![](assets/exclusion.png)

**[!UICONTROL Exclusion]** 活動可讓您根據特定條件從一個人口族群排除元素。

## Context of use {#context-of-use}

**[!UICONTROL Exclusion]** 此活動主要用於對傳入轉換人口進行其他篩選。

在傳入轉場之間定義主要集。其他傳入轉場的成員會從主要集合中排除。排除活動的對外轉換僅包含其他傳入轉場中未出現的主要集成員。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Exclusion]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Primary set]** from the inbound transitions. 此為排除元素的規則集。另一個會在被排除於主要集之前，先設定元素。

   >[!NOTE]
   >
   >傳入的轉場必須包含相同類型的人口族群。例如，如果主要設定包含測試描述檔，其他轉場也必須包含測試描述檔。

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. 確認活動的設定並儲存工作流程。

## Example {#example}

下列範例顯示兩個設定為篩選來自Adobe Campaign資料庫之Adobe Campaign資料庫之描述檔的查詢活動，並有無效的電子郵件地址。然後，會排除具有無效電子郵件地址的描述檔，並從第一個設定中排除。這可讓您傳送電子郵件。

![](assets/wkf_exclusion_example.png)

