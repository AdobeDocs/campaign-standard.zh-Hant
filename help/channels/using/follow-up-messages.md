---
title: 後續追蹤訊息
description: 了解如何建立、管理和傳送後續訊息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 0a05cf20-7c8f-406b-acfd-7aece2c5dd26
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 2%

---

# 後續追蹤訊息 {#follow-up-messages}

後續訊息是預先定義的行銷傳送範本，可用於工作流程，以傳送其他通訊給特定交易式訊息的收件者。

讓我們重複使用 [交易式訊息傳送操作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) 小節：購物車放棄電子郵件會傳送給將產品新增至購物車，但未進行購買便離開網站的網站使用者。

您想要傳送好記提醒給收到購物車放棄通知，但三天後未開啟通知的所有客戶。 他們將會收到後續訊息，其依據是第一封電子郵件中所使用的相同資料。

## 設定事件以傳送後續訊息 {#configuring-an-event-to-send-a-follow-up-message}

若要傳送後續訊息，您必須先相應地設定與已接收的交易式訊息相對應的事件。

1. 使用您建立的事件設定，以傳送事件交易式訊息。 請參閱 [設定交易式事件](../../channels/using/configuring-transactional-event.md).
1. 設定事件時，請核取 **[!UICONTROL Create follow-up delivery template for this event]** 方塊，再發佈事件。

   ![](assets/message-center_follow-up-checkbox.png)

1. [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

發佈事件後，系統會自動建立連結至新事件的交易式訊息和後續傳送範本。 如需後續訊息的傳送步驟，請參閱 [本節](#sending-a-follow-up-message).

## 存取後續訊息 {#accessing-the-follow-up-messages}

若要處理工作流程中的事件，需要傳遞範本。 不過，發佈事件時， [異動訊息](../../channels/using/editing-transactional-message.md) 建立的無法作為範本使用。 因此，您需要建立特定的後續傳送範本，專門設計以支援此事件類型，並用作工作流程中的範本。

若要存取此範本：

1. 按一下 **Adobe** 徽標，在左上角。
1. 選擇 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. 檢查 **[!UICONTROL Follow-up messages]** 框。

   ![](assets/message-center_follow-up-search.png)

只會顯示後續訊息。

>[!IMPORTANT]
>
>僅使用 [管理](../../administration/using/users-management.md#functional-administrators) 角色可以存取及編輯交易式訊息。

## 傳送後續訊息 {#sending-a-follow-up-message}

建立後續傳送範本後，您就可以在工作流程中使用該範本，以傳送後續訊息。

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. 存取行銷活動清單並建立新的工作流程。

   請參閱 [建立工作流程](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. 拖放 **[!UICONTROL Scheduler]** 活動並開啟至工作流程。 將執行頻率設為一天一次。

   排程器活動會顯示在 [排程器](../../automating/using/scheduler.md) 區段。

1. 拖放 **[!UICONTROL Query]** 活動並開啟至工作流程。

   「查詢」活動會顯示在 [查詢](../../automating/using/query.md) 區段。

1. 若要對設定檔資源以外的資源執行查詢，請前往活動的 **[!UICONTROL Properties]** ，然後按一下 **[!UICONTROL Resource]** 下拉式清單。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >依預設，活動會預先設定為搜尋設定檔。

1. 選取您要定位的事件，以便您只能存取此事件中的資料。

   ![](assets/message-center_follow-up-query-resource.png)

1. 前往活動的 **[!UICONTROL Target]** 標籤，並拖放 **[!UICONTROL Delivery logs (logs)]** 元素（從浮動視窗移入工作區）。

   ![](assets/message-center_follow-up-delivery-logs.png)

   選擇 **[!UICONTROL Exists]** 定位收到電子郵件的所有客戶。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. 移動 **[!UICONTROL Tracking logs (tracking)]** 從浮動視窗到工作區的元素，並選取 **[!UICONTROL Does not exist]** 定位未開啟電子郵件的所有客戶。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. 拖放您正在定位的事件(**放棄購買** 在此範例中)從浮動視窗移入工作區。 然後定義規則，以定位三天前傳送的所有訊息。

   ![](assets/message-center_follow-up-created.png)

   這表示所有在執行工作流程三天前收到交易式訊息但尚未開啟的收件者，都會設為目標。

   按一下 **[!UICONTROL Confirm]** ，保存查詢。

1. 拖放 **電子郵件傳送** 活動移入工作流程。

   電子郵件傳送活動會顯示在 [電子郵件傳送](../../automating/using/email-delivery.md) 區段。

   ![](assets/message-center_follow-up-workflow.png)

   您也可以使用 [簡訊傳送](../../automating/using/sms-delivery.md) 或 [推播通知傳送](../../automating/using/push-notification-delivery.md) 活動。 在此情況下，請務必選取 **[!UICONTROL Mobile (SMS)]** 或 **[!UICONTROL Mobile application]** 建立事件設定時的通道。 請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。

1. 開啟 **電子郵件傳送** 活動。 在建立精靈中，核取 **[!UICONTROL Follow-up messages]** 方塊，然後選取發佈事件後建立的後續傳送範本。

   ![](assets/message-center_follow-up-template.png)

1. 在後續訊息內容中，您可以新增個人化欄位，以運用事件的內容。

   ![](assets/message-center_follow-up-content.png)

1. 透過選取 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. 請參閱 [個人化交易式訊息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   這表示您可以運用第一次傳送事件時使用的相同內容，包括擴充資料，以建立個人化的好記提醒。

1. 儲存活動並啟動工作流程。

工作流程開始後，每個在三天前收到購物車放棄通知但未開啟的客戶，都會收到以相同資料為基礎的後續訊息。

>[!NOTE]
>
>如果您選取 **[!UICONTROL Profile]** 建立事件設定時的目標維度，後續訊息也會運用Adobe Campaign行銷資料庫。 請參閱[設定檔交易式訊息](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)。
