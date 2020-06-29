---
title: 增量查詢
description: 「增量查詢」活動可讓您從Adobe Campaign資料庫中篩選及擷取一組元素。
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---


# 增量查詢{#incremental-query}

## 說明 {#description}

![](assets/incremental.png)

此活 **[!UICONTROL Incremental query]** 動可讓您從Adobe Campaign資料庫中篩選及擷取一組元素。 每次執行此活動時，都會排除先前執行的結果。 這可讓您只鎖定新元素。

您可以透過 **[!UICONTROL Additional data]** 專用標籤來定義目標人口。 此資料會儲存在其他欄中，且僅能用於進行中的工作流程。

活動使用查詢編輯器工具。 此工具在專屬章節中 [有詳細說明](../../automating/using/editing-queries.md#about-query-editor)。

## 使用內容 {#context-of-use}

必須 **[!UICONTROL Incremental query]** 將一個連結到一個， **[!UICONTROL Scheduler]** 才能定義工作流的執行頻率，從而定義查詢。

該 **[!UICONTROL Processed data]** 頁籤特定於此活動，允許您根據需要查看活動先前執行的任何結果。

此活 **[!UICONTROL Incremental query]** 動可用於各種類型的使用：

* 將個人分段以定義訊息、對象等的目標。

* 匯出資料.

   您可以使用活 **[!UICONTROL Incremental query]** 動定期匯出檔案中的新記錄檔。 例如，如果您想在外部報表或BI工具中使用記錄檔資料，則此功能會很有用。 「導出日誌」部分提供了 [完整示例](../../automating/using/exporting-logs.md) 。

**相關主題**

* [使用案例： 對服務訂戶的增量查詢](../../automating/using/incremental-query-on-subscribers.md)

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Incremental query]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 如果要對配置檔案資源以外的資源運行查詢，請轉至活動的頁籤， **[!UICONTROL Properties]** 然後選擇 **[!UICONTROL Resource]** 和 **[!UICONTROL Targeting dimension]**。

   您 **[!UICONTROL Resource]** 可以調整浮動視窗中顯示的篩選條件，而與所選資源相關的 **[!UICONTROL Targeting dimension]**，則與您要取得的人口類型（識別的設定檔、傳送、連結至所選資源的資料等）相對應。

1. 在標籤 **[!UICONTROL Target]** 中，定義並結合規則以執行查詢。
1. 在該選 **[!UICONTROL Processed data]** 項卡中，選擇要用於工作流下一個執行的增量模式：

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: 會排除每個新執行的先前執行結果。
   * **[!UICONTROL Use a date field]**: 下次執行只考慮所選日期欄位大於或等於活動最後執行日期的結 **[!UICONTROL Incremental query]** 果。 您可以選擇與在頁籤中選擇的資源相關的任何日期 **[!UICONTROL Properties]** 欄位。 此模式在查詢大型資源（如日誌資料）時具有更好的效能。

      在第一次執行工作流程後，您可以在此標籤中看到下次執行時使用的最後一個執行日期。 每次執行工作流程時，都會自動更新它。 您仍然可以手動輸入新值來覆寫此值，以符合您的需求。
   >[!NOTE]
   >
   >此模 **[!UICONTROL Use a date field]** 式會根據選取的日期欄位，提供更大的彈性。 例如，如果選定欄位與修改日期相對應，則日期欄位模式將允許您檢索最近更新的資料，而另一個模式將僅排除在先前執行中已定位的記錄，即使這些記錄自上次執行工作流後已被修改。

   ![](assets/incremental_query_usedatefield.png)

1. 您可以透過 **[!UICONTROL Additional data]** 專用標籤來定義目標人口。 此資料會儲存在其他欄中，且僅能用於進行中的工作流程。 尤其是，您可以從連結至查詢定位維度的Adobe Campaign資料庫表格新增資料。 請參閱「 [豐富資料](../../automating/using/query.md#enriching-data) 」一節。
1. 確認活動的設定並儲存工作流程。

## 豐富資料 {#enriching-data}

和查詢一樣，您也可以豐富來自的資料 **[!UICONTROL Incremental query]**。 請參閱「 [豐富資料](../../automating/using/query.md#enriching-data) 」一節。
