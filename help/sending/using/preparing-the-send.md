---
solution: Campaign Standard
product: campaign
title: 準備傳送
description: 瞭解如何在傳送前定義準備。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---


# 準備傳送{#preparing-the-send}

準備對應於計算目標總量和為目標中包括的每個配置檔案生成消息內容的步驟。 準備完成後，即可立即或在排程的日期和時間 [傳送訊息](../../sending/using/about-scheduling-messages.md)。

1. 若要開始準備傳送，請按一下動作 **列中的** 「準備」按鈕。

   ![](assets/preparing_delivery_2.png)

1. 該 **[!UICONTROL Deployment]** 塊顯示準備進度，然後是準備統計：目標訊息的數目、要傳送的訊息數目等。

   根據目標人口的大小，此操作可能需要一些時間。

   ![](assets/preparing_delivery.png)

1. 使用動作列中的「停止」按 **鈕** ，隨時停止準備工作。

   在準備階段，不會傳送任何訊息。 因此，您可以開始或停止此動作，而不會有影響任何內容的風險。

   ![](assets/preparing_delivery_6.png)

1. 您的訊息會在準備傳送階段期間自動儲存。 如果在準備步驟後需要對郵件的時間表進行任何更改，則需要確保再次按一下按鈕，以便將這些更改納入考慮範圍。 **[!UICONTROL Prepare]** For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. 要查看準備日誌，請按一下位於塊右下角的按鈕。

   ![](assets/preparing_delivery_4.png)

1. 窗口 **[!UICONTROL Deployment]** 開啟，更正所有錯誤，然後重新啟動準備。

   最後一條日誌消息顯示所有錯誤消息和錯誤數。 特定圖示顯示所遇到的錯誤類型：黃色圖示表示非嚴重處理錯誤，紅色圖示表示嚴重錯誤，導致無法啟動傳送。

   ![](assets/preparing_delivery_3.png)

1. 在確認發送消息之前，請檢查準備統計資訊。 如果要傳送的訊息數量與您的設定不相符，請編輯目標群體(請參閱「在訊息中選 [擇對象](../../audiences/using/selecting-an-audience-in-a-message.md)」)，然後重新開始準備。

準備完成後，您的訊息就會準備好傳送。 有關詳細資訊，請參 [閱確認發送](../../sending/using/confirming-the-send.md)。

**類型規則**

Adobe Campaign隨附一組內建的排版規則，這些規則會在訊息準備期間套用。 它們用來檢查訊息是否有效，以及是否符合您的品質標準。 請參閱 [類型](../../sending/using/about-typology-rules.md)。 例如，您可以定義自己的排版規則，以設定全域跨通道疲勞規則，自動排除促銷活動中過度索取的個人檔案。 請參閱[疲勞規則](../../sending/using/fatigue-rules.md)。

**SMS訊息檢查**

如果您已將個人化欄位或條件文字插入SMS訊息的內容，這些因素可能會引入GSM編碼未考慮的字元。 當準備運行時，會監視消息長度，並且如果它通過限制，將顯示警告消息。

如需詳細資訊，請參閱 [SMS編碼、長度與音譯](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)[與個人化SMS訊息](../../channels/using/personalizing-sms-messages.md) 。
