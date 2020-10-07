---
title: 應用程式內傳送
description: 「應用程式內傳送」活動可讓您設定在工作流程中傳送「應用程式內」訊息。
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 應用程式內傳送{#in-app-delivery}

## 說明 {#description}

![](assets/wkf_in_app_1.png)

「應 **用程式內傳送** 」活動可讓您設定在工作流程中傳送應用程式內訊息。 應用程式內訊息可讓您在使用者在應用程式中處於作用中時顯示訊息。 如需應用程式內傳送的詳細資訊，請參閱本 [節](../../channels/using/about-in-app-messaging.md)。

## 使用內容 {#context-of-use}

The **[!UICONTROL In-App delivery]** activity is generally used to automate sending an In-App message to a target audience calculated in the same workflow.

收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的位置。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選取是否要求傳送訊息的手動確認（預設為必要）。您可以手動啟動工作流程，或將排程器活動置於工作流程中以自動執行。

## 設定 {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity to your workflow. 請注意，標籤中 **[!UICONTROL Query]** 的活動定位維 **[!UICONTROL Properties]** 度必鬚根據步驟4中選擇的範本進行更新：

   * 定位維度應設為范 **[!UICONTROL mobileApp (mobileAppV5)]** 本的目 **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** 標。
   * 定位維度應設為范 **[!UICONTROL profile (profile)]** 本的目 **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** 標。
   * 定位維度應設為范 **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 本的目 **[!UICONTROL Target users based on their Mobile profile (inApp)]** 標。

1. 將 **[!UICONTROL In-App delivery]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的 ![](assets/dlv_activity_params-24px.png) 按鈕，存取活動（而非傳送本身）的一般屬性和進階選項。

   ![](assets/wkf_in_app_3.png)

1. 選取「應用程式內」訊息類型。 這將視您活動中定位的資料而 **[!UICONTROL Query]** 定。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:此訊息類型可讓您鎖定已訂閱您行動應用程式的Adobe Campaign設定檔，並使用Campaign中的設定檔屬性個人化應用程式內訊息。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:此訊息類型可讓您傳送訊息給行動應用程式的所有使用者，即使他們在促銷活動中沒有現有的設定檔。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**:此訊息類型可讓您定位在Campaign中具有行動設定檔的行動應用程式的所有使用者（無論已知或未知），並使用從行動裝置取得的任何設定檔屬性個人化應用程式內訊息。

   ![](assets/wkf_in_app_4.png)

1. Enter your In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.
1. 在 **[!UICONTROL Triggers]** 索引標籤中，拖放將觸發訊息的事件。有三類事件可供使用：
1. 定義您的應用程式內容。 請參閱「應用程式內 [自訂」一節](../../channels/using/customizing-an-in-app-message.md)。
1. 依預設，**[!UICONTROL In-App delivery]** 活動不包含任何外站轉變。如果要將出站轉變新增到 **[!UICONTROL In-App delivery]** 活動中，請轉至高階活動選項的　**[!UICONTROL General]**　索引標籤（活動快速操作中的　![](assets/dlv_activity_params-24px.png)　按鈕），然後核取以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生一個外站轉變，其中包含與入站轉變完全相同的母體。
   * **[!UICONTROL Add outbound transition with the population]**:這可讓您產生對外轉場，其中包含傳送訊息給的人口。 傳送準備期間排除的目標成員會排除在此轉換之外。

   ![](assets/wkf_in_app_5.png)

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會直接帶您至「應用程式內」儀表板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。在工作流程啟動後，仍需要確認從工作流程建立的訊息的傳送。但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用 **[!UICONTROL Request confirmation before sending messages]** 選項。取消核取此選項後，訊息會在準備完成後不另行通知而傳送。

## 註釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。您可以使用控制面板來檢視工作流程的執行狀態。推播通知摘要窗格中的連結可讓您直接存取連結的元素（工作流程、促銷活動等）。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL In-App delivery]** activity was configured). 若要這麼做，請選取 ![](assets/wkf_dlv_detail_button.png)，以開啟上層傳送 **[!UICONTROL Deployment]** 區塊的詳細資訊檢視。
