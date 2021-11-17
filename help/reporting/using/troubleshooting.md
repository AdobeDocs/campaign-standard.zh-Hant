---
title: 疑難排解
description: 請在這裡找到與動態報告相關的常見問題。
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 5%

---

# 疑難排解{#troubleshooting}

您可在本節中找到與動態報告相關的常見問題。

## 對於「不重複」開啟和「不重複」點按，匯總列中的計數不會與個別列中的計數相符 {#unique-open-clicks-no-match}

這是預期中的行為。
我們可以舉下列範例來解釋此行為。

會傳送電子郵件至設定檔P1和P2。

P1在第一天開啟電子郵件兩次，第二天開啟三次。

然而，P2會在第一天開啟電子郵件一次，並且不會在後幾天重新開啟。
以下是設定檔與已傳送電子郵件互動的視覺表示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>開啟的郵件</strong> <br /> </th> 
   <th align="center"> <strong>不重複開啟次數</strong> <br /> </th> 
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

若要了解不重複開啟的總數，我們需要加總 **[!UICONTROL Unique Opens]** 這給了我們3的價值。 但由於電子郵件的目標僅為2個設定檔，因此開放率應會顯示150%。

若要取得高於100的百分比，請定義 **[!UICONTROL Unique Opens]** 維護為已開啟的不重複broadlog數。 在此情況下，即使P1在第1天和第2天開啟電子郵件，其唯一開啟次數仍會是1。

這會產生下表：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>開啟的郵件</strong> <br /> </th> 
   <th align="center"> <strong>不重複開啟次數</strong> <br /> </th> 
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
>唯一計數是以HLL型草圖為基礎，這可能在大計數時造成輕微的不準確。

## 開啟計數與資料庫計數不匹配 {#open-counts-no-match-database}

這可能是因為，即使無法追蹤 **[!UICONTROL Open]** 動作。

例如，如果使用者在其用戶端上停用影像，然後按一下電子郵件中的連結，便會 **[!UICONTROL Open]** 可能不會由資料庫追蹤，但 **[!UICONTROL Click]** 。

因此， **[!UICONTROL Open]** 追蹤記錄計數在資料庫中可能沒有相同的計數。

這些發生次數會新增為 **「電子郵件點按表示電子郵件開啟」**.

>[!NOTE]
>
>由於唯一計數是以HLL型草圖為基礎，因此可能會發生計數之間的細微不一致。

## 如何計算循環/交易式傳送的計數？ {#counts-recurring-deliveries}

使用循環和交易式傳送時，計數會歸因於父傳送和子傳送。
我們可以以循環傳送的範例，命名為 **R1** 設為在第1天(RC1)、第2天(RC2)和第3天(RC3)執行。
假設只有一個人開啟了所有子傳遞多次。 在此情況下，個別循環的子傳送會顯示 **[!UICONTROL Open]** 每個計為1。
不過，由於同一人已點按所有傳送，因此父重複傳送也會 **[!UICONTROL Unique open]** 作為1。

報表應如下所示：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>傳送</strong> <br /> </th> 
   <th align="center"> <strong>已傳送</strong> <br /> </th> 
   <th align="center"> <strong>傳遞</strong> <br /> </th>
   <th align="center"> <strong>開啟的郵件</strong> <br /> </th> 
   <th align="center"> <strong>不重複開啟次數</strong> <br /> </th>
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

## 這些顏色在我的報告表中有什麼意義？ {#reports-color-signification}

報表上顯示的顏色是隨機的，無法個人化。 它們代表進度列，可協助您更清楚標示報表中達到的最大值。

在以下範例中，儲存格的顏色相同，因為其值為100%。

![](assets/troubleshooting_1.png)

如果您變更 **[!UICONTROL Conditional formatting]** 若設為自訂，當值達到上限時，儲存格就會更綠。 而如果達到下限，就會變紅。

例如，在此，我們設定 **[!UICONTROL Upper limit]** 到500和 **[!UICONTROL Lower limit]** 0。

![](assets/troubleshooting_2.png)

## 為什麼值N/A會出現在我的報表中？

![](assets/troubleshooting_3.png)

值 **不適用** 有時會顯示在動態報表中。 顯示此畫面的原因有三：

* 傳送已刪除，如下所示 **不適用** 不會造成結果不一致。
* 拖放 **[!UICONTROL Transactional Delivery]** 維度，值 **不適用** 可能會隨之顯示。 這是因為動態報表會擷取每個傳送，即使它們不是交易式傳送亦然。 拖放 **[!UICONTROL Delivery]** 維度，但在此情況下， **不適用** 值代表交易式傳送。
* 維度與與維度無關的量度搭配使用時。 在以下範例中，會新增劃分，並搭配 **[!UICONTROL Tracking URL]** 維度，即使 **[!UICONTROL Click]** 此傳送中的計數設為0。

   ![](assets/troubleshooting_4.png)

