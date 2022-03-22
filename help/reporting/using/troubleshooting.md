---
title: 動態報告疑難解答
description: 在此處查找與動態報告相關的常見問題。
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 5%

---

# 疑難排解{#troubleshooting}

您可以在本節中找到與動態報告相關的常見問題。

## 對於「唯一」(Unique)開啟和「唯一」(Unique)按一下，聚合行中的計數與單個行中的計數不匹配 {#unique-open-clicks-no-match}

這是預期行為。
我們可以舉下例來解釋此行為。

向配置檔案P1和P2發送電子郵件。

P1在第一天開啟兩次電子郵件，然後在第二天開啟三次。

但是，P2在第一天開啟一次電子郵件，之後幾天不再重新開啟。
以下是配置檔案與已發送電子郵件交互的直觀表示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>開啟的郵件</strong> <br /> </th> 
   <th align="center"> <strong>唯一開啟</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> 第1天<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> 第2天<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

要瞭解唯一開啟的總數，我們需要總結 **[!UICONTROL Unique Opens]** 它給了我們值3。 但是，由於電子郵件只針對2個配置檔案，因此「開啟」率應顯示150%。

要獲得的百分比不高於100，請定義 **[!UICONTROL Unique Opens]** 保持為已開啟的唯一廣播數。 在這種情況下，即使P1在第1天和第2天開啟電子郵件，其唯一開啟時間仍為1。

這將生成下表：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>開啟的郵件</strong> <br /> </th> 
   <th align="center"> <strong>唯一開啟</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong> Day </strong><br /> </td> 
   <td align="center"> <strong> 6 </strong><br /> </td> 
   <td align="center"> <strong> 2</strong><br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 第1天<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 第2天<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>唯一計數基於基於HLL的草圖，這可能在大計數時造成輕微的不準確。

## 開啟計數與資料庫計數不匹配 {#open-counts-no-match-database}

這可能是因為，在動態報告中使用啟發式方法來跟蹤，即使我們無法跟蹤 **[!UICONTROL Open]** 操作。

例如，如果用戶在其客戶端上禁用了映像，並按一下電子郵件中的連結，則 **[!UICONTROL Open]** 資料庫可能無法跟蹤，但 **[!UICONTROL Click]** 。

因此， **[!UICONTROL Open]** 跟蹤日誌計數在資料庫中可能不具有相同計數。

此類事件將添加為 **&quot;按一下電子郵件意味著開啟電子郵件&quot;**。

>[!NOTE]
>
>由於唯一計數基於基於HLL的草繪，因此可以經歷計數之間的細微不一致。

## 如何計算經常性/事務性交貨的計數？ {#counts-recurring-deliveries}

處理定期交貨和事務處理交貨時，計數將同時歸屬於父交貨和子交貨。
我們可以舉一個名為 **R1** 設定為在第1天(RC1)、第2天(RC2)和第3天(RC3)運行。
假設只有一個人多次開啟所有交貨的子件。 在這種情況下，單個循環子交貨將顯示 **[!UICONTROL Open]** 每人數為1。
但是，由於同一人按一下了所有交貨，因此父定期交貨也 **[!UICONTROL Unique open]** 。

報告應如下所示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>傳送</strong> <br /> </th> 
   <th align="center"> <strong>已發送</strong> <br /> </th> 
   <th align="center"> <strong>已交付</strong> <br /> </th>
   <th align="center"> <strong>開啟的郵件</strong> <br /> </th> 
   <th align="center"> <strong>唯一開啟</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1</strong><br/> </td> 
   <td align="center"> <strong>100</strong><br/> </td> 
   <td align="center"> <strong>90</strong><br/> </td> 
   <td align="center"> <strong>10</strong><br/> </td> 
   <td align="center"> <strong>3</strong><br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 這些顏色在我的報告表中的含義是什麼？ {#reports-color-signification}

報告中顯示的顏色是隨機的，無法個性化。 它們代表一個進度條，並會顯示它們，以幫助您更好地突出顯示報告中達到的最大值。

在下面的示例中，單元格的顏色相同，因為其值為100%。

![](assets/troubleshooting_1.png)

如果更改 **[!UICONTROL Conditional formatting]** 自定義時，當值達到上限時，單元格將變得更綠。 而如果達到下限，就會變紅。

例如，我們在 **[!UICONTROL Upper limit]** 到500和 **[!UICONTROL Lower limit]** 到0。

![](assets/troubleshooting_2.png)

## 為什麼值N/A出現在我的報告中？

![](assets/troubleshooting_3.png)

值 **不適用** 有時會出現在動態報告中。 這可以顯示，原因有三：

* 已刪除交貨，此處顯示為 **不適用** 不會造成結果的差異。
* 拖放 **[!UICONTROL Transactional Delivery]** 維，值 **不適用** 可能會出現。 這是因為即使動態報告不是事務性的，也會提取每個傳遞。 當拖放 **[!UICONTROL Delivery]** 維，但在本例中， **不適用** 值將表示事務性交貨。
* 當維與與維無關的度量一起使用時。 在下面的示例中，將分類與 **[!UICONTROL Tracking URL]** 維度 **[!UICONTROL Click]** 計數在此交貨中設定為0。

   ![](assets/troubleshooting_4.png)

