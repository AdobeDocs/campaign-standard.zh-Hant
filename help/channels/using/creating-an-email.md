---
title: 建立電子郵件
description: 按照以下步驟在Adobe Campaign建立單發電子郵件。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 18%

---

# 建立電子郵件{#creating-an-email}

您可以通過 [活動](../../start/using/marketing-activities.md#creating-a-marketing-activity)，來自Adobe Campaign [首頁](../../start/using/interface-description.md#home-page)，或 [市場營銷活動清單](../../start/using/marketing-activities.md#about-marketing-activities)。 您也可以從工作流程建立單一傳送和循環寄送的電子郵件。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

1. 開始建立電子郵件市場營銷活動後，請選擇要使用的模板。

   預設情況下，您可以從多個模板中為每個市場營銷活動進行選擇。 這樣，您就可以根據您的需要預先配置某些參數，並為交付產品分配品牌。 有關此的詳細資訊，請參閱 [管理模板](../../start/using/marketing-activity-templates.md)。

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >預設會隱藏後續與 A/B 測試範本。選中左側的框( **[!UICONTROL Filter]** )。

1. 輸入電子郵件的常規屬性。 可在 **標籤** 編輯ID。

   >[!NOTE]
   >
   >活動名稱及其ID都顯示在介面中，但郵件收件人看不到它們。
   >
   >確保ID欄位不包含任何空格以避免任何差異，例如與Adobe Analytics整合時。

   您可以新增使用者可在行銷活動內容中看到的說明。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >您可以從首頁或市場營銷活動清單在父市場活動中建立電子郵件。 從已建立的市場活動中選擇它。

1. 根據業務標準定義郵件的目標。 請參閱 [關於配置檔案](../../audiences/using/about-profiles.md)。

   您還可以定義將驗證消息的test配置檔案。 請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_creation_3.png)

1. 使用 [電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md)。 有關此的詳細資訊，請參閱 [關於電子郵件內容設計](../../designing/using/designing-content-in-adobe-campaign.md)。

   ![](assets/email_creation_4.png)

   您可以直接使用預定義的內容模板或使用Dreamweaver或Adobe Experience Manager設計您的郵件。 如果您不覺得自己是設計師，您還可以上載為您準備的內容，或從URL導入現有內容。 請參閱「[選擇現有內容](../../designing/using/using-existing-content.md)」。

1. 預覽您的消息。 請參閱「[預覽訊息](../../sending/using/previewing-messages.md)」。
1. 確認建立電子郵件。

   >[!NOTE]
   >
   >要保存電子郵件，您首先需要對內容進行一些編輯。 如果按一下 **[!UICONTROL Cancel]** 此時，您將無法完成嚮導，並且不會建立您的電子郵件。

   然後顯示電子郵件儀表板。 它允許您檢查您的郵件 [準備發送](../../sending/using/preparing-the-send.md)。

   的 **[!UICONTROL Edit properties]** 按鈕，可編輯電子郵件的屬性。 例如，您可以配置電子郵件，以便在交付準備時間計算其標籤。  可用參數列於 [此部分](../../administration/using/configuring-email-channel.md#list-of-email-properties)。

   ![](assets/delivery_dashboard_2.png)

1. 排程傳送。請參閱[排程訊息](../../sending/using/about-scheduling-messages.md)。

   ![](assets/delivery_planning.png)

1. 準備郵件以分析其目標。 請參閱 [準備發送](../../sending/using/confirming-the-send.md)。

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >您可以設定全域跨通道疲勞規則，這會從促銷活動自動排除過度請求的設定檔。有關此的詳細資訊，請參閱 [疲勞規則](../../sending/using/fatigue-rules.md)。

1. 傳送校樣以檢查並驗證您的訊息，並監控其收件匣呈現。請參閱 [發送證明](../../sending/using/sending-proofs.md)。

   ![](assets/bat_select.png)

1. 通過消息儀表板和日誌發送並檢查其傳遞。 請參閱 [發送消息](../../sending/using/confirming-the-send.md)。

   ![](assets/confirm_delivery.png)

1. 使用傳遞報告衡量郵件的影響。 有關報告的詳細資訊，請參見 [此部分](../../reporting/using/about-dynamic-reports.md)。

**相關主題**：

* [建立個性化電子郵件](../../channels/using/key-steps-to-send-a-message.md) 逐步引導
* [Adobe Campaign和Dreamweaver一體化](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [與Adobe Experience Manager整合](../../integrating/using/integrating-with-experience-manager.md)

## 教程視頻 {#video}

此視頻顯示如何建立電子郵件。

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

可提供其他Campaign Standard操作視頻 [這裡](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)。
