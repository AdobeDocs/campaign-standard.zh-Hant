---
title: 使用工作流程傳送循環推播通知
description: 在此範例中，根據行動應用程式的時區，每個月的第一天晚上8點，都會傳送個人化推播通知給其訂閱者。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---

# 使用工作流程傳送循環推播通知 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此範例中，根據行動應用程式的時區，每個月的第一天晚上8點，都會傳送個人化推播通知給其訂閱者。

若要建立工作流程，請遵循下列步驟：

1. 此 [排程器](../../automating/using/scheduler.md) 活動可讓您在傳送開始前的工作流程天數開始，以便在任何指定時區的晚上8點將通知傳送給每個訂閱者：

   * 在 **[!UICONTROL Execution frequency]** 欄位，選擇「每月」。
   * 在 **[!UICONTROL Time]** 欄位。
   * 選擇每個月傳送傳送的日期。
   * 選取工作流程的開始日期，至少在傳送開始前一天。 否則，如果所選時間已在其時區中過，某些收件者可能會在一天後收到訊息。
   * 在 **[!UICONTROL Execution options]** 頁簽，選擇工作流將在哪個時區開始 **[!UICONTROL Time zone]** 欄位。 例如，在此，工作流程將在太平洋時間晚上8點開始（在當月第一天的一週前），以允許為所有適用時區建立傳送的一些時間。

   >[!NOTE]
   >
   >依預設，選取的時區是工作流程屬性中定義的時區（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

   ![](assets/wkf_push_example_5.png)

1. 此 [查詢](../../automating/using/query.md) 活動可讓您鎖定年齡介於20至30歲、已訂閱您行動應用程式且未開啟您所傳送電子郵件的VIP客戶：

   * 選取對象(您的VIP客戶)並依其年齡篩選。
   * 拖放 **應用程式的訂閱** 元素。 選擇 **存在** 並選取您要使用的行動應用程式。
   * 選取您傳送給客戶的電子郵件。
   * 拖放 **傳送記錄（記錄檔）** 元素並選取 **存在** 定位收到電子郵件的所有客戶。
   * 拖放 **追蹤記錄（追蹤）** 元素並選取 **不存在** 定位未開啟電子郵件的所有客戶。

      ![](assets/wkf_push_example_2.png)

1. 此 [推播通知傳送](../../automating/using/push-notification-delivery.md) 活動可讓您輸入訊息的內容，以及選取您要使用的個人化欄位：

   * 選取 **[!UICONTROL Recurring notification]** 選項。
   * 定義推播通知內容。 如需推播通知內容的詳細資訊，請參閱 [節](../../channels/using/preparing-and-sending-a-push-notification.md).
   * 在 **[!UICONTROL Schedule]** 塊，選擇 **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. 在這裡，我們選擇了 **[!UICONTROL Time zone of the contact date]** 在工作流程中 **[!UICONTROL Scheduler]**.
   * 在 **[!UICONTROL Optimize the sending time per recipient]** 欄位中，選取 **[!UICONTROL Send at the recipient's time zone]**。

      ![](assets/wkf_push_example_4.png)

1. 按一下 **[!UICONTROL Start]** 按鈕來啟動循環工作流程。

   ![](assets/wkf_push_example_3.png)

您的工作流程現在正在執行。 會從 **[!UICONTROL Scheduler]** 太平洋時間晚上8點，循環推播將根據客戶時區，於每月第一天晚上8點傳送。
