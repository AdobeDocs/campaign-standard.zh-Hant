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

1. [排程器](../../automating/using/scheduler.md)活動可讓您在傳送開始前的工作流程天數開始，以便能夠在任何指定時區的晚上8點將通知傳送給每個訂閱者：

   * 在&#x200B;**[!UICONTROL Execution frequency]**&#x200B;欄位中，選擇每月。
   * 在&#x200B;**[!UICONTROL Time]**&#x200B;欄位中選取下午8點。
   * 選擇每個月傳送傳送的日期。
   * 選取工作流程的開始日期，至少在傳送開始前一天。 否則，如果所選時間已在其時區中過，某些收件者可能會在一天後收到訊息。
   * 在&#x200B;**[!UICONTROL Execution options]**&#x200B;標籤中，在&#x200B;**[!UICONTROL Time zone]**&#x200B;欄位中選取工作流程將在哪個時區啟動。 例如，在此，工作流程將在太平洋時間晚上8點開始（在當月第一天的一週前），以允許為所有適用時區建立傳送的一些時間。

   >[!NOTE]
   >
   >依預設，選取的時區是工作流程屬性中定義的時區（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

   ![](assets/wkf_push_example_5.png)

1. [Query](../../automating/using/query.md)活動可讓您鎖定年齡介於20至30歲、已訂閱您行動應用程式且未開啟您所傳送電子郵件的VIP客戶：

   * 選取對象(您的VIP客戶)並依其年齡篩選。
   * 將&#x200B;**「應用程式訂閱**」元素拖放至工作區。 選擇&#x200B;**存在**&#x200B;並選擇要使用的移動應用程式。
   * 選取您傳送給客戶的電子郵件。
   * 將&#x200B;**傳送記錄檔（記錄檔）**&#x200B;元素拖放至工作區，並選取&#x200B;**Exists**&#x200B;來鎖定收到電子郵件的所有客戶。
   * 將&#x200B;**追蹤記錄（追蹤）**&#x200B;元素拖放至工作區中，並選取&#x200B;**不存在**&#x200B;來鎖定所有未開啟電子郵件的客戶。

      ![](assets/wkf_push_example_2.png)

1. [推播通知傳送](../../automating/using/push-notification-delivery.md)活動可讓您輸入訊息的內容，並選取您要使用的個人化欄位：

   * 選擇&#x200B;**[!UICONTROL Recurring notification]**&#x200B;選項。
   * 定義推播通知內容。 如需推播通知內容的詳細資訊，請參閱此[區段](../../channels/using/preparing-and-sending-a-push-notification.md)。
   * 在&#x200B;**[!UICONTROL Schedule]**&#x200B;塊中，選擇&#x200B;**[!UICONTROL Messages to be sent automatically on the time zone specified below]**。 在此處，我們選擇了&#x200B;**[!UICONTROL Time zone of the contact date]**&#x200B;太平洋，如工作流&#x200B;**[!UICONTROL Scheduler]**&#x200B;中。
   * 在 **[!UICONTROL Optimize the sending time per recipient]** 欄位中，選取 **[!UICONTROL Send at the recipient's time zone]**。

      ![](assets/wkf_push_example_4.png)

1. 按一下&#x200B;**[!UICONTROL Start]**&#x200B;按鈕，開始循環工作流程。

   ![](assets/wkf_push_example_3.png)

您的工作流程現在正在執行。 它會在太平洋時間下午8點從&#x200B;**[!UICONTROL Scheduler]**&#x200B;的所選開始日期開始，然後會根據客戶時區，在每月的第一天晚上8點傳送週期性推播。
