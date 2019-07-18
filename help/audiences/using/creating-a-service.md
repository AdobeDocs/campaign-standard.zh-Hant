---
title: 建立服務
seo-title: 建立服務
description: 建立服務
seo-description: 瞭解如何建立第一個服務，並設定它以傳送電子郵件確認給用戶。
page-status-flag: 從未啓動
uuid: 0d95d852-0f22-4b7b-b301-8fb4844 c ca2
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受眾
content-type: reference
topic-tags: 管理訂閱
discoiquuid: 6b7788Fe-fa6 c-472a-97db-765595ce1589
context-tags: service，wizard；service，main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Creating a service{#creating-a-service}

若要能夠管理訂閱，您必須先建立服務並進行設定。設定新服務可讓您指定描述檔在訂閱或取消訂閱服務時將接收的電子郵件確認。您也將定義連結至服務的訂閱和取消訂閱著陸頁面。例如，插入電子郵件中的服務訂閱連結會自動將描述檔導向服務中指定的訂閱著陸頁面。

若要設定服務：

1. From the advanced menu **Profiles &amp; audiences** &gt; **Services** via the Adobe Campaign logo, add a new service or select an existing service. 如果您建立新服務，只要遵循螢幕上顯示的步驟即可。

   可使用預設服務範本。此範本已預先設定預設登陸頁面和確認電子郵件。您可以建立其他範本來定義特定設定。For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **Service properties** section, accessed via the ![](assets/edit_darkgrey-24px.png) button in the service dashboard, configure the confirmation messages for subscriptions and unsubscriptions.

   ![](assets/lp_service_parameters.png)

1. 選取訂閱和取消訂閱的確認訊息範本。共有三種模式：

   * **[!UICONTROL No message]**：此模式可讓您建立服務，而不需確認訊息。
   * **[!UICONTROL Default message]**：此模式會使用預設訂閱或取消訂閱確認交易訊息。預設確認訊息是通用的，所有使用預設模式的服務都相同。
   * **[!UICONTROL Custom message]**：此模式可讓您處理每個服務專屬的自訂確認訊息。You then select the **[!UICONTROL Custom subscription event configuration]** which is associated with a specific transactional message template. Refer to [Transactional messages](../../channels/using/about-transactional-messaging.md) for more information on transactional event and message configuration.

1. 儲存服務。現在已可供使用。

一旦建立服務後，您就可以開始促銷。

**相關主題：**

* [管理服務與訂閱](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html) 視訊
* [促銷服務](../../audiences/using/promoting-a-service.md)
* [建立由訂閱者製作的觀眾](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [將表單連結至著陸頁面中的服務](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service)

