---
title: 關於簡訊訊息
description: 探索Adobe Campaign中SMS通道的主要特性。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 23%

---

# 關於簡訊訊息{#about-sms-messages}

Adobe Campaign可讓您傳送SMS（簡訊服務）訊息。

>[!NOTE]
>
>SMS通道是附加元件。 請檢查您的授權合約。

對於SMS訊息，您只能以文字格式建立、修改及個人化訊息。 您也可以在傳送SMS訊息之前先預覽這些訊息。

SMS訊息的長度若為GSM編碼，則限制為160個字元，若為Unicode，則限制為70個字元。 但某些特殊字元會影響訊息的長度。 如需詳細資訊，請參閱[SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)區段。

可從&#x200B;**[!UICONTROL Marketing activities]**&#x200B;功能表、行銷活動或工作流程建立SMS訊息，請參閱[建立SMS訊息](../../channels/using/creating-an-sms-message.md)。

若要將簡訊傳送至行動電話，您需要：

* 在 **[!UICONTROL Mobile (SMS)]** 通道上使用 **[!UICONTROL Bulk delivery]** 模式設定的 **[!UICONTROL Routing]** 外部帳戶。如需詳細資訊，請參閱[區段](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)區段。
* 正確連結至此外部帳戶的傳遞範本。

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
* [SMS設定](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [簡訊報告](../../reporting/using/sms-report.md)
* [Campaign Standard　行動指南](https://helpx.adobe.com/tw/campaign/kb/acs-mobile.html)

## 簡訊傳送範本 {#sms-delivery-template}

Adobe Campaign提供行動裝置的傳遞範本。 此範本必須正確連結至用於&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;通道的外部帳戶。 要訪問和修改它：

1. 從高級菜單中選擇&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**。
1. 用滑鼠暫留在&#x200B;**[!UICONTROL Send via SMS]**&#x200B;範本上，然後選取&#x200B;**重複元素**&#x200B;選項。
1. 選取新範本。
1. 按一下 **[!UICONTROL Edit properties]** 按鈕。
1. 在範本屬性的&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;區段中，確認範本已連結至要用於傳送SMS的外部帳戶。

   ![](assets/sms_template.png)

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
