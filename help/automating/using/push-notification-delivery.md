---
title: 推播通知傳遞
description: 「推送通知傳遞」活動允許您配置在工作流中發送單個發送推送通知或定期推送通知。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b6a43d51-32d4-4806-b4e4-33236f1e27f5
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---

# 推播通知傳遞{#push-notification-delivery}

## 說明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

的 **[!UICONTROL Push notification]** 活動允許您配置在工作流中發送推送通知。 這可以是單個發送通知，並且只發送一次，也可以是循環通知。

* **單** 發送通知是標準移動應用推送通知遞送，發送一次。
* **循環** 通知允許您在定義的期間內多次向不同目標發送相同的移動應用推送通知傳遞。 您可以彙總每個期間的傳送，以取得符合您需求的報表。

## 使用內容 {#context-of-use}

的 **[!UICONTROL Push notification]** 活動通常用於自動將通知發送到在同一工作流中計算的目標。

連結到調度程式時，可以定義定期推送通知。

收件人是通過目標活動（如查詢、交叉點等）在同一工作流中活動的上游定義的。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選取是否要求傳送訊息的手動確認（預設為必要）。您可以手動啟動工作流程，或將排程器活動置於工作流程中以自動執行。

**相關主題**

* [使用工作流發送循環推送通知](../../automating/using/recurring-push-notifications.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Push notification]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的 ![](assets/dlv_activity_params-24px.png) 按鈕，存取活動（而非傳送本身）的一般屬性和進階選項。此按鈕是 **[!UICONTROL Push notification]** 活動的特定按鈕。可通過推式操控板中的操作欄訪問推式通知的屬性。

1. 選擇推送通知發送模式：

   * **[!UICONTROL Single notification]**:推送通知一次發送。 您可以在此處指定是否要向活動新增出站轉變。在本過程的步驟 7 中詳細說明不同的轉變類型。
   * **[!UICONTROL Recurring notification]**:按照在 **[!UICONTROL Scheduler]** 的子菜單。 選取傳送的彙總期間。這樣，您就可以重新分組在定義期間內發生的所有發送，同時也調用了一個推送通知 **循環執行** 並可以從應用程式的市場營銷活動清單訪問。

      例如，對於每天發送的定期生日通知，您可以選擇每月匯總發送。 這樣，您就可以每月接收有關您的交貨的報告，儘管通知每天都會發送。

1. 選擇通知類型。 這些類型來自在 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 的子菜單。
1. 輸入推送通知的常規屬性。 您也可以將它附加至現有的行銷活動。工作流的傳遞活動的標籤將用推送通知標籤更新。
1. 定義推送通知內容。 請參閱 [建立推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
1. 依預設，**[!UICONTROL Push notification]** 活動不包含任何外站轉變。如果要將出站轉變新增到 **[!UICONTROL Push Notification]** 活動中，請轉至高階活動選項的　**[!UICONTROL General]**　索引標籤（活動快速操作中的　![](assets/dlv_activity_params-24px.png)　按鈕），然後核取以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生一個外站轉變，其中包含與入站轉變完全相同的母體。
   * **[!UICONTROL Add outbound transition with the population]**:這允許您生成包含通知發送到的人口的出站轉移。 在交付準備期間排除的目標成員將排除在此過渡之外。

1. 確認活動的設定並儲存工作流程。

重新開啟活動時，將直接帶到推式通知儀表板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。在工作流程啟動後，仍需要確認從工作流程建立的訊息的傳送。但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用 **[!UICONTROL Request confirmation before sending messages]** 選項。取消核取此選項後，訊息會在準備完成後不另行通知而傳送。

## 註釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。您可以使用控制面板來檢視工作流程的執行狀態。推送通知摘要窗格中的連結允許您直接訪問連結的元素（工作流、市場活動等）。

在可從市場營銷活動清單訪問的父交貨中，您可以查看已處理的發送總數（根據在以下日期指定的匯總期間） **[!UICONTROL Push notification]** 活動已配置)。 若要這麼做，請選取 ![](assets/wkf_dlv_detail_button.png)，以開啟上層傳送 **[!UICONTROL Deployment]** 區塊的詳細資訊檢視。
