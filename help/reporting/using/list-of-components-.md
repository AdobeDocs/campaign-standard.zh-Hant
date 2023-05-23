---
title: 元件清單
description: 在此處查找動態報告中可用的每個元件的清單及其定義。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 8980bf05-60a8-4360-a354-445e1faeb5b2
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 4%

---

# 元件清單 {#list-of-components}

要瞭解有關維和度量之間相容性的詳細資訊，請參閱 [表](/help/reporting/using/assets/dynamic_report_compatibility.pdf)。 如果兩個元件不相容，單元格將顯示值 **無**。

[![影像](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf)

## 維度 {#dimensions}

下表提供了報表中使用的維清單及其定義。

<table> 
 <thead> 
  <tr> 
   <th> 維度<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 瀏覽器<br /> </td> 
   <td> 開啟或按一下消息的瀏覽器。<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign<br /> </td> 
   <td> 您活動的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 城市<br /> </td> 
   <td> 在收件人的個人資料中註冊的城市。<br /> </td> 
  </tr> 
  <tr> 
   <td> 國家/地區<br /> </td> 
   <td> 在收件人配置檔案中註冊的國家/地區。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞<br /> </td> 
   <td> 交貨的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 設備<br /> </td> 
   <td> 開啟/查看/按一下電子郵件/SMS/推送通知的設備。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失敗原因<br /> </td> 
   <td> 導致每個傳遞跳轉的錯誤類型，例如用戶未知、無效域或郵箱已滿。<br /> </td> 
  </tr> 
  <tr> 
   <td> 性別<br /> </td> 
   <td> 接受者的性別，如男性或女性。 如果收件人的配置檔案中的性別欄位為空，則該值將為無。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用內消息操作<br /> </td> 
   <td> 已傳遞的In-App消息操作，例如按鈕1或2上的操作或取消。<br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息類型<br /> </td> 
   <td> 用於傳遞的渠道，如電子郵件、簡訊、推送通知或In-App。<br /> </td> 
  </tr> 
  <tr> 
   <td> 移動應用名稱<br /> </td> 
   <td> 移動應用程式的名稱<br /> </td> 
  </tr> 
  <tr> 
   <td> 平台<br /> </td> 
   <td> 開啟/查看/按一下消息的設備的平台。<br /> </td> 
  </tr> 
  <tr> 
   <td> 設定檔<br /> </td> 
   <td> 重新分組在配置檔案資源擴展期間建立的出廠設定和自定義配置檔案欄位，有關詳細資訊，請參閱此 <a href="../../developing/using/key-steps-to-add-a-resource.md">頁</a> 或 <a href="../../reporting/using/creating-a-custom-profile-dimension.md">示例</a>。<br /> 請注意，一旦發佈連結到配置檔案欄位的自定義資源，就會立即檢索此維的資料。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播平台<br /> </td> 
   <td> 開啟推送通知的設備的平台，如iOS或Android。<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件人域<br /> </td> 
   <td> 用於開啟電子郵件的域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 重複傳送<br /> </td> 
   <td> 循環傳遞的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 發件人域<br /> </td> 
   <td> 用於發送電子郵件的域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 發件人IP<br /> </td> 
   <td> 用於發送電子郵件的IP。<br /> </td> 
  </tr> 
  <tr> 
   <td> 狀態<br /> </td> 
   <td> 在收件人配置檔案中註冊的狀態。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跟蹤URL<br /> </td> 
   <td> 用戶從消息中按一下的URL。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跟蹤URL類別<br /> </td> 
   <td> 分配給跟蹤URL的類別。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跟蹤URL標籤<br /> </td> 
   <td> 給URL的標籤（如鏡像頁）與我們聯繫或開啟。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事務性交付<br /> </td> 
   <td> 事務性傳遞的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 變體<br /> </td> 
   <td> A/B測試時電子郵件的變型。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 量度 {#metrics}

下表根據交付類型為您提供報告中使用的度量及其定義的清單。

### 電子郵件和SMS度量 {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 登錄<br /> </td> 
   <td> 已將電子郵件聲明為垃圾郵件或垃圾郵件的收件人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 登錄率<br /> </td> 
   <td> 登錄清單中標籤的交貨百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 邊界+錯誤<br /> </td> 
   <td> 在傳遞和自動返回處理期間累積的與已發送消息總數有關的錯誤總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 彈出+錯誤率<br /> </td> 
   <td> 與發送的電子郵件相比，已跳轉的電子郵件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> 在傳遞中按一下內容的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> 交貨中的點擊百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> 成功發送的消息數，與已發送的消息總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交貨率<br /> </td> 
   <td> 成功發送的郵件百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬彈<br /> </td> 
   <td> 永久錯誤（如錯誤的電子郵件地址）的總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬彈跳率<br /> </td> 
   <td> 由於永久錯誤而失敗的交貨百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 鏡像頁面<br /> </td> 
   <td> 按一下鏡像頁面連結的收件人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 鏡像頁速率<br /> </td> 
   <td> 鏡像頁面連結上的按一下與總傳遞消息相比的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 提供點擊<br /> </td> 
   <td> 在交貨中按一下要約的時間數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 服務點擊率<br /> </td> 
   <td> 服務點擊百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> 在傳遞中開啟消息的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟率<br /> </td> 
   <td> 已開啟郵件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/已發送<br /> </td> 
   <td> 交貨的發送總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔離<br /> </td> 
   <td> 已跳轉並導致地址隔離的郵件數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔離率<br /> </td> 
   <td> 與已發送郵件相比隔離的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已拒絕<br /> </td> 
   <td> 被SMTP伺服器分類為垃圾郵件的郵件數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 拒絕率<br /> </td> 
   <td> 標籤為已拒絕的郵件百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 軟彈跳<br /> </td> 
   <td> 臨時錯誤（如完整收件箱）的總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 軟彈跳率<br /> </td> 
   <td> 由於臨時原因而失敗的交貨百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> 按一下傳遞中內容的收件人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟次數<br /> </td> 
   <td> 開啟交貨的收件人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一取消訂閱<br /> </td> 
   <td> 按一下取消訂閱連結的收件人數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱率<br /> </td> 
   <td> 與已傳遞消息相比唯一取消訂閱的數目。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未訂閱<br /> </td> 
   <td> 取消訂閱連結上的按一下次數。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 推送通知度量 {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 邊界+錯誤<br /> </td> 
   <td> 在傳遞期間累積的與已發送消息總數（例如MCPNS或提供程式的錯誤）相關的錯誤總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 彈出+錯誤率<br /> </td> 
   <td> 與發送的推送通知相比，已跳轉的推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> 推送通知已傳送到設備並由用戶按一下的次數。 用戶要麼想查看通知，然後將通知移到「推開開啟」跟蹤，要麼將其關閉。<br /> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> 與推送通知交互的用戶百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> 成功發送的推送通知數，與已發送的推送通知總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交貨率<br /> </td> 
   <td> 已成功發送推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 印象<br /> </td> 
   <td> 推送通知已傳送到設備且未在通知中心中保留的次數。 在大多數情況下，印數應與交貨數相似。 這確保設備收到消息並將該資訊中繼回伺服器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/已發送<br /> </td> 
   <td> 發送的推送通知總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> 用戶通過點擊將推送通知發送到設備並開啟應用的總數。 這與「推式按一下」類似，但「推式開啟」在通知被撤消時不會觸發。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟率<br /> </td> 
   <td> 開啟的推送通知百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> 唯一用戶與推送通知交互的次數，例如按一下通知或按鈕。<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特印象<br /> </td> 
   <td> 接收人印象數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟次數<br /> </td> 
   <td> 開啟交貨的收件人數。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 應用內度量 {#in-app-metrics}

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
   <td> 服務提供商向設備傳遞的In-App消息總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 印象<br /> </td> 
   <td> 收件人所看到的In-App消息總數，具體取決於是否滿足觸發條件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內按一下 <br /> </td> 
   <td> 按一下按鈕1或按鈕2的收件人總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> In-App按一下率<br /> </td> 
   <td> 按一下按鈕1或按鈕2的用戶與看到消息的用戶的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用內解除<br /> </td> 
   <td> 通過按一下「關閉」按鈕或「自動關閉」，收件人已撤消的郵件總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解雇率<br /> </td> 
   <td> 接收者拒絕的In-App郵件百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/已發送<br /> </td> 
   <td> 作為傳遞發送過程的一部分從Adobe Campaign發送的In-App郵件總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特印象<br /> </td> 
   <td> 唯一收件人的印象數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用內唯一按一下<br /> </td> 
   <td> 在按鈕1或按鈕2上按一下收件人的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式中的唯一解雇<br /> </td> 
   <td> In-App消息的收件人被拒絕的時間數。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 區段 {#segments}

下表提供了報告中使用的段清單及其定義。

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
   <td> 1946年至1954年出生的受贈者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：嬰兒潮2<br /> </td> 
   <td> 1955年至1965年出生的受贈者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從18到25<br /> </td> 
   <td> 18到25歲的受贈者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從26到30<br /> </td> 
   <td> 26到30歲的受贈者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從31到40<br /> </td> 
   <td> 31到40歲的受贈者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：從41到50<br /> </td> 
   <td> 41至50歲的受贈者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：X代<br /> </td> 
   <td> 1966年至1976年出生的受贈者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：Y代（千禧一代）<br /> </td> 
   <td> 1977年至1994年生的受贈者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：Z代<br /> </td> 
   <td> 從1995年到今天出生的受助者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：大於50<br /> </td> 
   <td> 年齡大於50的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於25<br /> </td> 
   <td> 年齡低於25歲的受贈人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於30<br /> </td> 
   <td> 年齡低於30的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於40<br /> </td> 
   <td> 年齡低於40的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於50<br /> </td> 
   <td> 年齡低於50的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：沈默的一代<br /> </td> 
   <td> 生於1945年或之前的受助者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 所有訪問<br /> </td> 
   <td> 每個收件人<br /> </td> 
  </tr>
 </tbody> 
</table>
