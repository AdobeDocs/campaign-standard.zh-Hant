---
title: 個人化簡訊訊息
description: 探索個人化簡訊訊息時音譯選項的特定性。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 6c01662e-1e19-4cec-aa21-6e84b9b7a677
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 99%

---

# 個人化簡訊訊息{#personalizing-sms-messages}

個人化簡訊訊息的原則與[電子郵件](../../designing/using/personalization.md#inserting-a-personalization-field)的原則。不過，您必須注意音譯選項，因為這些選項可能會影響編碼，進而影響要傳送的簡訊訊息數量。如需詳細資訊，請參閱[音譯和簡訊長度](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)區段。

在此處，根據是否選取音譯，我們舉一個包含個人化欄位簡訊訊息作為範例，這些欄位將不會產生相同數目的傳送：

**嗨 &lt; FirstName > &lt; LastName >，新產品現已推出。來店裡看看！**

* 對於名為 &#39;John Smith&#39; 的收件者，由於其不含特殊字元，Adobe Campaign 將選取 GSM 編碼，此編碼將授權每則簡訊訊息最多 160 個字元。因此，訊息會以單一部分傳送。
* 對於名為 &#39;Raphaël Forêt&#39; 的收件者，字元 &#39;ë&#39; 和 &#39;ê&#39; 無法在 GSM 中編碼。視是否已啟用音譯而定，Adobe Campaign 可以在兩種行為之間進行選取：

   * 如果音譯是授權的 &#39;ë&#39;，而且 &#39;ê&#39; 將被 &#39;e&#39; 取代，這表示 GSM 編碼可使用，因此在簡訊中最多可使用 160 個字元。此訊息會以單一簡訊訊息的形式傳送，但會稍作變更。
   * 如果未授權音譯，Adobe Campaign 會選取以二進位格式 (Unicode) 傳送訊息：因此，所有字元都會依此傳送。由於 Unicode 中的簡訊訊息限制為 70 個字元，Adobe Campaign 必須分兩部分傳送訊息。

>[!NOTE]
>
>自動選取最佳編碼的演算法會針對每則訊息分別執行。這樣，只有需要 Unicode 編碼的個人化訊息才會以 Unicode 傳送；其他所有人都使用 GSM 編碼。

## SMS寄件者 {#sms-sender}

>[!IMPORTANT]
>
>請查看您所在國家/地區有關修改寄件者地址的法規。您也應洽詢您的簡訊服務提供者，以瞭解他們是否提供此功能。

**[!UICONTROL From]** 選項可讓您使用字串個人化簡訊訊息寄件者的名稱。此名稱將顯示為收件者行動電話上簡訊訊息的傳送者姓名。

如果此欄位為空，則會是使用的外部帳戶中提供的來源號碼。如果未提供來源號碼，則將使用簡短代碼。簡訊傳送專用的外部帳戶會顯示在[定義簡訊路由](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)區段。

![](assets/sms_creation_8.png)



