---
title: 設定檔交易式訊息
description: 瞭解如何建立和發佈個人資料交易訊息。
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
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 1%

---


# 設定檔交易式訊息{#profile-transactional-messages}

您可以根據客戶行銷個人檔案傳送交易訊息，這可讓您：

* 套用行銷類型學規則，例 **[!UICONTROL Address on block list]** 如 [疲勞規則](../../sending/using/fatigue-rules.md)。
* 在訊息中加入取消訂閱連結。
* 將交易訊息新增至全域傳送報表。
* 在客戶歷程中運用交易訊息。

在您建立並發佈事件後(如上例所示 [](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) ，購物車放棄率)，就會自動建立對應的交易訊息。

配置步驟顯示在配置事 [件以發送配置檔案事務性消息部分](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

為了讓事件觸發傳送交易訊息，您必須個人化訊息，然後測試並發佈訊息。

>[!NOTE]
>
>要訪問事務性消息，您必須是安全組的一 **[!UICONTROL Administrators (all units)]** 部分。
>
>疲勞規則與描述檔交易訊息相容。 請參 [閱疲勞規則](../../sending/using/fatigue-rules.md)。

## 傳送描述檔交易訊息 {#sending-a-profile-transactional-message}

建立、個人化和發佈配置檔案事務性消息的步驟與事件事務性消息的步驟相同。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

差異列於下方。

1. 轉至為編輯而建立的交易訊息。
1. 在事務性消息中，按一下該 **[!UICONTROL Content]** 部分。 除了交易範本外，您也可以選擇任何電子郵件範本定位 **[!UICONTROL Profile]**。

   ![](assets/message-center_marketing_templates.png)

1. 選取預設的電子郵件範本。

   與所有行銷電子郵件類似，它包含取消訂閱連結。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   此外，與基於即時事件的配置不同，您可以直接訪問所有配置檔案資訊以個性化您的消息。 請參 [閱插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)。

1. 儲存變更並發佈訊息。 請參 [閱發佈交易訊息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

## 監控配置檔案事務性消息傳送 {#monitoring-a-profile-transactional-message-delivery}

一旦訊息發佈並完成網站整合後，您就可以監控傳送。

1. 要查看消息傳送日誌，請按一下塊右下方的圖 **[!UICONTROL Deployment]** 標。

   如需存取記錄檔的詳細資訊，請參 [閱監控傳送](../../sending/using/monitoring-a-delivery.md)。

1. 選擇選 **[!UICONTROL Sending logs]** 項卡。 在欄中 **[!UICONTROL Status]** ，指 **[!UICONTROL Sent]** 出描述檔已選擇加入。

   ![](assets/message-center_marketing_sending_logs.png)

1. 選擇該 **[!UICONTROL Exclusions logs]** 頁籤可查看已從消息目標中排除的收件人，如塊清單中的地址。

   ![](assets/message-center_marketing_exclusion_logs.png)

對於任何已選擇退出的設定檔，排 **[!UICONTROL Address on block list]** 除了對應的收件者。

此規則是特定類型學的一部分，適用於基於表的所有事務性消 **[!UICONTROL Profile]** 息。

![](assets/message-center_marketing_typology.png)

**相關主題**:

* [網站整合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [類型](../../sending/using/about-typology-rules.md)

