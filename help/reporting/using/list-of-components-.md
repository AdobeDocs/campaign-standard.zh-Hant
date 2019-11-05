---
title: '元件清單 '
description: 在這裡尋找動態報表中可用的每個元件清單及其定義。
page-status-flag: 從未激活
uuid: a2403806-8df4-4bb1-bac2-2689dc584ae0
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 報告
content-type: 參考
topic-tags: about-reporting
discoiquuid: 17cf126a-7ce1-4e11-bb5e-2bdce01cfded
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 元件清單 {#list-of-components}

若要進一步瞭解維度與量度之間的相容性，請參 [閱表](https://docs.campaign.adobe.com/doc/standard/en/Technotes/dynamic_report_compatibility.pdf)。 如果兩個元件不相容，儲存格將顯示值 **None**。

[![影像](/help/reporting/using/assets/dynamic_report_compatibility.png)](https://docs.campaign.adobe.com/doc/standard/en/Technotes/dynamic_report_compatibility.pdf)

## 維度 {#dimensions}

下表提供報表中使用的維度清單及其定義。

<table> 
 <thead> 
  <tr> 
   <th> 維<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 瀏覽器<br /> </td> 
   <td> 開啟或點按訊息的瀏覽器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 促銷活動<br /> </td> 
   <td> 促銷活動的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 城市<br /> </td> 
   <td> 在收件者個人檔案中註冊的城市。<br /> </td> 
  </tr> 
  <tr> 
   <td> 國家／地區<br /> </td> 
   <td> 在收件者個人檔案中註冊的國家／地區。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送<br /> </td> 
   <td> 傳送的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 裝置<br /> </td> 
   <td> 開啟／檢視／點按電子郵件／簡訊／推播通知的裝置。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失敗原因<br /> </td> 
   <td> 導致每個傳送的彈回的錯誤類型，例如使用者未知、無效網域或郵箱已滿。<br /> </td> 
  </tr> 
  <tr> 
   <td> 性別<br /> </td> 
   <td> 受助者的性別，如男性或女性。 如果收件者的設定檔中的性別欄位空白，則值將為無。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內訊息動作<br /> </td> 
   <td> 已傳送之應用程式內訊息上的動作，例如按鈕1或2的動作或解除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 消息類型<br /> </td> 
   <td> 用於傳送的渠道，例如電子郵件、簡訊、推播通知或應用程式內。<br /> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式名稱<br /> </td> 
   <td> 行動應用程式的名稱<br /> </td> 
  </tr> 
  <tr> 
   <td> 平台<br /> </td> 
   <td> 開啟／檢視／點按訊息之裝置的平台。<br /> </td> 
  </tr> 
  <tr> 
   <td> 設定檔<br /> </td> 
   <td> 重新分組在配置檔案資源擴展期間建立的出廠設定和自定義配置檔案欄位，有關詳細資訊，請參閱本頁 <a href="../../developing/using/key-steps-to-add-a-resource.md"></a> 或本 <a href="../../reporting/using/creating-a-custom-profile-dimension.md">示例</a>。<br /> 請注意，當連結至描述檔欄位的自訂資源發佈時，會立即擷取此維度的資料。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播平台<br /> </td> 
   <td> 開啟推播通知的裝置平台，例如iOS或Android。<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件者網域<br /> </td> 
   <td> 用於開啟電子郵件的域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 循環傳送<br /> </td> 
   <td> 循環傳送的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送者網域<br /> </td> 
   <td> 用於傳送電子郵件的網域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送者IP<br /> </td> 
   <td> 用來傳送電子郵件的IP。<br /> </td> 
  </tr> 
  <tr> 
   <td> 州<br /> </td> 
   <td> 在收件者描述檔中註冊的州。<br /> </td> 
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
   <td> URL的標籤，例如鏡像頁面，請聯絡我們或開啟。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易傳送<br /> </td> 
   <td> 交易傳送的標籤和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 變體<br /> </td> 
   <td> A/B測試時電子郵件的變體。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 量度 {#metrics}

下表提供報表中使用的量度清單及其定義，視傳送類型而定。

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
   <td> 黑名單<br /> </td> 
   <td> 宣告電子郵件為垃圾訊息或垃圾訊息的收件者數目。<br /> </td> 
  </tr> 
  <tr> 
   <td> 黑名單比率<br /> </td> 
   <td> 標示為黑名單的遞送百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 彈回數+錯誤<br /> </td> 
   <td> 傳送和自動傳回處理期間累積的錯誤總數，與傳送的訊息總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 反彈+錯誤率<br /> </td> 
   <td> 與傳送的電子郵件相比，遭拒的電子郵件百分比。<br /> </td> 
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
   <td> 交付<br /> </td> 
   <td> 成功發送的消息數，與已發送消息總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> 成功發送的消息百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬彈跳<br /> </td> 
   <td> 永久錯誤的總數，例如錯誤的電子郵件地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬反彈率<br /> </td> 
   <td> 因永久錯誤而失敗的傳送百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 鏡像頁<br /> </td> 
   <td> 點按鏡像頁面連結的收件者數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 鏡像頁面速率<br /> </td> 
   <td> 鏡像頁面連結上的點按次數與傳送消息總數的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 選件點按次數<br /> </td> 
   <td> 選件在傳送中的點按次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 選件點按率<br /> </td> 
   <td> 選件的點按百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> 傳送中訊息開啟的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開放率<br /> </td> 
   <td> 已開啟消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理／已傳送<br /> </td> 
   <td> 傳送的傳送總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔離<br /> </td> 
   <td> 已跳回並導致地址隔離的消息數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔離率<br /> </td> 
   <td> 隔離與已傳送訊息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已拒絕<br /> </td> 
   <td> SMTP伺服器分類為垃圾郵件的郵件數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 拒絕率<br /> </td> 
   <td> 標籤為已拒絕的消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 軟彈跳<br /> </td> 
   <td> 臨時錯誤（如完整收件箱）的總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 軟反彈率<br /> </td> 
   <td> 因暫時原因而失敗的傳送百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特點按<br /> </td> 
   <td> 點選傳送中內容的收件者數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一開啟<br /> </td> 
   <td> 開啟傳送的收件者數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱率<br /> </td> 
   <td> 收件者未訂閱與已傳送訊息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱<br /> </td> 
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
   <td> 彈回數+錯誤<br /> </td> 
   <td> 發送過程中累積的與發送消息總數相關的錯誤總數，例如MCPNS或提供者的錯誤。<br /> </td> 
  </tr> 
  <tr> 
   <td> 反彈+錯誤率<br /> </td> 
   <td> 與傳送的推播通知相比，遭彈回的推播通知百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> 推播通知傳送至裝置並被使用者點按的次數。 使用者要麼想要檢視通知，然後將其移至「推播開啟」追蹤，要麼將其關閉。<br /> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> 與推播通知互動的使用者百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> 成功傳送的推播通知數，與傳送的推播通知總數相關。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> 成功傳送推播通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 印象<br /> </td> 
   <td> 推播通知傳送至裝置且未在通知中心受到影響的次數。 在大多數情況下，印象數目應與傳送的數目類似。 這可確保設備收到消息並將該資訊轉發回伺服器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理／已傳送<br /> </td> 
   <td> 傳送的推播通知總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> 傳送至裝置並由使用者點按的推播通知總數，以開啟應用程式。 這類似於推播點按，但是當通知關閉時，不會觸發推播開啟。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開放率<br /> </td> 
   <td> 已開啟推播通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一點按<br /> </td> 
   <td> 獨特使用者與推播通知互動的次數，例如點按通知或按鈕。<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特印象<br /> </td> 
   <td> 收件者的曝光次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一開啟次數<br /> </td> 
   <td> 開啟傳送的收件者數。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 應用程式內度量 {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> 服務供應商傳送至裝置的應用程式內訊息總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 印象<br /> </td> 
   <td> 收件者看到的應用程式內訊息總數，視觸發條件是否符合而定。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內點按次數 <br /> </td> 
   <td> 按一下按鈕1或按鈕2的收件者總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內點進率<br /> </td> 
   <td> 按一下Button 1或Button 2的使用者與看到訊息的使用者之比例。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解雇<br /> </td> 
   <td> 收件者按一下關閉按鈕或自動關閉而關閉的訊息總數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解雇率<br /> </td> 
   <td> 收件者關閉的應用程式內訊息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理／已傳送<br /> </td> 
   <td> 從Adobe Campaign傳送的應用程式內訊息總數，是傳送傳送程式的一部分。<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特印象<br /> </td> 
   <td> 獨特收件者的曝光次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特的應用程式內點按次數<br /> </td> 
   <td> 收件者點按按鈕1或按鈕2的次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特的應用程式內解雇<br /> </td> 
   <td> 收件者關閉應用程式內訊息的時間。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 區段 {#segments}

>[!NOTE]
>
>依預設，區段 **[!UICONTROL Exclude proof]** 已選取以篩選報表，但可視需要變更。

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
   <td> 年齡：嬰兒潮一代1<br /> </td> 
   <td> 1946年到1954年出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：嬰兒潮一代2<br /> </td> 
   <td> 1955年到1965年出生的收件者。<br /> </td> 
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
   <td> 年齡：X代<br /> </td> 
   <td> 1966年到1976年出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：Y世代（千禧一代）<br /> </td> 
   <td> 1977年到1994年出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：Z世代<br /> </td> 
   <td> 1995年到今天的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：大於50<br /> </td> 
   <td> 年齡大於50歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於25<br /> </td> 
   <td> 年齡低於25歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於30<br /> </td> 
   <td> 年齡低於30歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於40<br /> </td> 
   <td> 年齡低於40歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：少於50<br /> </td> 
   <td> 年齡低於50歲的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齡：無訊息的產生<br /> </td> 
   <td> 1945年或之前出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 所有瀏覽<br /> </td> 
   <td> 每位收件者<br /> </td> 
  </tr> 
    <tr> 
   <td> 排除證明<br /> </td> 
   <td> 從報表中排除校樣（僅限從Campaign 19.4版開始）<br /> </td> 
  </tr> 
 </tbody> 
</table>

