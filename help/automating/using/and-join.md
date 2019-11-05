---
title: 合併連結
description: AND-join活動允許您同步工作流的多個執行分支。
page-status-flag: 從未激活
uuid: 9b54fd4c-9915-400f-a494-74e52c329b8a
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 執行活動
discoiquuid: 4b55efa2-652e-4493-bfa7-eae59b383ca
context-tags: 和連接，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 合併連結{#and-join}

## 說明 {#description}

![](assets/and_join.png)

此活 **[!UICONTROL AND-join]** 動可讓您同步工作流的多個執行分支。

## 使用內容 {#context-of-use}

活 **[!UICONTROL AND-join]** 動只會在所有入站轉變激活後觸發其出站轉變，換言之，在所有前面的活動完成後。

## 配置 {#configuration}

1. 將多個活動（例如查詢）拖放到您的工作流中，以形成至少兩個不同的執行分支。
1. 將活動拖放 **[!UICONTROL AND-join]** 至工作流程。
1. 在您要同步的兩個不同分支之後再連接它。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 選擇要保留在出站轉變中的主集。 如果您未選取任何集合，則會從活動傳送隨機人口。
1. 確認活動的設定並儲存工作流程。

## Example {#example}

下列範例顯示兩個工作流程分支在與活動連結之前的 **[!UICONTROL AND-join]** 情形。 只有啟用活動的三個傳入轉換時，才能進 **[!UICONTROL AND-join]** 行檔案擷取。

![](assets/wkf_and-join_example.png)

