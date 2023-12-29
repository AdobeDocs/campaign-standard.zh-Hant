---
title: 推播通知傳遞
description: 推播通知傳送活動可讓您設定在工作流程中傳送單一傳送推播通知或循環推播通知。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b6a43d51-32d4-4806-b4e4-33236f1e27f5
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 46%

---

# 推播通知傳遞{#push-notification-delivery}

## 說明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

此 **[!UICONTROL Push notification]** 活動可讓您設定在工作流程中傳送推播通知。 這可以是單一傳送通知，只傳送一次，或是重複通知。

* **單一** 傳送通知是標準的行動應用程式推播通知傳送，只傳送一次。
* **週期性** 通知可讓您在定義的時段內，多次傳送相同的行動應用程式推播通知傳送至不同的目標。 您可以彙總每個期間的傳送，以取得符合您需求的報表。

## 使用內容 {#context-of-use}

此 **[!UICONTROL Push notification]** 活動通常用於自動傳送通知至在相同工作流程中計算的目標。

當連結至排程器時，您可以定義循環推播通知。

收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的活動。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選取是否要求傳送訊息的手動確認（預設為必要）。您可以手動啟動工作流程，或將排程器活動置於工作流程中以自動執行。

**相關主題**

* [使用工作流程傳送循環推播通知](../../automating/using/recurring-push-notifications.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Push notification]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速動作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的 ![](assets/dlv_activity_params-24px.png) 按鈕，存取活動（而非傳送本身）的一般屬性和進階選項。此按鈕是 **[!UICONTROL Push notification]** 活動的特定按鈕。您可以透過推播控制面板中的動作列存取推播通知的屬性。

1. 選取推播通知傳送模式：

   * **[!UICONTROL Single notification]**：推播通知只會傳送一次。 您可以在此處指定是否要向活動新增出站轉變。在本過程的步驟 7 中詳細說明不同的轉變類型。
   * **[!UICONTROL Recurring notification]**：根據 **[!UICONTROL Scheduler]** 活動。 選取傳送的彙總期間。這可讓您將定義期間發生的所有傳送重新分組，並透過也稱為的單一推播通知執行 **循環執行** 並可從應用程式的行銷活動清單存取和。

     例如，對於每日傳送的循環生日通知，您可以選取彙總每月傳送的傳送。 這可讓您每月收到傳送的報告，不過通知會每天傳送。

1. 選取通知型別。 這些型別來自中定義的推播通知範本 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 功能表。
1. 輸入推播通知的一般屬性。 您也可以將它附加至現有的行銷活動。工作流程傳送活動的標籤會以推播通知標籤更新。
1. 定義推播通知內容。 另請參閱 [建立推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)
1. 依預設，**[!UICONTROL Push notification]** 活動不包含任何外站轉變。如果要將出站轉變新增到 **[!UICONTROL Push Notification]** 活動中，請轉至高階活動選項的　**[!UICONTROL General]**　索引標籤（活動快速動作中的　![](assets/dlv_activity_params-24px.png)　按鈕），然後核取以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生一個外站轉變，其中包含與入站轉變完全相同的母體。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生出站轉變，其中包含接收通知的母體。 在傳遞準備期間排除的目標成員會從此轉變中排除。

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會直接帶您至推播通知控制面板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。在工作流程啟動後，仍需要確認從工作流程建立的訊息的傳送。但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用 **[!UICONTROL Request confirmation before sending messages]** 選項。取消核取此選項後，訊息會在準備完成後不另行通知而傳送。

## 備註 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。您可以使用控制面板來檢視工作流程的執行狀態。推播通知摘要窗格中的連結可讓您直接存取連結的元素（工作流程、行銷活動等）。

在可從行銷活動清單存取的父傳送中，您可以檢視已處理的傳送總數(根據在 **[!UICONTROL Push notification]** 活動已設定)。 若要這麼做，請選取 ![](assets/wkf_dlv_detail_button.png)，以開啟上層傳送 **[!UICONTROL Deployment]** 區塊的詳細資訊檢視。
