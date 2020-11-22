---
solution: Campaign Standard
product: campaign
title: 推播通知傳送
description: 「推播通知傳送」活動可讓您設定在工作流程中傳送單一傳送推播通知或週期性推播通知。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---


# 推播通知傳送{#push-notification-delivery}

## 說明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

The **[!UICONTROL Push notification]** activity allows you to configure sending a push notification in a workflow. 這可以是單一傳送通知，只傳送一次，也可以是循環通知。

* **單一** 傳送通知是標準的行動應用推播通知傳送，只傳送一次。
* **循環通知** ，可讓您在定義的時段內，多次傳送相同的行動應用程式推播通知傳送至不同的目標。 您可以彙總每個期間的傳送，以取得符合您需求的報表。

## 使用內容 {#context-of-use}

The **[!UICONTROL Push notification]** activity is generally used to automate sending a notification to a target calculated in the same workflow.

當連結至排程器時，您可以定義循環推播通知。

收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的位置。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選取是否要求傳送訊息的手動確認（預設為必要）。您可以手動啟動工作流程，或將排程器活動置於工作流程中以自動執行。

**相關主題**

* [傳送具有工作流程的循環推播通知](../../automating/using/recurring-push-notifications.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Push notification]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的 ![](assets/dlv_activity_params-24px.png) 按鈕，存取活動（而非傳送本身）的一般屬性和進階選項。此按鈕是 **[!UICONTROL Push notification]** 活動的特定按鈕。推播通知的屬性可透過推播控制面板中的動作列加以存取。

1. 選取推播通知傳送模式：

   * **[!UICONTROL Single notification]**:推播通知只會傳送一次。 您可以在此處指定是否要向活動新增出站轉變。在本過程的步驟 7 中詳細說明不同的轉變類型。
   * **[!UICONTROL Recurring notification]**:根據活動中定義的頻率，推播通知會傳送數次 **[!UICONTROL Scheduler]** 。 選取傳送的彙總期間。This allows you to regroup all the sends that occur during the defined period in one single push notification that is also called **recurring execution** and can be accessed from the application&#39;s marketing activity list.

      例如，對於每日傳送的循環生日通知，您可以選擇匯總每月傳送的傳送。 這可讓您每月收到有關傳送的報表，不過通知會每天傳送。

1. 選擇通知類型。 這些類型來自「 > >」功能表中定義 **[!UICONTROL Resources]** 的推 **[!UICONTROL Templates]** 播通 **[!UICONTROL Delivery templates]** 知範本。
1. 輸入推播通知的一般屬性。 您也可以將它附加至現有的行銷活動。工作流程的傳送活動標籤會以推播通知標籤更新。
1. 定義推播通知內容。 請參閱 [建立推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)
1. 依預設，**[!UICONTROL Push notification]** 活動不包含任何外站轉變。如果要將出站轉變新增到 **[!UICONTROL Push Notification]** 活動中，請轉至高階活動選項的　**[!UICONTROL General]**　索引標籤（活動快速操作中的　![](assets/dlv_activity_params-24px.png)　按鈕），然後核取以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生一個外站轉變，其中包含與入站轉變完全相同的母體。
   * **[!UICONTROL Add outbound transition with the population]**:這可讓您產生對外轉場，其中包含傳送通知的人口。 傳送準備期間排除的目標成員會排除在此轉換之外。

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會將您直接帶至推播通知控制面板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。在工作流程啟動後，仍需要確認從工作流程建立的訊息的傳送。但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用 **[!UICONTROL Request confirmation before sending messages]** 選項。取消核取此選項後，訊息會在準備完成後不另行通知而傳送。

## 註釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。您可以使用控制面板來檢視工作流程的執行狀態。推播通知摘要窗格中的連結可讓您直接存取連結的元素（工作流程、促銷活動等）。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Push notification]** activity was configured). 若要這麼做，請選取 ![](assets/wkf_dlv_detail_button.png)，以開啟上層傳送 **[!UICONTROL Deployment]** 區塊的詳細資訊檢視。
