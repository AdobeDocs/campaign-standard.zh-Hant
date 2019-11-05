---
title: 建立電子郵件
description: 請依照下列步驟，在Adobe Campaign中建立單一傳送的電子郵件。
page-status-flag: 從未激活
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 頻道
content-type: 參考
topic-tags: 電子郵件訊息
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 建立電子郵件{#creating-an-email}

您可以從促銷活動、 [Adobe Campaign首頁或](../../start/using/marketing-activities.md#creating-a-marketing-activity)行銷活動清單 [中建立電子郵件](../../start/using/interface-description.md#home-page)[](../../start/using/marketing-activities.md#about-marketing-activities)。 您也可以從工作流程建立單一傳送和循環寄送的電子郵件。

1. 開始建立電子郵件行銷活動後，請選取您要使用的範本。

   依預設，您可以從多個範本中選擇每個行銷活動。 這可讓您根據您的需求預先設定某些參數，並指派品牌給您的傳送。 有關詳細資訊，請參閱管 [理模板](../../start/using/about-templates.md)。

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >預設會隱藏後續和A/B測試範本。 如果要顯示，請勾選左側 **[!UICONTROL Filter]** 的方塊（側面板）。

1. 輸入電子郵件的一般屬性。 您可以在「標籤」欄位中輸 **入名稱** ，並編輯ID。 活動名稱及其ID都會出現在介面中，但訊息收件者看不到。

   您可以新增使用者可在促銷活動內容中看到的說明。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >您可以從首頁或行銷活動清單中在父促銷活動中建立電子郵件。 從已建立的促銷活動中選取它。

1. 根據您的業務條件定義訊息的目標。 請參 [閱管理描述檔](../../audiences/using/about-profiles.md)。

   您也可以定義將驗證訊息的測試設定檔。 請參閱 [管理測試設定檔](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles)。

   ![](assets/email_creation_3.png)

1. 使用電子郵件設計工具定義並個人化訊息內容、傳送者名 [稱和主旨](../../designing/using/overview.md)。 如需詳細資訊，請參閱關於 [電子郵件內容設計](../../designing/using/overview.md)。

   ![](assets/email_creation_4.png)

   您可以直接使用預先定義的內容範本，或使用Dreamweaver或Adobe Experience Manager來設計訊息。 如果您不想當設計人員，也可以上傳已為您準備好的內容，或從URL匯入現有內容。 請參 [閱選擇現有內容](../../designing/using/using-existing-content.md)。

1. 預覽您的訊息。 請參閱 [預覽訊息](../../sending/using/previewing-messages.md)。
1. 確認建立電子郵件。

   >[!NOTE]
   >
   >若要儲存您的電子郵件，您必須先對內容進行一些編輯。 如果您按 **[!UICONTROL Cancel]** 一下此時，將無法完成精靈，而且您的電子郵件將無法建立。

   接著會顯示電子郵件控制面板。 它可讓您檢查訊息並準 [備傳送](../../sending/using/preparing-the-send.md)。

   右 **[!UICONTROL Edit properties]** 上角的按鈕可讓您編輯電子郵件的屬性。 例如，您可以設定電子郵件，以便在傳送準備時計算其標籤。  此部分列出了可用 [的參數](../../administration/using/configuring-email-channel.md#list-of-email-properties)。

   ![](assets/delivery_dashboard_2.png)

1. 排程傳送。 請參閱 [排程訊息](../../sending/using/about-scheduling-messages.md)。

   ![](assets/delivery_planning.png)

1. 準備訊息以分析其目標。 See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >您可以設定全域跨通道疲勞規則，自動從促銷活動中排除過度徵求的個人檔案。 如需詳細資訊，請參閱「疲 [乏規則」](../../administration/using/fatigue-rules.md)。

1. 傳送校樣以檢查並驗證您的訊息，並監控其收件匣轉譯。 請參 [閱傳送證明](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)。

   ![](assets/bat_select.png)

1. 傳送訊息並透過訊息儀表板和記錄來檢查其傳送。 請參閱 [傳送訊息](../../sending/using/confirming-the-send.md)。

   ![](assets/confirm_delivery.png)

1. 使用傳送報表評估訊息的影響。 如需有關報告的詳細資訊，請參 [閱本節](../../reporting/using/about-dynamic-reports.md)。

**相關主題**:

* [建立電子郵件](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) 視訊
* [建立個人化電子郵件](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GettingStartedEmail.html) ，逐步指南
* [Adobe Campaign與Dreamweaver整合視訊](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html)
* [與Adobe Experience Manager整合](../../integrating/using/integrating-with-experience-manager.md)

