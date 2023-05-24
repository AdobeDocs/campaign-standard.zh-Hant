---
title: 將訂閱擴充到應用程式資源
description: 瞭解如何將訂閱擴展到應用程式資源
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

在 Adobe Campaign 中，由行動裝置傳送的行動設定檔屬性資料會儲存在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 資源中，您可藉此定義要從應用程式訂閱者收集的資料。有關自定義資源的詳細資訊，請參閱 [此頁](../../developing/using/key-steps-to-add-a-resource.md)。

可以擴展此資源，以收集要從移動設備發送到Adobe Campaign的資料。

1. 從進階功能表，透過 Adobe Campaign 標誌，依序選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** 及 **[!UICONTROL Custom resources]**。
1. 按一下 **[!UICONTROL Create]** 選擇 **[!UICONTROL Extend an existing resource]** 的雙曲餘切值。
1. 選擇 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 按一下 **[!UICONTROL Create]**。

   ![](assets/in_app_personal_data_4.png)

1. 在 **[!UICONTROL Fields]** 類別 **[!UICONTROL Data structure]** 頁籤，通過按一下 **[!UICONTROL Add field]** 按鈕

   >[!NOTE]
   >
   >如果要管理多個移動應用程式，則必須列出所有應用程式使用的所有欄位。 iOS或Android收集PII調用定義了每個應用程式捕獲哪些欄位。

   ![](assets/in_app_personal_data.png)

1. 添加 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 你的新領域。 選擇域的 **[!UICONTROL Type]**。

   ![](assets/schema_extension_uc9.png)

1. 在 **[!UICONTROL Link to profiles]** 類別，配置用於將配置檔案從Adobe Campaign資料庫連結到應用程式訂閱者（如電子郵件）的協調密鑰。

   請注意，對於In-App消息，您只能為所有移動應用程式定義一個協調密鑰。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** 並發佈自定義資源。 有關自定義資源發佈的詳細資訊，請參閱 [頁](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。
