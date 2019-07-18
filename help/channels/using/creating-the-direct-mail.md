---
title: 建立直接郵件
seo-title: 建立直接郵件
description: 建立直接郵件
seo-description: 請遵循下列步驟，在Adobe Campaign中建立直接郵件傳送。
page-status-flag: 從未啓動
uuid: 3b1365c4-4ea1-4434-818b-05ff0c9b42c1
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 直接郵件
discoiquuid: 5b0227f-9438-4001-bc2 f-3d8661 d173 b3
context-tags: delivery，DirectMailContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Creating the direct mail{#creating-the-direct-mail}

建立直接郵件的方式與建立一般電子郵件非常類似。下列步驟說明此渠道專屬的組態。Refer to [Creating an email](../../channels/using/creating-an-email.md) for more information on other options.

1. 建立新的直效郵件傳送。You can create one from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), in a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or in a [marketing activity list](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   >[!NOTE]
   >
   >您也可以在工作流程中新增直效郵件活動。For more on this, refer to the [Workflows](../../automating/using/direct-mail-delivery.md) guide.

   ![](assets/direct_mail_1.png)

1. Choose either the out-of-the-box **[!UICONTROL Direct mail]** template or one of your own templates. For more information on templates, refer to the [Managing templates](../../start/using/about-templates.md) section.

   ![](assets/direct_mail_2.png)

1. 輸入傳送的一般屬性。

   ![](assets/direct_mail_3.png)

1. 定義要包含在擷取檔案中的對象，以及測試和補漏白描述檔。See [Defining the direct mail audience](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >觀眾定義與定義一般電子郵件對象非常相似。See [Creating audiences](../../audiences/using/creating-audiences.md).

1. 編輯檔案的內容：欄以包含每個描述檔、檔案結構、頁首和頁尾。See [Defining the direct mail content](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Click on the **[!UICONTROL Schedule]** section of the delivery dashboard to define the contact date. 對於直接郵件，必須使用聯絡日期。For more information, refer to [Scheduling the send](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. If you added test profiles (refer to [Adding test and trap profiles](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)), you can test your delivery before preparing the final file. 它可讓您建立僅包含測試描述檔的範例檔案。

   Click on **[!UICONTROL Test]** to generate the sample file. Click on **[!UICONTROL Summary]**, in the top left corner, then select **[!UICONTROL Proofs]**. On the left part of the screen, select the proof and click on **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >**[!UICONTROL Export]** 必須角色才能讓Adobe Campaign匯出檔案並供下載。請聯絡您的管理員。

   ![](assets/direct_mail_19.png)

1. Once you have defined your delivery content, audience and contact date, click on the **[!UICONTROL Prepare]** button, on the delivery dashboard.

   ![](assets/direct_mail_16.png)

   套用「打字」規則。例如，所有未指定的郵遞地址都會從目標中排除。This is why you need to make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information (see [Recommendations](../../channels/using/about-direct-mail.md#recommendations)). If you have defined a **[!UICONTROL Maximum volume of message]** in the direct mail properties or at the template level, it will also be applied here.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >您可以設定全域跨通道疲勞規則，自動排除促銷活動中被覆蓋的設定檔。See [Fatigue rules](../../administration/using/fatigue-rules.md).

1. Click on **[!UICONTROL Explore file]** to preview the first 100 lines of the file.

   ![](assets/direct_mail_18.png)

   在畫面左側的本機下載可存取完整檔案。Downloading the file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

   >[!NOTE]
   >
   >**[!UICONTROL Export]** 必須角色才能讓Adobe Campaign匯出檔案並供下載。請聯絡您的管理員。

   If you need to change the delivery content, you only have to click on the **[!UICONTROL Regenerate file]** button to take the change into account. 不需要再進行準備。

   ![](assets/direct_mail_21.png)

1. To confirm that the file is final, click on **[!UICONTROL Confirm]** in the delivery dashboard.

   ![](assets/direct_mail_20.png)

您現在已準備好將擷取檔案傳送至直接郵件提供者。為此，您有幾個選項：

* 透過一般電子郵件傳送，並附帶檔案
* Send it via Campaign: perform your direct mail within a campaign [workflow](../../automating/using/direct-mail-delivery.md) and add a **[!UICONTROL Transfer file]** to send the file via FTP for example. See [Transfer file](../../automating/using/transfer-file.md).

提供者會擷取錯誤位址清單，並將此資訊傳送至Adobe Campaign，自動列入錯誤的地址。See [Return to sender](../../channels/using/return-to-sender.md).
