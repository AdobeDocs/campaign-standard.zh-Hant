---
title: 準備傳送
description: 瞭解如何在傳送前定義準備作業。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: 0140c41a-7255-4b77-a1b7-c6f7b1135e51
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 12%

---

# 準備傳送{#preparing-the-send}

準備對應於計算目標人口並為目標中包含的每個設定檔產生訊息內容的步驟。 準備完成後，訊息就可以立即或在[排程的日期和時間](../../sending/using/about-scheduling-messages.md)傳送。

1. 若要開始準備傳送，請按一下動作列中的&#x200B;**準備**&#x200B;按鈕。

   ![](assets/preparing_delivery_2.png)

1. **[!UICONTROL Deployment]**&#x200B;區塊顯示準備進度，然後顯示準備統計資料：目標訊息數、要傳送的訊息數等。

   根據目標母體的大小，此操作可能需要一些時間。

   ![](assets/preparing_delivery.png)

1. 使用動作列中的&#x200B;**停止**&#x200B;按鈕隨時停止準備。

   在準備階段，不傳送任何訊息。因此，您可以開始或停止準備而不會影響任何東西。

   ![](assets/preparing_delivery_6.png)

1. 您的訊息會在準備傳送階段期間自動儲存。 如果您需要在準備步驟後對訊息排程進行任何變更，請務必再次按一下&#x200B;**[!UICONTROL Prepare]**&#x200B;按鈕，將這些變更納入考量。 如需如何排程訊息的詳細資訊，請參閱此[頁面](../../sending/using/about-scheduling-messages.md)。

   ![](assets/preparing_delivery_5.png)

1. 若要檢視準備記錄，請按一下位於區塊右下方的按鈕。

   ![](assets/preparing_delivery_4.png)

1. **[!UICONTROL Deployment]**&#x200B;視窗隨即開啟，請更正所有錯誤，然後重新啟動準備作業。

   最後的記錄訊息顯示所有錯誤訊息和錯誤數量。特定圖示會顯示遇到的錯誤型別：黃色圖示表示非嚴重處理錯誤，紅色圖示表示嚴重錯誤，導致傳送無法啟動。

   ![](assets/preparing_delivery_3.png)

1. 在確認傳送訊息之前，請檢查準備統計資料。 如果要傳送的訊息數目與您的設定不符，請編輯目標母體（請參閱[在訊息中選取對象](../../audiences/using/selecting-an-audience-in-a-message.md)），然後重新啟動準備作業。

完成準備工作後，即可傳送您的訊息。 如需詳細資訊，請參閱[確認傳送](../../sending/using/confirming-the-send.md)。

**類型規則**

Adobe Campaign隨附一組內建型別規則，這些規則會在訊息準備期間套用。 它們用於檢查訊息是否有效並符合您的品質條件。 請參閱[型別](../../sending/using/about-typology-rules.md)。 例如，您可以定義自己的型別規則，並設定全域跨頻道疲勞規則，以便自動將過度請求的設定檔從行銷活動中排除。 請參閱[疲勞規則](../../sending/using/fatigue-rules.md)。

**簡訊檢查**

如果您已將個人化欄位或條件文字插入SMS訊息的內容，則這些因素可能會引進GSM編碼未考慮的字元。 執行準備作業時，會監控訊息長度，如果超過限制，則會顯示警告訊息。

如需詳細資訊，請參閱[SMS編碼、長度和音譯](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)及[個人化SMS訊息](../../channels/using/personalizing-sms-messages.md)區段。
