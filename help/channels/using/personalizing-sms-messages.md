---
title: 個人化 SMS 訊息
description: 探索個人化SMS訊息時音譯選項的特定性。
page-status-flag: 從未激活
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 頻道
content-type: 參考
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990ae3f9
delivercontext-tags: deliveryCreation，精靈；delivery,smsContent,back;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 個人化 SMS 訊息{#personalizing-sms-messages}

個人化SMS訊息的原則與電子郵件的原 [則](../../designing/using/personalization.md#inserting-a-personalization-field)。 不過，您必須注意音譯選項，因為這些選項可能會影響編碼，進而影響要傳送的SMS訊息數量。 如需詳細資訊，請參閱音 [譯和SMS長度一節](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 。

在這裡，我們取了一個包含個人化欄位的範例SMS訊息，視是否選取了音譯，這些欄位將不會產生相同數目的傳送：

**嗨&lt; FirstName &gt; &lt; lastName &gt;，新產品現已推出。 來店裡看看！**

* 對於名為「John Smith」的收件者，由於其不含特殊字元，Adobe Campaign將選擇GSM編碼，此編碼將授權每則SMS訊息最多160個字元。 因此，訊息會以單一部分傳送。
* 對於名為「Raphaël Forêt」的收件者，字元「ë」和「ê」無法在GSM中編碼。 視音譯是否已啟用而定，Adobe Campaign可以在兩種行為之間進行選擇：

   * 如果音譯是授權的'ë','ê'將被'e'取代，這表示GSM編碼可使用，因此在SMS中最多可使用160個字元。 此訊息會以單一SMS訊息的形式傳送，但會稍作變更。
   * 如果未授權音譯，Adobe Campaign會選擇以二進位格式(Unicode)傳送訊息：因此，所有字元都會依此傳送。 由於Unicode中的SMS訊息限制為70個字元，Adobe Campaign必須分兩部分傳送訊息。

>[!NOTE]
>
>自動選擇最佳編碼的算法會針對每條消息分別執行。 這樣，只有需要Unicode編碼的個人化訊息才會以Unicode傳送；其他所有人都使用GSM編碼。

## SMS傳送者 {#sms-sender}

您可以個人化SMS傳送者的名稱。 有關詳細資訊，請參閱 [SMS配置部分](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) 。
