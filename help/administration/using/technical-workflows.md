---
title: 技術工作流程
seo-title: 技術工作流程
description: 技術工作流程
seo-description: 技術工作流程是用來處理Adobe Campaign背景技術流程的現成可用工作流程，確保平台的行為正確。
page-status-flag: 從未啓動
uuid: 6e763dc1-e1 d3-4d94-bc0 b-ef5 b1703 d e5
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 應用程式設定
discoiquuid: e9f147bd-6a5b-4b82-b82-b9 bb-311e32 e22 c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2541b6dadd005c74d6bb737a0e3692e63a5b85db

---


# Technical workflows{#technical-workflows}

Adobe Campaign提供技術工作流程。技術工作流程是計劃在伺服器上定期執行的作業或工作。

它們可讓您在資料庫上執行維護作業、運用傳送中的追蹤資訊，並更新傳送的臨時工作。

Functional administrators can access technical workflows under the **[!UICONTROL Administration > Application settings > Workflows]** menu.

>[!NOTE]
>
>身為功能管理員，您可以重新啓動或暫停技術工作流程，並修改其屬性和結構。

![](assets/technical_workflows.png)

## List of technical workflows {#list-of-technical-workflows}

技術工作流程可用來處理Adobe Campaign中的自我觸發背景和技術程序。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B測試</span><br /> </td> 
   <td> <span class="uicontrol">ABTesting</span><br /> </td> 
   <td> 此工作流程會分析每個變體的追蹤記錄檔。A/B測試期間結束時，會自動計算獲勝變體。By default, it is started every day.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">帳單</span><br /> </td> 
   <td> <span class="uicontrol">帳單</span><br /> </td> 
   <td> 此工作流程會透過電子郵件傳送系統活動報表給「帳單」使用者。By default, it is automatically started every day at 1am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">資料庫清除</span><br /> </td> 
   <td> <span class="uicontrol">清除</span><br /> </td> 
   <td> 此工作流程為資料庫維護工作流程：它會執行不同的統計資料和程序，並根據定義的組態從資料庫刪除過時資料。By default, it is automatically started every day 4am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">預測功能</span><br /> </td> 
   <td> <span class="uicontrol">預測功能</span><br /> </td> 
   <td> 此工作流程會執行暫存分析中儲存的傳送分析(臨時記錄建立)。By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">匯入共用觀眾</span><br /> </td> 
   <td> <span class="uicontrol">ImportSharedAudience</span><br /> </td> 
   <td> 此工作流程會同步Adobe Campaign中匯入的Adobe Experience Cloud觀眾資料。By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即時報告分享</span><br /> </td> 
   <td> <span class="uicontrol">ReportSendingNow</span><br /> </td> 
   <td> 當計劃傳送報表時，此工作流程就會立即開始。It converts your report into a pdf file then sends it in an email to the targeted recipients.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">使用Adobe Analytics進行KPI協調</span><br /> </td> 
   <td> <span class="uicontrol">KPijalization</span><br /> </td> 
   <td> 此工作流程會每天從報告服務擷取KPI一次，並與來自Adobe Analytics的資料協調。然後視需要推播差異。By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">管理NMAC選擇退出</span><br /> </td> 
   <td> <span class="uicontrol">MobileApptoMgt</span><br /> </td> 
   <td> 此工作流程更新會取消訂閱行動裝置的通知。By default, it is started every 6 hours between 1am and midnight.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">訊息中心本機封存</span><br /> </td> 
   <td> <span class="uicontrol">McSynch_ local</span><br /> </td> 
   <td> 此工作流程將即時事件封存為歷史表格。By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">報告匯總</span><br /> </td> 
   <td> <span class="uicontrol">報表整合</span><br /> </td> 
   <td> 此工作流程會更新報告中使用的匯總。By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">與Adobe Analytics共用KPI</span><br /> </td> 
   <td> <span class="uicontrol">KPiSharing</span><br /> </td> 
   <td> This workflow pushes KPI data every 15 minutes from Adobe Campaign Standard to Adobe Analytics.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新傳送執行</span><br /> </td> 
   <td> <span class="uicontrol">UpdatedLiveryExecutInfo</span><br /> </td> 
   <td> 此工作流程會更新傳送的追蹤。By default, it is started every 10 minutes.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新傳送指標</span><br /> </td> 
   <td> <span class="uicontrol">更新詳細資料</span><br /> </td> 
   <td> 此工作流程會更新傳送的KPI(關鍵績效指標)。By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新事件狀態</span><br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> 此工作流程可讓您將狀態歸因於事件。The following event statuses are available:<br /> <strong>Pending</strong>: The event is in a queue. 尚未指派訊息範本。<br /><span class="uicontrol">待定傳送</span> ：事件位於佇列中，已指派訊息範本給它，並由傳送處理。<br /><strong>傳送</strong>：此狀態會從傳送記錄檔中複製。這表示傳送是傳送的。<br /><strong>傳送時忽略</strong>：此狀態會從傳送記錄檔中複製。這表示傳送被忽略。<br /><strong>傳送失敗</strong>：此狀態會從傳送記錄檔中複製。這表示傳送失敗。<br /><span class="uicontrol">未考量事件</span> ：無法連結事件至訊息範本。The event will not be processed.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">提供可傳送的更新</span><br /> </td> 
   <td> <span class="uicontrol">遞送程序更新</span><br /> </td> 
   <td> 此工作流程可讓您建立反彈規則規則的清單，以及平台中的網域清單和MX清單。只有當HTTPS開啓時，才會運作此工作流程。By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
 </tbody> 
</table>

