---
title: 設定檔交易式訊息
description: 瞭解如何建立與發佈設定檔交易式訊息。
page-status-flag: never-activated
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 95%

---


# 設定檔交易式訊息{#profile-transactional-messages}

您可以根據客戶行銷設定檔傳送交易式訊息，這可讓您：

* 套用行銷類型規則，例如 **[!UICONTROL Denylisted address]** 或[疲勞規則](../../sending/using/fatigue-rules.md)。
* 在訊息中包含取消訂閱連結。
* 將交易式訊息新增至全域傳送報告。
* 在客戶歷程中善用交易式訊息。

一旦您建立並發佈事件（如上述[範例](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)所述的購物車放棄率）之後，就會自動建立對應的交易式訊息。

設定步驟顯示在[設定事件以傳送設定檔交易式訊息](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)區段中。

為了讓事件觸發傳送交易式訊息，您必須個人化訊息，然後再測試之後發佈訊息。

>[!NOTE]
>
>您必須是 **[!UICONTROL Administrators (all units)]** 安全群組的成員，才能存取交易式訊息。
>
>疲勞規則與設定檔交易式訊息相容。請參閱[疲勞規則](../../sending/using/fatigue-rules.md)。

## 請參閱設定檔交易式訊息 {#sending-a-profile-transactional-message}。

建立、個人化及發佈設定檔交易式訊息的步驟與事件交易式訊息的步驟相同。請參閱[事件交易式訊息](../../channels/using/event-transactional-messages.md)。

差異列示於下方。

1. 移至建立的交易式訊息，以編輯其內容。
1. 在交易式訊息中，按一下 **[!UICONTROL Content]** 區段。除了交易範本以外，您也可以選取任何電子郵件範本目標定位 **[!UICONTROL Profile]**。

   ![](assets/message-center_marketing_templates.png)

1. 選取預設的電子郵件範本。

   它與所有行銷電子郵件類似，其中包含取消訂閱連結。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   此外，與以即時事件為基礎的設定相反，您可以直接存取所有設定檔資訊，以個人化您的訊息。請參閱[插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)。

1. 儲存您的變更並發佈訊息。請參閱[發佈交易式訊息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

## 監控設定檔交易式訊息傳送 {#monitoring-a-profile-transactional-message-delivery}

一旦訊息發佈並完成網站整合後，您就能監控傳送。

1. 若要檢視訊息傳送記錄檔，請按一下 **[!UICONTROL Deployment]** 區塊右下方的圖示。

   如需存取記錄檔的詳細資訊，請參閱[監控傳送](../../sending/using/monitoring-a-delivery.md)。

1. 選取 **[!UICONTROL Sending logs]** 索引標籤。在 **[!UICONTROL Status]** 欄中，**[!UICONTROL Sent]** 表示設定檔已選取加入。

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as denylisted addresses.

   ![](assets/message-center_marketing_exclusion_logs.png)

對於已選取退出的任何設定檔，**[!UICONTROL Denylisted address]**　類型規則會排除相對應的收件人。

此規則是特定類型的一部分，其適用於以 **[!UICONTROL Profile]** 表格為基礎的所有交易式訊息。

![](assets/message-center_marketing_typology.png)

**相關主題**：

* [網站整合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [類型](../../sending/using/about-typology-rules.md)

