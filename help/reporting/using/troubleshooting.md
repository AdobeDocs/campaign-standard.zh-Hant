---
title: 疑難排解
seo-title: 疑難排解
description: 疑難排解
seo-description: 在這裡尋找與動態報表相關的常見問題。
page-status-flag: 從未啓動
uuid: a84a18bd-4e33-466e-a6 ce-d7008 fe12746
contentOwner: benst
products: SG_ CAMPAIGN/STANDARD
audience: 報告功能
content-type: reference
topic-tags: 疑難排解
discoiquuid: bbb41c38-10c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e0cbdfecde495d7c9f8bfa33dd5ee8598cdfe60a

---


# Troubleshooting{#troubleshooting}

您可以在本節中找到與動態報表相關的常見問題。

## For Unique opens and Unique clicks, the count in the aggregate row is not matching the ones in individual rows {#unique-open-clicks-no-match}

這是預期的行為。
我們可以採取下列範例來說明此行為。

電子郵件會傳送至個人檔案P和P2。

P會在第一天開啓電子郵件兩次，然後在第二天開啓樹狀結構。

而P在第一天就會開啓一次電子郵件，而不會在接下來的天數重新開啓。
以下是描述檔與傳送電子郵件互動的視覺表示法：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong><br /> </th> 
   <th align="center"> <strong>開啓次數</strong><br /> </th> 
   <th align="center"> <strong>開啓獨特</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

To understand the overall number of unique opens, we need to sum up the row counts of **[!UICONTROL Unique Opens]** which gives us the value 3. 但是，由於電子郵件僅針對個人檔案，因此Open率應顯示為15%。

To not obtain percentage higher than 100, the definition of **[!UICONTROL Unique Opens]** is maintained to be the number of unique broadlogs that were opened. 在這種情況下，即使P在第天和第天開啓電子郵件，他的獨特開啓還是1。

這樣會產生下表：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong><br /> </th> 
   <th align="center"> <strong>開啓次數</strong><br /> </th> 
   <th align="center"> <strong>開啓獨特</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>獨特計數是以HLL為基礎的素描，可能會造成大量的不準確計數。

## Open counts do not match the Database count {#open-counts-no-match-database}

This may be due to the fact that, heuristics are used in Dynamic reporting to track opens even when we can't track the **[!UICONTROL Open]** action.

For example, if a user has disabled images on their client and click on a link in the email, the **[!UICONTROL Open]** may not be tracked by the database but the **[!UICONTROL Click]** will.

Therefore, the **[!UICONTROL Open]** tracking logs counts may not have the same count in the database.

Such occurrences are added as **"an email click implies an email open"**.

>[!NOTE]
>
>由於獨特計數是以HLL為基礎的素描，所以可以體驗計數之間的次要不一致。

## 計算循環/交易傳遞的計數如何計算？

使用循環和交易傳遞時，計數會歸屬於父項和子傳送。

We can take the example of a recurring delivery named **R1** set to run every day on day 1 (RC1), day 2 (RC2) and day 3 (RC3).

假設只有一個人會多次開啓所有的子傳送。In this case, the individual recurring child deliveries will show the **[!UICONTROL Open]** count as 1 for each.

However, since the same person clicked on all the deliveries, the parent recurring delivery will also have **[!UICONTROL Unique open]** as 1.

After the Adobe Campaign Standard 19.2.1 release, the definition of **Unique counts** is changed from **Number of unique persons interacting with the delivery** to **Number of unique messages interacted**.

在Adobe Campaign Standard19.2.1發行前，報表外觀如下：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>發送內容</strong><br /> </th> 
   <th align="center"> <strong>已傳送</strong><br /> </th> 
   <th align="center"> <strong>遞送內容</strong><br /> </th>
   <th align="center"> <strong>開啓次數</strong><br /> </th> 
   <th align="center"> <strong>開啓獨特</strong><br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>1<br/> </td> 
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

在Adobe Campaign Standard19.2.1發行後，報表外觀如下：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>發送內容</strong><br /> </th> 
   <th align="center"> <strong>已傳送</strong><br /> </th> 
   <th align="center"> <strong>遞送內容</strong><br /> </th>
   <th align="center"> <strong>開啓次數</strong><br /> </th> 
   <th align="center"> <strong>開啓獨特</strong><br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>3<br/> </td> 
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

## What is the colors' signification in my reports' table? {#reports-color-signification}

報表中顯示的顏色是randomized的，無法個人化。它們代表進度列並顯示，以協助您更好地反白顯示報表中所達到的最大值。

在下列範例中，儲存格的色彩相同，因為其值為100%。

![](assets/troubleshooting_1.png)

If you change the **Conditional formatting** to custom, when the value reaches the upper limit the cell will get greener. 而如果它達到較低的限制，則會變得更密文。

For example, here, we set the **Upper limit** to 500 and **Lower limit** to 0.

![](assets/troubleshooting_2.png)