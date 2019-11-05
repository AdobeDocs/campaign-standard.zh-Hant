---
title: 應用程式內傳送
description: 「應用程式內傳送」活動可讓您設定在工作流程中傳送「應用程式內」訊息。
page-status-flag: 從未激活
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 頻道活動
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 應用程式內傳送{#in-app-delivery}

## 說明 {#description}

![](assets/wkf_in_app_1.png)

「應 **用程式內傳送** 」活動可讓您設定在工作流程中傳送應用程式內訊息。 應用程式內訊息可讓您在使用者在應用程式中處於作用中時顯示訊息。 如需應用程式內傳送的詳細資訊，請參閱本 [節](../../channels/using/about-in-app-messaging.md)。

## 使用內容 {#context-of-use}

此活 **[!UICONTROL In-App delivery]** 動通常用於自動傳送應用程式內訊息給在相同工作流程中計算的目標對象。

收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的位置。

根據工作流執行參數觸發消息準備。 在訊息控制面板中，您可以選擇是否要求傳送訊息的手動確認（預設為必要）。 您可以手動啟動工作流，或將排程器活動置於工作流中以自動執行。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Query]** 至工作流程。 請注意，標籤中 **[!UICONTROL Query]** 的活動定位維 **[!UICONTROL Properties]** 度必鬚根據步驟4中選擇的範本進行更新：

   * 定位維度應設為范 **[!UICONTROL mobileApp (mobileAppV5)]** 本的目 **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** 標。
   * 定位維度應設為范 **[!UICONTROL profile (profile)]** 本的目 **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** 標。
   * 定位維度應設為范 **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 本的目 **[!UICONTROL Target users based on their Mobile profile (inApp)]** 標。

1. 將活動拖放 **[!UICONTROL In-App delivery]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的按鈕，存取活動（而非傳送本身）的一 ![](assets/dlv_activity_params-24px.png) 般屬性和進階選項。

   ![](assets/wkf_in_app_3.png)

1. 選取「應用程式內」訊息類型。 這將視您活動中定位的資料而 **[!UICONTROL Query]** 定。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:此訊息類型可讓您鎖定已訂閱您行動應用程式的Adobe Campaign設定檔，並使用Campaign中的設定檔屬性個人化應用程式內訊息。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:此訊息類型可讓您傳送訊息給行動應用程式的所有使用者，即使他們在促銷活動中沒有現有的設定檔。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**:此訊息類型可讓您定位在Campaign中具有行動設定檔的行動應用程式的所有使用者（無論已知或未知），並使用從行動裝置取得的任何設定檔屬性個人化應用程式內訊息。
   ![](assets/wkf_in_app_4.png)

1. 輸入您的應用程式內訊息屬性，然後在欄位中選取您的行動應用 **[!UICONTROL Associate a Mobile App to a delivery]** 程式。
1. 在標籤 **[!UICONTROL Triggers]** 中，拖放將觸發訊息的事件。 有三類事件可供使用：
1. 定義您的應用程式內容。 請參閱「應用程式內 [自訂」一節](../../channels/using/customizing-an-in-app-message.md)。
1. 依預設，活動 **[!UICONTROL In-App delivery]** 不包含任何對外轉場。 如果要將出站轉移添加到活動 **[!UICONTROL In-App delivery]** 中，請轉至高級活動選項的頁籤( **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) 活動快速操作中的按鈕)，然後選中以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**:這可讓您產生一個對外轉移，其中包含與傳入轉移完全相同的人口。
   * **[!UICONTROL Add outbound transition with the population]**:這可讓您產生對外轉場，其中包含傳送訊息給的人口。 傳送準備期間排除的目標成員會排除在此轉換之外。
   ![](assets/wkf_in_app_5.png)

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會直接帶您至「應用程式內」儀表板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。 在工作流啟動後，仍需要確認從工作流建立的消息的發送。 但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用選 **[!UICONTROL Request confirmation before sending messages]** 項。 取消勾選此選項後，訊息會在準備完成後不另行通知而傳送。

## 注釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。 您可以使用控制面板來檢視工作流程的執行狀態。 推播通知摘要窗格中的連結可讓您直接存取連結的元素（工作流程、促銷活動等）。

在可從行銷活動清單存取的父傳送中，您可以檢視已處理的傳送總數（根據設定活動時指定的匯總期間）。 **[!UICONTROL In-App delivery]** 若要這麼做，請選取以開啟父傳送區塊的詳 **[!UICONTROL Deployment]** 細資料檢視 ![](assets/wkf_dlv_detail_button.png)。
