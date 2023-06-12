---
title: 使用 Adobe Experience Platform 屬性個人化行銷活動
description: 瞭解如何使用Adobe體驗平台屬性個人化您的行銷活動。
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
>Audience Destinations服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上託管（目前僅北美地區適用Beta版）才能存取這些功能。 如果您想要存取許可權，請聯絡Adobe客戶服務。
>
>**推播** 和 **應用程式內** 管道尚不適用於使用Adobe Experience Platform中的內容資料進行個人化。

使用設定您的工作流程後 [Adobe Experience Platform對象](../../integrating/using/aep-about-audience-destinations-service.md)，您就可以使用Experience Data Model (XDM)中獨有的設定檔屬性來個人化訊息。

若要這麼做，您必須將這些屬性新增至 **[!UICONTROL Read audience]** 活動：

1. 開啟 **[!UICONTROL Read audience]** 活動。 在 **[!UICONTROL Additional data]** 索引標籤，按一下 **[!UICONTROL Create element]** 按鈕。

   請注意 **[!UICONTROL Additional data]** 標籤僅在選取Adobe Experience Platform對象後才能使用。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >此功能不支援陣列和對應資料型別。 此外，選取器中只會顯示聯合結構描述的資料。

1. 從清單中選取所需的XDM欄位，然後按一下 **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 按一下 **[!UICONTROL Add]** 按鈕以將其新增至其他資料清單。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. 對您想要新增至工作流程的每個XDM欄位重複這些步驟。

   >[!NOTE]
   >
   >您最多可以在中新增20個XDM欄位 **[!UICONTROL Read audience]** 活動。

1. 新增所有欄位後，按一下 **[!UICONTROL Confirm]** 按鈕以儲存您的變更。 現在可透過這些對話方塊來個人化您的傳遞。

如需如何建立及個人化傳送的詳細資訊，請參閱Campaign Standard檔案：

* [探索通訊通道](../../channels/using/get-started-communication-channels.md)
* [關於頻道活動](../../automating/using/about-channel-activities.md)
* [個人化傳遞](../../designing/using/personalization.md)
