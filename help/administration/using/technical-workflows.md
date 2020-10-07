---
title: 技術工作流程
description: 技術工作流程是現成的工作流程，旨在處理 Adobe Campaign 中的背景技術程式，以確保平台正常運作。
page-status-flag: never-activated
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 100%

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
   <td> <span class="uicontrol">資料庫清除</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> 此工作流程是資料庫維護工作流程：會執行不同的統計和進度，並根據已定義的設定，從資料庫中刪除過時資料。預設會每天凌晨 4:00 自動啟動。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">預測</span> <br /> </td> 
   <td> <span class="uicontrol">預測</span> <br /> </td> 
   <td> 此工作流程會執行臨時預測（建立臨時記錄）中儲存的傳送分析。預設會每天早上 1:00 點開始。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">匯入共用的對象</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> 此工作流程會同步在 Adobe Campaign 中匯入的 Adobe Experience Cloud 對象資料。預設會每小時啟動一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即時報告共用</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> 排程傳送報告時，就會立即啟動此工作流程。它會將您的報告轉換為 PDF 檔案，然後以電子郵件傳送給目標收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI 與 Adobe Analytics 之調解</span> <br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span> <br /> </td> 
   <td> 此工作流程每天從報告服務擷取 KPI 一次，並與 Adobe Analytics 中的資料進行調解。之後，會視需要推播差異。預設會每天凌晨 4:20 開始。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">管理 CCPA 選取退出</span> <br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span> <br /> </td> 
   <td> 此工作流程會更新行動裝置上通知的取消訂閱。預設會從上午 1:00 到午夜，每 6 小時啟動一次。<br /> </td> 
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
   <td> 此工作流程會同步在 Adobe Campaign Standard 中匯入的 Adobe Launch 行動裝置屬性。每 15 分鐘開始一次。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">更新傳送執行</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br /> </td> 
   <td> 此工作流程會更新傳送的追蹤。預設會每 10 分鐘啟動一次。<br /> </td> 
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

