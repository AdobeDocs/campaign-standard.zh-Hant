---
title: 直接郵件傳送
description: 「直接郵件傳送」活動允許您配置在工作流程中發送單個發送直接郵件或循環發送直接郵件。
page-status-flag: never-activated
uuid: bfa7b176-a17c-4079-a073-64b8ce4788ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: b9ddb2a0-54ff-4ada-be6f-8109fa06d461
context-tags: directMail,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eac45f6e5491703a39c19a4787be6f285e841e14
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 99%

---


# 直接郵件傳送{#direct-mail-delivery}

## 說明 {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

**[!UICONTROL Direct mail delivery]** 活動可讓您設定並準備包含您要用於直接郵件促銷活動之設定檔資料的檔案。這可以是一次使用的直接郵件，也可以是循環性直接郵件。

* **標準的直接郵件只傳送一次。**
* **循環郵件可讓您在定義的時段內，多次傳送相同的直接郵件給不同的目標。**&#x200B;您可以彙總每個期間的傳送，以取得符合您需求的報表。

## 使用內容 {#context-of-use}

**[!UICONTROL Direct mail delivery]** 活動通常用於自動準備包含設定檔資料的檔案。然後，可將此檔案傳送給負責郵寄的合作夥伴/供應商。

當連結至排程器時，您可以定義循環的直接電子郵件。

直接郵件收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的活動。在準備直接郵件時，不會自動排除未指定郵寄地址的個人檔案。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選取是否要求傳送訊息的手動確認（預設為必要）。您可以手動啟動工作流程，或將排程器活動置於工作流程中以自動執行。

**相關主題：**

* [使用案例：將電子郵件與直效郵件傳送結合](../../automating/using/coupling-email-direct-mail.md)
* [關於直接郵件](../../channels/using/about-direct-mail.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Direct mail delivery]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的 ![](assets/dlv_activity_params-24px.png) 按鈕，存取活動（而非傳送本身）的一般屬性和進階選項。此按鈕是通道活動專屬的按鈕。您可以透過直接郵件控制面板中的動作列來存取直接郵件的屬性。

1. 選取直接郵件發送模式：

   * **[!UICONTROL Direct mail]**：直接郵件只發一次。您可以在此處指定是否要向活動新增出站轉變。在本過程的步驟 7 中詳細說明不同的轉變類型。
   * **[!UICONTROL Recurring direct mail]**：根據 **[!UICONTROL Scheduler]** 活動中定義的頻率，直接郵件會被發送多次。選取傳送的彙總期間。這可讓您將定義期間發生的所有傳送重新分組，並透過一封名為 **Recurring execution** 且可從應用程式的行銷活動清單存取的直接郵件。

      例如，對於每日處理的循環生日郵件，您可以選取彙總每月的傳送。這可讓您每月收到傳送的報表，不過每天都會處理郵件。

      >[!NOTE]
      >
      >對於循環的直接郵件，在工作流程的每次執行時都產生新檔案。選定的彙總期間對此行為沒有影響。

1. 選取直接郵件類型。直接郵件類型來自 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 功能表中定義的範本。
1. 輸入直接郵件的常規屬性。您也可以將它附加至現有的行銷活動。工作流程的傳送活動的標籤會以直接郵件標籤更新。
1. 定義直接郵件內容。請參閱關於[內容編輯](../../designing/using/personalization.md)的區段。
1. 依預設，**[!UICONTROL Direct mail delivery]** 活動不包含任何外站轉變。如果要將出站轉變新增到 **[!UICONTROL Direct mail delivery]** 活動中，請轉至高階活動選項的　**[!UICONTROL General]**　索引標籤（活動快速操作中的　![](assets/dlv_activity_params-24px.png)　按鈕），然後選中以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生一個外站轉變，其中包含與入站轉變完全相同的母體。此轉換包含直接郵件活動產生的檔案以及直接郵件活動收到的原始母體。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生一個外站轉變，其中包含將要向其發送直接郵件的母體。在直接郵件準備過程中排除的目標成員（隔離、無效地址等）會從此轉換中排除。轉換也包含直接郵件產生的檔案。

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會將您直接帶至直接郵件控制面板。只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。在工作流程啟動後，仍需要確認從工作流程建立的訊息的傳送。但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用 **[!UICONTROL Request confirmation before sending messages]** 選項。取消核取此選項後，訊息會在準備完成後不另行通知而傳送。

## 註釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。您可以使用控制面板來檢視工作流程的執行狀態。直接郵件摘要窗格中的連結可讓您直接存取連結的元素(工作流程、促銷活動、上層傳送若是重複寄送的直接郵件）。

![](assets/wkf_display_parent_elements_direct_mail.png)

循環傳送的執行預設為遮罩。若要檢視，請核取行銷活動搜尋面板中的 **[!UICONTROL Show recurring executions]** 選項。

![](assets/wkf_display_recurrent_executions_direct_mail.png)

在可從行銷活動清單存取或直接透過相關循環執行存取的父傳送中，您可以檢視已處理的郵件總數（根據設定 **[!UICONTROL Direct mail delivery]** 活動時指定的彙總期間）。若要這麼做，請選取 ![](assets/wkf_dlv_detail_button.png) 按鈕，以開啟上層傳送 **[!UICONTROL Deployment]** 區塊的詳細資訊檢視。

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)
