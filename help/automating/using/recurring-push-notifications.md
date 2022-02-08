---
title: 使用工作流發送循環推送通知
description: 在本示例中，根據移動應用程式的時區，每月的第一天晚上8點向其訂閱者發送個性化推送通知
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---

# 使用工作流發送循環推送通知 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在本示例中，根據移動應用程式的時區，每月的第一天晚上8點向其訂戶發送個性化推送通知。

要構建工作流，請執行以下步驟：

1. 的 [調度程式](../../automating/using/scheduler.md) 活動允許您在交貨開始前的幾天啟動工作流，以便能夠在任何給定時區的晚上8點向每個訂戶發送通知：

   * 在 **[!UICONTROL Execution frequency]** 欄位，選擇「每月」。
   * 在 **[!UICONTROL Time]** 的子菜單。
   * 選擇每月發送交貨的日期。
   * 選擇工作流的起始日期，至少在交貨開始前一天。 否則，如果所選時間已在其時區中過去，某些收件人可能會在一天後收到該消息。
   * 在 **[!UICONTROL Execution options]** 頁籤，選擇工作流將在哪個時區啟動 **[!UICONTROL Time zone]** 的子菜單。 例如，在此，工作流將在太平洋時間晚8點開始，即在月的第一天前一週，以允許為所有適用的時區建立交貨的時間。

   >[!NOTE]
   >
   >依預設，選取的時區是工作流程屬性中定義的時區（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

   ![](assets/wkf_push_example_5.png)

1. 的 [查詢](../../automating/using/query.md) 活動允許您針對20VIP至30歲之間、已訂閱移動應用程式且未開啟您發送的電子郵件的客戶：

   * 選擇受眾(您的VIP客戶)並篩選其年齡。
   * 拖放 **對應用程式的訂閱** 元素。 選擇 **存在** 並選擇要使用的移動應用程式。
   * 選擇您發送給客戶的電子郵件。
   * 拖放 **交付日誌（日誌）** 元素到工作區並選取 **存在** 以接收該電子郵件的所有客戶為目標。
   * 拖放 **跟蹤日誌（跟蹤）** 元素到工作區並選取 **不存在** 瞄準所有未開啟電子郵件的客戶。

      ![](assets/wkf_push_example_2.png)

1. 的 [推送通知傳遞](../../automating/using/push-notification-delivery.md) 活動允許您輸入消息的內容，並選擇要使用的個性化欄位：

   * 選擇 **[!UICONTROL Recurring notification]** 的雙曲餘切值。
   * 定義推送通知內容。 有關推送通知內容的詳細資訊，請參閱此 [節](../../channels/using/preparing-and-sending-a-push-notification.md)。
   * 在 **[!UICONTROL Schedule]** 塊，選擇 **[!UICONTROL Messages to be sent automatically on the time zone specified below]**。 我們選了 **[!UICONTROL Time zone of the contact date]** 與工作流中相同的太平洋 **[!UICONTROL Scheduler]**。
   * 在 **[!UICONTROL Optimize the sending time per recipient]** 欄位中，選取 **[!UICONTROL Send at the recipient's time zone]**。

      ![](assets/wkf_push_example_4.png)

1. 按一下 **[!UICONTROL Start]** 按鈕啟動循環工作流。

   ![](assets/wkf_push_example_3.png)

您的工作流正在運行。 它將從選定的開始日期開始 **[!UICONTROL Scheduler]** 太平洋時間晚8點，將根據客戶時區的不同，在每月的第一天8點發送定期推送。
