---
title: 簡訊傳送
description: SMS傳送活動可讓您在工作流程中設定傳送單一傳送SMS或循環SMS。
page-status-flag: 從未激活
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 頻道活動
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 簡訊傳送{#sms-delivery}

## 說明 {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

此活 **[!UICONTROL SMS delivery]** 動可讓您在工作流程中設定傳送SMS。 這可以是單 **一傳送** SMS，只傳送一次，或是重複 **傳送** SMS。

單一傳送的簡訊是標準的簡訊，只傳送一次。

循環SMS訊息可讓您在定義的時段內，多次傳送相同的SMS至不同的目標。 您可以匯總每個期間的交貨，以取得符合您需求的報表。

## 使用內容 {#context-of-use}

該 **[!UICONTROL SMS delivery]** 活動通常用於自動傳送SMS至在相同工作流程中計算的目標。

當連結至排程器時，您可以定義循環的SMS訊息。

SMS收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的活動。

根據工作流執行參數觸發消息準備。 在訊息控制面板中，您可以選擇是否要求傳送訊息的手動確認（預設為必要）。 您可以手動啟動工作流，或將排程器活動置於工作流中以自動執行。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL SMS delivery]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。

   >[!NOTE]
   >
   >您可以透過工作流程動作列中的按鈕，存取活動（而非傳送本身）的 ![](assets/dlv_activity_params-24px.png) 一般屬性和進階選項。 此按鈕是活動的特 **[!UICONTROL SMS delivery]** 定按鈕。 SMS屬性可透過SMS儀表板中的動作列存取。

1. 選擇SMS傳送模式：

   * **[!UICONTROL SMS]**:簡訊只會傳送一次。 您可以在此處指定是否要向活動添加出站轉變。 在本過程的步驟7中詳細介紹了不同的過渡類型。
   * **[!UICONTROL Recurring SMS]**:根據活動中定義的頻率，會多次傳送簡訊 **[!UICONTROL Scheduler]** 。 選擇發送的聚合期間。 這可讓您將定義期間發生的所有傳送重新分組為一個稱為「循環執行 **** 」的單一檢視，並可從應用程式的行銷活動清單存取。

      例如，對於每日傳送的循環生日SMS，您可以選擇匯總每月傳送的傳送。 這可讓您每月收到傳送的報告，不過SMS會每天傳送。

1. 選擇SMS類型。 SMS類型來自「 &gt; &gt;」功能表中定義的 **[!UICONTROL Resources]** SMS **[!UICONTROL Templates]** 范 **[!UICONTROL Delivery templates]** 本。
1. 輸入SMS的一般屬性。 您也可以將它附加至現有的促銷活動。 工作流程傳送活動的標籤會以SMS標籤更新。
1. 定義SMS內容。 請參閱「建立 [SMS訊息」一節](../../channels/using/creating-an-sms-message.md)。
1. 依預設，活動 **[!UICONTROL SMS delivery]** 不包含任何對外轉場。 如果要將出站轉移添加到活動 **[!UICONTROL SMS delivery]** 中，請轉至高級活動選項的頁籤( **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) 活動快速操作中的按鈕)，然後選中以下選項之一：

   * **[!UICONTROL Add outbound transition without the population]**:這可讓您產生一個對外轉移，其中包含與傳入轉移完全相同的人口。
   * **[!UICONTROL Add outbound transition with the population]**:這可讓您產生對外轉場，其中包含傳送SMS的人口。 在交付準備期間排除的目標成員（隔離、無效編號等）會從此轉換中排除。

1. 確認活動的設定並儲存工作流程。

當您重新開啟活動時，會直接帶您至SMS儀表板。 只能編輯其內容。

依預設，啟動傳送工作流程只會觸發訊息準備。 在工作流啟動後，仍需要確認從工作流建立的消息的發送。 但是，在訊息控制面板中，只有在訊息是從工作流程建立時，您才能停用選 **[!UICONTROL Request confirmation before sending messages]** 項。 取消勾選此選項後，訊息會在準備完成後不另行通知而傳送。

## 注釋 {#remarks}

您可以在應用程式的行銷活動清單中存取在工作流程中建立的傳送。 您可以使用控制面板來檢視工作流程的執行狀態。 SMS摘要窗格中的連結可讓您直接存取連結的元素(工作流程、促銷活動、父項傳送（若是重複的SMS）)。

不過，循環傳送的執行依預設會被遮色。 若要檢視，請勾選行 **[!UICONTROL Show recurring executions]** 銷活動搜尋面板中的選項。

在可從行銷活動清單存取或直接透過相關循環執行存取的父傳送中，您可以檢視已處理的傳送總數（根據設定活動時指定的匯總期間）。 **[!UICONTROL SMS delivery]** 若要這麼做，請選取以開啟父傳送區塊的詳 **[!UICONTROL Deployment]** 細資料檢視 ![](assets/wkf_dlv_detail_button.png)。

## Example {#example}

![](assets/wkf_sms_example_1.png)

此範例是生日工作流程。 每天都會傳送簡訊給當天生日的個人檔案。 操作步驟：

* 它 **[!UICONTROL Scheduler]** 可讓您每天上午8點開始工作流程。

   ![](assets/wkf_delivery_example_2.png)

* 此活 **[!UICONTROL Query]** 動可讓您計算每次執行工作流程時，提供行動電話號碼且其生日是當天的設定檔。 生日計算是使用查詢編輯工具的浮動視窗中可用的預先定義篩選器來執行。

   ![](assets/wkf_delivery_example_3.png)

* 重複 **[!UICONTROL SMS]** 出現。 傳送會依月份匯總。 所以，在一個月內傳送的所有SMS訊息都會匯整成單一檢視。 因此，在一年內，會執行365個傳送，但會在Adobe Campaign介面中重新分組為12個檢視(也稱 **為循環執行**)。 歷史記錄和報表詳細資訊會每個月顯示一次，而非每次傳送。

   ![](assets/wkf_sms_example_4.png)

如需工作流程中SMS傳送的另一個範例，請參閱使 [用案例：重新定位傳送新傳送給非開啟者的工作流程](../../automating/using/workflow-cross-channel-retargeting.md)。
