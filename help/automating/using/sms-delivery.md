---
title: SMS傳送
seo-title: SMS傳送
description: SMS傳送
seo-description: SMS傳送活動可讓您設定在工作流程中傳送單一傳送SMS或循環SMS。
page-status-flag: 從未啓動
uuid: 736078c6-ac91-4440-825b-4a6 ae31894 ef
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: channel-activity
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms，main；傳送，SMSContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# SMS傳送{#sms-delivery}

## 說明 {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

**[!UICONTROL SMS delivery]** 此活動可讓您設定工作流程中的SMS。這可以是 **單一傳送** SMS，只傳送一次，或者可能是 **循環** SMS。

單一傳送SMS訊息是標準SMS，只需傳送一次。

循環SMS訊息可讓您在定義的期間內，多次傳送相同的SMS至不同的目標。您可以匯總每個時段的傳送，取得符合您需求的報表。

## 使用內容 {#context-of-use}

**[!UICONTROL SMS delivery]** 此活動通常用於將SMS傳送至相同工作流程中計算的目標。

當連結至排程器時，您可以定義循環SMS訊息。

SMS收件者可透過定位活動(例如查詢、交叉點等)，在相同工作流程中定義為上游。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選擇要請求還是不要手動確認傳送訊息(預設為必要)。您可以手動開始工作流程，或在工作流程中放置排程器活動，以自動化執行。

## 組態配置 {#configuration}

1. 將 **[!UICONTROL SMS delivery]** 活動拖放至工作流程中。
1. 選取活動，然後使用顯示的快速動作 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啓。

   >[!NOTE]
   >
   >您可以透過工作流程動作列中 ![](assets/dlv_activity_params-24px.png) 的按鈕，存取活動的一般屬性和進階選項(而不是傳送本身)。此按鈕適用於 **[!UICONTROL SMS delivery]** 活動。SMS屬性可透過SMS儀表板中的動作列存取。

1. 選取SMS傳送模式：

   * **[!UICONTROL SMS]**：SMS會一次傳送。您可以在此處指定是否要為活動新增對外轉場。此程序步驟中會詳述不同的轉場類型。
   * **[!UICONTROL Recurring SMS]**：SMS會根據 **[!UICONTROL Scheduler]** 活動中定義的頻率數次傳送。選取傳送的匯總期間。這可讓您將定義期間內發生的所有傳送重新群組為一個名為 **循環執行的** 單一檢視，並可從應用程式的行銷活動清單存取。

      例如，若是每日傳送的生日SMS，您可以選擇匯總每個月傳送的傳送次數。這可讓您每月收到報告，但每日傳送SMS。

1. 選取SMS類型。SMS類型來自 **[!UICONTROL Resources]** 於&gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** 功能表中定義的SMS範本。
1. 輸入SMS的一般屬性。您也可以將其附加至現有促銷活動。工作流程的傳送活動標籤會使用SMS標籤更新。
1. 定義SMS內容。請參閱 [建立SMS訊息的相關章節](../../channels/using/creating-an-sms-message.md)。
1. 依預設 **[!UICONTROL SMS delivery]** ，活動不包含任何傳出轉場。如果您想要新增傳出轉換至 **[!UICONTROL SMS delivery]** 活動，請前往進階活動選項 **[!UICONTROL General]** 的標籤( ![](assets/dlv_activity_params-24px.png) 活動快速動作中的按鈕)，然後檢查下列其中一個選項：

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生對外轉場，其中包含與傳入轉換完全相同的人口族群。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生內含SMS的對外轉場轉換。傳送準備期間排除的目標成員(隔離、無效數字等)被排除在外。

1. 確認活動的設定並儲存工作流程。

當您重新開啓活動時，會直接進入SMS儀表板。只能編輯其內容。

根據預設，啓動傳送工作流程只會觸發訊息準備。在工作流程啓動後，仍需要確認從工作流程建立的訊息。但在訊息控制面板中，只有在從工作流程建立訊息時，您可以停用 **[!UICONTROL Request confirmation before sending messages]** 選項。取消勾選此選項後，就會在準備完成後，不會進一步通知訊息。

## 注釋 {#remarks}

在工作流程中建立的傳送可在應用程式的行銷活動清單中存取。您可以使用控制面板來檢視工作流程的執行狀態。SMS摘要窗格中的連結可讓您直接存取連結的元素(工作流程、促銷活動、父項傳送，以發生循環SMS)。

不過，預設會遮罩週期性傳送的執行。若要檢視它們，請查看行銷活動的搜尋面板 **[!UICONTROL Show recurring executions]** 中的選項。

在父傳送中，可從行銷活動清單存取，或直接透過關聯的週期性執行次數存取，您可以檢視已處理的總次數(根據設定 **[!UICONTROL SMS delivery]** 活動時指定的匯總期間)。若要這麼做，請透過選取，開啓父傳送 **[!UICONTROL Deployment]** 區塊的詳細資料檢視 ![](assets/wkf_dlv_detail_button.png)。

## 範例 {#example}

![](assets/wkf_sms_example_1.png)

此範例為生日工作流程。每天將SMS傳送給當天生日的個人檔案。若要這麼做：

* 可 **[!UICONTROL Scheduler]** 讓您每天早上開始工作流程。

   ![](assets/wkf_delivery_example_2.png)

* **[!UICONTROL Query]** 此活動可讓您計算提供行動電話號碼和生日當天(每次執行工作流程)的個人檔案。您可以使用查詢編輯工具中浮動視窗中可用的預先定義篩選來進行生日計算。

   ![](assets/wkf_delivery_example_3.png)

* **[!UICONTROL SMS]** 週期性。傳送會依月份匯總。因此，在一個月內傳送的所有SMS訊息都會匯總至單一檢視中。在一年內，就會執行365個傳送，但在Adobe Campaign介面中重新整理為12個檢視(也稱為 **循環執行)**。歷史和報告細節會每個月顯示，而不是每次傳送。

   ![](assets/wkf_sms_example_4.png)

如需工作流程中的另一個SMS傳送範例，請參閱 [「使用案例：重新定向工作流程，將新傳送傳送給非電子書廠商](../../automating/using/workflow-cross-channel-retargeting.md)。
