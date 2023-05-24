---
title: 關於簡訊訊息
description: 瞭解Adobe CampaignSMS通道的主要特點。
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
ht-degree: 23%

---

# 關於簡訊訊息{#about-sms-messages}

Adobe Campaign允許您傳遞SMS（短消息服務）消息。

>[!NOTE]
>
>SMS通道是附加模組。 請檢查您的授權合約。

對於SMS消息，您只能建立、修改和個性化文本格式的消息。 您還可以在發送簡訊之前預覽它們。

如果SMS消息採用GSM編碼，則其長度限制為160個字元；如果SMS消息採用Unicode，則僅限70個字元。 但是，某些特殊字元會影響消息的長度。 有關詳細資訊，請參閱 [SMS編碼](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 的子菜單。

可以從 **[!UICONTROL Marketing activities]** 菜單，從市場活動或工作流中，請參閱 [建立SMS消息](../../channels/using/creating-an-sms-message.md)。

要將SMS消息傳遞到行動電話，您需要：

* 在 **[!UICONTROL Mobile (SMS)]** 通道上使用 **[!UICONTROL Bulk delivery]** 模式設定的 **[!UICONTROL Routing]** 外部帳戶。如需詳細資訊，請參閱[區段](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)區段。
* 正確連結至此外部帳戶的傳遞範本。

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
* [SMS配置](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [簡訊報告](../../reporting/using/sms-report.md)
* [Campaign Standard　行動指南](../../channels/using/get-started-communication-channels.md)

## 簡訊傳遞範本 {#sms-delivery-template}

Adobe Campaign為移動設備提供交付模板。 此模板必須正確連結到用於 **[!UICONTROL Mobile (SMS)]** 頻道。 要訪問和修改它：

1. 選擇 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 的子菜單。
1. 懸停在 **[!UICONTROL Send via SMS]** 使用滑鼠進行模板並選擇 **重複元素** 的雙曲餘切值。
1. 選擇新模板。
1. 按一下 **[!UICONTROL Edit properties]** 按鈕。
1. 在 **[!UICONTROL Advanced parameters]** 部分，確保模板已連結到要用於傳遞SMS的外部帳戶。

   ![](assets/sms_template.png)

**相關主題：**

* [管理範本](../../start/using/marketing-activity-templates.md)
