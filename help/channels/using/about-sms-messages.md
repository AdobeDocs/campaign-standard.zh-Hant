---
title: 關於簡訊訊息
description: 探索Adobe Campaign中SMS頻道的主要特性。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 30%

---

# 關於簡訊訊息{#about-sms-messages}

Adobe Campaign可讓您傳遞SMS （短訊息服務）訊息。

>[!NOTE]
>
>SMS頻道為附加元件。 請檢查您的授權合約。

對於 SMS 訊息，您只能以文字格式建立、修改和個人化訊息。 您也可以在傳送簡訊之前先預覽簡訊。

SMS訊息的長度限製為160個字元（若是GSM編碼），僅限70個字元（若是Unicode）。 不過，某些特殊字元可能會影響訊息的長度。 如需詳細資訊，請參閱[SMS編碼](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)區段。

SMS訊息可從&#x200B;**[!UICONTROL Marketing activities]**&#x200B;功能表、行銷活動或工作流程中建立，請參閱[建立SMS訊息](../../channels/using/creating-an-sms-message.md)。

若要將SMS訊息傳送至行動電話，您需要：

* 在 **[!UICONTROL Mobile (SMS)]** 通道上使用 **[!UICONTROL Bulk delivery]** 模式設定的 **[!UICONTROL Routing]** 外部帳戶。如需詳細資訊，請參閱[區段](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)區段。
* 正確連結至此外部帳戶的傳遞範本。

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
* [簡訊設定](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [簡訊報告](../../reporting/using/sms-report.md)
* [Campaign Standard Mobile指南](../../channels/using/get-started-communication-channels.md)

## 簡訊傳遞範本 {#sms-delivery-template}

Adobe Campaign提供行動裝置的傳遞範本。 此範本必須正確連結至&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;管道所使用的外部帳戶。 若要存取及修改它：

1. 從進階功能表選取&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**。
1. 使用滑鼠將游標停留在&#x200B;**[!UICONTROL Send via SMS]**&#x200B;範本上，並選取&#x200B;**重複的專案**&#x200B;選項。
1. 選取新範本。
1. 按一下 **[!UICONTROL Edit properties]** 按鈕。
1. 在範本屬性的&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;區段中，確定範本已連結至要用於傳遞SMS的外部帳戶。

   ![](assets/sms_template.png)

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
