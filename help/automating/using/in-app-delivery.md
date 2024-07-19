---
title: 應用程式內傳遞
description: 應用程式內傳送活動可讓您設定在工作流程中傳送應用程式內訊息。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 39%

---

# 應用程式內傳遞{#in-app-delivery}

## 說明 {#description}

![](assets/wkf_in_app_1.png)

**應用程式內傳遞**&#x200B;活動可讓您設定在工作流程中傳送應用程式內訊息。 應用程式內傳訊功能可讓您在使用者於應用程式內活動時顯示訊息。 如需應用程式內傳遞的詳細資訊，請參閱本[區段](../../channels/using/about-in-app-messaging.md)。

## 使用內容 {#context-of-use}

**[!UICONTROL In-App delivery]**&#x200B;活動通常用於自動傳送應用程式內訊息給在相同工作流程中計算的目標對象。

收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的活動。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選取是否要求傳送訊息的手動確認（預設為必要）。您可以手動啟動工作流程，或將排程器活動置於工作流程中以自動執行。

## 設定 {#configuration}

1. 將&#x200B;**[!UICONTROL Query]**&#x200B;活動拖放至您的工作流程。 請注意，**[!UICONTROL Properties]**&#x200B;索引標籤中的&#x200B;**[!UICONTROL Query]**&#x200B;活動目標維度需要根據步驟4中選擇的範本進行更新：

   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**&#x200B;範本的目標維度應設為&#x200B;**[!UICONTROL mobileApp (mobileAppV5)]**。
   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**&#x200B;範本的目標維度應設為&#x200B;**[!UICONTROL profile (profile)]**。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**&#x200B;範本的目標維度應設為&#x200B;**[!UICONTROL subscriptions to an application (`nms:appSubscriptionRcp:appSubscriptionRcpDetail`)]**。

1. 將 **[!UICONTROL In-App delivery]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速動作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的![](assets/dlv_activity_params-24px.png)按鈕，存取活動（而非傳送本身）的一般屬性和進階選項。

   ![](assets/wkf_in_app_3.png)

1. 選取應用程式內訊息型別。 這將取決於您的&#x200B;**[!UICONTROL Query]**&#x200B;活動中鎖定的資料。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**：此訊息型別可讓您定位已訂閱您行動應用程式的Adobe Campaign設定檔，並以Campaign提供的設定檔屬性個人化應用程式內訊息。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**：此訊息型別可讓您傳送訊息給行動應用程式的所有使用者，即使他們在Campaign中沒有現有的設定檔亦然。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**：此訊息型別可讓您鎖定在Campaign中具有行動設定檔的行動應用程式的所有使用者（無論已知或未知），並使用從行動裝置取得的任何設定檔屬性來個人化應用程式內訊息。

   ![](assets/wkf_in_app_4.png)

1. 輸入您的應用程式內訊息屬性，並在&#x200B;**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;欄位中選取您的行動應用程式。
1. 在 **[!UICONTROL Triggers]** 索引標籤中，拖放將觸發訊息的事件。提供三種事件類別：
1. 定義您的應用程式內內容。 請參閱關於[應用程式內自訂](../../channels/using/customizing-an-in-app-message.md)的區段。
1. 依預設，**[!UICONTROL In-App delivery]** 活動不包含任何外站轉變。如果要將出站轉變新增到 **[!UICONTROL In-App delivery]** 活動中，請轉至高階活動選項的　**[!UICONTROL General]**　索引標籤（活動快速動作中的　![](assets/dlv_activity_params-24px.png)　按鈕），然後核取以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生一個外站轉變，其中包含與入站轉變完全相同的母體。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生出站轉變，其中包含傳送訊息的母體。 在傳遞準備期間排除的目標成員會從此轉變中排除。

   ![](assets/wkf_in_app_5.png)

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會直接帶您至應用程式內控制面板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。在工作流程啟動後，仍需要確認從工作流程建立的訊息的傳送。但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用 **[!UICONTROL Request confirmation before sending messages]** 選項。取消核取此選項後，訊息會在準備完成後不另行通知而傳送。

## 備註 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。您可以使用控制面板來檢視工作流程的執行狀態。推播通知摘要窗格中的連結可讓您直接存取連結的元素（工作流程、行銷活動等）。

在可從行銷活動清單存取的父傳送中，您可以檢視已處理的傳送總數（根據設定&#x200B;**[!UICONTROL In-App delivery]**&#x200B;活動時指定的彙總期間）。 若要這麼做，請選取 ![](assets/wkf_dlv_detail_button.png)，以開啟上層傳送 **[!UICONTROL Deployment]** 區塊的詳細資訊檢視。
