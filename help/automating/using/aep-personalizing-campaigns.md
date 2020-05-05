---
title: 使用 Adobe Experience Platform屬性個人化行銷活動
description: 瞭解如何使用Adobe Experience Platform屬性個人化您的宣傳活動。
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# 使用 Adobe Experience Platform屬性個人化行銷活動 {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>觀眾目標服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。
>
>**推播和** 應用程式內通道 **** ，目前尚未提供使用Adobe Experience Platform的內容相關資料進行個人化的管道。

在您的工作流程設定好 [Adobe Experience Platform觀眾後](../../audiences/using/aep-about-audience-destinations-service.md)，您就可以使用Experience Data Model(XDM)中獨家存在的描述檔屬性來個人化訊息。

若要這麼做，您必須將下列屬性新增至活 **[!UICONTROL Read audience]** 動：

1. 開啟活 **[!UICONTROL Read audience]** 動。 在標籤 **[!UICONTROL Additional data]** 中，按一下按 **[!UICONTROL Create element]** 鈕。

   請注意， **[!UICONTROL Additional data]** 標籤只有在選取Adobe Experience Platform對象後才可用。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >此功能不支援陣列和地圖資料類型。 此外，只有聯合架構中的資料才會顯示在選擇器中。

1. 從清單中選取所需的XDM欄位，然後按一下 **[!UICONTROL Confirm]**。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 按一下 **[!UICONTROL Add]** 按鈕，將其新增至其他資料清單。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. 對要添加到工作流中的每個XDM欄位重複這些步驟。

   >[!NOTE]
   >
   >在活動中最多可以添加20個XDM字 **[!UICONTROL Read audience]** 段。

1. 新增所有欄位後，按一下按 **[!UICONTROL Confirm]** 鈕以儲存變更。 現在，您可以透過這些工具個人化您的遞送。

如需如何建立和個人化傳送的詳細資訊，請參閱Campaign Standard檔案：

* [探索通訊通道](../../channels/using/get-started-communication-channels.md)
* [關於通道活動](../../automating/using/about-channel-activities.md)
* [個人化遞送](../../designing/using/personalization.md)
