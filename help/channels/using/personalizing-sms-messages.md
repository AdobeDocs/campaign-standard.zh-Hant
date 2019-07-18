---
title: 個人化SMS訊息
seo-title: 個人化SMS訊息
description: 個人化SMS訊息
seo-description: 在個人化SMS訊息時，探索翻譯選項的特殊性。
page-status-flag: 從未啓動
uuid: 123Fe70c-c279-40a3-88b6-6bfb2453 ec83
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: sms-messages
discoiquuid: 7c64785c-e3 c2-4casa-a547-002990aae3 f9
delivercontext-tags: Delivery Creation，wizard；傳送，SMSContent，back；傳送，SMSContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Personalizing SMS messages{#personalizing-sms-messages}

The principles for personalizing SMS messages are the same as those for [emails](../../designing/using/inserting-a-personalization-field.md). 不過，您仍必須注意轉換選項，因為這些選項可能會影響編碼，因此會傳送SMS訊息。For more on this, refer to the [Transliteration and SMS length](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

這裡我們會使用範例SMS訊息，其中包含個人化欄位，視是否已選取翻譯而定，並不會產生相同數目的傳送：

**&lt; FirstName&gt;&lt; lastName&gt;，新產品現在可供使用。Come and check them out in store!**

* 對於名為「John Smith」的收件者，Adobe Campaign將選擇「GSM編碼」，並選擇「GSM編碼」，以每SMS訊息最多授權160個字元。因此，訊息將以單一部分傳送。
* 對於名為「Raphael Foret」的收件者，無法在GSM中編碼字元't'和'ef'。Adobe Campaign可以在兩個行為之間選取：

   * 如果轉譯為authorized'af'和'ef'將取代'e'，這表示可以使用GSM編碼，因此最多可用於SMS。此訊息將會以單一SMS訊息傳送，但會稍微變更。
   * 如果未授權翻譯，Adobe Campaign將選擇以二進位格式傳送訊息(Unicode)：因此，所有字元都會隨之傳送。由於Unicode中的SMS訊息僅限70個字元，因此Adobe Campaign必須以兩個部分傳送訊息。

>[!NOTE]
>
>自動選擇最佳編碼的演算法會單獨執行每個訊息，個案依個案而定。如此，只會在Unicode中傳送需要Unicode編碼的個人化訊息；所有其他人都將使用GSM編碼。

