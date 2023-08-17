---
title: 使用工作流程傳送循環推播通知
description: 在此範例中，個人化推播通知會根據訂閱者的時區，在每月的第一天晚上8點傳送給行動應用程式
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---

# 使用工作流程傳送循環推播通知 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此範例中，個人化推播通知會根據訂閱者的時區，於每月第一天晚上8點傳送給行動應用程式的訂閱者。

若要建置工作流程，請遵循下列步驟：

1. 此 [排程器](../../automating/using/scheduler.md) 活動可讓您在傳送開始前幾天啟動工作流程，以便能夠在任何指定時區的晚上8點將通知傳送給每個訂閱者：

   * 在 **[!UICONTROL Execution frequency]** 欄位中，選取每月。
   * 選取8 pm的 **[!UICONTROL Time]** 欄位。
   * 選擇每月傳送傳遞的日期。
   * 請為工作流程選取開始日期，至少在開始傳送的前一天。 否則，如果所選時間已在其時區中經過，則某些收件者可能會在隔天收到訊息。
   * 在 **[!UICONTROL Execution options]** 索引標籤中，選取工作流程將在哪個時區開始 **[!UICONTROL Time zone]** 欄位。 舉例來說，工作流程將在太平洋時間晚上8點（該月第一天的前一週）開始，以便給建立所有適用時區的傳送留出一些時間。

   >[!NOTE]
   >
   >依預設，選取的時區是工作流程屬性中定義的時區（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

   ![](assets/wkf_push_example_5.png)

1. 此 [查詢](../../automating/using/query.md) 活動可讓您鎖定年齡介於20到30歲、已訂閱您的行動應用程式且未開啟您傳送之電子郵件的VIP客戶：

   * 選取對象(您的VIP客戶)並根據其年齡進行篩選。
   * 拖放 **應用程式的訂閱** 元素加入工作區。 選取 **存在** 並選取您要使用的行動應用程式。
   * 選取您傳送給客戶的電子郵件。
   * 拖放 **傳遞記錄（記錄）** 元素並選取 **存在** 以定位所有收到電子郵件的客戶。
   * 拖放 **追蹤記錄（追蹤）** 元素並選取 **不存在** 將目標鎖定在所有未開啟電子郵件的客戶。

     ![](assets/wkf_push_example_2.png)

1. 此 [推播通知傳遞](../../automating/using/push-notification-delivery.md) 活動可讓您輸入訊息內容，並選取您要使用的個人化欄位：

   * 選取 **[!UICONTROL Recurring notification]** 選項。
   * 定義推播通知內容。 如需推播通知內容的詳細資訊，請參閱此 [區段](../../channels/using/preparing-and-sending-a-push-notification.md).
   * 在 **[!UICONTROL Schedule]** 區塊，選取 **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. 在此，我們選擇了 **[!UICONTROL Time zone of the contact date]** 太平洋如工作流程一樣 **[!UICONTROL Scheduler]**.
   * 在 **[!UICONTROL Optimize the sending time per recipient]** 欄位中，選取 **[!UICONTROL Send at the recipient's time zone]**。

     ![](assets/wkf_push_example_4.png)

1. 按一下 **[!UICONTROL Start]** 按鈕以開始您的週期性工作流程。

   ![](assets/wkf_push_example_3.png)

您的工作流程目前正在執行中。 它將在的所選開始日期開始 **[!UICONTROL Scheduler]** 太平洋時間晚上8點，系統會根據客戶時區，在該月的每個第一天晚上8點傳送週期性推播。
