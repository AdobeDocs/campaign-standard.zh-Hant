---
title: 電子郵件傳送
description: 「電子郵件傳送」活動可讓您設定在工作流程中傳送單一傳送電子郵件或循環電子郵件。
page-status-flag: 從未激活
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 頻道活動
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: 交付，工作流，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 電子郵件傳送{#email-delivery}

## 說明 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

此活 **[!UICONTROL Email delivery]** 動可讓您設定在工作流程中傳送電子郵件。 這可以是單一 **傳送電子郵件** ，只傳送一次，或是循環 **寄送** 電子郵件。

單一傳送電子郵件是標準電子郵件，只傳送一次。

循環電子郵件可讓您在定義的期間內多次傳送相同的電子郵件至不同的目標。 您可以匯總每個期間的交貨，以取得符合您需求的報表。

## 使用內容 {#context-of-use}

活動 **[!UICONTROL Email delivery]** 通常用於自動傳送電子郵件至相同工作流程中計算的目標。

當連結至排程器時，您可以定義循環的電子郵件。

電子郵件收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的位置。

根據工作流執行參數觸發消息準備。 在訊息控制面板中，您可以選擇是否要求傳送訊息的手動確認（預設為必要）。 您可以手動啟動工作流，或將排程器活動置於工作流中以自動執行。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Email delivery]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過活動快速動作的按鈕，存取活動（而非傳送本身）的一 ![](assets/dlv_activity_params-24px.png) 般屬性和進階選項。 此按鈕是活動的特 **[!UICONTROL Email delivery]** 定按鈕。 您可以透過電子郵件控制面板中的動作列存取電子郵件的屬性。

1. 選擇電子郵件傳送模式：

   * **[!UICONTROL Email]**:電子郵件只會傳送一次。 您可以在此處指定是否要向活動添加出站轉變。 在本過程的步驟7中詳細介紹了不同的過渡類型。
   * **[!UICONTROL Recurring email]**:根據活動中定義的頻率，會多次傳送電子郵 **[!UICONTROL Scheduler]** 件。 選擇發送的聚合期間。 這可讓您在一個電子郵件中重新分組定義期間發生的所有傳送，該電子郵件也稱為 **Recurring execution** ，可從應用程式的行銷活動清單存取。

      例如，對於每日傳送的循環生日電子郵件，您可以選擇匯總每月傳送的傳送。 這可讓您每月收到有關傳送的報表，不過每天都會傳送電子郵件。

1. 選擇電子郵件類型。 電子郵件類型來自「 &gt; &gt;」功能表中定 **[!UICONTROL Resources]** 義的 **[!UICONTROL Templates]** 電子郵件 **[!UICONTROL Delivery templates]** 範本。
1. 輸入電子郵件的一般屬性。 您也可以將它附加至現有的促銷活動。 工作流程的傳送活動標籤會以電子郵件標籤更新。
1. 定義電子郵件內容。 請參閱有關內容編輯 [的章節](../../designing/using/overview.md)。
1. 依預設，活動 **[!UICONTROL Email delivery]** 不包含任何對外轉場。 如果要將出站轉移添加到活動 **[!UICONTROL Email delivery]** 中，請轉至高級活動選項的頁籤( **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) 活動快速操作中的按鈕)，然後選中以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**:這可讓您產生一個對外轉移，其中包含與傳入轉移完全相同的人口。
   * **[!UICONTROL Add outbound transition with the population]**:這可讓您產生對外轉場，其中包含傳送電子郵件的人口。 傳送準備期間排除的目標成員（隔離、無效電子郵件等）會從此轉換中排除。

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會將您直接帶至電子郵件控制面板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。 在工作流啟動後，仍需要確認從工作流建立的消息的發送。 但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用選 **[!UICONTROL Request confirmation before sending messages]** 項。 取消勾選此選項後，訊息會在準備完成後不另行通知而傳送。

## 注釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。 您可以使用控制面板來檢視工作流程的執行狀態。 電子郵件摘要窗格中的連結可讓您直接存取連結的元素（工作流程、促銷活動、父項傳送，以防重複傳送電子郵件）。

![](assets/wkf_display_recurrent_executions_2.png)

不過，循環傳送的執行依預設會被遮色。 若要檢視，請勾選行 **[!UICONTROL Show recurring executions]** 銷活動搜尋面板中的選項。

![](assets/wkf_display_recurrent_executions.png)

在可從行銷活動清單存取或直接透過相關循環執行存取的父傳送中，您可以檢視已處理的傳送總數（根據設定活動時指定的匯總期間）。 **[!UICONTROL Email delivery]** 若要這麼做，請選取以開啟父傳送區塊的詳 **[!UICONTROL Deployment]** 細資料檢視 ![](assets/wkf_dlv_detail_button.png)。

![](assets/wkf_display_recurrent_executions_3.png)

## Example {#example}

![](assets/wkf_delivery_example_1.png)

此範例是生日工作流程。 每天都會傳送電子郵件給當天生日的個人檔案。 操作步驟：

* 它 **[!UICONTROL Scheduler]** 可讓您每天上午8點開始工作流程。

   ![](assets/wkf_delivery_example_2.png)

* 此活 **[!UICONTROL Query]** 動可讓您計算每次執行工作流程時，提供電子郵件的設定檔，以及其生日。 生日計算是使用查詢編輯工具的浮動視窗中可用的預先定義篩選器來執行。

   ![](assets/wkf_delivery_example_3.png)

* 重複 **[!UICONTROL Email]** 出現。 傳送會依月份匯總。 因此，一個月內傳送的所有電子郵件都會匯總成單一檢視。 因此，在一年內，會執行365個傳送，但會在Adobe Campaign介面中重新分組為12個檢視(也稱 **為循環執行**)。 歷史記錄和報表詳細資訊會每個月顯示一次，而非每次傳送。

   ![](assets/wkf_delivery_example_4.png)

**相關主題**

* [使用案例：建立每週一次的電子郵件傳送](../../automating/using/workflow-weekly-offer.md)
* [使用案例：建立依位置分段的傳送](../../automating/using/workflow-segmentation-location.md)
* [使用案例：建立具備輔助功能的傳送](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重新定位傳送新傳送給非開啟者的工作流程](../../automating/using/workflow-cross-channel-retargeting.md)