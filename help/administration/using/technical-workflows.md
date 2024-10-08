---
title: 技術工作流程
description: 進一步瞭解技術工作流程
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: da3a3af5-207a-4289-bd07-00a8c5d1cf57
source-git-commit: f87795ee2378a1e9e1b393c6cce002bcb70178b8
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 74%

---

# 技術工作流程{#technical-workflows}

Adobe Campaign 可立即提供技術工作流程。技術工作流程是排程定期在伺服器上執行的操作或作業。

它們可讓您對資料庫執行維護操作、利用傳送中的追蹤資訊，以及更新傳送的臨時工作。

功能管理員可存取 **[!UICONTROL Administration > Application settings > Workflows]** 功能表下的技術工作流程。

>[!NOTE]
>
>身為功能管理員，您可以重新啟動或暫停技術工作流程，並修改其屬性和結構。

![](assets/technical_workflows.png)

## 技術工作流程清單 {#list-of-technical-workflows}

技術工作流程可用於處理 Adobe Campaign 中自我觸發的背景和技術程式。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B 測試</span> <br /> </td> 
   <td> <span class="uicontrol">abTesting</span> <br /> </td> 
   <td> 此工作流程會分析每個變體的追蹤記錄檔。在 A/B 測試期間結束時，會自動計算成功變數。預設會每天啟動。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">帳單</span> <br /> </td> 
   <td> <span class="uicontrol">帳單</span> <br /> </td> 
   <td> 此工作流程會透過電子郵件，將系統活動報告傳送給「帳單」使用者。預設會每天凌晨 1:00 自動啟動。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">從傳遞範本複製標頭</span> <br /> </td> 
   <td> <span class="uicontrol">smtpHeaderupdate</span> <br /> </td> 
   <td> 此工作流程會將為電子郵件傳遞範本設定的SMTP標題複製到對應的子非範本傳遞。 此工作流程只會擷取電子郵件行銷傳遞。 SMTP標頭不會複製到交易式傳送和校樣傳送。 <br>此工作流程未定期執行。 必須由使用者根據每次使用而啟動。 <!--So it'not really a technical workflow like all workflows on this page, because it's not run automatically - TBC--> <br>如果您的執行個體上有大量傳遞，您可以在<strong>應用程式設定</strong>中更新NmsCleanup_DeliveryPurgeDelay選項。 如果您變更任何範本的SMTP標頭，您就必須在變更後再次執行工作流程，以便將更正後的標頭複製到非範本的傳送。<a href="data-retention.md#deliveries">進一步瞭解</a>
   <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">資料庫清除</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> 此工作流程是資料庫維護工作流程：會執行不同的統計和進度，並根據已定義的設定，從資料庫中刪除過時資料。預設會每天凌晨 4:00 自動啟動。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">匯入共用的客群</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> 此工作流程會同步在 Adobe Campaign 中匯入的 Adobe Experience Cloud 客群資料。預設會每小時啟動一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即時報告共用</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> 排程傳送報告時，就會立即啟動此工作流程。它會將您的報告轉換為 PDF 檔案，然後以電子郵件傳送給目標收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI 與 Adobe Analytics 之調解</span> <br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span> <br /> </td> 
   <td> 此工作流程每天從報告服務擷取 KPI 一次，並與 Adobe Analytics 中的資料進行調和。之後，會視需要推播差異。預設會每天凌晨 4:20 開始。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">訊息中心本機封存</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span> <br /> </td> 
   <td> 此工作流程會將即時事件封存至歷史表格。預設會每小時啟動一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">報告彙總</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> 此工作流程會更新報告中使用的彙總。預設會在凌晨 2:00 自動啟動。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">與 Adobe Analytics 共用 KPI</span> <br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span> <br /> </td> 
   <td> 此工作流程每 15 分鐘將 KPI 資料從 Adobe Campaign Standard 推播至 Adobe Analytics。<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">與 Launch 同步</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> 此工作流程會同步在Adobe Campaign Standard中匯入的標籤行動裝置屬性。 每 15 分鐘開始一次。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">追蹤記錄復原</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> 此工作流程會同步在Adobe Campaign Standard中匯入的標籤行動裝置屬性。 每 15 分鐘開始一次。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">復原追蹤記錄</span> <br /> </td> 
   <td> <span class="uicontrol">trackingLogRecovery</span> <br /> </td> 
   <td> 此工作流程會還原遺失的追蹤記錄。 請注意，此技術工作流程用於特定內容，並僅限於Adobe內部使用。 <br>預設會每10分鐘啟動一次。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">更新傳送執行</span> <br/> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br/> </td> 
   <td> 此工作流程會複製本機資料庫中的broadlog和追蹤記錄。 預設會每 10 分鐘啟動一次。<br/> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">更新傳送指標</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span> <br /> </td> 
   <td> 此工作流程會更新傳送的 KPI（關鍵績效指標）。預設會每小時啟動一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新事件狀態</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> 此工作流程可讓您將狀態歸因於事件。可使用下列事件狀態：<br /><strong>待定</strong>：事件位於佇列中。尚未為其指派訊息範本。<br /> <span class="uicontrol">待定傳送</span>：事件在佇列中，已指派訊息範本給該事件，並由傳送處理。<br /> <strong>已傳送</strong>：此狀態是從傳送記錄檔複製而來。這表示傳送已進行。<br /> <strong>由傳送忽略</strong>：此狀態是從傳送記錄檔複製而來。這表示會由傳送忽略。<br /> <strong>傳送失敗</strong>：此狀態是從傳送記錄檔複製而來。這表示傳送失敗。<br /> <span class="uicontrol">未考慮事件</span>：無法將事件連結至訊息範本。將不會處理事件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">傳送能力更新</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> 此工作流程可讓您建立退回規則限定規則清單，以及平台中的網域及 MX 的清單。只有在 HTTPS 開啟時，此工作流程才能運作。預設會在凌晨 2:00 自動啟動。<br /> </td> 
  </tr> 
 </tbody> 
</table>
