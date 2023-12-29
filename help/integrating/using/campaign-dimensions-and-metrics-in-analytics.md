---
title: Analytics 中的 Campaign 維度和量度
description: 瞭解您可以在Adobe Analytics中找到的不同維度，以開始從Adobe Campaign追蹤您的電子郵件傳送。
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

Adobe Campaign與Adobe Analytics整合可讓您直接在Adobe Analytics中追蹤電子郵件傳送的成功情況。

Campaign **[!UICONTROL dimensions]** 以下列出可在Analytics中找到的：

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
   <td> 在Campaign中看到的行銷活動的內部名稱<br /> </td> 
  </tr> 
  <tr> 
   <td> 行銷活動標籤<br /> </td> 
   <td> 在Campaign中看到的行銷活動標籤<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞ID<br /> </td> 
   <td> 在Campaign中看到的傳遞內部名稱。<br /> 例如，DM1是排程每週傳送子傳送的循環傳送。 DM2、DM3和DM4會在最初三週傳送。 「傳遞ID」維度接著會顯示每個傳遞的結果，即DM1到DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞標籤<br /> </td> 
   <td> 在Campaign中看到的傳遞標籤<br /> </td> 
  </tr> 
  <tr> 
   <td> 已執行的傳遞ID<br /> </td> 
   <td> 在Campaign中看到的傳遞內部名稱。 這僅涉及Campaign中的傳送執行。<br /> 例如，DM1是排程每週傳送子傳送的循環傳送。 DM2、DM3和DM4會在最初三週傳送。 「已執行的傳送ID」維度接著會顯示已執行傳送的結果，即子傳送DM2、DM3和DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 已執行的傳遞標籤<br /> </td> 
   <td> 在Campaign中看到的傳送標籤。 這僅涉及Campaign中的傳送執行。<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campaign **[!UICONTROL metrics]** 以下列出可在Analytics中找到的：

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
   <td> 成功傳送的訊息數（與已傳送訊息總數相關）。<br /> </td> 
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
   <td> 與已傳送訊息總數相關的傳遞和自動回訪處理期間累計的錯誤總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟<br /> </td> 
   <td> 開啟傳遞的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複點按<br /> </td> 
   <td> 在傳遞中點按內容的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已取消訂閱<br /> </td> 
   <td> 對取消訂閱連結的點按次數。<br /> </td> 
  </tr> 
 </tbody> 
</table>
