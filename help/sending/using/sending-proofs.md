---
title: 傳送校樣
description: 瞭解如何傳送校樣。
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff9d0c3ca42606f097a34b1835d285541061e57b

---


# 傳送校樣 {#sending-proofs}

證明是一種特定訊息，可讓您在將訊息傳送至主要目標之前先測試訊息。

證明的收件者負責核准訊息（其內容和表格）。 它們在測試配置檔案 **中定義**。 如需詳細資訊，請參閱「管 [理測試設定檔](../../audiences/using/managing-test-profiles.md)」。

為了傳送證明，測試設定檔必須包含在訊息的觀眾中。

在訊息中：

1. Click the **[!UICONTROL Send a test]** button.

   ![](assets/bat_select.png)

1. 選擇您要使用的校樣類型：

   * **[!UICONTROL Email rendering]**:選取此選項，以測試根據收件匣定位的訊息接收方式。 如需詳細資訊，請參閱「電子郵 [件轉換」](../../sending/using/email-rendering.md)。
   * **[!UICONTROL Proof]**:選擇此選項，在將消息發送到主目標之前測試該消息。 證明收件者負責核准傳送內容及格式，
   * **[!UICONTROL Proof + Email rendering]**:此選項會結合前兩個選項。
   ![](assets/bat_select1.png)

1. 確認您的選擇。

   校樣會傳送至測試描述檔。

   ![](assets/bat_select2.png)

1. 您可以使用下拉式清單 **[!UICONTROL Proofs]** 來檢視校樣。

   ![](assets/bat_view.png)

1. 選取要存取其摘要的證明。 對於電子郵件，如果您已選取「 **Email rendering** 」(電子郵件轉換 **[!UICONTROL Access email rendering]** )選項作為校對類型，則校對標籤右側會顯示圖示。 請參閱 [電子郵件轉譯](../../sending/using/email-rendering.md)。

   ![](assets/bat_view2.png)

根據收到證明之人員的意見，您可能會被要求修改傳送的內容。 修改完成後，您必須重新開始準備電子郵件，然後重新傳送證明。 每個新校樣都可使用按鈕 **[!UICONTROL Show proofs]** 存取。

您必須視需要傳送多份校樣，直到完成傳送內容為止。 完成此作業後，您可以將傳送內容傳送至主要目標並關閉核准週期。

**相關主題：**

[傳送測試、準備和傳送電子郵件視訊](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html) 。
