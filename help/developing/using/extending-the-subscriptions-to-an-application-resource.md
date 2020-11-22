---
solution: Campaign Standard
product: campaign
title: 將訂閱擴充到應用程式資源
description: null
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 25%

---


# 將訂閱擴充到應用程式資源{#extending-the-subscriptions-to-an-application-resource}

在 Adobe Campaign 中，由行動裝置傳送的行動設定檔屬性資料會儲存在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 資源中，您可藉此定義要從應用程式訂閱者收集的資料。For more information on custom resources, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

此資源可加以擴充，以收集您要從行動裝置傳送至Adobe Campaign的資料。

1. 從進階功能表，透過 Adobe Campaign 標誌，依序選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** 及 **[!UICONTROL Custom resources]**。
1. 按一 **[!UICONTROL Create]** 下並選擇 **[!UICONTROL Extend an existing resource]** 選項。
1. Select the **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource and click **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. 在標籤 **[!UICONTROL Fields]** 的類別中， **[!UICONTROL Data structure]** 定義您要從行動應用程式擷取的客戶資料，方法是按一下 **[!UICONTROL Add field]** 按鈕。

   >[!NOTE]
   >
   >如果您要管理數個行動應用程式，則必須列出所有應用程式所使用的所有欄位。 iOS或Android收集PII呼叫會定義每個應用程式擷取的欄位。

   ![](assets/in_app_personal_data.png)

1. 新增 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 新欄位。 選擇欄位的 **[!UICONTROL Type]**。

   ![](assets/schema_extension_uc9.png)

1. 在類別 **[!UICONTROL Link to profiles]** 中，設定用於將Adobe Campaign資料庫的描述檔連結至應用程式的訂閱者（例如電子郵件）的協調金鑰。

   請注意，對於您的應用程式內訊息，您只能為所有行動應用程式定義一個協調金鑰。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** 並發佈您的自訂資源。 有關自定義資源發佈的詳細資訊，請參 [閱此頁](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

