---
title: Analytics 中的 Campaign 維度和度量
description: 瞭解您可在Adobe Analytics中找到的不同維度，以開始追蹤您從Adobe Campaign傳送的電子郵件。
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Analytics 中的 Campaign 維度和度量{#campaign-dimensions-and-metrics-in-analytics}

Adobe Campaign與Adobe Analytics整合可讓您直接在Adobe Analytics中追蹤電子郵件傳送的成功。

Analytics中 **[!UICONTROL dimensions]** 找到的促銷活動列於下列：

<table> 
 <thead> 
  <tr> 
   <th> 維<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 促銷活動ID<br /> </td> 
   <td> 促銷活動的內部名稱，如促銷活動中所示<br /> </td> 
  </tr> 
  <tr> 
   <td> 促銷活動標籤<br /> </td> 
   <td> 促銷活動中顯示的促銷活動標籤<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送ID<br /> </td> 
   <td> 如促銷活動中所示的傳送內部名稱。<br /> 例如，DM1是計畫每週傳送子傳送的循環傳送。 DM2 、 DM3和DM4在前三週發送。 然後，「傳送ID」維度會顯示每個傳送的結果，即DM1到DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送標籤<br /> </td> 
   <td> 促銷活動中顯示的傳送標籤<br /> </td> 
  </tr> 
  <tr> 
   <td> 已執行傳送ID<br /> </td> 
   <td> 如促銷活動中所示的傳送內部名稱。 這隻涉及在促銷活動中執行時的傳送。<br /> 例如，DM1是計畫每週傳送子傳送的循環傳送。 DM2 、 DM3和DM4在前三週發送。 然後，「已執行的傳送ID」維將顯示已執行傳送的結果，即子傳送DM2、DM3和DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 已執行傳送標籤<br /> </td> 
   <td> 促銷活動中顯示的傳送標籤。 這隻涉及在促銷活動中執行時的傳送。<br /> </td> 
  </tr> 
 </tbody> 
</table>

Analytics中 **[!UICONTROL metrics]** 找到的促銷活動列於下列：

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已點按<br /> </td> 
   <td> 內容在傳送中被點按的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> 成功發送的消息數，與已發送消息總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已開啟<br /> </td> 
   <td> 傳送中訊息開啟的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳送<br /> </td> 
   <td> 傳送的傳送總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 總彈回數<br /> </td> 
   <td> 傳送和自動傳回處理期間累積的錯誤總數，與傳送的訊息總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特開啟<br /> </td> 
   <td> 開啟傳送的收件者數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一點按<br /> </td> 
   <td> 點選傳送中內容的收件者數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱<br /> </td> 
   <td> 取消訂閱連結的點按次數。<br /> </td> 
  </tr> 
 </tbody> 
</table>

