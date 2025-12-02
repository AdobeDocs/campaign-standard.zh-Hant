---
title: 使用工作流程傳送循環推播通知
description: 在此範例中，個人化推播通知會根據訂閱者的時區，在每月的第一天晚上8點傳送給行動應用程式
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 5%

---

# 使用工作流程傳送循環推播通知 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此範例中，個人化推播通知會根據訂閱者的時區，於每月第一天晚上8點傳送給行動應用程式的訂閱者。

若要建置工作流程，請遵循下列步驟：

1. [排程器](../../automating/using/scheduler.md)活動可讓您在傳送開始前啟動工作流程天數，以便在任何指定時區的晚上8點將通知傳送給每個訂閱者：

   * 在&#x200B;**[!UICONTROL Execution frequency]**&#x200B;欄位中，選取[每月]。
   * 在&#x200B;**[!UICONTROL Time]**&#x200B;欄位中選取8 pm。
   * 選擇每月傳送傳遞的日期。
   * 請為工作流程選取開始日期，至少在開始傳送的前一天。 否則，如果所選時間已在其時區中經過，則某些收件者可能會在隔天收到訊息。
   * 在&#x200B;**[!UICONTROL Execution options]**&#x200B;索引標籤中，選取工作流程將在&#x200B;**[!UICONTROL Time zone]**&#x200B;欄位中開始的時區。 舉例來說，工作流程將在太平洋時間晚上8點（該月第一天的前一週）開始，以便給建立所有適用時區的傳送留出一些時間。

   >[!NOTE]
   >
   >依預設，選取的時區是工作流程屬性中定義的時區（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

   ![](assets/wkf_push_example_5.png)

1. [查詢](../../automating/using/query.md)活動可讓您鎖定年齡介於20到30歲、已訂閱您的行動應用程式且未開啟您傳送之電子郵件的VIP客戶：

   * 選取對象(您的VIP客戶)，並根據其年齡篩選。
   * 將&#x200B;**Subscriptions to an application**&#x200B;元素拖放至工作區。 選取&#x200B;**存在**，然後選取您要使用的行動應用程式。
   * 選取您傳送給客戶的電子郵件。
   * 將&#x200B;**傳遞記錄（記錄）**&#x200B;元素拖放到工作區中，並選取&#x200B;**存在**&#x200B;以鎖定所有收到電子郵件的客戶。
   * 將&#x200B;**追蹤記錄（追蹤）**&#x200B;元素拖放到工作區中，並選取「**不存在**」以鎖定所有未開啟電子郵件的客戶。

     ![](assets/wkf_push_example_2.png)

1. [推播通知傳遞](../../automating/using/push-notification-delivery.md)活動可讓您輸入訊息的內容，並選取您要使用的個人化欄位：

   * 選取 **[!UICONTROL Recurring notification]** 選項。
   * 定義推播通知內容。 如需推播通知內容的詳細資訊，請參閱此[區段](../../channels/using/preparing-and-sending-a-push-notification.md)。
   * 在&#x200B;**[!UICONTROL Schedule]**&#x200B;區塊中，選取&#x200B;**[!UICONTROL Messages to be sent automatically on the time zone specified below]**。 在此處，我們在工作流程&#x200B;**[!UICONTROL Time zone of the contact date]**&#x200B;中選擇了&#x200B;**[!UICONTROL Scheduler]** Pacific。
   * 在 **[!UICONTROL Optimize the sending time per recipient]** 欄位中，選取 **[!UICONTROL Send at the recipient's time zone]**。

     ![](assets/wkf_push_example_4.png)

1. 按一下&#x200B;**[!UICONTROL Start]**&#x200B;按鈕以開始您的週期性工作流程。

   ![](assets/wkf_push_example_3.png)

您的工作流程目前正在執行中。 這將會在太平洋時間晚上8點在&#x200B;**[!UICONTROL Scheduler]**&#x200B;的選定開始日期開始，然後依據客戶時區將於每月第一天晚上8點傳送週期性推播。
