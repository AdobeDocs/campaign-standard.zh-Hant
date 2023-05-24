---
title: 目標定位 Adobe Experience Platform 對象
description: 瞭解如何在工作流中針對Adobe Experience Platform受眾。
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
>受眾目標服務當前處於測試版，可能需要頻繁更新，恕不另行通知。 客戶需要在Azure上托管（目前僅在北美試用版）才能訪問這些功能。 如果您想訪問，請聯繫Adobe客戶服務。

建立 [Adobe Experience Platform觀眾](../../integrating/using/aep-about-audience-destinations-service.md) 使用「段生成器」，您可以像對工作流中的「市場活動」受眾那樣使用它來個性化和發送消息。

要在工作流中激活Adobe Experience Platform受眾，請執行以下步驟：

1. 添加 **[!UICONTROL Read audience]** 活動，然後將其開啟。

1. 選擇 **[!UICONTROL Adobe Experience Platform]** 選項 **[!UICONTROL Type of audience]**，然後添加所需的受眾。

   ![](assets/aep_wkf_readaudience.png)

1. （可選）選擇受眾後，您可以按一下眼睛按鈕來查看和/或編輯段定義（確保再次保存更改）。

   按一下「眼睛」按鈕將只是將您引導至「市場活動」中與選定受眾關聯的「段生成器」（在另一個頁籤中）。

1. 選擇 **[!UICONTROL Platform data mapping]** 元素，指定所選Adobe Experience Platform受眾的所需目標維。

   預設情況下，用於協調的主鍵（例如，配置檔案表的iRecipientID、AppSubscription表的iAppSubscriptionID）將自動從下拉清單中可用。 要在主鍵之外定位，必須建立自定義 **命名空間**。

   >[!NOTE]
   >
   >對於主鍵之外的目標，還必須建立與自定義命名空間對應的自定義目標映射。 有關目標映射的詳細資訊，請參閱 [此部分](../../administration/using/target-mappings-in-campaign.md)。

   ![](assets/aep_wkf_readaudience_namespace.png)

   此清單包含已在實例上配置的所有體驗資料模型(XDM)映射。 有關Adobe Experience Platform資料連接器的詳細資訊，請參閱 [此專用文檔](../../integrating/using/aep-about-data-connector.md)。

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. 正確配置受眾和目標維後，按一下 **[!UICONTROL Confirm]** 按鈕。

現在，您可以配置工作流，使其與其他活動一起進行。 例如，可以連結 **[!UICONTROL Email delivery]** 活動，向已選擇的受眾發送電子郵件。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard允許您在所有傳送渠道中瞄準Adobe Experience Platform受眾：電子郵件、SMS消息、直接郵件消息、推送通知和In-App消息。
>
>*注意：對於所有推送消息和In-App消息，Campaign Standard僅支援已知配置檔案的傳遞。

有關如何使用工作流和交貨的詳細資訊，請參閱以下各節：

* [探索工作流程](../../automating/using/get-started-workflows.md)
* [建立工作流程](../../automating/using/building-a-workflow.md)
* [探索通訊通道](../../channels/using/get-started-communication-channels.md)
* [關於頻道活動](../../automating/using/about-channel-activities.md)
