---
title: 準備傳送
seo-title: 準備傳送
description: 準備傳送
seo-description: 瞭解如何在傳送之前定義準備。
page-status-flag: 從未啓動
uuid: 1038de2-164c-4579-9294-bdf2 a4 EB12 d6
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 傳送
content-type: reference
topic-tags: 準備與測試訊息
discoiquuid: 003abc83-7f07-471f-ab2 f-1d352 d22 c26 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Preparing the send{#preparing-the-send}

準備對應至計算目標人口的步驟，以及針對包含在目標中的每個描述檔產生訊息內容。Once preparation is finished, the messages are ready to be sent, either immediately or at [the scheduled date and time](../../sending/using/about-scheduling-messages.md).

1. To start preparing the send, click the **Prepare** button located in the action bar.

   ![](assets/preparing_delivery_2.png)

1. **[!UICONTROL Deployment]** 區塊顯示準備進度，然後是準備統計資料：目標訊息數、傳送訊息數等等。

   視目標人口的大小而定，此作業可能需要一些時間。

   ![](assets/preparing_delivery.png)

1. Stop the preparation at any time using the **Stop** button, located in the action bar.

   在準備階段中，不會傳送訊息。因此，您可以開始或停止這項作業，而不會影響任何風險。

   ![](assets/preparing_delivery_6.png)

1. 在準備傳送階段時，會自動儲存您的訊息。If you need to make any changes to your message's schedule after the preparation step, you will need to make sure that you click the **[!UICONTROL Prepare]** button again for those changes to be taken into account. For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. 若要檢視準備記錄，請按一下位於區塊右下方的按鈕。

   ![](assets/preparing_delivery_4.png)

1. **[!UICONTROL Deployment]** 視窗開啓、更正任何錯誤，然後重新開始準備。

   最後一個記錄訊息會顯示任何錯誤訊息和錯誤數目。特定圖示會顯示遇到的錯誤類型：黃色圖示表示非關鍵處理錯誤，紅色圖示指出導致傳送無法開始的重大錯誤。

   ![](assets/preparing_delivery_3.png)

1. 請先檢查準備統計資料，然後確認傳送訊息。If the number of messages to send does not correspond to your configuration, edit the targeted population (see [Selecting an audience in a message](../../audiences/using/selecting-an-audience-in-a-message.md)) and restart the preparation.

準備完成後，您的訊息就可以傳送。For more on this, see [Confirming send](../../sending/using/confirming-the-send.md).

**Typology規則**

Adobe Campaign隨附一組建置的打字規則，在訊息準備期間套用。它們可用來檢查訊息是否有效並符合您的品質標準。See [Typologies](../../administration/using/about-typology-rules.md). 例如，您可以定義自己的打字規則規則，例如，設定全域跨通道疲勞規則，自動排除促銷活動中被覆蓋的個人檔案。See [Fatigue rules](../../administration/using/fatigue-rules.md).

**SMS訊息檢查**

如果您在SMS訊息中插入個人化欄位或條件文字，這些因素可能會引入GSM編碼未考量的字元。執行準備時，訊息長度會受到監控，如果會通過限制，則會顯示警告訊息。

For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) and [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) sections.
