---
title: 應用程式內傳遞
description: 應用內傳遞活動允許您配置在工作流內發送應用內消息。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 43%

---

# 應用程式內傳遞{#in-app-delivery}

## 說明 {#description}

![](assets/wkf_in_app_1.png)

的 **應用內交付** 活動允許您配置在工作流中發送In-App消息。 In-App消息傳遞允許您在用戶在應用程式內處於活動狀態時顯示消息。 有關In-App交付的詳細資訊，請參閱 [節](../../channels/using/about-in-app-messaging.md)。

## 使用內容 {#context-of-use}

的 **[!UICONTROL In-App delivery]** 活動通常用於自動將In-App消息發送到同一工作流中計算的目標受眾。

收件人是通過目標活動（如查詢、交叉點等）在同一工作流中活動的上游定義的。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選取是否要求傳送訊息的手動確認（預設為必要）。您可以手動啟動工作流程，或將排程器活動置於工作流程中以自動執行。

## 設定 {#configuration}

1. 拖放 **[!UICONTROL Query]** 活動。 請注意 **[!UICONTROL Query]** 活動目標維 **[!UICONTROL Properties]** 頁籤需要根據步驟4中選擇的模板進行更新：

   * 目標維度應設定為 **[!UICONTROL mobileApp (mobileAppV5)]** 為 **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** 的下界。
   * 目標維度應設定為 **[!UICONTROL profile (profile)]** 為 **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** 的下界。
   * 目標維度應設定為 **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 為 **[!UICONTROL Target users based on their Mobile profile (inApp)]** 的下界。

1. 將 **[!UICONTROL In-App delivery]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的 ![](assets/dlv_activity_params-24px.png) 按鈕，存取活動（而非傳送本身）的一般屬性和進階選項。

   ![](assets/wkf_in_app_3.png)

1. 選擇In-App消息類型。 這取決於您的 **[!UICONTROL Query]** 的子菜單。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:此消息類型使您能夠將訂閱了您的移動應用程式的Adobe Campaign配置檔案作為目標，並使用市場活動中可用的配置檔案屬性個性化In-App消息。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:此消息類型允許您向移動應用程式的所有用戶發送消息，即使他們在市場活動中沒有現有配置檔案。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**:通過此消息類型，您可以將市場活動中具有移動配置檔案的移動應用的所有用戶作為目標，並使用從移動設備獲取的任何配置檔案屬性對In-App消息進行個性化。

   ![](assets/wkf_in_app_4.png)

1. 輸入您的In-App消息屬性，然後在 **[!UICONTROL Associate a Mobile App to a delivery]** 的子菜單。
1. 在 **[!UICONTROL Triggers]** 索引標籤中，拖放將觸發訊息的事件。有三類事件：
1. 定義您的In-App內容。 請參閱有關 [應用程式內自定義](../../channels/using/customizing-an-in-app-message.md)。
1. 依預設，**[!UICONTROL In-App delivery]** 活動不包含任何外站轉變。如果要將出站轉變新增到 **[!UICONTROL In-App delivery]** 活動中，請轉至高階活動選項的　**[!UICONTROL General]**　索引標籤（活動快速操作中的　![](assets/dlv_activity_params-24px.png)　按鈕），然後核取以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生一個外站轉變，其中包含與入站轉變完全相同的母體。
   * **[!UICONTROL Add outbound transition with the population]**:這允許您生成包含消息發送到的人口的出站轉移。 在交付準備期間排除的目標成員將排除在此過渡之外。

   ![](assets/wkf_in_app_5.png)

1. 確認活動的設定並儲存工作流程。

重新開啟活動時，您將直接轉到In-App儀表板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。在工作流程啟動後，仍需要確認從工作流程建立的訊息的傳送。但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用 **[!UICONTROL Request confirmation before sending messages]** 選項。取消核取此選項後，訊息會在準備完成後不另行通知而傳送。

## 註釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。您可以使用控制面板來檢視工作流程的執行狀態。推送通知摘要窗格中的連結允許您直接訪問連結的元素（工作流、市場活動等）。

在可從市場營銷活動清單訪問的父交貨中，您可以查看已處理的發送總數（根據在以下日期指定的匯總期間） **[!UICONTROL In-App delivery]** 活動已配置)。 若要這麼做，請選取 ![](assets/wkf_dlv_detail_button.png)，以開啟上層傳送 **[!UICONTROL Deployment]** 區塊的詳細資訊檢視。
