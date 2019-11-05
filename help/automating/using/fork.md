---
title: 分支
description: Fork活動允許您建立出站轉場，以同時啟動多個活動。
page-status-flag: 從未激活
uuid: e4eaf69b-84ee-4f79-8b80-99284697cd2c
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 執行活動
discoiquuid: f8ffe7af-e18c-4599-8fd0-fcd192565323
context-tags: 叉子，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 分支{#fork}

## 說明 {#description}

![](assets/fork.png)

活動 **[!UICONTROL Fork]** 允許您建立出站轉場，以便同時啟動多個活動。

## 使用內容 {#context-of-use}

此活 **[!UICONTROL Fork]** 動可讓您在相同的工作流程中，獨立執行數個不同的活動。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Fork]** 至工作流程。
1. 將其連接到前面的其他活動，如查詢。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 建立、刪除或複製輸出轉場，以指定轉場數。 您也可以為其指定名稱和標籤。
1. 確認活動的設定並儲存工作流程。

## Example {#example}

下列範例顯示兩個查詢活動的交集，這些活動是以Adobe Campaign資料庫中的描述檔為目標，在本例中為巴黎女性。 因此，fork活動允許您同時使用多個活動：一個可讓讀者記住計算的人口數量，另一個可區隔人口數量，以傳送兩個不同的電子郵件，並針對每個區段設定目標內容。 第一封郵件是發給18至40歲的巴黎女性，另一封則針對40歲以上的巴黎女性。

![](assets/wkf_fork_example.png)

