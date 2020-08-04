---
title: 個人化 SMS 訊息
description: 探索個人化 SMS 訊息時音譯選項的特定性。
page-status-flag: never-activated
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990aae3f9
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '331'
ht-degree: 100%

---


# 個人化 SMS 訊息{#personalizing-sms-messages}

個人化 SMS 訊息的原則與[電子郵件](../../designing/using/personalization.md#inserting-a-personalization-field)的原則。不過，您必須注意音譯選項，因為這些選項可能會影響編碼，進而影響要傳送的 SMS 訊息數量。如需詳細資訊，請參閱[音譯和 SMS 長度](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)區段。

在此處，根據是否選取音譯，我們舉一個包含個人化欄位 SMS 訊息作為範例，這些欄位將不會產生相同數目的傳送：

**嗨 &lt; FirstName > &lt; LastName >，新產品現已推出。來店裡看看！**

* 對於名為 &#39;John Smith&#39; 的收件者，由於其不含特殊字元，Adobe Campaign 將選取 GSM 編碼，此編碼將授權每則 SMS 訊息最多 160 個字元。因此，訊息會以單一部分傳送。
* 對於名為 &#39;Raphaël Forêt&#39; 的收件者，字元 &#39;ë&#39; 和 &#39;ê&#39; 無法在 GSM 中編碼。視是否已啟用音譯而定，Adobe Campaign 可以在兩種行為之間進行選取：

   * 如果音譯是授權的 &#39;ë&#39;，而且 &#39;ê&#39; 將被 &#39;e&#39; 取代，這表示 GSM 編碼可使用，因此在 SMS 中最多可使用 160 個字元。此訊息會以單一 SMS 訊息的形式傳送，但會稍作變更。
   * 如果未授權音譯，Adobe Campaign 會選取以二進位格式 (Unicode) 傳送訊息：因此，所有字元都會依此傳送。由於 Unicode 中的 SMS 訊息限制為 70 個字元，Adobe Campaign 必須分兩部分傳送訊息。

>[!NOTE]
>
>自動選取最佳編碼的演算法會針對每則訊息分別執行。這樣，只有需要 Unicode 編碼的個人化訊息才會以 Unicode 傳送；其他所有人都使用 GSM 編碼。

## SMS 寄件者 {#sms-sender}

您可以個人化 SMS 寄件者的名稱。有關詳細資訊，請參閱 [SMS 設定](../../administration/using/configuring-sms-channel.md#configuring-sms-properties)區段。
