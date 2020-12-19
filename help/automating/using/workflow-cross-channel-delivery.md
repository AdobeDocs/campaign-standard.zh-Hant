---
solution: Campaign Standard
product: campaign
title: 跨通道傳送
description: 此使用案例說明如何建立跨通道傳送
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 86%

---


# 建立跨通道傳送{#cross-channel-delivery}

該文件允許您透過標準使用案例來探索以下 Adobe Campaign 功能：建立跨通道傳送工作流程。

該目標是從資料庫的收件者中選取一位對象，並將其細分成兩個不同的群組，以便向第一群組發送電子郵件並向第二群組發送簡訊。

![](assets/wkf_segment_overview.png)

如需 Adobe Campaign 工作流程與不同通道的詳細資訊，請查閱以下文件：

* [探索工作流程](../../automating/using/get-started-workflows.md)
* [探索通訊通道](../../channels/using/get-started-communication-channels.md)

## 建立工作流程 {#creating-workflow}

若要傳送兩個不同傳送至指定群組，您必須先定義目標。

若要這麼做，您將需要建立查詢來識別收件者，因此您必須建立工作流程。

在方案或您選取的行銷活動中建立新的工作流程：

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

[建立工作流](../../automating/using/building-a-workflow.md)區段中會列出建立工作流程的詳細步驟。

## 建立「查詢」活動 {#creating-query-activity}

建立工作流程後，您就可以存取其介面。

將「查詢」活動插入您的工作流程，以目標定位將接收您傳送的設定檔。

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查詢](../../automating/using/query.md)活動。
1. 連按兩下此活動。
1. 在 **[!UICONTROL Target]** 標籤中，瀏覽捷徑並選取其中一個 [對象](../../audiences/using/about-audiences.md)。
1. 將捷徑拖放至編輯區域。根據所選的捷徑類型，將會出現一個視窗。
1. 設定目標定位元素，然後確認查詢。

![](assets/wkf_segment_query.png)

您可以對一或多個元素建立查詢。

使用 **[!UICONTROL Count]** 按鈕可查看查詢所目標定位的設定檔估算數量。

## 建立細分活動 {#creating-segmentation-activity}

由「查詢」活動識別目標後，您必須選取一個準則，將目標細分成兩個不同的母體：一個會收到電子郵件，另一個則會收到簡訊。

您必須使用[Segmentation](../../automating/using/segmentation.md)活動，才能從查詢上游計算的人口中建立一或多個區段。

![](assets/wkf_segment_activity.png)

**電子郵件** 群組將目標設定為已定義電子郵件地址但沒有行動電話號碼的收件者。**簡訊**&#x200B;群組將包含其行動電話號碼已儲存在設定檔中的收件者。

若要設定第一個轉變（電子郵件）:

1. 在 **[!UICONTROL Segments]** 標籤中，依照預設會顯示第一個區段。編輯其屬性以設定該區段。

   ![](assets/wkf_segment_properties.png)

1. 選取設定檔 **[!UICONTROL Email]** 作為篩選準則。

   ![](assets/wkf_segment_email.png)

1. 在螢幕上顯示的新視窗中，選取 **[!UICONTROL Is not empty]** 運算子。

   ![](assets/wkf_segment_email_not_empty.png)

1. 新增第二個篩選準則 **[!UICONTROL Mobile]**，並選取運算子 **[!UICONTROL Is empty]**。

   ![](assets/wkf_segment_mobile_empty.png)

   來自査詢的所有設定檔都會有一個電子郵件，但未定義行動電話號碼，都將處於此轉變中。

1. 若要讓工作流程更加清楚，您可以編輯轉變標籤。確認您的變更。

   ![](assets/wkf_segment_transition_label.png)

已設定您的第一個轉變。若要設定第二個轉變（簡訊）：

1. 按一下 **[!UICONTROL Add an element]** 按鈕以新增轉變。
1. 定義條件，可讓您擷取已提供行動電話號碼的所有設定檔。若要這麼做，請使用 **[!UICONTROL Mobile]** 邏輯運算子，在欄位上 **[!UICONTROL Is not empty]** 建立規則。

   ![](assets/wkf_segment_mobile_not_empty.png)

   來自定義行動電話號碼之查詢的所有設定檔都將在此轉變中。

1. 您可以編輯轉變的標籤。確認您的變更。

您的第二個轉變現在也已設定。

![](assets/wkf_segment_transitions.png)

## 建立傳送 {#creating-deliveries}

由於已建立兩個轉場，您現在必須將兩種類型的傳送新增至「區段」活動的對外轉場：[電子郵件傳送](../../automating/using/email-delivery.md)活動和[SMS傳送](../../automating/using/sms-delivery.md)活動。

Adobe Campaign 可讓您將傳送新增至工作流程。若要這麼做，請從工作流程的活動色盤 **[!UICONTROL Channels]** 類別中選取傳送。

![](assets/wkf_segment_deliveries1.png)

若要建立電子郵件傳送：

1. 將[電子郵件傳送](../../automating/using/email-delivery.md)活動拖放至第一個區段之後。
1. 連按兩下活動以進行編輯。
1. 選取 **[!UICONTROL Simple email]**。
1. 選取 **[!UICONTROL Add an outbound transition with the population]** 並按一下 **[!UICONTROL Next]**。

   ![](assets/wkf_segment_deliveries2.png)

   出站轉變可讓您復原母體及追蹤記錄。例如，您可以使用此功能，傳送第二封郵件給未點按第一封郵件的使用者。

1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請選取 **[!UICONTROL Use the Email Designer]**。
1. 編輯並儲存您的內容。
1. 在消息儀表板的&#x200B;**[!UICONTROL Schedule]**&#x200B;部分中，取消選擇&#x200B;**[!UICONTROL Request confirmation before sending messages]**&#x200B;選項。

若要建立簡訊傳送：

1. 將[SMS delivery](../../automating/using/sms-delivery.md)活動拖放到另一個區段後面。
1. 連按兩下活動以進行編輯。
1. 選取 **[!UICONTROL SMS]** 並按一下 **[!UICONTROL Next]**。
1. 選取簡訊範本，並按一下 **[!UICONTROL Next]**。
1. 輸入簡訊屬性，並按一下 **[!UICONTROL Next]**。
1. 編輯並儲存您的內容。

在建立與編輯您的傳送後，您的工作流程已準備就緒即可開始。

![](assets/wkf_segment_deliveries.png)

## 執行工作流程 {#running-the-workflow}

工作流程啟動後，**[!UICONTROL Query]**&#x200B;活動所定位的人口族群將會分段，以接收電子郵件或簡訊傳送。

若要執行工作流程，請按一下動作列中的 **[!UICONTROL Start]** 按鈕。

您可以透過 Adobe Campaign 標誌，從進階功能表「**[!UICONTROL Marketing plans]** > **[!UICONTROL Marketing activities]**」存取傳送。按一下傳送，然後 **[!UICONTROL Reports]** 按鈕即可存取[傳送報告](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports)，例如傳送摘要、開放率或根據收件者的郵件收件匣而呈現的電子郵件。
