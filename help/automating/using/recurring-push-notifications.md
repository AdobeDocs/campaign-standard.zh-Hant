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


# 傳送具有工作流程{#sending-a-recurring-push-notification-with-a-workflow}的循環推播通知

![](assets/wkf_push_example_1.png)

在此範例中，根據行動應用程式的時區，每月的第一天晚上8點會傳送個人化推播通知給其訂閱者。

若要建立工作流程，請依照下列步驟進行：

1. [排程器](../../automating/using/scheduler.md)活動允許您在傳送開始前的工作流天數啟動，以便能夠在任意時區的晚上8點向每個訂戶發送通知：

   * 在&#x200B;**[!UICONTROL Execution frequency]**&#x200B;欄位中，選取「每月」。
   * 在&#x200B;**[!UICONTROL Time]**&#x200B;欄位中選擇8 pm。
   * 選擇每月傳送的日期。
   * 為工作流選擇開始日期，至少在交貨開始前一天。 否則，如果所選時間已在其時區中過去，某些收件者可能會在一天後收到此訊息。
   * 在&#x200B;**[!UICONTROL Execution options]**&#x200B;標籤中，從&#x200B;**[!UICONTROL Time zone]**&#x200B;欄位中選擇工作流程的開始時區。 例如，在這裡，工作流程將於太平洋時間的晚上8點開始，即當月第一天的一週，以便為所有適用的時區建立傳送。

   >[!NOTE]
   >
   >依預設，選取的時區是工作流程屬性中定義的時區（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

   ![](assets/wkf_push_example_5.png)

1. [Query](../../automating/using/query.md)活動可讓您定位20-30歲、已訂閱您行動應用程式且未開啟您傳送電子郵件的VIP客戶：

   * 選取對象（您的VIP客戶）並依年齡篩選。
   * 將&#x200B;**訂閱拖放至應用程式**&#x200B;元素至工作區。 選擇&#x200B;**Exists**&#x200B;並選擇要使用的移動應用程式。
   * 選擇您傳送給客戶的電子郵件。
   * 將&#x200B;**傳送記錄檔（記錄檔）**&#x200B;元素拖放至工作區，並選取&#x200B;**Exists**&#x200B;以鎖定收到電子郵件的所有客戶。
   * 將&#x200B;**追蹤記錄檔（追蹤）**&#x200B;元素拖放至工作區，並選取&#x200B;**不存在**&#x200B;來定位所有未開啟電子郵件的客戶。

      ![](assets/wkf_push_example_2.png)

1. [推播通知傳送](../../automating/using/push-notification-delivery.md)活動可讓您輸入訊息內容，並選取您要使用的個人化欄位：

   * 選擇&#x200B;**[!UICONTROL Recurring notification]**&#x200B;選項。
   * 定義推播通知內容。 如需推播通知內容的詳細資訊，請參閱此[章節](../../channels/using/preparing-and-sending-a-push-notification.md)。
   * 在&#x200B;**[!UICONTROL Schedule]**&#x200B;塊中，選擇&#x200B;**[!UICONTROL Messages to be sent automatically on the time zone specified below]**。 在此，我們選擇&#x200B;**[!UICONTROL Time zone of the contact date]**&#x200B;太平洋作為工作流&#x200B;**[!UICONTROL Scheduler]**。
   * 在 **[!UICONTROL Optimize the sending time per recipient]** 欄位中，選取 **[!UICONTROL Send at the recipient's time zone]**。

      ![](assets/wkf_push_example_4.png)

1. 按一下&#x200B;**[!UICONTROL Start]**&#x200B;按鈕，開始循環工作流程。

   ![](assets/wkf_push_example_3.png)

您的工作流程現在正在執行中。 它將於太平洋時間下午8點從&#x200B;**[!UICONTROL Scheduler]**&#x200B;的選定開始日期開始，然後會根據客戶時區，於每月的第一天晚上8點傳送循環推播。
