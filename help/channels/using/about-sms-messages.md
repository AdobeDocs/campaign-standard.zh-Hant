---
solution: Campaign Standard
product: campaign
title: 關於 SMS 訊息
description: 瞭解Adobe Campaign中SMS頻道的主要特性。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 23%

---


# 關於 SMS 訊息{#about-sms-messages}

Adobe Campaign可讓您傳遞SMS（簡訊服務）訊息。

>[!NOTE]
>
>SMS頻道是附加元件。 請檢查您的授權合約。

對於SMS訊息，您只能以文字格式建立、修改及個人化訊息。 您也可以在傳送SMS訊息之前先預覽。

如果SMS訊息在GSM編碼中，則長度限制為160個字元，如果在Unicode中，則限制為70個字元。 不過，某些特殊字元會影響訊息的長度。 有關詳細資訊，請參閱[SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)部分。

您可從&#x200B;**[!UICONTROL Marketing activities]**&#x200B;功能表、促銷活動或工作流程建立SMS訊息，請參閱[建立SMS訊息](../../channels/using/creating-an-sms-message.md)。

若要將SMS訊息傳送至行動電話，您需要：

* 在 **[!UICONTROL Mobile (SMS)]** 通道上使用 **[!UICONTROL Bulk delivery]** 模式設定的 **[!UICONTROL Routing]** 外部帳戶。如需詳細資訊，請參閱[區段](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)區段。
* 正確連結至此外部帳戶的傳遞範本。

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
* [SMS設定](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS 報告](../../reporting/using/sms-report.md)
* [Campaign Standard　行動指南](https://helpx.adobe.com/tw/campaign/kb/acs-mobile.html)

## SMS傳送範本{#sms-delivery-template}

Adobe Campaign提供行動裝置的傳送範本。 此範本必須正確連結至&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;頻道使用的外部帳戶。 要訪問和修改它：

1. 從高級菜單中選擇&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**。
1. 將滑鼠暫留在&#x200B;**[!UICONTROL Send via SMS]**&#x200B;範本上，然後選取「複製元素&#x200B;**」選項。**
1. 選擇新模板。
1. 按一下 **[!UICONTROL Edit properties]** 按鈕。
1. 在範本屬性的&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;區段中，請確定範本已連結至要用來傳送SMS的外部帳戶。

   ![](assets/sms_template.png)

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
