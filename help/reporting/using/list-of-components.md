---
title: 元件清單
description: 您可以在這裡找到每個可用元件的清單，     動態報告及其定義。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 8980bf05-60a8-4360-a354-445e1faeb5b2
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 0%

---

# 元件清單 {#list-of-components}

若要進一步瞭解維度與量度之間的相容性，請參閱此[表格](/help/reporting/using/assets/dynamic_report_compatibility.pdf)。 如果兩個元件不相容，儲存格會顯示值&#x200B;**無**。

[![影像](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf)

## 維度 {#dimensions}

下表列出報表中使用的維度及其定義。

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 瀏覽器<br /> </td> 
   <td> 開啟或點選訊息的瀏覽器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 行銷活動<br /> </td> 
   <td> 行銷活動的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 城市<br /> </td> 
   <td> 在收件者設定檔中註冊的城市。<br /> </td> 
  </tr> 
  <tr> 
   <td> 國家/地區<br /> </td> 
   <td> 在收件者設定檔中註冊的國家/地區。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞<br /> </td> 
   <td> 傳遞的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 裝置<br /> </td> 
   <td> 電子郵件/簡訊/推播通知開啟/檢視/點按的裝置。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失敗原因<br /> </td> 
   <td> 造成每個傳遞跳出的錯誤型別，例如使用者不明、無效的網域或信箱已滿。<br /> </td> 
  </tr> 
  <tr> 
   <td> 性別<br /> </td> 
   <td> 收件者的性別，例如男性或女性。 如果收件者設定檔中的性別欄位為空，則值將為無。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內訊息動作<br /> </td> 
   <td> 已傳遞應用程式內訊息的動作，例如按鈕1或2的動作或解除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息型別<br /> </td> 
   <td> 用於傳遞的頻道，例如電子郵件、簡訊、推播通知或應用程式內。<br /> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式名稱<br /> </td> 
   <td> 行動應用程式的名稱<br /> </td> 
  </tr> 
  <tr> 
   <td> 平台<br /> </td> 
   <td> 開啟/檢視/點選訊息的裝置平台。<br /> </td> 
  </tr> 
  <tr> 
   <td> 設定檔<br /> </td> 
   <td> 重新分組在設定檔資源擴充期間建立的現成和自訂設定檔欄位，如需詳細資訊，請參閱此<a href="../../developing/using/key-steps-to-add-a-resource.md">頁面</a>或此<a href="../../reporting/using/creating-a-custom-profile-dimension.md">範例</a>。<br />請注意，當連結至設定檔欄位的自訂資源發佈後，就會擷取此維度的資料。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播平台<br /> </td> 
   <td> 開啟推播通知的裝置平台，例如iOS或Android。<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件者網域<br /> </td> 
   <td> 用來開啟電子郵件的網域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 循環傳遞<br /> </td> 
   <td> 重複傳遞的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 寄件者網域<br /> </td> 
   <td> 用來傳送電子郵件的網域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 寄件者IP<br /> </td> 
   <td> 用來傳送電子郵件的IP。<br /> </td> 
  </tr> 
  <tr> 
   <td> 狀態<br /> </td> 
   <td> 在收件者設定檔中登入的狀態。<br /> </td> 
  </tr> 
  <tr> 
   <td> 追蹤URL<br /> </td> 
   <td> 使用者從訊息點按的URL。<br /> </td> 
  </tr> 
  <tr> 
   <td> 追蹤URL類別<br /> </td> 
   <td> 指派給追蹤URL的類別。<br /> </td> 
  </tr> 
  <tr> 
   <td> 追蹤URL標籤<br /> </td> 
   <td> 指定給URL的標籤，例如映象頁面、聯絡我們或開啟。<br /> </td> 
  </tr> 
  <tr> 
   <td> 異動傳遞<br /> </td> 
   <td> 異動傳遞的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 變體<br /> </td> 
   <td> A/B測試時的電子郵件變體。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 量度 {#metrics}

下表提供報表中使用的量度清單，以及量度定義（視傳送型別而定）。

### 電子郵件和簡訊量度 {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 在封鎖清單<br />上 </td> 
   <td> 已將電子郵件宣告為垃圾郵件或垃圾郵件的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 封鎖清單速率<br /> </td> 
   <td> 封鎖清單上標籤的傳遞百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回+錯誤<br /> </td> 
   <td> 傳遞期間累計的錯誤總數與自動傳回處理相對於已傳送訊息的總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回+錯誤率<br /> </td> 
   <td> 與已傳送的電子郵件相比退回的電子郵件百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> 內容在傳遞中被點按的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> 傳遞中的點按百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> 成功傳送的訊息數，與已傳送的訊息總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞率<br /> </td> 
   <td> 已成功傳送的訊息百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬退回<br /> </td> 
   <td> 永久錯誤總數，例如錯誤的電子郵件地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬跳出率<br /> </td> 
   <td> 因永久錯誤而失敗的傳遞百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 映象頁面<br /> </td> 
   <td> 點按映象頁面連結的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 映象頁面速率<br /> </td> 
   <td> 與傳遞訊息總數相較之下，映象頁面連結的點按百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠點按<br /> </td> 
   <td> 在傳遞中點按優惠方案的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 選件點按率<br /> </td> 
   <td> 對優惠的點按百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> 訊息在傳遞中開啟的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟率<br /> </td> 
   <td> 已開啟郵件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/傳送<br /> </td> 
   <td> 傳遞的傳送總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔離<br /> </td> 
   <td> 退回並導致地址隔離的郵件數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔離率<br /> </td> 
   <td> 與已傳送訊息比較的隔離百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已拒絕<br /> </td> 
   <td> SMTP伺服器分類為垃圾郵件的郵件數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 拒絕率<br /> </td> 
   <td> 標籤為已拒絕的郵件百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 軟退信<br /> </td> 
   <td> 暫存錯誤總數，例如完整的收件匣。<br /> </td> 
  </tr> 
  <tr> 
   <td> 軟跳出率<br /> </td> 
   <td> 因暫時原因而失敗的傳遞百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複點按<br /> </td> 
   <td> 點按傳遞中內容的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟<br /> </td> 
   <td> 開啟傳遞的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一取消訂閱<br /> </td> 
   <td> 點按取消訂閱連結的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱率<br /> </td> 
   <td> 與傳遞的訊息相較之下的唯一取消訂閱數目。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已取消訂閱<br /> </td> 
   <td> 對取消訂閱連結的點按次數。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 推播通知量度 {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 退回+錯誤<br /> </td> 
   <td> 傳遞期間累計的錯誤總數與已傳送訊息的總數相關，例如來自MCPNS或提供者的錯誤。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回+錯誤率<br /> </td> 
   <td> 與已傳送的推播通知相比退回的推播通知百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> 推播通知已傳送至裝置並由使用者點按的次數。 使用者想要檢視通知（該通知隨後將移至推播開啟追蹤），或將其關閉。<br /> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> 與推播通知互動的使用者百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> 成功傳送的推播通知數目，與已傳送的推播通知總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞率<br /> </td> 
   <td> 已成功傳送的推播通知百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 曝光次數<br /> </td> 
   <td> 推播通知已傳送至裝置並在通知中心保持未觸及的次數。 在大多數情況下，曝光次數應該與傳送的數目類似。 這樣可確保裝置收到訊息，並將該資訊轉送回伺服器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/傳送<br /> </td> 
   <td> 已傳送的推播通知總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> 傳遞到裝置且使用者因此開啟應用程式而點按的推播通知總數。 這類似於「推送點按」，但如果通知已關閉，則不會觸發「推送開啟」。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟率<br /> </td> 
   <td> 已開啟推播通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複點按<br /> </td> 
   <td> 不重複使用者與推播通知互動的次數，例如點選通知或按鈕。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複曝光次數<br /> </td> 
   <td> 收件者的曝光次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟<br /> </td> 
   <td> 開啟傳遞的收件者人數。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 應用程式內量度 {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> 服務提供者傳遞到裝置的應用程式內訊息總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 曝光次數<br /> </td> 
   <td> 根據是否符合觸發條件，收件者看到的應用程式內訊息總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內點按<br /> </td> 
   <td> 按一下Button 1或Button 2的收件者總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內點進率<br /> </td> 
   <td> 與看到訊息的使用者相比，按一下「按鈕1」或「按鈕2」的使用者百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解除<br /> </td> 
   <td> 收件者按一下關閉按鈕或自動解除所解除的訊息總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解僱率<br /> </td> 
   <td> 收件者已解除的應用程式內訊息百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/傳送<br /> </td> 
   <td> 在傳遞傳送程式中，從Adobe Campaign傳送的應用程式內訊息總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複曝光次數<br /> </td> 
   <td> 不重複收件者的曝光次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複的應用程式內點按<br /> </td> 
   <td> 收件者點選按鈕1或按鈕2的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複應用程式內解除服務<br /> </td> 
   <td> 收件者解除應用程式內訊息的次數。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 區段 {#segments}

下表提供報告中使用的區段清單及其定義。

<table> 
 <thead> 
  <tr> 
   <th> 區段<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 年齡：嬰兒潮一代1<br /> </td> 
   <td> 1946年至1954年出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：嬰兒潮一代2<br /> </td> 
   <td> 1955年至1965年出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從18到25<br /> </td> 
   <td> 18到25歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從26到30<br /> </td> 
   <td> 26到30歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從31到40<br /> </td> 
   <td> 31到40歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從41到50<br /> </td> 
   <td> 41到50歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：層代X<br /> </td> 
   <td> 1966年至1976年出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：第Y代（千禧一代）<br /> </td> 
   <td> 1977年至1994年出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：層代Z<br /> </td> 
   <td> 1995年至今天出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：大於50<br /> </td> 
   <td> 年齡超過50歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：小於25<br /> </td> 
   <td> 年齡小於25歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：小於30<br /> </td> 
   <td> 年齡小於30歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：小於40<br /> </td> 
   <td> 年齡小於40歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：小於50<br /> </td> 
   <td> 年齡小於50歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：靜音產生<br /> </td> 
   <td> 在1945年或之前出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 所有造訪<br /> </td> 
   <td> 每個收件者<br /> </td> 
  </tr>
 </tbody> 
</table>
