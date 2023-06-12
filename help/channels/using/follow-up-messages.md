---
title: 後續追蹤訊息
description: 瞭解如何建立、管理和傳送後續追蹤訊息。
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

後續訊息是預先定義的行銷傳遞範本，可用於工作流程，以傳送其他通訊給特定交易式訊息的收件者。

讓我們重複使用中說明的範例： [異動訊息傳遞操作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) 區段：系統會傳送購物車放棄電子郵件給您的網站使用者，他們已將產品新增至購物車，但離開網站而未完成購買。

您想要向所有收到購物車放棄通知但在三天後未開啟購物車的客戶傳送好記提醒。 他們將會根據所傳送第一封電子郵件中所使用的相同資料，收到後續追蹤訊息。

## 設定事件以傳送後續追蹤訊息 {#configuring-an-event-to-send-a-follow-up-message}

若要傳送後續訊息，您首先需要相應地設定與已收到之交易式訊息對應的事件。

1. 使用您建立用來傳送事件交易式訊息的相同事件設定。 另請參閱 [設定交易式事件](../../channels/using/configuring-transactional-event.md).
1. 設定事件時，請核取 **[!UICONTROL Create follow-up delivery template for this event]** 方塊中。

   ![](assets/message-center_follow-up-checkbox.png)

1. [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

發佈事件後，系統會自動建立交易式訊息及連結至新事件的後續傳送範本。 有關傳送後續追蹤訊息的詳細步驟，請參閱 [本節](#sending-a-follow-up-message).

## 存取後續追蹤訊息 {#accessing-the-follow-up-messages}

若要在工作流程中處理事件，需要傳遞範本。 不過，發佈事件時， [異動訊息](../../channels/using/editing-transactional-message.md) 建立的範本無法使用。 因此，您需要建立特定的後續傳送範本，以支援此事件型別，並作為工作流程中的範本使用。

若要存取此範本：

1. 按一下 **Adobe** 標誌，位於左上角。
1. 選取 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. 檢查 **[!UICONTROL Follow-up messages]** 方塊中。

   ![](assets/message-center_follow-up-search.png)

只顯示後續追蹤訊息。

>[!IMPORTANT]
>
>僅限具有下列專案的使用者： [管理](../../administration/using/users-management.md#functional-administrators) 角色可以存取及編輯交易式訊息。

## 傳送後續追蹤訊息 {#sending-a-follow-up-message}

建立後續傳送範本後，您便可在工作流程中使用它來傳送後續訊息。

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. 存取行銷活動清單並建立新的工作流程。

   另請參閱 [建立工作流程](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. 拖放 **[!UICONTROL Scheduler]** 活動至工作流程並開啟。 將執行頻率設定為每天一次。

   排程器活動會顯示在中 [排程器](../../automating/using/scheduler.md) 區段。

1. 拖放 **[!UICONTROL Query]** 活動至工作流程並開啟。

   「查詢」活動會顯示在中 [查詢](../../automating/using/query.md) 區段。

1. 若要對設定檔資源以外的資源執行查詢，請移至活動的 **[!UICONTROL Properties]** 標籤並按一下 **[!UICONTROL Resource]** 下拉式清單。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >依預設，活動會預先設定為搜尋設定檔。

1. 選取您要鎖定的事件，以便只存取此事件的資料。

   ![](assets/message-center_follow-up-query-resource.png)

1. 前往活動的 **[!UICONTROL Target]** 標籤，然後拖放 **[!UICONTROL Delivery logs (logs)]** 元素移入工作區。

   ![](assets/message-center_follow-up-delivery-logs.png)

   選取 **[!UICONTROL Exists]** 以定位收到電子郵件的所有客戶。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. 移動 **[!UICONTROL Tracking logs (tracking)]** 元素並選取「 」 **[!UICONTROL Does not exist]** 以鎖定所有未開啟電子郵件的客戶。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. 拖放您要鎖定的事件(**放棄購買** 在此範例中)從浮動視窗移入工作區。 然後定義規則以定位三天前傳送的所有訊息。

   ![](assets/message-center_follow-up-created.png)

   這表示會在執行工作流程三天前收到交易式訊息，且仍未開啟該訊息的所有收件者都會成為目標。

   按一下 **[!UICONTROL Confirm]** 以儲存查詢。

1. 拖放 **電子郵件傳遞** 活動放入您的工作流程。

   電子郵件傳送活動會顯示在中 [電子郵件傳遞](../../automating/using/email-delivery.md) 區段。

   ![](assets/message-center_follow-up-workflow.png)

   您也可以使用 [簡訊傳送](../../automating/using/sms-delivery.md) 或 [推播通知傳遞](../../automating/using/push-notification-delivery.md) 活動。 在此情況下，請務必選取 **[!UICONTROL Mobile (SMS)]** 或 **[!UICONTROL Mobile application]** 頻道。 請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。

1. 開啟 **電子郵件傳遞** 活動。 在建立精靈中，核取 **[!UICONTROL Follow-up messages]** 方塊並選取在發佈事件後建立的後續傳遞範本。

   ![](assets/message-center_follow-up-template.png)

1. 在後續訊息內容中，您可以新增個人化欄位，以善用您的事件內容。

   ![](assets/message-center_follow-up-content.png)

1. 透過選取「 」，尋找您在建立事件時定義的欄位 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. 另請參閱 [個人化交易式訊息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   這表示您可以運用第一次傳送事件時所使用的相同內容（包括擴充資料）來建立個人化的友善提醒。

1. 儲存活動並啟動工作流程。

工作流程啟動後，三天前收到購物車放棄通知但未開啟通知的每個客戶都會收到基於相同資料的後續追蹤訊息。

>[!NOTE]
>
>如果您已選取 **[!UICONTROL Profile]** 建立事件設定時，後續訊息也會利用Adobe Campaign行銷資料庫。 請參閱[設定檔交易式訊息](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)。
