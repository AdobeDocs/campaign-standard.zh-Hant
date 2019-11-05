---
title: 建立 SMS 訊息
description: 請依照下列步驟，在Adobe Campaign中建立單一傳送的SMS訊息。
page-status-flag: 從未激活
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 頻道
content-type: 參考
topic-tags: sms-messages
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: deliveryCreation，精靈
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 建立 SMS 訊息{#creating-an-sms-message}

建立簡訊傳送與建立一般電子郵件非常類似。 下列步驟將說明此渠道的特定配置。 如需其 [他選項的詳細資訊](../../channels/using/creating-an-email.md) ，請參閱建立電子郵件。

進階SMS參數在 [SMS設定一節中詳細說明](../../administration/using/configuring-sms-channel.md) 。

若要建立SMS訊息並傳送至行動電話，您需要：

* 在 **[!UICONTROL Routing]** 頻道上以模式 **[!UICONTROL Mobile (SMS)]** 設定的外部 **[!UICONTROL Bulk delivery]** 帳戶。 For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* 正確連結至此外部帳戶的傳送範本。

1. 建立簡訊傳送。 您可從Adobe Campaign首頁、促銷活 [動或行銷活動清單](../../start/using/interface-description.md#home-page)[中](../../start/using/marketing-activities.md#creating-a-marketing-activity) , [執行此動作](../../start/using/programs-and-campaigns.md#creating-a-campaign)。

   您也可以在工作流程中新增SMS活動。 如需詳細資訊，請參閱「工作 [流程](../../automating/using/sms-delivery.md) 」指南。

   建立消息時，將顯示嚮導，引導您完成最重要的步驟。 通過嚮導定義的內容仍然可以從消息儀表板進行編輯。

1. 選取您要使用的範本。 您可以選擇現成可用的SMS範本或您自己的範本。

   ![](assets/sms_creation_1.png)

   若要傳送至行動電話，傳送範本必須正確連結至傳送外部帳戶的SMS。

1. 輸入SMS的一般屬性。

   ![](assets/sms_creation_2.png)

   活動標籤及其ID都會出現在介面中，但訊息收件者看不到。

1. 指定您要定位的對象。 您可以定義並結合規則，以選取現有對象或直接定位人口。

   ![](assets/sms_creation_3.png)

1. 將內容新增至SMS 您也可以在SMS建立完成後，按一 **[!UICONTROL Content]** 下傳送控制面板的區段來定義內容。 請參閱 [關於SMS內容設計](../../channels/using/about-sms-and-push-content-design.md)。

   如果您已將個人化欄位或條件文字插入SMS訊息的內容，則訊息的長度可能會因收件者而異。 事實上，這些因素可能會引入GSM編碼未考慮的字元。 這就是為什麼在個人化實施後，必須評估訊息長度。 See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. 確認建立消息。 接著會顯示其控制面板。
1. 排程傳送。 SMS可在訊息準備後手動傳送，或在排程日期自動傳送。 請參閱 [排程訊息](../../sending/using/about-scheduling-messages.md)。
1. 準備訊息以分析其有效性、個人化和目標。

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >您可以設定全域跨通道疲勞規則，自動從促銷活動中排除過度徵求的個人檔案。 請參 [閱疲勞規則](../../administration/using/fatigue-rules.md)。

1. 傳送校樣以檢查並驗證您的訊息，並監控其收件匣轉譯。 請參閱「 [傳送校樣](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) 」一節。
1. 確認訊息的傳送。 發送將相應地啟動到您定義的調度。

   ![](assets/sms_creation_7.png)

訊息會傳送。 您可以透過訊息儀表板和記錄來檢查傳送。

傳送完成後，您就可以開始使用內建或自訂傳送報表來測量訊息的影響。

**相關主題：**

* [關於SMS和推播內容版](../../channels/using/about-sms-and-push-content-design.md)
* [管理範本](../../start/using/about-templates.md)
* [建立SMS傳送視訊](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-sms-delivery-feature-video-use.html) 。

