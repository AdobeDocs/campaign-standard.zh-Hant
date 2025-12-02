---
title: 使用 Adobe Experience Platform 屬性個人化行銷活動
description: 瞭解如何使用Adobe Experience Platform屬性個人化您的促銷活動。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 6%

---

# 使用 Adobe Experience Platform 屬性個人化行銷活動 {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Audience Destinations服務目前為測試版，可能會經常更新，恕不另行通知。 客戶需在Azure上代管（目前僅限北美地區使用Beta版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。
>
>使用Adobe Experience Platform中的內容資料的&#x200B;**推播**&#x200B;和&#x200B;**應用程式內**&#x200B;管道還不可用於個人化。

您的工作流程設定為[Adobe Experience Platform對象](../../integrating/using/aep-about-audience-destinations-service.md)後，您就可以使用Experience Data Model (XDM)中獨有的設定檔屬性來個人化訊息。

若要這麼做，您必須將這些屬性新增至&#x200B;**[!UICONTROL Read audience]**&#x200B;活動：

1. 開啟&#x200B;**[!UICONTROL Read audience]**&#x200B;活動。 在&#x200B;**[!UICONTROL Additional data]**&#x200B;索引標籤中，按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕。

   請注意，**[!UICONTROL Additional data]**&#x200B;標籤只有在選取Adobe Experience Platform對象後才能使用。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >此功能不支援陣列和對應資料型別。 此外，選擇器中只會顯示聯合結構描述的資料。

1. 從清單中選取所需的XDM欄位，然後按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 按一下「**[!UICONTROL Add]**」按鈕，將其新增至其他資料清單。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. 對您想要新增到工作流程中的每個XDM欄位重複這些步驟。

   >[!NOTE]
   >
   >您可以在&#x200B;**[!UICONTROL Read audience]**&#x200B;活動中新增最多20個XDM欄位。

1. 新增所有欄位後，按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;按鈕以儲存變更。 現在可供個人化您的傳遞。

如需如何建立及個人化傳送的詳細資訊，請參閱Campaign Standard檔案：

* [探索通訊頻道](../../channels/using/get-started-communication-channels.md)
* [關於頻道活動](../../automating/using/about-channel-activities.md)
* [個人化傳遞](../../designing/using/personalization.md)
