---
title: Analytics 中的 Campaign 維度和量度
description: 了解您可在Adobe Analytics中找到的不同維度，以開始從Adobe Campaign追蹤電子郵件傳遞。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 3%

---

# Analytics 中的 Campaign 維度和量度{#campaign-dimensions-and-metrics-in-analytics}

Adobe Campaign和Adobe Analytics整合可讓您直接在Adobe Analytics中追蹤電子郵件傳送的成功。

Analytics中的Campaign **[!UICONTROL dimensions]**&#x200B;列於下列：

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 促銷活動ID<br /> </td> 
   <td> 如促銷活動<br />中所示的促銷活動內部名稱 </td> 
  </tr> 
  <tr> 
   <td> 促銷活動標籤<br /> </td> 
   <td> 如促銷活動<br />中所示的促銷活動標籤 </td> 
  </tr> 
  <tr> 
   <td> 傳送ID<br /> </td> 
   <td> 如Campaign中所示的傳送內部名稱。<br /> 例如，DM1是排程每週傳送子傳送的循環傳送。DM2、DM3和DM4會在前三週傳送。 接著，「傳送ID」維度會顯示每個傳送的結果，即DM1到DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞標籤<br /> </td> 
   <td> 如Campaign<br />所示的傳送標籤 </td> 
  </tr> 
  <tr> 
   <td> 已執行的傳送ID<br /> </td> 
   <td> 如Campaign中所示的傳送內部名稱。 這隻與Campaign執行中的傳送有關。<br /> 例如，DM1是排程每週傳送子傳送的循環傳送。DM2、DM3和DM4會在前三週傳送。 然後，「已執行的傳送ID」維度會顯示已執行傳送的結果，即子傳送DM2、DM3和DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 已執行傳送標籤<br /> </td> 
   <td> 如Campaign中所示的傳送標籤。 這隻與在Campaign執行中的傳送有關。<br /> </td> 
  </tr> 
 </tbody> 
</table>

Analytics中的Campaign **[!UICONTROL metrics]**&#x200B;列於下列：

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
   <td> 傳送中點按內容的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳送<br /> </td> 
   <td> 已成功發送的消息數，與已發送的消息總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已開啟<br /> </td> 
   <td> 在傳遞中開啟消息的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已發送<br /> </td> 
   <td> 傳送的傳送總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 總跳出數<br /> </td> 
   <td> 與已發送消息的總數相關，在傳送和自動返回處理期間累積的錯誤總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一開啟<br /> </td> 
   <td> 開啟傳遞的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複點按<br /> </td> 
   <td> 按一下傳遞內容的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱<br /> </td> 
   <td> 取消訂閱連結的點按次數。<br /> </td> 
  </tr> 
 </tbody> 
</table>
