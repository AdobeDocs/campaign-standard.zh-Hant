---
solution: Campaign Standard
product: campaign
title: 鎖定 Adobe Experience Platform 閱聽眾
description: 瞭解如何在工作流程中鎖定Adobe Experience PLatform受眾。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---


# 鎖定 Adobe Experience Platform 閱聽眾 {#targeting-aep-audiences}

>[!IMPORTANT]
>
>觀眾目標服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

使用「區段產生器」建立[Adobe Experience Platform觀眾](../../audiences/using/aep-about-audience-destinations-service.md)後，您就可以與工作流程中的「促銷活動」觀眾相同的方式使用&lt;a0/>Adobe Experience Platform觀眾，以個人化和傳送訊息。

若要將Adobe Experience Platform觀眾啟動至您的工作流程，請遵循下列步驟：

1. 將&#x200B;**[!UICONTROL Read audience]**&#x200B;活動新增至工作流程，然後開啟它。

1. 選取&#x200B;**[!UICONTROL Type of audience]**&#x200B;下方的&#x200B;**[!UICONTROL Adobe Experience Platform]**&#x200B;選項，然後新增所要的對象。

   ![](assets/aep_wkf_readaudience.png)

1. （選擇性）在選取對象後，您可以按一下眼睛按鈕來檢閱和／或編輯區段定義（請務必再次儲存變更）。

   按一下眼睛按鈕，您只需將您導向「區段產生器」（在另一個標籤中），此「區段產生器」與「促銷活動」中選取的對象相關聯。

1. 選取&#x200B;**[!UICONTROL Platform data mapping]**&#x200B;元素，以指定所選Adobe Experience Platform對象所需的定位維度。

   依預設，用於協調的主要金鑰（例如，描述檔表格的iRecipientID、AppSubscription表格的iAppSubscriptionID）將自動從下拉式清單中提供。 若要定位在主鍵以外，您必須建立自訂的&#x200B;**Namespace**。

   >[!NOTE]
   >
   >對於主鍵以外的目標，您還必須建立與自定義命名空間對應的自定義目標映射。 有關「目標映射」的詳細資訊，請參閱[本節](../../administration/using/target-mappings-in-campaign.md)。

   ![](assets/aep_wkf_readaudience_namespace.png)

   此清單包含您例項上已設定的所有體驗資料模型(XDM)映射。 有關Adobe Experience Platform Data Connector的更多資訊，請參閱[本專用檔案](../../developing/using/aep-about-data-connector.md)。

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. 對象和定位維度正確設定後，按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;按鈕以儲存變更。

您現在可以搭配其他活動來設定工作流程。 例如，您可以連結&#x200B;**[!UICONTROL Email delivery]**&#x200B;活動，將電子郵件傳送給已選取的對象。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard可讓您在所有傳送通道中鎖定Adobe Experience Platform受眾：電子郵件、簡訊、直接郵件訊息、推播通知和應用程式內訊息。
>
>*注意：對於所有推播和應用程式內訊息，Campaign Standard僅支援傳送已知描述檔。

如需如何使用工作流程和傳送的詳細資訊，請參閱下列章節：

* [探索工作流程](../../automating/using/get-started-workflows.md)
* [建立工作流程](../../automating/using/building-a-workflow.md)
* [探索通訊通道](../../channels/using/get-started-communication-channels.md)
* [關於通道活動](../../automating/using/about-channel-activities.md)
