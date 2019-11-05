---
title: 技術工作流程
description: 技術工作流程是現成可用的工作流程，旨在處理Adobe Campaign中的背景技術程式，以確保平台的正確行為。
page-status-flag: 從未激活
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 參考
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 技術工作流程{#technical-workflows}

Adobe Campaign可立即提供技術工作流程。 技術工作流程是計畫定期在伺服器上執行的作業或作業。

它們允許您對資料庫執行維護操作、利用交貨中的跟蹤資訊，以及更新交貨的臨時任務。

功能管理員可存取功能表下的技術工 **[!UICONTROL Administration > Application settings > Workflows]** 作流程。

>[!NOTE]
>
>身為功能管理員，您可以重新啟動或暫停技術工作流程，並修改其屬性和結構。

![](assets/technical_workflows.png)

## 技術工作流程清單 {#list-of-technical-workflows}

技術工作流程可用來處理Adobe Campaign中自我觸發的背景和技術程式。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B測試</span><br /> </td> 
   <td> <span class="uicontrol">abTesting</span><br /> </td> 
   <td> 此工作流程會分析每個變體的追蹤記錄檔。 在A/B測試期間結束時，會自動計算成功變數。 依預設，它會每天啟動。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">帳單</span><br /> </td> 
   <td> <span class="uicontrol">帳單</span><br /> </td> 
   <td> 此工作流程會透過電子郵件將系統活動報表傳送至「帳單」使用者。 依預設，它會每天凌晨1點自動啟動。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">資料庫清理</span><br /> </td> 
   <td> <span class="uicontrol">清除</span><br /> </td> 
   <td> 此工作流是資料庫維護工作流：它運行不同的統計和進程，並根據已定義的配置從資料庫中刪除過時資料。 依預設，每天凌晨4點會自動啟動。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">預測</span><br /> </td> 
   <td> <span class="uicontrol">預測</span><br /> </td> 
   <td> 此工作流程會執行臨時預測（建立臨時記錄）中儲存的傳送分析。 依預設，每天早上1點開始。 <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">匯入共用的觀眾</span><br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span><br /> </td> 
   <td> 此工作流程會同步在Adobe Campaign中匯入的Adobe Experience cloud受眾資料。 依預設，會每小時啟動一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即時報表共用</span><br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> 當排程傳送報表時，就會立即啟動此工作流程。 它會將您的報表轉換為PDF檔案，然後以電子郵件傳送給目標收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI與Adobe Analytics協調</span><br /> </td> 
   <td> <span class="uicontrol">kpiConnigration</span><br /> </td> 
   <td> 此工作流程每天從Reporting服務擷取KPI一次，並與Adobe Analytics中的資料進行協調。 如有需要，這會推高差異。 依預設，每天4時20分開始。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">管理NMAC退出</span><br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMagt</span><br /> </td> 
   <td> 此工作流程會更新行動裝置上通知的取消訂閱。 依預設，從上午1點到午夜，每6小時啟動一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">郵件中心本地歸檔</span><br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> 此工作流程會將即時事件封存至歷史表格。 依預設，會每小時啟動一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">報告匯總</span><br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span><br /> </td> 
   <td> 此工作流程會更新報表中使用的匯總。 依預設，會在凌晨2點自動啟動。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">與Adobe Analytics共用KPI</span><br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span><br /> </td> 
   <td> 此工作流程每15分鐘將KPI資料從Adobe Campaign Standard推送至Adobe Analytics。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新傳送執行</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> 此工作流程會更新傳送的追蹤。 依預設，每10分鐘啟動一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新傳送指標</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> 此工作流程會更新傳送的KPI（關鍵績效指標）。 依預設，會每小時啟動一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新事件狀態</span><br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> 此工作流程可讓您將狀態歸因於事件。 <br /> 可使用下列事件狀態：待 <strong>定</strong>:事件位於隊列中。 尚未為其指派消息模板。<br /> 待 <span class="uicontrol">定傳送</span> :事件在佇列中，已指派訊息範本給該事件，並由傳送處理。<br /> 已 <strong>傳送</strong>:此狀態會從傳送記錄複製。 這表示送貨是送的。<br /> 傳 <strong>送忽略</strong>:此狀態會從傳送記錄複製。 這表示傳送被忽略。<br /> 傳 <strong>送失敗</strong>:此狀態會從傳送記錄複製。 這意味著交付失敗。<br /> 未 <span class="uicontrol">考慮事件</span> :事件無法連結至訊息範本。 不會處理事件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">提供性更新</span><br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span><br /> </td> 
   <td> 此工作流程可讓您建立彈回數規則限定規則清單，以及平台中網域和MX的清單。 只有在HTTPS開啟時，此工作流程才能運作。 依預設，會在凌晨2點自動啟動。<br /> </td> 
  </tr> 
 </tbody> 
</table>

