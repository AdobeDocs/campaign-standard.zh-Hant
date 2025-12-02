---
title: Analytics 中的 Campaign 維度和量度
description: 瞭解您可以在Adobe Analytics中找到的不同維度，以開始從Adobe Campaign追蹤您的電子郵件傳送。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 3%

---

# Analytics 中的 Campaign 維度和量度{#campaign-dimensions-and-metrics-in-analytics}

Adobe Campaign與Adobe Analytics整合可讓您直接在Adobe Analytics中追蹤電子郵件傳送的成功情況。

在Analytics中找到的行銷活動&#x200B;**[!UICONTROL dimensions]**&#x200B;列示如下：

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 行銷活動ID<br /> </td> 
   <td> 如行銷活動<br />中所見的行銷活動內部名稱 </td> 
  </tr> 
  <tr> 
   <td> 行銷活動標籤<br /> </td> 
   <td> 行銷活動中的行銷活動標籤，如Campaign<br />中所示 </td> 
  </tr> 
  <tr> 
   <td> 傳遞ID<br /> </td> 
   <td> 在Campaign中看到的傳遞內部名稱。<br />例如，DM1是排程每週傳送子傳遞的循環傳遞。 DM2、DM3和DM4會在最初三週傳送。 然後，傳遞ID維度會顯示每個傳遞的結果，即DM1到DM4。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞標籤<br /> </td> 
   <td> 在Campaign<br />中看到的傳遞標籤 </td> 
  </tr> 
  <tr> 
   <td> 已執行的傳遞ID<br /> </td> 
   <td> 在Campaign中看到的傳遞內部名稱。 這僅涉及Campaign中的傳送執行。<br />例如，DM1是排程每週傳送子傳遞的循環傳遞。 DM2、DM3和DM4會在最初三週傳送。 然後，「已執行的傳送ID」維度會顯示已執行傳送的結果，即子傳送DM2、DM3和DM4。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已執行的傳遞標籤<br /> </td> 
   <td> 在Campaign中看到的傳送標籤。 這僅與行銷活動中執行的傳遞有關。<br /> </td> 
  </tr> 
 </tbody> 
</table>

在Analytics中找到的行銷活動&#x200B;**[!UICONTROL metrics]**&#x200B;列示如下：

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
   <td> 內容在傳遞中被點按的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> 成功傳送的訊息數，與已傳送的訊息總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已開啟<br /> </td> 
   <td> 訊息在傳遞中開啟的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳送<br /> </td> 
   <td> 傳遞的傳送總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 總跳出數<br /> </td> 
   <td> 傳遞期間累計的錯誤總數與自動傳回處理相對於已傳送訊息的總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟<br /> </td> 
   <td> 開啟傳遞的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複點按<br /> </td> 
   <td> 點按傳遞中內容的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已取消訂閱<br /> </td> 
   <td> 對取消訂閱連結的點按次數。<br /> </td> 
  </tr> 
 </tbody> 
</table>
