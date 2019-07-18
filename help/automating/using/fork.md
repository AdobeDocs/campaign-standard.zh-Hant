---
title: 分叉
seo-title: 分叉
description: 分叉
seo-description: 分叉活動可讓您建立傳出轉場，同時啓動多個活動。
page-status-flag: 從未啓動
uuid: e4eAF69b-84ee-4f79-8b80-9928497cd2c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 執行活動
discoiquuid: f8ffe7af-e18 c-4599-1fd0-fcd192565323
context-tags: fork，main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Fork{#fork}

## Description {#description}

![](assets/fork.png)

**[!UICONTROL Fork]** 活動可讓您建立傳出轉場，同時啓動多個活動。

## Context of use {#context-of-use}

**[!UICONTROL Fork]** 此活動可讓您在同一工作流程中獨立執行數個不同的活動。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Fork]** activity into your workflow.
1. 將它連接至之前的其他活動，例如查詢。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 透過建立、刪除或複製傳出轉場次數來指定傳出轉場次數。您也可以為他們指定名稱和標籤。
1. 確認活動的設定並儲存工作流程。

## Example {#example}

以下範例顯示兩個用於Adobe Campaign資料庫中設定檔的查詢活動交叉點，在此案例中，女性居住在巴黎。因此，分叉活動可讓您同時使用多個活動：一個可讓觀眾記住計算的人口族群，而另一個群體則是群體，以針對每個群體傳送兩封不同的電子郵件。第一封電子郵件傳送給年齡介於18到40歲的Pariasian女性，以及另一位鎖定40歲以上的Pariasian女性。

![](assets/wkf_fork_example.png)

