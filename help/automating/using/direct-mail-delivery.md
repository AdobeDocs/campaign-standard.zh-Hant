---
title: 直接傳送郵件
seo-title: 直接傳送郵件
description: 直接傳送郵件
seo-description: 直接郵件傳送活動可讓您設定傳送單一傳送直接郵件或在工作流程中循環直接郵件。
page-status-flag: 從未啓動
uuid: bfa7b176-a17 c-4079-a073-64b8 ce4788 ed
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: channel-activity
discoiquuid: b9ddb2a0-54ff-4ada-be6 f-8109fa06 d461
context-tags: Directmail、工作流程、主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Direct mail delivery{#direct-mail-delivery}

## Description {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

**[!UICONTROL Direct mail delivery]** 活動可讓您設定並準備包含您要用於直接郵件促銷活動之描述檔資料的檔案。This can be a direct mail that is used just once, or it can be a **recurring** direct mail.

標準直接郵件只會傳送一次。

循環郵件可讓您在定義的期間內，多次傳送相同的直接郵件至不同的目標。您可以匯總每個時段的傳送，取得符合您需求的報表。

## Context of use {#context-of-use}

**[!UICONTROL Direct mail delivery]** 此活動通常用於自動化包含描述檔資料的檔案。然後可將此檔案傳送給負責郵寄的合作夥伴/供應商。

連結至排程器時，您可以定義循環的直接郵件。

直接郵件收件者透過定位活動(例如查詢、交叉點等)，在相同工作流程中定義為上游。直接郵件備妥時，會自動排除未指定郵寄地址的描述檔。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選擇要請求還是不要手動確認傳送訊息(預設為必要)。您可以手動開始工作流程，或在工作流程中放置排程器活動，以自動化執行。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Direct mail delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. 此按鈕適用於頻道活動。直接郵件的屬性可透過直接郵件控制面板中的動作列存取。

1. 選取直接郵件傳送模式：

   * **[!UICONTROL Direct mail]**：直接郵件會傳送一次。您可以在此處指定是否要為活動新增對外轉場。此程序步驟中會詳述不同的轉場類型。
   * **[!UICONTROL Recurring direct mail]**：直接郵件會根據 **[!UICONTROL Scheduler]** 活動中定義的頻率數次傳送。選取傳送的匯總期間。This allows you to regroup all the sends that occur during the defined period in one single direct mail that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      例如，針對每日處理的循環生日郵件，您可以選擇匯總每個月傳送的郵件。這可讓您每月收到報告，但每天收到郵件。

      >[!NOTE]
      >
      >對於循環直接郵件，會在工作流程的每次執行時產生新檔案。選取的匯總期間對此行為沒有影響。

1. 選取直接郵件類型。The direct mail types come from templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. 輸入直接郵件的一般屬性。您也可以將其附加至現有促銷活動。工作流程的傳送活動標籤會使用直接郵件標籤更新。
1. 定義直接郵件內容。Refer to the section concerning [content editing](../../designing/using/about-personalization.md).
1. By default, the **[!UICONTROL Direct mail delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Direct mail delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生對外轉場，其中包含與傳入轉換完全相同的人口族群。此轉換包含直接郵件活動所接收的直接郵件活動和原始人口所產生的檔案。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生包含直接郵件寄送之人口的對外轉換。直接郵件準備期間排除的目標成員(隔離、無效位址等)被排除在外。轉場也包含直接郵件產生的檔案。

1. 確認活動的設定並儲存工作流程。

當您重新開啓活動時，會直接進入直接郵件控制面板。只能編輯其內容。

根據預設，啓動傳送工作流程只會觸發訊息準備。在工作流程啓動後，仍需要確認從工作流程建立的訊息。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. 取消勾選此選項後，就會在準備完成後，不會進一步通知訊息。

## Remarks {#remarks}

在工作流程中建立的傳送可在應用程式的行銷活動清單中存取。您可以使用控制面板來檢視工作流程的執行狀態。直接郵件摘要窗格中的連結可讓您直接存取連結的元素(工作流程、促銷活動、父項傳送，萬一是週期性的直接郵件)。

![](assets/wkf_display_parent_elements_direct_mail.png)

預設會遮罩週期性傳送的執行。To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of mails that have been processed (according to the aggregation period specified when the **[!UICONTROL Direct mail delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)

## Example {#example}

**[!UICONTROL Direct mail delivery]**[「直接郵件](../../channels/using/example-of-direct-mail-in-a-workflow.md) 」章節中提供了一個範例。
