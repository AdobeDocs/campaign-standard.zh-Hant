---
solution: Campaign Standard
product: campaign
title: 簡訊傳送
description: SMS 傳送活動可讓您在工作流程中設定傳送單一傳送 SMS 或循環 SMS。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: sms,main;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 100%

---


# 簡訊傳送{#sms-delivery}

## 說明 {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

**[!UICONTROL SMS delivery]** 活動可讓您在工作流程中設定傳送 SMS。這可以是單一傳送 SMS，只傳送一次，或是重複傳送 SMS。

* **單一傳送的簡訊是標準的簡訊，只傳送一次。**
* **循環 SMS 訊息可讓您在定義的時段內，多次傳送相同的 SMS 至不同的目標。**&#x200B;您可以彙總每個期間的傳送，以取得符合您需求的報表。

## 使用內容 {#context-of-use}

**[!UICONTROL SMS delivery]** 活動通常用於自動傳送 SMS 至在相同工作流程中計算的目標。

當連結至排程器時，您可以定義循環的 SMS 訊息。

SMS 收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的活動。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選取是否要求傳送訊息的手動確認（預設為必要）。您可以手動啟動工作流程，或將排程器活動置於工作流程中以自動執行。

## 設定 {#configuration}

1. 將 **[!UICONTROL SMS delivery]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過工作流程動作列中的 ![](assets/dlv_activity_params-24px.png) 按鈕，存取活動（而非傳送本身）的一般屬性和進階選項。此按鈕是 **[!UICONTROL SMS delivery]** 活動的特定按鈕。SMS 屬性可透過 SMS 儀表板中的動作列存取。

1. 選取 SMS 傳送模式：

   * **[!UICONTROL SMS]**：簡訊只會傳送一次。您可以在此處指定是否要向活動新增出站轉變。在本過程的步驟 7 中詳細說明不同的轉變類型。
   * **[!UICONTROL Recurring SMS]**：根據 **[!UICONTROL Scheduler]** 活動中定義的頻率，會多次傳送簡訊。選取傳送的彙總期間。這可讓您將定義期間發生的所有傳送重新分組為一個稱為 **Recurring execution** 的單一檢視，並可從應用程式的行銷活動清單存取。

      例如，對於每日傳送的循環生日 SMS，您可以選取匯總每月傳送的傳送。這可讓您每月收到傳送的報告，不過 SMS 會每天傳送。

1. 選取 SMS 類型。SMS 類型來自 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 功能表中定義的 SMS 範本\。
1. 輸入 SMS 的一般屬性。您也可以將它附加至現有的行銷活動。工作流程傳送活動的標籤會以 SMS 標籤更新。
1. 定義 SMS 內容。請參閱[建立 SMS 訊息](../../channels/using/creating-an-sms-message.md)區段
1. 依預設，**[!UICONTROL SMS delivery]** 活動不包含任何外站轉變。如果要將出站轉變新增到 **[!UICONTROL SMS delivery]** 活動中，請轉至高階活動選項的　**[!UICONTROL General]**　索引標籤（活動快速操作中的　![](assets/dlv_activity_params-24px.png)　按鈕），然後核取以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生一個外站轉變，其中包含與入站轉變完全相同的母體。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生出站轉變，其中包含傳送 SMS 的母體。在傳送準備期間排除的目標成員（隔離、無效編號等）會從此轉換中排除。

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會直接帶您至 SMS 控制面板。只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。在工作流程啟動後，仍需要確認從工作流程建立的訊息的傳送。但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用 **[!UICONTROL Request confirmation before sending messages]** 選項。取消核取此選項後，訊息會在準備完成後不另行通知而傳送。

## 註釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。您可以使用控制面板來檢視工作流程的執行狀態。SMS 摘要窗格中的連結可讓您直接存取連結的元素（工作流程、行銷活動、上層傳送，若是重複的 SMS）。

但是，循環傳送的執行預設為遮罩。若要檢視，請核取行銷活動搜尋面板中的 **[!UICONTROL Show recurring executions]** 選項。

在可從行銷活動清單存取或直接透過相關循環執行存取的父傳送中，您可以檢視已處理的傳送總數（根據設定 **[!UICONTROL SMS delivery]** 活動時指定的彙總期間）。若要這麼做，請選取 ![](assets/wkf_dlv_detail_button.png)，以開啟上層傳送 **[!UICONTROL Deployment]** 區塊的詳細資訊檢視。
