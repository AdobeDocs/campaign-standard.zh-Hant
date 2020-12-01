---
solution: Campaign Standard
product: campaign
title: 傳送校樣
description: 瞭解如何傳送校樣。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
translation-type: tm+mt
source-git-commit: e20485978deba54f45010a41921b948f049222f2
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 100%

---


# 傳送校樣 {#sending-proofs}

## 關於校樣 {#about-proofs}

校樣是一種特定訊息，可讓您在將訊息傳送至主要目標之前先測試訊息。校樣的收件者負責核准訊息（其內容和表格）。

校樣收件者有兩種類型：

* **測試設定檔**&#x200B;可讓您鎖定不符合已定義定位準則的其他收件者。

   您可以將這些資料新增至訊息的對象，以偵測任何詐用收件者資料庫的行為，或確保電子郵件送達收件匣。如需詳細資訊，請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

   >[!NOTE]
   >
   >為了傳送校樣，必須將測試設定檔包含在訊息的對象中。

* **替代設定檔**&#x200B;可讓您將自己置於其中一個目標設定檔的位置，並取得設定檔將接收到之訊息的精確表示。如需詳細資訊，請參閱[使用目標設定檔測試電子郵件訊息](../../sending/using/testing-messages-using-target.md)。

   >[!NOTE]
   >
   >此功能僅適用於電子郵件通道。

## 傳送校樣 {#sending-a-proof}

若要傳送校樣，請依照下列步驟進行：

1. 請確定校樣收件者已設定：
   * **測試設定檔**&#x200B;必須包含在訊息的對象中。
   * 訊息準備成功之後，必須新增&#x200B;**替代設定檔**（請參閱[本區段](../../sending/using/testing-messages-using-target.md)）。

1. 按一下 **[!UICONTROL Send a test]** 按鈕。

   ![](assets/bat_select.png)

1. 選取要使用的校樣類型：

   * **[!UICONTROL Email rendering]**：選取此選項，依據設定為目標的收件匣，以測試接收訊息的方式。如需詳細資訊，請參閱[電子郵件呈現](../../sending/using/email-rendering.md)。
   * **[!UICONTROL Proof]**：選取此選項，在將訊息發送到主要目標之前測試該訊息。校樣收件者會負責藉由檢查傳送的內容及格式來核准傳送。
   * **[!UICONTROL Proof + Email rendering]**：此選項會結合前兩個選項。

   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >只有測試設定檔才提能供電子郵件呈現。如果未將測試設定檔新增至訊息，則只有　**[!UICONTROL Proof]**　選項可供選取。

1. 確認您的選取。

   會將校樣傳送至已設定的收件者。

   ![](assets/bat_select2.png)

1. 您可以使用下拉式清單 **[!UICONTROL Proofs]** 來檢視校樣。

   ![](assets/bat_view.png)

1. 選取校樣以存取其摘要。對於電子郵件，如果您已選取&#x200B;**電子郵件呈現**&#x200B;作為校樣類型，**[!UICONTROL Access email rendering]** 圖示就會顯示在校樣標籤的右側。請參閱[電子郵件呈現](../../sending/using/email-rendering.md)。

   ![](assets/bat_view2.png)

依據收到校樣之人員的意見，可能會要求您修改傳送的內容。執行修改之後，您必須重新開始電子郵件準備作業，然後重新傳送校樣。每個新校樣都可使用 **[!UICONTROL Show proofs]** 按鈕進行存取。

您必須視需要傳送多份校樣，直到完成傳送內容為止。完成此操作後，您可以將傳送內容傳送至主要目標並關閉核准週期。

## 設定校樣的主旨行 {#configuring-proofs-subject-line}

傳送校樣時，其主旨行預設會包含　**&quot;Proof&quot;**　字首，以及表示校樣號碼的計數器。

![](assets/proof-prefix.png)

若要變更要使用的預設主題行，請依照下列步驟執行：

1. 在訊息控制面板中，按一下 **[!UICONTROL Open properties]** 按鈕。
1. 在 **[!UICONTROL Advanced parameters]** 區段中，定義您預設要在主旨行中使用的字首。

若要隱藏主旨行中的校樣號碼，請啟動 **[!UICONTROL Hide proof prefix counter]** 選項。

>[!NOTE]
>
>如果要隱藏整個校樣字首，請將　**[!UICONTROL Subject line prefix]**　欄位留空。

![](assets/proof-prefix-configuration.png)

1. 按一下 **[!UICONTROL Confirm]**。預設會將設定套用至針對所選訊息傳送的所有校樣。

**相關主題：**

* [傳送測試、準備和傳送電子郵件](../../sending/using/get-started-sending-messages.md#video)視訊
* [使用目標設定檔測試電子郵件訊息](../../sending/using/testing-messages-using-target.md)
* [管理測試設定檔](../../audiences/using/managing-test-profiles.md)
* [預覽訊息](../../sending/using/previewing-messages.md)
* [設定電子郵件通道](../../administration/using/configuring-email-channel.md)
