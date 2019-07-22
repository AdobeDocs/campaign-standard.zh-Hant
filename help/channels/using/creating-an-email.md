---
title: 建立電子郵件
seo-title: 建立電子郵件
description: 建立電子郵件
seo-description: 請依照下列步驟，在Adobe Campaign中建立單一傳送電子郵件。
page-status-flag: 從未啓動
uuid: 74c7ef35-82c0-4bc4-b1 f6-8e74 fdcaea3 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 電子郵件訊息
discoiquuid: b27e0170-e73 f-4782-8568-02927fb374 f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8f4c849adf1852d8a23c5ff5252da25c175faa84

---


# Creating an email{#creating-an-email}

You can create an email from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity), from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), or in the [marketing activity list](../../start/using/marketing-activities.md#about-marketing-activities). 您也可以從工作流程建立單一傳送和週期性電子郵件。

1. 開始建立電子郵件行銷活動後，選取您要使用的範本。

   根據預設，您可以從各個行銷活動的範本中選擇。這可讓您根據需求預先設定某些參數，並為您的遞送指派品牌。For more on this, see [Managing templates](../../start/using/about-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >依預設會隱藏後續和A/B測試範本。Check the boxes on the left side ( **[!UICONTROL Filter]** lateral panel) if you want to display them.

1. 輸入電子郵件的一般屬性。You can enter a name in the **Label** field and edit the ID. 活動名稱及其ID都會出現在介面中，但訊息收件者看不到。

   您可以新增使用者在促銷活動內容中看到的說明。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >您可以從首頁或行銷活動清單中，建立父促銷活動內的電子郵件。從已建立的促銷活動中選取它。

1. 根據您的業務標準定義訊息的目標。See [Managing profiles](../../audiences/using/about-profiles.md).

   您也可以定義將驗證訊息的測試設定檔。See [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

   ![](assets/email_creation_3.png)

1. Define and personalize the message content, sender name and subject using the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer). For more on this, see [About email content design](../../designing/using/about-email-content-design.md).

   ![](assets/email_creation_4.png)

   您可以直接使用預先定義的內容範本，或使用Dreamweaver或Adobe Experience Manager來設計訊息。如果您不想設計人員，也可以上傳已準備好的內容，或是從URL匯入現有內容。See [Selecting an existing content](../../designing/using/selecting-an-existing-content.md).

1. 預覽您的訊息。See [Previewing messages](../../sending/using/previewing-messages.md).
1. 確認建立電子郵件。

   >[!NOTE]
   >
   >若要儲存您的電子郵件，您必須先對內容進行一些編輯。If you click **[!UICONTROL Cancel]** at this point, you will not complete the wizard and your email will not be created.

   接著會顯示電子郵件控制面板。It allows you to check your message and [prepare the send](../../sending/using/preparing-the-send.md).

   The **[!UICONTROL Edit properties]** button in the upper-right corner allows you to edit the properties of the email. 例如，您可以設定電子郵件，以便在傳送準備時計算其標籤。Available parameters are listed in [this section](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. 排程傳送。See [Scheduling messages](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. 準備訊息以分析其目標。See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >您可以設定全域跨通道疲勞規則，自動排除促銷活動中被覆蓋的設定檔。For more on this, see [Fatigue rules](../../administration/using/fatigue-rules.md).

1. 傳送校樣以檢查並驗證您的訊息，並監控其收件匣演算。See [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   ![](assets/bat_select.png)

1. 傳送訊息並檢查透過訊息儀表板和記錄檔傳送的訊息。See [Sending messages](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. 透過傳送報告評估訊息的影響力。For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**相關主題**：

* [建立電子郵件](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) 視訊
* [建立個人化電子郵件](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GettingStartedEmail.html) 逐步指南
* [Adobe Campaign和Dreamweaver整合](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) 影片
* [與Adobe Experience Manager整合](../../integrating/using/integrating-with-experience-manager.md)

