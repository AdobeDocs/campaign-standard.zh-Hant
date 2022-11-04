---
title: 建立電子郵件
description: 請依照下列步驟，在Adobe Campaign中建立單一傳送的電子郵件。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: add823f51b0907628ed52cb2f4453743bc939cbf
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 19%

---

# 建立電子郵件{#creating-an-email}

您可以從 [行銷活動](../../start/using/marketing-activities.md#creating-a-marketing-activity)，來自Adobe Campaign [首頁](../../start/using/interface-description.md#home-page)，或 [行銷活動清單](../../start/using/marketing-activities.md#about-marketing-activities). 您也可以從工作流程建立單一傳送和循環寄送的電子郵件。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

1. 開始建立電子郵件行銷活動後，請選取您要使用的範本。

   依預設，您可以從多個範本中選擇每個行銷活動。 這可讓您根據需求預先設定特定參數，並將品牌指派給您的傳送。 有關詳細資訊，請參閱 [管理範本](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >預設會隱藏後續與 A/B 測試範本。勾選左側的方塊( **[!UICONTROL Filter]** 側面面板)。

1. 輸入電子郵件的一般屬性。 您可以在 **標籤** 欄位和編輯ID。

   {{$include /help/_includes/channel-activities-name-id-fields.md}}

   您可以新增使用者可在行銷活動內容中看到的說明。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >您可以從首頁或行銷活動清單，在父行銷活動內建立電子郵件。 從已建立的促銷活動中選取。

1. 根據您的業務條件定義訊息的目標。 請參閱 [關於設定檔](../../audiences/using/about-profiles.md).

   您也可以定義將驗證訊息的測試設定檔。 請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_creation_3.png)

1. 使用定義並個人化訊息內容、寄件者名稱和主旨 [電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md). 有關詳細資訊，請參閱 [關於電子郵件內容設計](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   您可以直接使用預先定義的內容範本，或使用Dreamweaver或Adobe Experience Manager來設計訊息。 如果您不像設計師，也可以上傳已為您準備的內容，或從URL匯入現有內容。 請參閱「[選擇現有內容](../../designing/using/using-existing-content.md)」。

1. 預覽訊息。 請參閱「[預覽訊息](../../sending/using/previewing-messages.md)」。
1. 確認建立電子郵件。

   >[!NOTE]
   >
   >若要儲存您的電子郵件，您必須先對內容進行一些編輯。 如果您按一下 **[!UICONTROL Cancel]** 此時，您將無法完成精靈，且將無法建立您的電子郵件。

   接著會顯示電子郵件控制面板。 它可讓您檢查訊息，並 [準備傳送](../../sending/using/preparing-the-send.md).

   此 **[!UICONTROL Edit properties]** 按鈕，即可編輯電子郵件的屬性。 例如，您可以設定電子郵件，以便在準備傳送時計算其標籤。  可用參數列於 [本節](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. 排程傳送。請參閱[排程訊息](../../sending/using/about-scheduling-messages.md)。

   ![](assets/delivery_planning.png)

1. 準備您的訊息以分析其目標。 請參閱 [準備傳送](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >您可以設定全域跨通道疲勞規則，這會從促銷活動自動排除過度請求的設定檔。有關詳細資訊，請參閱 [疲勞規則](../../sending/using/fatigue-rules.md).

1. 傳送校樣以檢查並驗證您的訊息，並監控其收件匣呈現。請參閱 [傳送校樣](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. 傳送訊息並透過訊息控制面板和記錄來檢查其傳送。 請參閱 [傳送訊息](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. 使用傳送報告測量訊息的影響。 如需報告的詳細資訊，請參閱 [本節](../../reporting/using/about-dynamic-reports.md).

**相關主題**：

* [建立個人化電子郵件](../../channels/using/key-steps-to-send-a-message.md) 逐步指南
* [Adobe Campaign和Dreamweaver整合](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [與Adobe Experience Manager整合](../../integrating/using/integrating-with-experience-manager.md)

## 教學課程影片 {#video}

此影片說明如何建立電子郵件。

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

提供其他Campaign Standard作法影片 [此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant).
