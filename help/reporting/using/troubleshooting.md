---
title: 疑難排解
description: 在這裡尋找與動態報表相關的常見問題。
page-status-flag: 從未激活
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: 班多
products: SG_CAMPAIGN/STANDARD
audience: 報告
content-type: 參考
topic-tags: 疑難排解
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 疑難排解{#troubleshooting}

您可在本節中找到與動態報表相關的常見問題。

## 對於「唯一」開啟和「唯一」點按，匯整列中的計數與個別列中的計數不符 {#unique-open-clicks-no-match}

這是預期的行為。
我們可以以下例子來解釋此行為。

電子郵件會傳送至描述檔P1和P2。

P1會在第一天開啟兩次電子郵件，然後在第二天開啟三次。

但是，P2會在第一天開啟一次電子郵件，而不會在後幾天重新開啟。
以下是描述檔與已傳送電子郵件互動的視覺化呈現：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong><br /> </th> 
   <th align="center"> <strong>開啟的郵件</strong> <br /> </th> 
   <th align="center"> <strong>唯一開啟次數</strong><br /> </th> 
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

若要瞭解唯一開啟的總數，我們需要總結其列數， **[!UICONTROL Unique Opens]** 其中會提供值3。 但是，由於電子郵件的目標僅為2個設定檔，因此開放率應顯示150%。

為了不獲得高於100的百分比，定義 **[!UICONTROL Unique Opens]** 將保持為開啟的唯一廣播的數量。 在此情況下，即使P1在第1天和第2天開啟電子郵件，其唯一開啟次數仍為1。

這將產生下表：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong><br /> </th> 
   <th align="center"> <strong>開啟的郵件</strong> <br /> </th> 
   <th align="center"> <strong>唯一開啟次數</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> 第1天<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 第2天<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>唯一計數是以HLL為基礎的草圖為基礎，這可能會在大計數時造成輕微的錯誤。

## 開啟計數與資料庫計數不匹配 {#open-counts-no-match-database}

這可能是因為，即使我們無法追蹤動作，動態報表中也會使用啟發式來追蹤開 **[!UICONTROL Open]** 啟。

例如，如果使用者在其用戶端上停用影像，然後按一下電子郵件中的連結，則資料庫 **[!UICONTROL Open]** 可能不會追蹤影像，但會 **[!UICONTROL Click]** 追蹤。

因此，追 **[!UICONTROL Open]** 蹤記錄計數在資料庫中可能沒有相同的計數。

此類事件會新增為 **「電子郵件點按表示電子郵件開啟」**。

>[!NOTE]
>
>由於唯一計數是以HLL為基礎的草圖為基礎，因此可體驗計數之間細微的不一致。

## 如何計算循環／交易傳送的計數？

使用循環傳送和交易傳送時，計數會歸因於父傳送和子傳送。

我們可以舉一個名為 **R1** set的循環傳送的示例，該傳送設定為每天在第1天(RC1)、第2天(RC2)和第3天(RC3)運行。

假設只有一個人多次開啟所有子交貨。 在這種情況下，個別循環子傳送會將每個 **[!UICONTROL Open]** 的計數顯示為1。

但是，由於同一人點按了所有傳送，因此父循環傳送也會有 **[!UICONTROL Unique open]** 1個。

在Adobe Campaign Standard 19.2.1發行後，「獨特」計數的定義會從「與傳送互動的獨特人數 **」變更為「互** 動的獨特訊息數」 ********。

在Adobe Campaign Standard 19.2.1發行之前，報表外觀如下：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>傳送</strong><br /> </th> 
   <th align="center"> <strong>已傳送</strong><br /> </th> 
   <th align="center"> <strong>交付</strong><br /> </th>
   <th align="center"> <strong>開啟的郵件</strong> <br /> </th> 
   <th align="center"> <strong>唯一開啟次數</strong><br /> </th>
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

在Adobe Campaign Standard 19.2.1發行後，報表外觀如下：

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>傳送</strong><br /> </th> 
   <th align="center"> <strong>已傳送</strong><br /> </th> 
   <th align="center"> <strong>交付</strong><br /> </th>
   <th align="center"> <strong>開啟的郵件</strong> <br /> </th> 
   <th align="center"> <strong>唯一開啟次數</strong><br /> </th>
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

## 顏色在我的報告表裡有什麼意義？ {#reports-color-signification}

報表上顯示的顏色是隨機的，無法個人化。 它們代表進度列，並會顯示，以協助您更好地反白標示報表中達到的最大值。

在以下範例中，儲存格的顏色相同，因為其值是100%。

![](assets/troubleshooting_1.png)

如果您變更為 **[!UICONTROL Conditional formatting]** 自訂，當值達到上限時，儲存格會變得更綠。 然而，如果達到下限，就會變紅。

例如，我們在這裡將 **[!UICONTROL Upper limit]** 值設為500和**[!UICONTROL Lower limit**] 0。

![](assets/troubleshooting_2.png)

## 為什麼值N/A會出現在我的報表中？

![](assets/troubleshooting_3.png)

值 **N/A** 有時候會出現在動態報表中。 這可顯示的原因有二：

* 傳送已刪除，此處顯示為 **N/A** ，不會造成結果不一致。
* 將維度拖放至 **[!UICONTROL Transactional Delivery]** 報表時，值 **N/A** 可能會因此出現。 這是因為動態報表會擷取每個傳送，即使它們不是交易性的。
此外，當將維度拖放至報表時 **[!UICONTROL Delivery]** ，也會發生此情況，但在此情況下， **** N/A值將代表交易傳送。
