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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
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

若要了解不重複開啟的總數，我們需要加總&#x200B;**[!UICONTROL Unique Opens]**&#x200B;的列計數，這會給我們提供值3。 但由於電子郵件的目標僅為2個設定檔，因此開放率應會顯示150%。

若要取得高於100的百分比，**[!UICONTROL Unique Opens]**&#x200B;的定義會維持為已開啟的唯一廣播數量。 在此情況下，即使P1在第1天和第2天開啟電子郵件，其唯一開啟次數仍會是1。

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
   <td align="center"> <strong> 6  </strong><br /> </td> 
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

這可能是因為，即使無法追蹤&#x200B;**[!UICONTROL Open]**&#x200B;動作，動態報告中仍會使用試探式來追蹤開啟次數。

例如，如果用戶在其客戶端上禁用了映像，並按一下電子郵件中的連結，則資料庫可能不會跟蹤&#x200B;**[!UICONTROL Open]**，但&#x200B;**[!UICONTROL Click]**&#x200B;將被跟蹤。

因此，**[!UICONTROL Open]**&#x200B;追蹤記錄計數在資料庫中可能沒有相同的計數。

這些發生次數會新增為&#x200B;**&quot;電子郵件點按表示電子郵件開啟&quot;**。

>[!NOTE]
>
>由於唯一計數是以HLL型草圖為基礎，因此可能會發生計數之間的微小不一致。

## 如何計算循環/交易式傳送的計數？ {#counts-recurring-deliveries}

使用循環和交易式傳送時，計數會歸因於父傳送和子傳送。
我們可以以名為**R1**的循環傳送為例，其設定為每天在第1天(RC1)、第2天(RC2)和第3天(RC3)執行。
假設只有一個人開啟了所有子傳遞多次。 在此情況下，個別循環子傳送會將每個的**[!UICONTROL Open]**計為1。
不過，由於同一人已點按所有傳送，父循環傳送也會將**[!UICONTROL Unique open]**&#x200B;設為1。

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

如果您將&#x200B;**[!UICONTROL Conditional formatting]**&#x200B;變更為自訂，當值達到上限時，儲存格就會更綠。 而如果達到下限，就會變紅。

例如，在此，我們將&#x200B;**[!UICONTROL Upper limit]**&#x200B;設為500，並將&#x200B;**[!UICONTROL Lower limit]**&#x200B;設為0。

![](assets/troubleshooting_2.png)

## 為什麼值N/A會出現在我的報表中？

![](assets/troubleshooting_3.png)

值&#x200B;**N/A**&#x200B;有時可能出現在動態報表中。 顯示此畫面的原因有三：

* 傳送已刪除，並在此顯示為&#x200B;**N/A**，以避免結果不一致。
* 將&#x200B;**[!UICONTROL Transactional Delivery]**&#x200B;維度拖放至報表時，可能會因此顯示值&#x200B;**N/A**。 這是因為動態報表會擷取每個傳送，即使它們不是交易式傳送亦然。 將&#x200B;**[!UICONTROL Delivery]**&#x200B;維度拖放至報表時，也可能發生此情況，但在此情況下，**N/A**&#x200B;值將代表交易式傳送。
* 維度與與維度無關的量度搭配使用時。 在以下範例中，即使此傳送中的&#x200B;**[!UICONTROL Click]**&#x200B;計數設為0，仍會以&#x200B;**[!UICONTROL Tracking URL]**&#x200B;維度新增劃分。

   ![](assets/troubleshooting_4.png)

