---
solution: Campaign Standard
product: campaign
title: 使用 Adobe Experience Platform屬性個人化行銷活動
description: 瞭解如何使用Adobe體驗平台屬性個人化您的宣傳活動。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---


# 使用 Adobe Experience Platform屬性個人化行銷活動 {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>觀眾目標服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。
>
>**Pushand** In- **** Appchannels尚無法使用來自Adobe Experience Platform的情境式資料進行個人化。

在您的工作流程設定了[Adobe Experience Platform觀眾](../../integrating/using/aep-about-audience-destinations-service.md)後，您就可以使用「體驗資料模型」(XDM)中獨家存在的描述檔屬性來個人化訊息。

若要這麼做，您必須將下列屬性新增至&#x200B;**[!UICONTROL Read audience]**&#x200B;活動：

1. 開啟&#x200B;**[!UICONTROL Read audience]**&#x200B;活動。 在&#x200B;**[!UICONTROL Additional data]**&#x200B;標籤中，按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕。

   請注意，**[!UICONTROL Additional data]**&#x200B;標籤僅在選取Adobe Experience Platform對象後才可用。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >此功能不支援陣列和地圖資料類型。 此外，只有聯合架構中的資料才會顯示在選擇器中。

1. 從清單中選擇所需的XDM欄位，然後按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕，將其新增至其他資料清單。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. 對要添加到工作流中的每個XDM欄位重複這些步驟。

   >[!NOTE]
   >
   >在&#x200B;**[!UICONTROL Read audience]**&#x200B;活動中最多可以添加20個XDM欄位。

1. 新增所有欄位後，按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;按鈕以儲存您所做的變更。 現在，您可以透過這些工具個人化您的遞送。

有關如何建立和個性化交貨的詳細資訊，請參閱Campaign Standard文檔：

* [探索通訊通道](../../channels/using/get-started-communication-channels.md)
* [關於通道活動](../../automating/using/about-channel-activities.md)
* [個人化傳遞](../../designing/using/personalization.md)
