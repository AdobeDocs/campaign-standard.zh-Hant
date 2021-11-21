---
title: '元件清單 '
description: 在此處找到動態報表中可用的每個元件清單及其定義。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 8980bf05-60a8-4360-a354-445e1faeb5b2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 1%

---

# 元件清單 {#list-of-components}

若要進一步了解維度與量度之間的相容性，請參閱 [表格](/help/reporting/using/assets/dynamic_report_compatibility.pdf). 如果兩個元件不相容，儲存格會顯示值 **無**.

[![影像](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

## Dimension {#dimensions}

下表提供報表中使用的維度清單及其定義。

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
   <td> 開啟或點按訊息的瀏覽器。<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign<br /> </td> 
   <td> 行銷活動的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 城市<br /> </td> 
   <td> 收件者設定檔中註冊的城市。<br /> </td> 
  </tr> 
  <tr> 
   <td> 國家/地區<br /> </td> 
   <td> 收件者設定檔中註冊的國家/地區。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞<br /> </td> 
   <td> 傳送的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 裝置<br /> </td> 
   <td> 開啟/檢視/點按電子郵件/簡訊/推播通知的裝置。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失敗原因<br /> </td> 
   <td> 導致每個傳送彈回的錯誤類型，例如使用者未知、無效網域或信箱已滿。<br /> </td> 
  </tr> 
  <tr> 
   <td> 性別<br /> </td> 
   <td> 接受者的性別，如男性或女性。 如果收件者設定檔中的性別欄位空白，則值將為「無」。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內訊息動作<br /> </td> 
   <td> 傳遞之應用程式內訊息的動作，例如按鈕1或2的動作或解除的動作。<br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息類型<br /> </td> 
   <td> 用於傳送的通道，例如電子郵件、簡訊、推播通知或應用程式內。<br /> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式名稱<br /> </td> 
   <td> 行動應用程式的名稱<br /> </td> 
  </tr> 
  <tr> 
   <td> 平台<br /> </td> 
   <td> 開啟/檢視/點按訊息的裝置平台。<br /> </td> 
  </tr> 
  <tr> 
   <td> 設定檔<br /> </td> 
   <td> 重新分組設定檔資源擴充期間建立的現成可用和自訂設定檔欄位，如需詳細資訊，請參閱 <a href="../../developing/using/key-steps-to-add-a-resource.md">頁面</a> 或 <a href="../../reporting/using/creating-a-custom-profile-dimension.md">範例</a>.<br /> 請注意，當連結至設定檔欄位的自訂資源發佈時，就會擷取此維度的資料。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播平台<br /> </td> 
   <td> 從中開啟推播通知的裝置平台，例如iOS或Android。<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件者網域<br /> </td> 
   <td> 用於開啟電子郵件的網域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 重複傳送<br /> </td> 
   <td> 循環傳送的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 寄件者網域<br /> </td> 
   <td> 用於傳送電子郵件的網域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 發件人IP<br /> </td> 
   <td> 用於傳送電子郵件的IP。<br /> </td> 
  </tr> 
  <tr> 
   <td> 狀態<br /> </td> 
   <td> 在收件者設定檔中註冊的狀態。<br /> </td> 
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
   <td> 為URL指定的標籤（例如鏡像頁面），請聯絡我們或開啟。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易式傳送<br /> </td> 
   <td> 交易式傳送的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 變體<br /> </td> 
   <td> A/B測試時的電子郵件變體。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 量度 {#metrics}

下表提供報表中使用的量度清單及其定義（視傳送類型而定）。

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
   <td> 封鎖清單上<br /> </td> 
   <td> 宣告電子郵件為垃圾郵件或垃圾郵件的收件人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 封鎖率<br /> </td> 
   <td> 封鎖清單上標示的傳送百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跳出數+錯誤<br /> </td> 
   <td> 傳送和自動回傳處理期間累積的錯誤總數，與已傳送訊息的總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 反彈+錯誤率<br /> </td> 
   <td> 跳出的電子郵件與已傳送的電子郵件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> 內容在傳送中被點按的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> 傳送中的點按百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞<br /> </td> 
   <td> 已成功傳送的訊息數，與已傳送的訊息總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交貨率<br /> </td> 
   <td> 已成功發送的消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬跳出<br /> </td> 
   <td> 永久錯誤的總數，例如錯誤的電子郵件地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬跳出率<br /> </td> 
   <td> 因永久錯誤而失敗的傳送百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 鏡像頁面<br /> </td> 
   <td> 按一下鏡像頁面連結的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 鏡像頁面速率<br /> </td> 
   <td> 鏡像頁面連結上的點按次數與傳送訊息總數的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 選件點按次數<br /> </td> 
   <td> 傳送中點按選件的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 選件點按率<br /> </td> 
   <td> 選件的點按百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> 傳送中開啟訊息的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開放率<br /> </td> 
   <td> 已開啟郵件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/已傳送<br /> </td> 
   <td> 傳送的傳送總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔離<br /> </td> 
   <td> 退信並導致地址隔離的郵件數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔離率<br /> </td> 
   <td> 隔離與已傳送訊息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已拒絕<br /> </td> 
   <td> 被SMTP伺服器分類為垃圾郵件的郵件數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 拒絕率<br /> </td> 
   <td> 標籤為已拒絕的郵件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 軟跳出<br /> </td> 
   <td> 臨時錯誤（如完整收件箱）的總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 軟跳出率<br /> </td> 
   <td> 因暫時原因而失敗的傳送百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複點按<br /> </td> 
   <td> 按一下傳遞內容的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟次數<br /> </td> 
   <td> 開啟傳遞的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一取消訂閱<br /> </td> 
   <td> 按一下取消訂閱連結的收件者人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱率<br /> </td> 
   <td> 與已傳送的訊息相比，不重複取消訂閱的數量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已取消訂閱<br /> </td> 
   <td> 取消訂閱連結的點按次數。<br /> </td> 
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
   <td> 跳出數+錯誤<br /> </td> 
   <td> 傳送期間累積的與已傳送訊息總數相關的錯誤總數，例如來自MCPNS或提供者的錯誤。<br /> </td> 
  </tr> 
  <tr> 
   <td> 反彈+錯誤率<br /> </td> 
   <td> 跳出的推播通知與傳送的推播通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> 推播通知傳送至裝置並由使用者點按的次數。 使用者要麼想要檢視通知，然後將其移至「推播開啟」追蹤，要麼將其關閉。<br /> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> 與推播通知互動的使用者百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞<br /> </td> 
   <td> 成功傳送的推播通知數，與已傳送的推播通知總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交貨率<br /> </td> 
   <td> 成功傳送推播通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 曝光數<br /> </td> 
   <td> 推播通知已傳送至裝置且未在通知中心中動作的次數。 在大多數情況下，曝光次數應與傳送的次數類似。 這可確保設備獲取消息並將該資訊轉發回伺服器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/已傳送<br /> </td> 
   <td> 傳送的推播通知總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> 傳送至裝置並由使用者點按以開啟應用程式的推播通知總數。 這類似於推播點擊，但若關閉通知，則不會觸發推播開啟。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開放率<br /> </td> 
   <td> 已開啟推播通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複點按<br /> </td> 
   <td> 不重複使用者與推播通知互動的次數，例如點按通知或按鈕。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複曝光數<br /> </td> 
   <td> 收件者的曝光次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟次數<br /> </td> 
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
   <td> 傳遞<br /> </td> 
   <td> 服務提供者傳遞至裝置的應用程式內訊息總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 曝光數<br /> </td> 
   <td> 收件者根據是否符合觸發條件所看到的應用程式內訊息總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內點按次數 <br /> </td> 
   <td> 按一下「按鈕1」或「按鈕2」的收件者總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內點進率<br /> </td> 
   <td> 按一下「按鈕1」或「按鈕2」的使用者比例，與看到訊息的使用者比例。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解雇<br /> </td> 
   <td> 通過按一下關閉按鈕或自動關閉而關閉的郵件總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解雇率<br /> </td> 
   <td> 收件者關閉的應用程式內訊息百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/已傳送<br /> </td> 
   <td> 在傳送傳送程式中從Adobe Campaign傳送的應用程式內訊息總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複曝光數<br /> </td> 
   <td> 不重複收件者的曝光次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內不重複點按次數<br /> </td> 
   <td> 收件者點按按鈕1或按鈕2的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內不重複解雇<br /> </td> 
   <td> 收件者解除應用程式內訊息的時間。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 區段 {#segments}

下表提供報表中使用的區段清單及其定義。

<table> 
 <thead> 
  <tr> 
   <th> 區段<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 年齡：嬰兒潮1<br /> </td> 
   <td> 收件者生於1946年至1954年。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：嬰兒潮2<br /> </td> 
   <td> 收件者生於1955年至1965年。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從18到25<br /> </td> 
   <td> 18至25歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從26到30<br /> </td> 
   <td> 26至30歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從31到40<br /> </td> 
   <td> 31至40歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從41到50<br /> </td> 
   <td> 41至50歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：第X代<br /> </td> 
   <td> 收件者生於1966年至1976年。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：Y代（千禧一代）<br /> </td> 
   <td> 收件者，1977年至1994年。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：Z代<br /> </td> 
   <td> 收件者從1995年到今天。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：大於50<br /> </td> 
   <td> 年齡大於50的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於25<br /> </td> 
   <td> 年齡小於25歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於30<br /> </td> 
   <td> 年齡小於30的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於40<br /> </td> 
   <td> 年齡小於40的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於50<br /> </td> 
   <td> 年齡小於50的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：沈默的一代<br /> </td> 
   <td> 收件者生於1945年或之前。<br /> </td> 
  </tr> 
  <tr> 
   <td> 所有造訪<br /> </td> 
   <td> 每個收件者<br /> </td> 
  </tr>
 </tbody> 
</table>
