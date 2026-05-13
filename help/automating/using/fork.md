---
title: 分支
description: 「分支」活動可讓您建立出站轉變，以同時啟動多個活動。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: fork,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1a5e1ecd-b3f1-4dbe-a816-12d27a3bc0f7
TQID: https://experienceleague.adobe.com/1-9VY3TjBBHAb-7bFikis3Ue5eWy5KXKSR4hXxXDLwc
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 213
ht-degree: 98%

---

# 分支{#fork}

## 說明 {#description}

![](assets/fork.png)

**[!UICONTROL Fork]** 活動可讓您建立出站轉變，以同時啟動多個活動。

## 使用內容 {#context-of-use}

**[!UICONTROL Fork]** 活動可讓您在相同的工作流程中，獨立執行數個不同的活動。

## 設定 {#configuration}

1. 將 **[!UICONTROL Fork]** 活動拖放至工作流程中。
1. 將其連接到其前面的其他活動，例如查詢。
1. 選取活動，然後使用所顯示快速動作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 建立、刪除或複製出站轉變，以指定轉變次數。 您也可以為其指定名稱和標籤。
1. 確認活動的設定並儲存工作流程。

## 範例 {#example}

下列範例顯示兩個查詢活動的交集，這些活動是以 Adobe Campaign 資料庫中的輪廓為目標，在此情況下，是指居住在巴黎的女性。 因此，「分支」活動可讓您同時使用多個活動：一個可讓客群記住計算的群體數量，另一個可區隔群體，以傳送兩封不同的電子郵件，並針對每個細分群體設定目標內容。 第一封電子郵件是傳送給年齡介於 18 至 40 歲的巴黎女性，另一封則傳送給 40 歲以上的巴黎女性。

![](assets/wkf_fork_example.png)
