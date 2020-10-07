---
title: 合併連結
description: 合併連結活動可讓您同步處理工作流的多個執行分支。
page-status-flag: never-activated
uuid: 9b54fd4c-9915-400f-a494-74e52c329b8a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 4b55efa2-652e-4493-bfa7-eaee59b383ca
context-tags: andjoin,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 合併連結{#and-join}

## 說明 {#description}

![](assets/and_join.png)

**[!UICONTROL AND-join]** 活動可讓您同步工作流的多個執行分支。

## 使用內容 {#context-of-use}

**[!UICONTROL AND-join]** 活動只會在所有入站轉變啟動後，才會觸發其出站轉變，換句話說，會在之前所有活動完成後觸發。

## 設定 {#configuration}

1. 將多個活動（例如查詢）拖放到您的工作流中，以形成至少兩個不同的執行分支。
1. 將 **[!UICONTROL AND-join]** 活動拖放至工作流程中。
1. 在您要同步的兩個不同分支之後，再連接它。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 選取要保留在出站轉變中的主集。如果您未選取任何集合，則會從活動傳送隨機母體。
1. 確認活動的設定並儲存工作流程。

## 範例 {#example}

下列範例顯示兩個工作流程分支在與 **[!UICONTROL AND-join]** 活動連結之前的情形。只有啟用 **[!UICONTROL AND-join]** 活動的三個入站轉變時，才能擷取檔案。

![](assets/wkf_and-join_example.png)

