---
title: 建立服務
seo-title: 建立服務
description: 建立服務
seo-description: 瞭解如何建立您的第一項服務，並設定它以傳送電子郵件確認給您的訂閱者。
page-status-flag: 從未激活
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 參考
topic-tags: 管理預訂
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: 服務，嚮導；服務，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: da59fad19bcf35b63afdfc6389be527c27f21fc3

---


# 建立服務{#creating-a-service}

為了能夠管理訂閱，您首先需要建立並設定服務。 設定新服務可讓您指定設定檔在訂閱或取消訂閱服務時，將會收到的電子郵件確認。 您也會定義連結至服務的訂閱和取消訂閱登陸頁面。 例如，插入電子郵件中的服務訂閱連結會自動將描述檔導向服務中指定的訂閱登陸頁面。

要配置服務：

1. 從進階功能表 **[!UICONTROL Profiles & audiences]** &gt;透 **[!UICONTROL Services]** 過Adobe Campaign標誌新增服務或選取現有服務。 如果您建立新服務，只需依照畫面上顯示的步驟進行。

   預設服務模板可用。 此範本已預先設定預設登陸頁面和確認電子郵件。 您可以建立其他範本來定義特定組態。 有關詳細資訊，請參閱「管 [理模板](../../start/using/about-templates.md) 」部分。

1. 在「服務」 **[!UICONTROL Service properties]** 儀表板中通過按鈕訪 ![](assets/edit_darkgrey-24px.png) 問的部分中，為預訂和取消預訂配置確認消息。

   ![](assets/lp_service_parameters.png)

1. 填寫欄 **[!UICONTROL Service label]** 位。 使用自訂確認訊息時，服務標籤是必備的。

1. 為預訂和取消預訂選擇確認消息模板。 Three modes are available:

   * **[!UICONTROL No message]**: this mode allows you to create a service without a confirmation message.
   * **[!UICONTROL Default message]**: this mode will use the default subscription or unsubscription confirmation transactional message. The default confirmation messages are generic and will be the same for all services that use the default mode.

      >[NOTE]
      >
      >You can modify a default message by clicking its label in the  section or by selecting it from the Adobe Campaign transactional message list, after checking the  box.**[!UICONTROL Service properties]****[!UICONTROL Show internal transactional messages]**

   * **[!UICONTROL Custom message]**: this mode allows you to handle custom confirmation messages, specific for each service. You then select the **[!UICONTROL Custom subscription event configuration]** which is associated with a specific [transactional message](../../channels/using/about-transactional-messaging.md) template. For more on this, see Confirming subscription to a service.[](../../audiences/using/confirming-subscription-to-a-service.md)

1. Save the service. It is now ready to be used.

Once a service has been created, you can start promoting it.

**Related topics:**

* [Managing a service and subscriptions video](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html)
* [Promoting a service](../../audiences/using/promoting-a-service.md)
* [建立由訂閱者建立的觀眾](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [將表單連結至著陸頁面中的服務](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service)

