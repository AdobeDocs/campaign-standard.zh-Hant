---
title: 關於 SMS 訊息
description: 瞭解Adobe Campaign中SMS頻道的主要特性。
page-status-flag: never-activated
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966effaccf
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 501ba6f97a86076116d4d84f43df674536e12f6a

---


# 關於 SMS 訊息{#about-sms-messages}

Adobe Campaign可讓您傳遞SMS（簡訊服務）訊息。

>[!NOTE]
>
>SMS頻道是附加元件。 請檢查您的授權合約。

對於SMS訊息，您只能以文字格式建立、修改及個人化訊息。 您也可以在傳送SMS訊息之前先預覽。

如果SMS訊息在GSM編碼中，則長度限制為160個字元，如果在Unicode中，則限制為70個字元。 不過，某些特殊字元會影響訊息的長度。 如需詳細資訊，請參閱「 [SMS編碼」一節](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 。

您可從功能表、促銷活 **[!UICONTROL Marketing activities]**動或工作流程建立SMS訊息，請參閱[建立SMS訊息](../../channels/using/creating-an-sms-message.md)。

若要將SMS訊息傳送至行動電話，您需要：

* 在 **[!UICONTROL Routing]**頻道上以模式**[!UICONTROL Mobile (SMS)]** 設定的外部 **[!UICONTROL Bulk delivery]**帳戶。 For more on this, refer to the[Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)section.
* 正確連結至此外部帳戶的傳送範本。

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
* [SMS設定](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS 報告](../../reporting/using/sms-report.md)
* [Campaign Standard行動指南](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## 簡訊傳送範本 {#sms-delivery-template}

Adobe Campaign提供行動裝置的傳送範本。 此範本必須正確連結至用於渠道的外部帳 **[!UICONTROL Mobile (SMS)]**戶。 要訪問和修改它：

1. 從進 **[!UICONTROL Resources]**階功**[!UICONTROL Templates]** 能表 **[!UICONTROL Delivery templates]**選取> >。
1. 將滑鼠暫留在 **[!UICONTROL Send via SMS]**範本上，並選取「復**&#x200B;制」元素&#x200B;**。
1. 選擇新模板。
1. Click the **[!UICONTROL Edit properties]**button.
1. 在範本 **[!UICONTROL Advanced parameters]**屬性的區段中，請確定範本已連結至要用來傳送SMS的外部帳戶。

   ![](assets/sms_template.png)

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
