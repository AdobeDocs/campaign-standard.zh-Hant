---
solution: Campaign Standard
product: campaign
title: 測試異動訊息
description: 瞭解如何在Adobe Campaign中測試交易訊息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 39%

---


# 測試交易式訊息 {#testing-a-transactional-message}

在發佈交易訊息之前，您可以建立特定測試設定檔，讓您正確檢查訊息。

## 定義特定測試配置檔案{#defining-specific-test-profile}

定義將連結至您事件的測試設定檔，讓您預覽訊息並傳送相關證明。

1. 在[事務性消息儀表板](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)中，按一下&#x200B;**[!UICONTROL Create test profile]**&#x200B;按鈕。

   ![](assets/message-center_test-profile.png)

1. 在 **[!UICONTROL Event data used for personalization]** 區段中指定要以 JSON 格式傳送的資訊。這是預覽訊息與測試設定檔收到校樣時，將會使用的內容。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >如果您豐富了消息，還可以輸入與其它表相關的資訊，如&#x200B;**[!UICONTROL Profile]**。 請參閱[豐富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)和[個人化事務性消息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)。

1. 建立後，測試描述檔將預先指定在交易訊息中。 按一下訊息的 **[!UICONTROL Test profiles]** 區塊以檢查您的校樣目標。

   ![](assets/message-center_5.png)

您也可以建立新的測試設定檔，或是使用 **[!UICONTROL Test profiles]** 功能表中已存在的測試設定檔。操作步驟：

1. 按一下左上方的標誌 **[!UICONTROL Adobe Campaign]**，然後選取 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**。
1. 在&#x200B;**[!UICONTROL Event]**&#x200B;區段中，選取您剛建立的事件。 在此範例中，選取「購物車放棄率 (EVTcartAbandonment)」。
1. 在 **[!UICONTROL Event data]** 文字方塊中指定要以 JSON 格式傳送的資訊。

   ![](assets/message-center_3.png)

1. 儲存您的變更。
1. [存取您建](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) 立的訊息，並選取更新的測試設定檔。

**相關主題：**

* [管理測試設定檔](../../audiences/using/managing-test-profiles.md)
* [建立閱聽眾](../../audiences/using/creating-audiences.md)

## 傳送證明{#sending-proof}

建立一或多個特定測試設定檔並儲存交易訊息後，您就可以傳送測試證明。

![](assets/message-center_10.png)

傳送校樣的步驟詳見[傳送校樣](../../sending/using/sending-proofs.md)一節。
