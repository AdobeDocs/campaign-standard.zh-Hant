---
title: 排除
description: 「排除」活動可讓您根據特定條件從一個人口中排除元素。
page-status-flag: 從未激活
uuid: b79e7f73-37a0-4ec3-ac5a-5449dc1b1f22
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 定位活動
discoiquuid: d5312fcd-43ad-428e-bde9-90f062e9358c
context-tags: 排除，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 排除{#exclusion}

## 說明 {#description}

![](assets/exclusion.png)

此活 **[!UICONTROL Exclusion]** 動可讓您根據特定條件，從單一人口中排除元素。

## 使用內容 {#context-of-use}

該活 **[!UICONTROL Exclusion]** 動主要用於對傳入的過渡人口進行額外過濾。

主集在入站轉變中定義。 其他入站轉變的成員將從主集中排除。 排除活動的出站轉換只包含其他入站轉換中未遇到的主整合員。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Exclusion]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 從入站 **[!UICONTROL Primary set]** 轉變中選擇。 這是從中排除元素的集合。 其他組在被排除在主組之外之前設定匹配元素。

   >[!NOTE]
   >
   >傳入的轉場必須包含相同類型的人口。 例如，如果主集包含測試描述檔，其他轉場也必須包含測試描述檔。

1. 如有需要，請管理活動的 [轉場](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) ，以存取出站人口的進階選項。
1. 確認活動的設定並儲存工作流程。

## Example {#example}

下列範例顯示兩個查詢活動，其設定是從Adobe Campaign資料庫篩選18到27歲之間且電子郵件地址無效的描述檔。 接著，含有無效電子郵件地址的描述檔會從第一組中排除。 例如，這可讓您傳送電子郵件。

![](assets/wkf_exclusion_example.png)

