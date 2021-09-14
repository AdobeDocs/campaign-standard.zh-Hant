---
title: 目標定位 Adobe Experience Platform 對象
description: 了解如何在工作流程中鎖定Adobe Experience Platform對象。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 11e2cd7e-99b7-45cc-a0c2-41049128fe49
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---

# 目標定位 Adobe Experience Platform 對象 {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Audience Destinations服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上托管（目前測試版僅供北美使用），才能存取這些功能。 如果您想要存取權限，請聯絡Adobe客戶服務。

使用區段產生器建立[Adobe Experience Platform對象](../../integrating/using/aep-about-audience-destinations-service.md)後，您就可以使用與工作流程中促銷活動對象個人化和傳送訊息相同的方式使用它。

若要在工作流程中啟用Adobe Experience Platform對象，請遵循下列步驟：

1. 將&#x200B;**[!UICONTROL Read audience]**&#x200B;活動新增至工作流程，然後開啟它。

1. 選取&#x200B;**[!UICONTROL Type of audience]**&#x200B;下方的&#x200B;**[!UICONTROL Adobe Experience Platform]**&#x200B;選項，然後新增所需的對象。

   ![](assets/aep_wkf_readaudience.png)

1. （選用）選取對象後，您可以按一下眼睛按鈕來檢閱和/或編輯區段定義（請務必再次儲存您的變更）。

   按一下眼睛按鈕，只需將您導向與Campaign中所選對象相關聯的區段產生器（在另一個標籤中）。

1. 選取&#x200B;**[!UICONTROL Platform data mapping]**&#x200B;元素，以指定所選Adobe Experience Platform對象的所需目標維度。

   依預設，用於調解的主要金鑰（例如設定檔表格的iRecipientID、AppSubscription表格的iAppSubscriptionID）將自動從下拉式清單中提供。 若要在主索引鍵之外定位，您必須建立自訂&#x200B;**命名空間**。

   >[!NOTE]
   >
   >對於主索引鍵以外的目標，您也必須建立與自訂命名空間對應的自訂目標對應。 如需目標對應的詳細資訊，請參閱[此區段](../../administration/using/target-mappings-in-campaign.md)。

   ![](assets/aep_wkf_readaudience_namespace.png)

   此清單包含您執行個體上已設定的所有Experience Data Model(XDM)對應。 如需Adobe Experience Platform Data Connector的詳細資訊，請參閱[此專屬檔案](../../integrating/using/aep-about-data-connector.md)。

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. 正確設定對象和目標維度後，按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;按鈕以儲存您的變更。

您現在可以使用其他活動來設定您的工作流程。 例如，您可以連結&#x200B;**[!UICONTROL Email delivery]**&#x200B;活動，以傳送電子郵件給已選取的對象。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard可讓您鎖定所有傳送管道中的Adobe Experience Platform對象：電子郵件、簡訊、直接郵件訊息、推播通知和應用程式內訊息。
>
>*注意：對於所有推送訊息和應用程式內訊息，Campaign Standard僅支援已知設定檔的傳送。

如需如何使用工作流程和傳送的詳細資訊，請參閱以下章節：

* [探索工作流程](../../automating/using/get-started-workflows.md)
* [建立工作流程](../../automating/using/building-a-workflow.md)
* [探索通訊通道](../../channels/using/get-started-communication-channels.md)
* [關於頻道活動](../../automating/using/about-channel-activities.md)
