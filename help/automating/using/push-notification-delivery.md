---
title: 推播通知傳送
description: 「推播通知傳送」活動可讓您設定在工作流程中傳送單一傳送推播通知或週期性推播通知。
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 0%

---


# 推播通知傳送{#push-notification-delivery}

## 說明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

此活 **[!UICONTROL Push notification]** 動可讓您設定在工作流程中傳送推播通知。 這可以是單一 **傳送通知** ，只傳送一次，或是循環 **通知** 。

單一傳送通知是標準行動應用程式推播通知傳送，只傳送一次。

週期性通知可讓您在定義的時段內，多次傳送相同的行動應用程式推播通知給不同的目標。 您可以匯總每個期間的交貨，以取得符合您需求的報表。

## 使用內容 {#context-of-use}

活動 **[!UICONTROL Push notification]** 通常用於自動傳送通知給在相同工作流程中計算的目標。

當連結至排程器時，您可以定義循環推播通知。

收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的位置。

根據工作流執行參數觸發消息準備。 在訊息控制面板中，您可以選擇是否要求傳送訊息的手動確認（預設為必要）。 您可以手動啟動工作流，或將排程器活動置於工作流中以自動執行。

**相關主題**

* [傳送具有工作流程的循環推播通知](../../automating/using/recurring-push-notifications.md)

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Push notification]** 到工作流程中。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的按鈕，存取活動（而非傳送本身）的一 ![](assets/dlv_activity_params-24px.png) 般屬性和進階選項。 此按鈕是活動的特 **[!UICONTROL Push notification]** 定按鈕。 推播通知的屬性可透過推播控制面板中的動作列加以存取。

1. 選取推播通知傳送模式：

   * **[!UICONTROL Single notification]**: 推播通知只會傳送一次。 您可以在此處指定是否要向活動添加出站轉變。 在本過程的步驟7中詳細介紹了不同的過渡類型。
   * **[!UICONTROL Recurring notification]**: 根據活動中定義的頻率，推播通知會傳送數次 **[!UICONTROL Scheduler]** 。 選擇發送的聚合期間。 這可讓您在單一推播通知(也稱為循環執行 **** )中，重新分組在定義期間發生的所有傳送，並可從應用程式的行銷活動清單存取。

      例如，對於每日傳送的循環生日通知，您可以選擇匯總每月傳送的傳送。 這可讓您每月收到有關傳送的報表，不過通知會每天傳送。

1. 選擇通知類型。 這些類型來自「 > >」功能表中定義 **[!UICONTROL Resources]** 的推 **[!UICONTROL Templates]** 播通 **[!UICONTROL Delivery templates]** 知範本。
1. 輸入推播通知的一般屬性。 您也可以將它附加至現有的促銷活動。 工作流程的傳送活動標籤會以推播通知標籤更新。
1. 定義推播通知內容。 請參閱 [建立推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)
1. 依預設，活動 **[!UICONTROL Push notification]** 不包含任何對外轉場。 如果要將出站轉移添加到活動 **[!UICONTROL Push Notification]** 中，請轉至高級活動選項的頁籤( **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) 活動快速操作中的按鈕)，然後選中以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**: 這可讓您產生一個對外轉移，其中包含與傳入轉移完全相同的人口。
   * **[!UICONTROL Add outbound transition with the population]**: 這可讓您產生對外轉場，其中包含傳送通知的人口。 在傳送準備期間排除的目標成員將排除在此轉變之外。

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會將您直接帶至推播通知控制面板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。 在工作流啟動後，仍需要確認從工作流建立的消息的發送。 但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用選 **[!UICONTROL Request confirmation before sending messages]** 項。 取消勾選此選項後，訊息會在準備完成後不另行通知而傳送。

## 注釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。 您可以使用控制面板來檢視工作流程的執行狀態。 推播通知摘要窗格中的連結可讓您直接存取連結的元素（工作流程、促銷活動等）。

在可從行銷活動清單存取的父傳送中，您可以檢視已處理的傳送總數（根據設定活動時指定的匯總期間）。 **[!UICONTROL Push notification]** 若要這麼做，請選取以開啟父傳送區塊的詳 **[!UICONTROL Deployment]** 細資料檢視 ![](assets/wkf_dlv_detail_button.png)。
