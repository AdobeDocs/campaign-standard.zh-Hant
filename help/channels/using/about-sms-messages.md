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
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 21%

---

# 關於簡訊訊息{#about-sms-messages}

Adobe Campaign可讓您傳送SMS（簡訊服務）訊息。

>[!NOTE]
>
>SMS通道是附加元件。 請檢查您的授權合約。

對於SMS訊息，您只能以文字格式建立、修改及個人化訊息。 您也可以在傳送SMS訊息之前先預覽這些訊息。

SMS訊息的長度若為GSM編碼，則限制為160個字元，若為Unicode，則限制為70個字元。 但某些特殊字元會影響訊息的長度。 有關詳細資訊，請參閱 [SMS編碼](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 區段。

SMS訊息可從 **[!UICONTROL Marketing activities]** 功能表，從促銷活動或工作流程，請參閱 [建立SMS訊息](../../channels/using/creating-an-sms-message.md).

若要將簡訊傳送至行動電話，您需要：

* 在 **[!UICONTROL Mobile (SMS)]** 通道上使用 **[!UICONTROL Bulk delivery]** 模式設定的 **[!UICONTROL Routing]** 外部帳戶。如需詳細資訊，請參閱[區段](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)區段。
* 正確連結至此外部帳戶的傳遞範本。

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
* [SMS設定](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [簡訊報告](../../reporting/using/sms-report.md)
* [Campaign Standard　行動指南](../../channels/using/get-started-communication-channels.md)

## 簡訊傳送範本 {#sms-delivery-template}

Adobe Campaign提供行動裝置的傳遞範本。 此範本必須正確連結至用於 **[!UICONTROL Mobile (SMS)]** 頻道。 要訪問和修改它：

1. 選擇 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 的上界。
1. 暫留在 **[!UICONTROL Send via SMS]** 模板，用滑鼠選取 **重複元素** 選項。
1. 選取新範本。
1. 按一下 **[!UICONTROL Edit properties]** 按鈕。
1. 在 **[!UICONTROL Advanced parameters]** 區段中，確定範本已連結至要用於傳送SMS的外部帳戶。

   ![](assets/sms_template.png)

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
