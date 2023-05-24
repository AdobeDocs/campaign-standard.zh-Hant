---
title: Analytics 中的 Campaign 維度和量度
description: 瞭解您在Adobe Analytics可以找到的不同維度，以開始跟蹤您從Adobe Campaign發送的電子郵件。
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
ht-degree: 8%

---

# Analytics 中的 Campaign 維度和量度{#campaign-dimensions-and-metrics-in-analytics}

Adobe Campaign和Adobe Analytics的整合使您能夠直接在Adobe Analytics跟蹤您電子郵件發送的成功。

活動 **[!UICONTROL dimensions]** 在分析中找到，如下所示：

<table> 
 <thead> 
  <tr> 
   <th> 維度<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 行銷活動 ID<br /> </td> 
   <td> 市場活動中看到的市場活動的內部名稱<br /> </td> 
  </tr> 
  <tr> 
   <td> 市場活動標籤<br /> </td> 
   <td> 市場活動中看到的市場活動標籤<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞 ID<br /> </td> 
   <td> 「活動」中顯示的交貨的內部名稱。<br /> 例如，DM1是計畫每週發送子交貨的定期交貨。 DM2 、 DM3和DM4在前三週發送。 然後，「交付ID」維將顯示每個交付的結果，即DM1到DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞標籤<br /> </td> 
   <td> 市場活動中顯示的交貨標籤<br /> </td> 
  </tr> 
  <tr> 
   <td> 已執行的傳遞ID<br /> </td> 
   <td> 「活動」中顯示的交貨的內部名稱。 這僅涉及在市場活動中執行時的交付。<br /> 例如，DM1是計畫每週發送子交貨的定期交貨。 DM2 、 DM3和DM4在前三週發送。 然後，「已執行交貨ID」維將顯示已執行交貨的結果，即子交貨DM2、DM3和DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 已執行的交貨標籤<br /> </td> 
   <td> 「活動」中顯示的交貨標籤。 這僅涉及在市場活動中執行時的交付。<br /> </td> 
  </tr> 
 </tbody> 
</table>

活動 **[!UICONTROL metrics]** 在分析中找到，如下所示：

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
   <td> 在傳遞中按一下內容的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> 成功發送的消息數，與已發送的消息總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已開啟<br /> </td> 
   <td> 在傳遞中開啟消息的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳送<br /> </td> 
   <td> 交貨的發送總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 總邊界<br /> </td> 
   <td> 在傳遞和自動返回處理期間累積的與已發送消息總數有關的錯誤總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一開啟<br /> </td> 
   <td> 開啟交貨的收件人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一按一下<br /> </td> 
   <td> 按一下傳遞中內容的收件人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未訂閱<br /> </td> 
   <td> 取消訂閱連結上的按一下次數。<br /> </td> 
  </tr> 
 </tbody> 
</table>
