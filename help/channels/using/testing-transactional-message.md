---
title: 測試異動訊息
description: 瞭解如何在Adobe Campaign中測試交易式訊息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 5138826d-ae08-403b-91ef-91027ef6e78e
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 36%

---

# 測試異動訊息 {#testing-a-transactional-message}

在發佈交易式訊息之前，您可以建立特定的測試設定檔，以允許您正確檢查訊息。

## 定義特定測試設定檔 {#defining-specific-test-profile}

定義將連結至您的事件的測試設定檔，可讓您預覽訊息並傳送相關校樣。

1. 從 [異動訊息儀表板](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)，按一下 **[!UICONTROL Create test profile]** 按鈕。

   ![](assets/message-center_test-profile.png)

1. 在 **[!UICONTROL Event data used for personalization]** 區段中指定要以 JSON 格式傳送的資訊。這是預覽訊息與測試設定檔收到校樣時，將會使用的內容。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >如果您豐富了訊息，也可以輸入與其他表格相關的資訊，例如 **[!UICONTROL Profile]**. 另請參閱 [豐富化事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) 和 [個人化交易式訊息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. 建立後，會在交易式訊息中預先指定測試設定檔。 按一下訊息的 **[!UICONTROL Test profiles]** 區塊以檢查您的校樣目標。

   ![](assets/message-center_5.png)

您也可以建立新的測試設定檔，或是使用 **[!UICONTROL Test profiles]** 功能表中已存在的測試設定檔。操作步驟：

1. 按一下 **Adobe** 標誌，在左上角，然後選取 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. 在 **[!UICONTROL Event]** 區段，選取您剛才建立的事件。 在此範例中，選取「購物車放棄率 (EVTcartAbandonment)」。
1. 在 **[!UICONTROL Event data]** 文字方塊中指定要以 JSON 格式傳送的資訊。

   ![](assets/message-center_3.png)

1. 儲存您的變更。
1. [存取訊息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) 建立並選取更新的測試設定檔。

**相關主題：**

* [管理測試設定檔](../../audiences/using/managing-test-profiles.md)
* [建立對象](../../audiences/using/creating-audiences.md)

## 傳送證明 {#sending-proof}

建立一個或多個特定測試設定檔並儲存交易式訊息後，您可以傳送校樣以測試它。

![](assets/message-center_10.png)

有關傳送證明的詳細步驟，請參見 [傳送校樣](../../sending/using/sending-proofs.md) 區段。
