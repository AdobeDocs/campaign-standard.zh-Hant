---
solution: Campaign Standard
product: campaign
title: 電子郵件傳送
description: 「電子郵件傳送」活動可讓您設定在工作流程中傳送單一傳送電子郵件或循環電子郵件。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 94%

---


# 電子郵件傳送{#email-delivery}

## 說明 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

**[!UICONTROL Email delivery]** 活動可讓您設定在工作流程中傳送電子郵件。這可以是&#x200B;**單一傳送**&#x200B;電子郵件，只傳送一次，或是&#x200B;**重複傳送**&#x200B;電子郵件。

單一傳送電子郵件是標準電子郵件，只傳送一次。

循環電子郵件可讓您在定義的時段內，多次傳送相同的電子郵件給不同的目標。您可以彙總每個期間的傳送，以取得符合您需求的報表。

## 使用內容 {#context-of-use}

**[!UICONTROL Email delivery]** 活動通常用於自動傳送電子郵件至在相同工作流程中計算的目標。

當連結至排程器時，您可以定義循環的電子郵件。

電子郵件收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的活動。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選取是否要求傳送訊息的手動確認（預設為必要）。您可以手動啟動工作流程，或將排程器活動置於工作流程中以自動執行。

**相關主題：**

* [使用案例：建立每週一次的電子郵件傳送](../../automating/using/workflow-weekly-offer.md)
* [使用案例：建立依位置分段的傳送](../../automating/using/workflow-segmentation-location.md)
* [使用案例：建立具備輔助功能的傳送](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重新定位傳送新傳送給非開啟者的工作流程](../../automating/using/workflow-cross-channel-retargeting.md)
* [使用案例：生日遞送](../../automating/using/birthday-delivery.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Email delivery]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的 ![](assets/dlv_activity_params-24px.png) 按鈕，存取活動（而非傳送本身）的一般屬性和進階選項。此按鈕是 **[!UICONTROL Email delivery]** 活動的特定按鈕。您可以透過電子郵件控制面板中的動作列來存取電子郵件的屬性。

1. 選取電子郵件傳送模式：

   * **[!UICONTROL Email]**：電子郵件只會傳送一次。您可以在此處指定是否要向活動新增出站轉變。在本過程的步驟 7 中詳細說明不同的轉變類型。
   * **[!UICONTROL Recurring email]**：根據 **[!UICONTROL Scheduler]** 活動中定義的頻率，會多次傳送電子郵件。選取傳送的彙總期間。這可讓您將定義期間發生的所有傳送重新分組，並透過一封名為 **Recurring execution** 且可從應用程式的行銷活動清單存取的電子郵件。

      例如，對於每日傳送的循環生日電子郵件，您可以選取匯總每月傳送的傳送。這可讓您每月收到傳送的報告，不過電子郵件會每天傳送。
   >[!NOTE]
   >
   >循環傳送是根據匯總期間 **準備的**。 例如，如果匯總期間是「按天」，則每天只重新準備一次傳送。 如果您計畫每天呼叫此工作流程多次，請使用 [!UICONTROL No aggregation]。

1. 選取電子郵件類型。電子郵件類型來自 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 功能表中定義的電子郵件範本。
1. 輸入電子郵件的一般屬性。您也可以將它附加至現有的行銷活動。工作流程傳送活動的標籤會以電子郵件標籤更新。
1. 定義電子郵件內容。請參閱關於[內容編輯](../../designing/using/designing-content-in-adobe-campaign.md)的區段。
1. 依預設，**[!UICONTROL Email delivery]** 活動不包含任何外站轉變。如果要將出站轉變新增到 **[!UICONTROL Email delivery]** 活動中，請轉至高階活動選項的　**[!UICONTROL General]**　索引標籤（活動快速操作中的　![](assets/dlv_activity_params-24px.png)　按鈕），然後核取以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生一個外站轉變，其中包含與入站轉變完全相同的母體。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生出站轉變，其中包含傳送電子郵件的母體。在傳送準備期間排除的目標成員（隔離、無效電子郵件等）會從此轉換中排除。

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會直接帶您至電子郵件控制面板。只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。在工作流程啟動後，仍需要確認從工作流程建立的訊息的傳送。但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用 **[!UICONTROL Request confirmation before sending messages]** 選項。取消核取此選項後，訊息會在準備完成後不另行通知而傳送。

## 註釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。您可以使用控制面板來檢視工作流程的執行狀態。電子郵件摘要窗格中的連結可讓您直接存取連結的元素（工作流程、行銷活動、上層傳送，若是重複的 SMS）。

![](assets/wkf_display_recurrent_executions_2.png)

但是，循環傳送的執行預設為遮罩。若要檢視，請核取行銷活動搜尋面板中的 **[!UICONTROL Show recurring executions]** 選項。

![](assets/wkf_display_recurrent_executions.png)

在可從行銷活動清單存取或直接透過相關循環執行存取的父傳送中，您可以檢視已處理的傳送總數（根據設定 **[!UICONTROL Email delivery]** 活動時指定的彙總期間）。若要這麼做，請選取 ![](assets/wkf_dlv_detail_button.png)，以開啟上層傳送 **[!UICONTROL Deployment]** 區塊的詳細資訊檢視。

![](assets/wkf_display_recurrent_executions_3.png)
