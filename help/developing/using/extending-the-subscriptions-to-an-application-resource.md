---
title: 將訂閱擴充到應用程式資源
description: 了解如何將訂閱擴充至應用程式資源
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ac9c556d-c0f6-4b33-8855-1f5f669c148f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 24%

---

# 將訂閱擴充到應用程式資源{#extending-the-subscriptions-to-an-application-resource}

在 Adobe Campaign 中，由行動裝置傳送的行動設定檔屬性資料會儲存在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 資源中，您可藉此定義要從應用程式訂閱者收集的資料。有關自定義資源的詳細資訊，請參閱[此頁](../../developing/using/key-steps-to-add-a-resource.md)。

可擴充此資源，以收集您要從行動裝置傳送至Adobe Campaign的資料。

1. 從進階功能表，透過 Adobe Campaign 標誌，依序選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** 及 **[!UICONTROL Custom resources]**。
1. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;並選擇&#x200B;**[!UICONTROL Extend an existing resource]**&#x200B;選項。
1. 選擇&#x200B;**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;資源，然後按一下&#x200B;**[!UICONTROL Create]**。

   ![](assets/in_app_personal_data_4.png)

1. 在&#x200B;**[!UICONTROL Data structure]**&#x200B;標籤的&#x200B;**[!UICONTROL Fields]**&#x200B;類別中，按一下&#x200B;**[!UICONTROL Add field]**&#x200B;按鈕，定義您要從行動應用程式擷取的客戶資料。

   >[!NOTE]
   >
   >如果您管理多個行動應用程式，則必須列出所有應用程式使用的所有欄位。 iOS或Android收集PII呼叫會定義每個應用程式擷取的欄位。

   ![](assets/in_app_personal_data.png)

1. 新增&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL ID]**&#x200B;至您的新欄位。 選取欄位的&#x200B;**[!UICONTROL Type]**。

   ![](assets/schema_extension_uc9.png)

1. 在&#x200B;**[!UICONTROL Link to profiles]**&#x200B;類別中，設定用於將設定檔從Adobe Campaign資料庫連結至應用程式訂閱者（例如電子郵件）的調解金鑰。

   請注意，針對您的應用程式內訊息，您只能為所有行動應用程式定義一個調解金鑰。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** 和發佈自訂資源。有關自定義資源發佈的詳細資訊，請參閱此[page](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。
