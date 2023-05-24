---
title: 使用 Adobe Experience Platform 屬性個人化行銷活動
description: 瞭解如何使用「Adobe體驗平台」屬性個性化您的活動。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---

# 使用 Adobe Experience Platform 屬性個人化行銷活動 {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>受眾目標服務當前處於測試版，可能需要頻繁更新，恕不另行通知。 客戶需要在Azure上托管（目前僅在北美試用版）才能訪問這些功能。 如果您想訪問，請聯繫Adobe客戶服務。
>
>**推** 和 **應用程式內** 尚無法使用來自Adobe Experience Platform的上下文資料進行個性化。

一旦您的工作流配置為 [Adobe Experience Platform觀眾](../../integrating/using/aep-about-audience-destinations-service.md)，您可以使用「體驗資料模型」(XDM)中僅存在的配置檔案屬性個性化消息。

為此，必須將這些屬性添加到 **[!UICONTROL Read audience]** 活動：

1. 開啟 **[!UICONTROL Read audience]** 的子菜單。 在 **[!UICONTROL Additional data]** 頁籤 **[!UICONTROL Create element]** 按鈕

   請注意 **[!UICONTROL Additional data]** 頁籤僅在選擇Adobe Experience Platform受眾後才可用。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >此功能不支援陣列和映射資料類型。 此外，在選取器中將只顯示聯合架構中的資料。

1. 從清單中選擇所需的XDM欄位，然後按一下 **[!UICONTROL Confirm]**。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 按一下 **[!UICONTROL Add]** 按鈕將其添加到附加資料清單。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. 對要添加到工作流中的每個XDM欄位重複這些步驟。

   >[!NOTE]
   >
   >您最多可以在 **[!UICONTROL Read audience]** 的子菜單。

1. 添加所有欄位後，按一下 **[!UICONTROL Confirm]** 按鈕。 現在，它們將可用於個性化您的交貨。

有關如何建立和個性化交貨的詳細資訊，請參閱Campaign Standard文檔：

* [探索通訊通道](../../channels/using/get-started-communication-channels.md)
* [關於頻道活動](../../automating/using/about-channel-activities.md)
* [個人化傳遞](../../designing/using/personalization.md)
