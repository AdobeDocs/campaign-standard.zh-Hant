---
solution: Campaign Standard
product: campaign
title: 後續訊息
description: 瞭解如何建立和發佈後續訊息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 4%

---


# 後續訊息{#follow-up-messages}

您可以傳送後續訊息給收到特定交易訊息的客戶。 若要這麼做，您必須設定針對對應事件的工作流程。

讓我們重複使用[事務性消息傳送操作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)部分中介紹的示例：購物車放棄電子郵件會傳送給將產品新增至購物車的網站使用者，但是離開網站卻未進行購買。

您想要傳送友好提醒給所有收到購物車放棄通知但三天後未開啟通知的客戶。

然後，每位相關客戶都會根據第一次傳送電子郵件中使用的相同資料收到後續訊息。

## 訪問後續消息{#accessing-the-follow-up-messages}

一旦您建立並發佈事件（根據上述[example](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)的放棄購物車行為），就會自動建立對應的交易訊息和後續訊息。

配置步驟顯示在[配置事件以發送後續消息](../../administration/using/configuring-transactional-messaging.md#configuring-an-event-to-send-a-follow-up-message)部分中。

若要處理工作流程中的事件，需要傳送範本。 但是，發佈事件時，所建立的[事務性消息](../../channels/using/event-transactional-messages.md)不能用作模板。 因此，您需要建立特定的後續傳送範本，以支援此事件類型，並用作工作流程中的範本。

若要存取此範本：

1. 按一下左上角的&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;徽標。
1. 選擇&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**。
1. 選中左窗格中的&#x200B;**[!UICONTROL Follow-up messages]**&#x200B;框。

   ![](assets/message-center_follow-up-search.png)

僅顯示後續消息。

>[!NOTE]
>
>您必須是 **[!UICONTROL Administrators (all units)]** 安全群組的成員，才能存取交易式訊息。

## 發送後續消息{#sending-a-follow-up-message}

建立後續傳送範本後，您就可以在工作流程中使用它來傳送後續訊息。

1. 存取行銷活動清單並建立新的工作流程。

   請參閱[建立工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)。

1. 將&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動拖放至工作流程並開啟。 將執行頻率設為一天一次。

   「調度程式」活動顯示在[Scheduler](../../automating/using/scheduler.md)部分。

1. 將&#x200B;**[!UICONTROL Query]**&#x200B;活動拖放至工作流程並開啟。

   查詢活動顯示在[Query](../../automating/using/query.md)節中。

1. 要對配置檔案資源以外的資源運行查詢，請轉至活動的&#x200B;**[!UICONTROL Properties]**&#x200B;頁籤，然後按一下&#x200B;**[!UICONTROL Resource]**&#x200B;下拉清單。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >依預設，活動會預先設定為搜尋設定檔。

1. 選擇您要定位的事件，以便您僅能存取此事件的資料。

   ![](assets/message-center_follow-up-query-resource.png)

1. 前往活動的&#x200B;**[!UICONTROL Target]**&#x200B;標籤，並從浮動視窗拖放&#x200B;**[!UICONTROL Delivery logs (logs)]**&#x200B;元素至工作區。

   ![](assets/message-center_follow-up-delivery-logs.png)

   選擇&#x200B;**[!UICONTROL Exists]**&#x200B;以鎖定收到電子郵件的所有客戶。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. 將&#x200B;**[!UICONTROL Tracking logs (tracking)]**&#x200B;元素從浮動視窗移至工作區，然後選取&#x200B;**[!UICONTROL Does not exist]**&#x200B;來定位所有未開啟電子郵件的客戶。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. 從浮動視窗拖放您要定位的事件（在此範例中為&#x200B;**放棄購物車**）至工作區。 然後定義規則，以定位三天前傳送的所有訊息。

   ![](assets/message-center_follow-up-created.png)

   這表示所有在工作流執行三天前收到交易性消息但尚未開啟該消息的接收者都將定位。

   按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;保存查詢。

1. 將&#x200B;**電子郵件傳送**&#x200B;活動拖放至您的工作流程中。

   「電子郵件傳送」活動會顯示在[「電子郵件傳送」](../../automating/using/email-delivery.md)區段中。

   ![](assets/message-center_follow-up-workflow.png)

   您也可以使用[SMS傳送](../../automating/using/sms-delivery.md)或[行動應用程式傳送](../../automating/using/push-notification-delivery.md)活動。 在這種情況下，請務必在建立事件配置時選擇&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;或&#x200B;**[!UICONTROL Mobile application]**&#x200B;通道。 請參閱[建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。

1. 開啟&#x200B;**電子郵件傳送**&#x200B;活動。 在建立精靈中，勾選&#x200B;**[!UICONTROL Follow-up messages]**&#x200B;方塊並選取發佈事件後建立的後續傳送範本。

   ![](assets/message-center_follow-up-template.png)

1. 在後續的訊息內容中，您可以新增個人化欄位，以運用活動的內容。

   ![](assets/message-center_follow-up-content.png)

1. 選擇&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**，以查找建立事件時定義的欄位。 請參閱[個人化事務性消息](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

   ![](assets/message-center_follow-up-personalization.png)

   這表示您可以運用第一次傳送活動時使用的相同內容（包括豐富資料）來建立個人化的友好提醒。

1. 儲存活動並啟動工作流程。

工作流程啟動後，每位在三天前收到購物車放棄通知但未開啟該通知的客戶，都會收到以相同資料為基礎的後續訊息。

>[!NOTE]
>
>如果您在建立事件設定時選取了&#x200B;**[!UICONTROL Profile]**&#x200B;定位維度，後續訊息也會運用Adobe Campaign行銷資料庫。 請參閱[設定檔交易式訊息](../../channels/using/profile-transactional-messages.md)。
