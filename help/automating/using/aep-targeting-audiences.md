---
title: 鎖定Adobe Experience platform受眾
description: 瞭解如何在工作流程中鎖定Adobe Experience PLatform受眾。
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# 鎖定Adobe Experience platform受眾 {#targeting-aep-audiences}

>[!IMPORTANT]
>
>觀眾目標服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

一旦您使用「統一設定檔」區段產生器建立 [](../../audiences/using/aep-about-audience-destinations-service.md) Adobe Experience platform觀眾後，您就可以像在工作流程中針對Campaign觀眾建立個人化訊息和傳送訊息一樣的方式使用。

若要將Adobe Experience Platform觀眾啟動至您的工作流程，請遵循下列步驟：

1. 將活動 **[!UICONTROL Read audience]**新增至工作流程，然後開啟它。

1. 選取下方 **[!UICONTROL Adobe Experience Platform]**的選**[!UICONTROL Type of audience]**&#x200B;項，然後新增所要的對象。

   ![](assets/aep_wkf_readaudience.png)

1. （選擇性）在選取對象後，您可以按一下眼睛按鈕來檢閱和／或編輯區段定義（請務必再次儲存變更）。

   按一下眼睛按鈕，您只需將您導向「統一區段產生器」（在另一個標籤中），該產生器與「促銷活動」中選取的對象相關聯。

1. 選取元 **[!UICONTROL Platform data mapping]**素，以指定所選Adobe Experience platform對象的所需定位維度。

   依預設，用於協調的主要金鑰（例如，描述檔表格的iRecipientID、AppSubscription表格的iAppSubscriptionID）將自動從下拉式清單中提供。 若要定位在主鍵以外，您必須建立自訂的命名 **空間**。

   >[!NOTE]
   >
   >對於主鍵以外的目標，您還必須建立與自定義命名空間對應的自定義目標映射。 For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   此清單包含您例項上已設定的所有體驗資料模型(XDM)映射。 有關Adobe Experience Platform Data Connector的更多資訊，請參閱 [本專用檔案](../../administration/using/aep-about-data-connector.md)。

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. 在正確設定對象和定位維度後，按一下按 **[!UICONTROL Confirm]**鈕以儲存變更。

您現在可以搭配其他活動來設定工作流程。 例如，您可以連結活動， **[!UICONTROL Email delivery]**將電子郵件傳送給已選取的對象。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign standard可讓您在所有傳送通道中鎖定Adobe Experience platform受眾：電子郵件、SMS訊息、直接郵件訊息、推播通知和應用程式內訊息。

如需如何使用工作流程和傳送的詳細資訊，請參閱下列章節：

* [探索工作流程](../../automating/using/discovering-workflows.md)
* [建立工作流程](../../automating/using/building-a-workflow.md)
* [探索通訊通道](../../channels/using/discovering-communication-channels.md)
* [關於通道活動](../../automating/using/about-channel-activities.md)
