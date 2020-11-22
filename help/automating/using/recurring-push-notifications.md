---
solution: Campaign Standard
product: campaign
title: 傳送具有工作流程的循環推播通知
description: 在此範例中，根據行動應用程式的時區，每月的第一天晚上8點會傳送個人化推播通知給其訂閱者。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# 傳送具有工作流程的循環推播通知 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此範例中，根據行動應用程式的時區，每月的第一天晚上8點會傳送個人化推播通知給其訂閱者。

若要建立工作流程，請依照下列步驟進行：

1. Scheduler [](../../automating/using/scheduler.md) （調度程式）活動允許您在傳送開始前的工作流天數開始，以便能夠在任何給定時區的晚上8點向每個訂戶發送通知：

   * In the **[!UICONTROL Execution frequency]** field, select Monthly.
   * 在欄位中選擇8 **[!UICONTROL Time]** pm。
   * 選擇每月傳送的日期。
   * 為工作流選擇開始日期，至少在交貨開始前一天。 否則，如果所選時間已在其時區中過去，某些收件者可能會在一天後收到此訊息。
   * 在標籤 **[!UICONTROL Execution options]** 中，在欄位中選取您的工作流程將在哪個時 **[!UICONTROL Time zone]** 區開始。 例如，在這裡，工作流程將於太平洋時間的晚上8點開始，即當月第一天的一週，以便為所有適用的時區建立傳送。

   >[!NOTE]
   >
   >依預設，選取的時區是工作流程屬性中定義的時區（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

   ![](assets/wkf_push_example_5.png)

1. 「查 [詢](../../automating/using/query.md) 」活動可讓您鎖定20-30歲、已訂閱您行動應用程式且未開啟您傳送電子郵件的VIP客戶：

   * 選取對象（您的VIP客戶）並依年齡篩選。
   * 將「訂閱」拖 **放至應用程式元素** ，並放入工作區。 選 **擇「存在** 」，然後選擇要使用的行動應用程式。
   * 選擇您傳送給客戶的電子郵件。
   * 將「傳送記 **錄檔（記錄檔）** 」元素拖放至工作區，並選取「存在 **」** ，以鎖定所有收到電子郵件的客戶。
   * 將追蹤記錄( **追蹤)元素拖放至工作區中** ，並選取「不存在 **** 」以定位所有未開啟電子郵件的客戶。

      ![](assets/wkf_push_example_2.png)

1. 「推 [播通知傳送](../../automating/using/push-notification-delivery.md) 」活動可讓您輸入訊息的內容，並選取您要使用的個人化欄位：

   * 選擇選 **[!UICONTROL Recurring notification]** 項。
   * 定義推播通知內容。 For more information on push notification content, refer to this [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In the **[!UICONTROL Schedule]** block, select **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. 在這裡，我們選擇了 **[!UICONTROL Time zone of the contact date]** 太平洋作為工作流 **[!UICONTROL Scheduler]**。
   * 在 **[!UICONTROL Optimize the sending time per recipient]** 欄位中，選取 **[!UICONTROL Send at the recipient's time zone]**。

      ![](assets/wkf_push_example_4.png)

1. 按一下按 **[!UICONTROL Start]** 鈕以開始循環工作流程。

   ![](assets/wkf_push_example_3.png)

您的工作流程現在正在執行中。 它將於太平洋時間晚上 **[!UICONTROL Scheduler]** 8點的選定開始日期開始，然後會根據客戶時區，在當月的第一天8點傳送週期性推播。
