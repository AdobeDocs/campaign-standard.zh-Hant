---
title: 測試異動訊息
description: 瞭解如何在Adobe Campaigntest事務性消息。
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

在發佈事務性消息之前，您可以建立特定的test配置檔案，以便正確檢查消息。

## 定義特定test配置檔案 {#defining-specific-test-profile}

定義將連結到您的活動的test配置檔案，該配置檔案將允許您預覽您的消息併發送相關證明。

1. 從 [事務消息儀表板](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)，按一下 **[!UICONTROL Create test profile]** 按鈕

   ![](assets/message-center_test-profile.png)

1. 在 **[!UICONTROL Event data used for personalization]** 區段中指定要以 JSON 格式傳送的資訊。這是預覽訊息與測試設定檔收到校樣時，將會使用的內容。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >如果您豐富了消息內容，還可以輸入與另一個表相關的資訊，如 **[!UICONTROL Profile]**。 請參閱 [豐富活動內容](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) 和 [個性化事務性消息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)。

1. 建立後，將在事務性消息中預先指定test配置檔案。 按一下訊息的 **[!UICONTROL Test profiles]** 區塊以檢查您的校樣目標。

   ![](assets/message-center_5.png)

您也可以建立新的測試設定檔，或是使用 **[!UICONTROL Test profiles]** 功能表中已存在的測試設定檔。操作步驟：

1. 按一下 **Adobe** 徽標，在左上角，然後選擇 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**。
1. 在 **[!UICONTROL Event]** 的子菜單。 在此範例中，選取「購物車放棄率 (EVTcartAbandonment)」。
1. 在 **[!UICONTROL Event data]** 文字方塊中指定要以 JSON 格式傳送的資訊。

   ![](assets/message-center_3.png)

1. 儲存您的變更。
1. [訪問消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) 建立並選擇更新的test配置檔案。

**相關主題：**

* [管理測試設定檔](../../audiences/using/managing-test-profiles.md)
* [建立對象](../../audiences/using/creating-audiences.md)

## 發送證據 {#sending-proof}

建立一個或多個特定的test配置檔案並保存事務性消息後，您可以發送證明來test它。

![](assets/message-center_10.png)

有關發送證明的步驟，請參見 [發送校樣](../../sending/using/sending-proofs.md) 的子菜單。
