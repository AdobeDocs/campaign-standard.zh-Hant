---
title: 將訂閱延伸至應用程式資源
seo-title: 將訂閱延伸至應用程式資源
description: 將訂閱延伸至應用程式資源
seo-description: null
page-status-flag: 從未啓動
uuid: 8879b427-b31 b-4311-bf54-258a91 b1 fb78
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 開發
content-type: reference
topic-tags: 使用案例—擴充資源
discoiquuid: 59fa74e-86fc-42d3-90da-f48580 b ec13
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 20b4d5dfb297cac4cd69fe6f945b4399abd7f06a

---


# Extending the subscriptions to an application resource{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers. For more information on custom resources, refer to this [page](../../developing/using/key-steps-to-add-a-resource.md).

您可以擴充此資源，收集您要從行動裝置傳送至Adobe Campaign的資料。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Custom resources]**.
1. Click **[!UICONTROL Create]** and choose the **[!UICONTROL Extend an existing resource]** option.
1. Select the **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource and click **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. In the **[!UICONTROL Fields]** category of the **[!UICONTROL Data structure]** tab, define the customer data that you want to retrieve from your mobile application by clicking the **[!UICONTROL Add field]** button.

   >[!NOTE]
   >
   >如果您要管理數個行動應用程式，則必須列出所有應用程式所使用的欄位。iOS或Android收集PII呼叫會定義每個應用程式擷取的欄位。

   ![](assets/in_app_personal_data.png)

1. Add a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to your new field. Select your field's **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. **[!UICONTROL Link to profiles]** 在類別中，設定用於將描述檔從Adobe Campaign資料庫連結至應用程式用戶的協調金鑰，例如電子郵件。

   請注意，對於您的應用程式內訊息，您只能為所有行動應用程式定義一個協調金鑰。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** 併發布您的自訂資源。For more information on custom resource publication, refer to this [page](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

