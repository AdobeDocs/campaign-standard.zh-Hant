---
title: 關於SMS訊息
seo-title: 關於SMS訊息
description: 關於SMS訊息
seo-description: 探索Adobe Campaign中SMS頻道的主要特點。
page-status-flag: 從未啓動
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134Fe72-77de-4fd0-b794-4d966 effaccf
delivercontext-tags: Delivery Creation，wizard；傳送，SMSContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About SMS messages{#about-sms-messages}

Adobe Campaign可讓您傳送SMS(簡短訊息服務)訊息。

>[!NOTE]
>
>SMS頻道是附加元件。請檢查您的授權合約。

對於SMS訊息，您只能以文字格式建立、修改和個人化訊息。您也可以在傳送SMS訊息之前預覽。

SMS訊息的長度上限為160個字元，如果它採用GSM編碼，而且只有70個字元位於Unicode中。但是，某些特殊字元會影響訊息長度。For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

SMS messages can be created from the **[!UICONTROL Marketing activities]** menu, from a campaign, or in a workflow, see [Creating an SMS message](../../channels/using/creating-an-sms-message.md).

若要傳送SMS訊息至您需要的行動電話：

* **[!UICONTROL Routing]****[!UICONTROL Mobile (SMS)]** 在頻道上設定 **[!UICONTROL Bulk delivery]** 模式的外部帳戶。For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* 已正確連結至此外部帳戶的傳送範本。

**相關主題：**

* [管理範本](../../start/using/about-templates.md)
* [SMS組態](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)

## SMS delivery template {#sms-delivery-template}

Adobe Campaign提供行動裝置的傳送範本。This template must be correctly linked to the external account used for the **[!UICONTROL Mobile (SMS)]** channel. 若要存取並修改：

1. Select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** from the advanced menu.
1. Hover over the **[!UICONTROL Send via SMS]** template with the mouse and select the **Duplicate element** option.
1. 選取新範本。
1. Click the **[!UICONTROL Edit properties]** button.
1. In the **[!UICONTROL Advanced parameters]** section of the template properties, make sure that the template is linked to the external account to be used for delivering SMS.

   ![](assets/sms_template.png)

**相關主題：**

* [管理範本](../../start/using/about-templates.md)

