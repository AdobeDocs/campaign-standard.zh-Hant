---
title: 建立電子郵件
description: 請依照下列步驟，在Adobe Campaign中建立單一傳送的電子郵件。
page-status-flag: never-activated
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e1e092249a447039c0d845f143be532f845ca1dc
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 建立電子郵件{#creating-an-email}

您可以從促銷活動、 [Adobe Campaign首頁或](../../start/using/marketing-activities.md#creating-a-marketing-activity)行銷活動清單 [中建立電子郵件](../../start/using/interface-description.md#home-page)[](../../start/using/marketing-activities.md#about-marketing-activities)。 您也可以從工作流程建立單一傳送和循環寄送的電子郵件。

1. 開始建立電子郵件行銷活動後，請選取您要使用的範本。

   依預設，您可以從多個範本中選擇每個行銷活動。 這可讓您根據您的需求預先設定某些參數，並指派品牌給您的傳送。 For more on this, see [Managing templates](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >預設會隱藏後續與 A/B 測試範本。如果要顯示，請勾選左側 **[!UICONTROL Filter]** 的方塊（側面板）。

1. 輸入電子郵件的一般屬性。 You can enter a name in the **Label** field and edit the ID. 活動名稱及其ID都會出現在介面中，但訊息收件者看不到。

   您可以新增使用者可在行銷活動內容中看到的說明。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >您可以從首頁或行銷活動清單中在父促銷活動中建立電子郵件。 從已建立的促銷活動中選取它。

1. 根據您的業務條件定義訊息的目標。 See [About profiles](../../audiences/using/about-profiles.md).

   您也可以定義將驗證訊息的測試設定檔。 請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_creation_3.png)

1. 使用電子郵件設計工具定義並個人化訊息內容、傳送者名 [稱和主旨](../../designing/using/designing-content-in-adobe-campaign.md)。 如需詳細資訊，請參閱關於 [電子郵件內容設計](../../designing/using/designing-content-in-adobe-campaign.md)。

   ![](assets/email_creation_4.png)

   您可以直接使用預先定義的內容範本，或使用Dreamweaver或Adobe Experience Manager來設計訊息。 如果您不想當設計人員，也可以上傳已為您準備好的內容，或從URL匯入現有內容。 請參 [閱選擇現有內容](../../designing/using/using-existing-content.md)。

1. 預覽您的訊息。 請參閱「[預覽訊息](../../sending/using/previewing-messages.md)」。
1. 確認建立電子郵件。

   >[!NOTE]
   >
   >若要儲存您的電子郵件，您必須先對內容進行一些編輯。 如果您按 **[!UICONTROL Cancel]** 一下此時，將無法完成精靈，而且您的電子郵件將無法建立。

   接著會顯示電子郵件控制面板。 它可讓您檢查訊息並準 [備傳送](../../sending/using/preparing-the-send.md)。

   右 **[!UICONTROL Edit properties]** 上角的按鈕可讓您編輯電子郵件的屬性。 例如，您可以設定電子郵件，以便在傳送準備時計算其標籤。  此部分列出了可用 [的參數](../../administration/using/configuring-email-channel.md#list-of-email-properties)。

   ![](assets/delivery_dashboard_2.png)

1. 排程傳送。請參閱[排程訊息](../../sending/using/about-scheduling-messages.md)。

   ![](assets/delivery_planning.png)

1. 準備訊息以分析其目標。 See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >您可以設定全域跨通道疲勞規則，這會從促銷活動自動排除過度請求的設定檔。如需詳細資訊，請參閱「疲 [乏規則」](../../sending/using/fatigue-rules.md)。

1. 傳送校樣以檢查並驗證您的訊息，並監控其收件匣呈現。請參 [閱傳送證明](../../sending/using/sending-proofs.md)。

   ![](assets/bat_select.png)

1. 傳送訊息並透過訊息儀表板和記錄來檢查其傳送。 請參閱 [傳送訊息](../../sending/using/confirming-the-send.md)。

   ![](assets/confirm_delivery.png)

1. 使用傳送報表評估訊息的影響。 For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**相關主題**：

* [建立電子郵件](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)影片
* [建立個人化電子郵件](https://helpx.adobe.com/tw/campaign/kb/acs-get-started-with-emails.html) ，逐步指南
* [Adobe Campaign與Dreamweaver整合視訊](https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html)
* [與Adobe Experience Manager整合](../../integrating/using/integrating-with-experience-manager.md)
