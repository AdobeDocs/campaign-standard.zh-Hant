---
title: 建立服務
description: 瞭解如何建立您的第一項服務，並設定它以傳送電子郵件確認給您的訂閱者。
page-status-flag: never-activated
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: service,wizard;service,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# 建立服務{#creating-a-service}

為了能夠管理訂閱，您首先需要建立並設定服務。 設定新服務可讓您指定設定檔在訂閱或取消訂閱服務時，將會收到的電子郵件確認。 您也會定義連結至服務的訂閱和取消訂閱登陸頁面。 例如，插入電子郵件中的服務訂閱連結會自動將描述檔導向服務中指定的訂閱登陸頁面。

要配置服務：

1. 從進階功能表 **[!UICONTROL Profiles & audiences]** &gt;透 **[!UICONTROL Services]** 過Adobe Campaign標誌新增服務或選取現有服務。 如果您建立新服務，只需依照畫面上顯示的步驟進行。

   預設服務模板可用。 此範本已預先設定預設登陸頁面和確認電子郵件。 您可以建立其他範本來定義特定組態。 有關詳細資訊，請參閱「管 [理模板](../../start/using/about-templates.md) 」部分。

1. 在「服務」 **[!UICONTROL Service properties]** 儀表板中通過按鈕訪 ![](assets/edit_darkgrey-24px.png) 問的部分中，為預訂和取消預訂配置確認消息。

   ![](assets/lp_service_parameters.png)

1. 填寫欄 **[!UICONTROL Service label]** 位。 使用自訂確認訊息時，服務標籤是必備的。

1. 為預訂和取消預訂選擇確認消息模板。 提供三種模式：

   * **[!UICONTROL No message]**:此模式允許您建立不帶確認消息的服務。
   * **[!UICONTROL Default message]**:此模式將使用預設訂閱或取消訂閱確認事務性消息。 預設確認消息是通用的，對於使用預設模式的所有服務都是相同的。

      >[!NOTE]
      >
      >您可以在勾選方塊後，按一下區段中的標籤，或從 **[!UICONTROL Service properties]** Adobe Campaign交易訊息清單中選取預設訊息，以修改預設 **[!UICONTROL Show internal transactional messages]** 訊息。

   * **[!UICONTROL Custom message]**:此模式允許您處理特定於每個服務的自定義確認消息。 然後，選擇與 **[!UICONTROL Custom subscription event configuration]** 特定事務性消息模板 [關聯的](../../channels/using/about-transactional-messaging.md) 。 如需詳細資訊，請參 [閱確認服務訂閱](../../audiences/using/confirming-subscription-to-a-service.md)。

1. 儲存服務。 現在已可供使用。

建立服務後，您就可以開始促銷它。

**相關主題：**

* [管理服務與訂閱視訊](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html)
* [推廣服務](../../audiences/using/promoting-a-service.md)
* [建立由訂閱者建立的觀眾](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [將登陸頁面連結至服務](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
