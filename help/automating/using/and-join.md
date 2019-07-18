---
title: AND-complement
seo-title: AND-complement
description: AND-complement
seo-description: AND-加入活動可讓您同步工作流程的多個執行分支。
page-status-flag: 從未啓動
uuid: 9b54fd4c-9915-400f-a494-74e52 c329 b8 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 執行活動
discoiquuid: 4b55efa2-652e-4493-bfa7-eaee59 b383 ca
context-tags: and complement，main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# AND-join{#and-join}

## Description {#description}

![](assets/and_join.png)

**[!UICONTROL AND-join]** 此活動可讓您同步工作流程的多個執行分支。

## Context of use {#context-of-use}

**[!UICONTROL AND-join]** 在所有前述活動完成後，活動只會觸發其傳出轉場，換言之，所有傳入的轉場都會啓動。

## Configuration {#configuration}

1. 將多個活動(例如查詢)拖放到您的工作流程中，形成至少兩個不同的執行分支。
1. Drag and drop an **[!UICONTROL AND-join]** activity into your workflow.
1. 在您要同步的兩個不同分支之後進行連接。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 選取要保留在對外轉場中的主要設定。如果您未選取任何設定，則會從活動中傳送隨機人口。
1. 確認活動的設定並儲存工作流程。

## Example {#example}

The following example shows two workflow branches before they are joined with the **[!UICONTROL AND-join]** activity. File extraction can only take place when the three inbound transitions of the **[!UICONTROL AND-join]** activity are enabled.

![](assets/wkf_and-join_example.png)

