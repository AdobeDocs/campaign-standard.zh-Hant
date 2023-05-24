---
title: 準備傳送
description: 瞭解如何在發送前定義準備。
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

準備對應於計算目標群體和為目標中包括的每個簡檔生成消息內容的步驟。 準備完成後，即可立即或在 [計畫日期和時間](../../sending/using/about-scheduling-messages.md)。

1. 要開始準備發送，請按一下 **準備** 按鈕。

   ![](assets/preparing_delivery_2.png)

1. 的 **[!UICONTROL Deployment]** 塊顯示準備進度，然後是準備統計：目標消息數、要發送的消息數等。

   根據目標母體的大小，此操作可能需要一些時間。

   ![](assets/preparing_delivery.png)

1. 使用 **停止** 按鈕。

   在準備階段，不傳送任何訊息。因此，您可以開始或停止準備而不會影響任何東西。

   ![](assets/preparing_delivery_6.png)

1. 在準備傳遞階段會自動保存您的郵件。 如果您需要在準備步驟之後對郵件的時間表進行任何更改，則需要確保按一下 **[!UICONTROL Prepare]** 按鈕。 有關如何安排消息的詳細資訊，請參閱此 [頁](../../sending/using/about-scheduling-messages.md)。

   ![](assets/preparing_delivery_5.png)

1. 要查看準備日誌，請按一下塊右下角的按鈕。

   ![](assets/preparing_delivery_4.png)

1. 的 **[!UICONTROL Deployment]** 窗口，更正所有錯誤，然後重新啟動準備。

   最後的記錄訊息顯示所有錯誤訊息和錯誤數量。特定表徵圖顯示遇到的錯誤類型：黃色表徵圖表示非臨界處理錯誤，紅色表徵圖表示阻止傳遞的嚴重錯誤。

   ![](assets/preparing_delivery_3.png)

1. 在確認發送消息之前，請檢查準備統計資訊。 如果要發送的消息數與您的配置不對應，請編輯目標填充(請參見 [在郵件中選擇受眾](../../audiences/using/selecting-an-audience-in-a-message.md))，然後重新開始準備。

準備完成後，即可發送您的消息。 有關此的詳細資訊，請參閱 [確認發送](../../sending/using/confirming-the-send.md)。

**類型規則**

Adobe Campaign提供了一套內置類型規則，這些規則在消息準備過程中應用。 它們用於檢查消息是否有效並符合您的質量標準。 請參閱 [類型](../../sending/using/about-typology-rules.md)。 例如，您可以定義自己的類型規則，以設定全局跨渠道的已聯繫人規則，這些規則將自動從市場活動中排除過度主動的配置檔案。 請參閱[疲勞規則](../../sending/using/fatigue-rules.md)。

**簡訊檢查**

如果您已將個性化欄位或條件文本插入SMS消息的內容，則這些因素可能會引入GSM編碼未考慮的字元。 當準備運行時，將監視消息長度，並且如果它通過限制，將顯示警告消息。

有關詳細資訊，請參閱 [簡訊編碼、長度和音譯](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 和 [個性化SMS消息](../../channels/using/personalizing-sms-messages.md) 的下界。
