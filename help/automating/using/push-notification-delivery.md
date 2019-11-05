---
title: 推播通知傳送
description: 「推播通知傳送」活動可讓您設定在工作流程中傳送單一傳送推播通知或週期性推播通知。
page-status-flag: 從未激活
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 頻道活動
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

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

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Push notification]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的按鈕，存取活動（而非傳送本身）的一 ![](assets/dlv_activity_params-24px.png) 般屬性和進階選項。 此按鈕是活動的特 **[!UICONTROL Push notification]** 定按鈕。 推播通知的屬性可透過推播控制面板中的動作列加以存取。

1. 選取推播通知傳送模式：

   * **[!UICONTROL Single notification]**:推播通知只會傳送一次。 您可以在此處指定是否要向活動添加出站轉變。 在本過程的步驟7中詳細介紹了不同的過渡類型。
   * **[!UICONTROL Recurring notification]**:根據活動中定義的頻率，推播通知會傳送數次 **[!UICONTROL Scheduler]** 。 選擇發送的聚合期間。 這可讓您在單一推播通知(也稱為循環執行 **** )中，重新分組在定義期間發生的所有傳送，並可從應用程式的行銷活動清單存取。

      例如，對於每日傳送的循環生日通知，您可以選擇匯總每月傳送的傳送。 這可讓您每月收到有關傳送的報表，不過通知會每天傳送。

1. 選擇通知類型。 這些類型來自「 &gt; &gt;」功能表中定義 **[!UICONTROL Resources]** 的推 **[!UICONTROL Templates]** 播通 **[!UICONTROL Delivery templates]** 知範本。
1. 輸入推播通知的一般屬性。 您也可以將它附加至現有的促銷活動。 工作流程的傳送活動標籤會以推播通知標籤更新。
1. 定義推播通知內容。 請參閱 [建立推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)
1. 依預設，活動 **[!UICONTROL Push notification]** 不包含任何對外轉場。 如果要將出站轉移添加到活動 **[!UICONTROL Push Notification]** 中，請轉至高級活動選項的頁籤( **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) 活動快速操作中的按鈕)，然後選中以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**:這可讓您產生一個對外轉移，其中包含與傳入轉移完全相同的人口。
   * **[!UICONTROL Add outbound transition with the population]**:這可讓您產生對外轉場，其中包含傳送通知的人口。 傳送準備期間排除的目標成員會排除在此轉換之外。

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會將您直接帶至推播通知控制面板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。 在工作流啟動後，仍需要確認從工作流建立的消息的發送。 但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用選 **[!UICONTROL Request confirmation before sending messages]** 項。 取消勾選此選項後，訊息會在準備完成後不另行通知而傳送。

## 注釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。 您可以使用控制面板來檢視工作流程的執行狀態。 推播通知摘要窗格中的連結可讓您直接存取連結的元素（工作流程、促銷活動等）。

在可從行銷活動清單存取的父傳送中，您可以檢視已處理的傳送總數（根據設定活動時指定的匯總期間）。 **[!UICONTROL Push notification]** 若要這麼做，請選取以開啟父傳送區塊的詳 **[!UICONTROL Deployment]** 細資料檢視 ![](assets/wkf_dlv_detail_button.png)。

## 傳送具有工作流程的循環推播通知 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此範例中，根據行動應用程式的時區，每月的第一天晚上8點會傳送個人化推播通知給其訂閱者。 操作步驟：

1. 此活 **[!UICONTROL Scheduler]** 動可讓您在傳送開始前的工作流程天數開始，以便在任何指定時區的晚上8點將通知傳送給每位訂閱者：

   * 在欄位中， **[!UICONTROL Execution frequency]** 選取「每月」。
   * 在欄位中選擇8 **[!UICONTROL Time]** pm。
   * 選擇每月傳送的日期。
   * 為工作流選擇開始日期，至少在交貨開始前一天。 否則，如果所選時間已在其時區中過去，某些收件者可能會在一天後收到此訊息。
   * 在標籤 **[!UICONTROL Execution options]** 中，在欄位中選取您的工作流程將在哪個時 **[!UICONTROL Time zone]** 區開始。 例如，在這裡，工作流程將於太平洋時間的晚上8點開始，即當月第一天的一週，以便為所有適用的時區建立傳送。
   ![](assets/wkf_push_example_5.png)

1. 「查 **詢** 」活動可讓您鎖定20-30歲、已訂閱您行動應用程式且未開啟您傳送電子郵件的VIP客戶：

   * 選取對象（您的VIP客戶）並依年齡篩選。
   * 將「訂閱」拖 **放至應用程式元素** ，並放入工作區。 選 **擇「存在** 」，然後選擇要使用的行動應用程式。
   * 選擇您傳送給客戶的電子郵件。
   * 將「傳送記 **錄檔（記錄檔）** 」元素拖放至工作區，並選取「存在 **」** ，以鎖定所有收到電子郵件的客戶。
   * 將追蹤記錄( **追蹤)元素拖放至工作區中** ，並選取「不存在 **** 」以定位所有未開啟電子郵件的客戶。

      ![](assets/wkf_push_example_2.png)

1. 「推 **播通知** 」活動可讓您輸入訊息的內容，並選取您要使用的個人化欄位：

   * 選擇選 **[!UICONTROL Recurring notification]** 項。
   * 定義推播通知內容。 如需推播通知內容的詳細資訊，請參閱此 [節](../../channels/using/preparing-and-sending-a-push-notification.md)。
   * 在塊中 **[!UICONTROL Schedule]** 選擇 **[!UICONTROL Messages to be sent automatically on the time zone specified below]**。 在這裡，我們選擇了 **[!UICONTROL Time zone of the contact date]** 太平洋作為工作流 **[!UICONTROL Scheduler]**。
   * 在欄位 **[!UICONTROL Optimize the sending time per recipient]** 中，選擇 **[!UICONTROL Send at the recipient's time zone]**。

      ![](assets/wkf_push_example_4.png)

1. 按一下按 **[!UICONTROL Start]** 鈕以開始循環工作流程。

   ![](assets/wkf_push_example_3.png)

您的工作流程現在正在執行中。 它將於太平洋時間晚上 **[!UICONTROL Scheduler]** 8點的選定開始日期開始，然後會根據客戶時區，在當月的第一天8點傳送週期性推播。
