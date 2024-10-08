---
title: 建立電子郵件
description: 請依照下列步驟，在Adobe Campaign中建立單一傳送電子郵件。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 15%

---

# 建立電子郵件{#creating-an-email}

您可以從[行銷活動](../../start/using/marketing-activities.md#creating-a-marketing-activity)、Adobe Campaign [首頁](../../start/using/interface-description.md#home-page)或[行銷活動清單](../../start/using/marketing-activities.md#about-marketing-activities)中建立電子郵件。 您也可以從工作流程建立單一傳送和循環寄送的電子郵件。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

1. 開始建立電子郵件行銷活動後，請選取您要使用的範本。

   依預設，您可以為每個行銷活動從數個範本中進行選擇。 這可讓您根據需求預先設定某些引數，並為您的傳送指派品牌。 如需詳細資訊，請參閱[管理範本](../../start/using/marketing-activity-templates.md)。

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >預設會隱藏後續與 A/B 測試範本。如果您想要顯示左側方塊（ **[!UICONTROL Filter]**&#x200B;側面板），請核取這些方塊。

1. 輸入電子郵件的一般屬性。 您可以在&#x200B;**標籤**&#x200B;欄位中輸入名稱並編輯識別碼。

   >[!NOTE]
   >
   >活動名稱及其ID都會顯示在介面中，但訊息收件者看不到它們。
   >
   >確認ID欄位未包含任何空白以避免出現任何差異，例如，在與Adobe Analytics整合時。

   您可以新增使用者可在行銷活動內容中看到的說明。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >您可以從首頁或行銷活動清單，在父行銷活動中建立電子郵件。 從已建立的行銷活動中選取。

1. 根據您的業務條件定義訊息的目標。 檢視[關於設定檔](../../audiences/using/about-profiles.md)。

   您也可以定義將驗證訊息的測試設定檔。 請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_creation_3.png)

1. 使用[電子郵件Designer](../../designing/using/designing-content-in-adobe-campaign.md)定義並個人化郵件內容、寄件者名稱和主旨。 如需詳細資訊，請參閱[關於電子郵件內容設計](../../designing/using/designing-content-in-adobe-campaign.md)。

   ![](assets/email_creation_4.png)

   您可以使用預先定義的內容範本，或使用Dreamweaver或Adobe Experience Manager，直接設計您的訊息。 如果您不覺得自己是設計人員，也可以上傳已為您準備的內容，或從URL匯入現有內容。 請參閱「[選擇現有內容](../../designing/using/using-existing-content.md)」。

1. 預覽您的訊息。 請參閱「[預覽訊息](../../sending/using/previewing-messages.md)」。
1. 確認建立電子郵件。

   >[!NOTE]
   >
   >若要儲存電子郵件，您必須先對內容進行一些編輯。 如果此時按一下「**[!UICONTROL Cancel]**」，您將無法完成精靈，且不會建立您的電子郵件。

   然後會顯示電子郵件控制面板。 它可讓您檢查訊息並[準備傳送](../../sending/using/preparing-the-send.md)。

   右上角的&#x200B;**[!UICONTROL Edit properties]**&#x200B;按鈕可讓您編輯電子郵件的屬性。 例如，您可以設定電子郵件，以便在準備傳送時計算其標籤。  可用的引數列在[此區段](../../administration/using/configuring-email-channel.md#list-of-email-properties)中。

   ![](assets/delivery_dashboard_2.png)

1. 排程傳送。請參閱[排程訊息](../../sending/using/about-scheduling-messages.md)。

   ![](assets/delivery_planning.png)

1. 準備您的訊息以分析其目標。 請參閱[準備傳送](../../sending/using/confirming-the-send.md)。

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >您可以設定全域跨通道疲勞規則，這會從促銷活動自動排除過度請求的設定檔。如需詳細資訊，請參閱[疲勞規則](../../sending/using/fatigue-rules.md)。

1. 傳送校樣以檢查並驗證您的訊息，並監控其收件匣呈現。請參閱[傳送校樣](../../sending/using/sending-proofs.md)。

   ![](assets/bat_select.png)

1. 傳送訊息，並透過訊息控制面板和記錄檔檢查其傳送。 請參閱[傳送訊息](../../sending/using/confirming-the-send.md)。

   ![](assets/confirm_delivery.png)

1. 使用傳遞報告測量訊息的影響。 如需報告的詳細資訊，請參閱[本節](../../reporting/using/about-dynamic-reports.md)。

**相關主題**：

* [建立個人化電子郵件](../../channels/using/key-steps-to-send-a-message.md)逐步指南
* [Adobe Campaign與Dreamweaver整合](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [與Adobe Experience Manager整合](../../integrating/using/integrating-with-experience-manager.md)

## 教學課程影片 {#video}

本影片說明如何建立電子郵件。

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)提供其他Campaign Standard操作說明影片。
