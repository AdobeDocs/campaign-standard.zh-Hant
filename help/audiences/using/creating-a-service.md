---
title: 建立服務
description: 瞭解如何建立您的第一項服務，並將之設定為傳送電子郵件確認給訂閱者。
page-status-flag: never-activated
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: service,wizard;service,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 建立服務{#creating-a-service}

為了能夠管理訂閱，您必須先建立並設定服務。設定新服務可讓您指定設定檔在訂閱或取消訂閱服務時，將會收到的電子郵件確認。您也會定義連結至服務的訂閱和取消訂閱登錄頁面。例如，插入電子郵件中的服務訂閱連結會自動將設定檔導向服務中指定的訂閱登錄頁面。

若要設定服務：

1. 透過 Adobe Campaign 標誌，從進階功能表選取 **[!UICONTROL Profiles & audiences]**  >  **[!UICONTROL Services]**，新增服務或選取現有服務。如果您建立新服務，只需依照畫面上顯示的步驟進行即可。

   預設服務範本可供使用。此範本已預先設定預設登錄頁面和確認電子郵件。您可以建立其他範本來定義特定組態。如需詳細資訊，請參閱[管理範](../../start/using/marketing-activity-templates.md)本區段。

1. 在 **[!UICONTROL Service properties]** 區段中，透過服務控制面板中的 ![](assets/edit_darkgrey-24px.png) 存取，為訂閱和取消訂閱設定確認訊息。

   ![](assets/lp_service_parameters.png)

1. 選取 **[!UICONTROL Subscriptions with an expiration date]** 選項，以設定訂閱的有效持續期間。

   ![](assets/lp_service_expiration.png)

   您可以在「分段」活動中使用到期日，為已訂閱未到期服務的人定位設定檔目標。

1. 填寫 **[!UICONTROL Service label]** 欄位。使用自訂確認訊息時，服務標籤是必填欄位。

1. 為訂閱和取消訂閱選取確認訊息範本。提供三種模式：

   * **[!UICONTROL No message]**：此模式可讓您建立不含確認訊息的服務。
   * **[!UICONTROL Default message]**：此模式將使用預設的訂閱或取消訂閱確認交易式訊息。預設確認訊息是通用的，而且對於使用預設模式的所有服務都是相同的。

      >[!NOTE]
      >
      >您可以在核取 **[!UICONTROL Show internal transactional messages]** 方塊後，按一下 **[!UICONTROL Service properties]** 區段中的標籤，或是從 Adobe Campaign 交易式訊息清單中選取預設訊息，進而修改預設訊息。

   * **[!UICONTROL Custom message]**：此模式可讓您處理每個服務專屬的自訂確認訊息。然後，選取與特定[交易式訊息範本](../../channels/using/getting-started-with-transactional-msg.md)相關聯的 **[!UICONTROL Custom subscription event configuration]**。如需詳細資訊，請參閱[確認服務訂閱](../../audiences/using/confirming-subscription-to-a-service.md)。

1. 儲存服務。現在已可供使用。

一旦建立服務之後，您就可以開始促銷它。

**相關主題：**

* [管理服務及訂閱](https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/profiles-and-audiences/services-and-subscriptions.translate.html)影片
* [推廣服務](../../audiences/using/promoting-a-service.md)
* [建立由訂閱者建立的對象](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [將登錄頁面連結至服務](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
