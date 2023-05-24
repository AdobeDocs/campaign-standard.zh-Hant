---
title: 發行說明 2018 年
description: 本頁列出 2018 年的所有 Adobe Campaign Standard 版本。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '5355'
ht-degree: 3%

---

# 發行說明 2018 年{#release-notes}

## 發行版本 18.9 – 2018 年 9 月 {#release-18-9---september-2018}

**有哪些新功能？**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 應用內消息傳遞（測試版）<br /> </td> 
   <td> In-App消息傳遞允許您通過提供上下文交互並使您能夠聯繫那些可能選擇不使用推送通知的用戶，更有效地與Mobile App用戶接觸。 將In-App消息傳遞與Push通知結合使用，以建立高度個性化且相關的體驗。 這可以更好地轉換和保留您的App用戶。<br /> 有關詳細資訊，請參閱 <a href="../../channels/using/about-in-app-messaging.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe啟動移動應用整合（測試版）<br /> </td> 
   <td> Adobe啟動與Adobe Campaign的整合現在使用移動SDK V5簡化和自動化了在活動中激活移動應用屬性的過程。<br /> 有關詳細資訊，請參閱 <a href="https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html">詳細文檔</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* Adobe Campaign Standard現在支援AmazonS3 API的4版。

**其他變更**

* 在廣播中，現在可以區分最大連接數和每小時最大消息數。 當達到限制時，就可以知道為什麼吞吐量受到限制。 以前，同一消息（「配額滿足」）應用於這兩種情況。
* 在市場活動中配置移動應用程式時，用戶現在可以知道iOS證書和Android伺服器密鑰是否已成功上載及其過期日期。

   有關詳細資訊，請參閱有關如何使用 [SDK V4](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html) 和 [SDK V5](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html)。

* 在定義市場活動屬性時選擇移動應用，以特定移動應用上的用戶為目標。 此功能適用於推送和應用內消息傳遞渠道。

   如需詳細資訊，請參閱[詳細文件](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)以瞭解詳情。

* 使用Creative Designer介面選擇內容塊時，現在將載入並顯示清單中的所有內容塊。 (CAMP-27311)

   有關詳細資訊，請參閱 [詳細文檔](../../designing/using/personalization.md#adding-a-content-block)。

**修補程式**

* 已修復一個問題，該問題表明電子郵件儀表板和事務性電子郵件的電子郵件摘要報告之間的日誌計數存在差異。 (CAMP-28237
* 已修復工作流中的問題，該問題在通過檔案傳輸活動導入檔案時可能顯示錯誤消息。 (CAMP-27435)
* 已修復登錄頁中包含25個以上服務的問題，導致以表單形式隨機取消選擇服務。 (CAMP-26572)
* 已修復工作流中的問題，當使用「檔案傳輸」活動時，該問題阻止使用SFTP URL配置外部帳戶。 (CAMP-26475)
* 已修復阻止更新服務摘要報告的問題。 (CAMP-26301)
* 在使用「富集」活動時修復了工作流中的問題，這阻止了自定義欄位顯示正確的日期。 (CAMP-26242)
* 修復了在通過檔案導入導入時無法更新服務訂閱日期的問題。
* 修復了載入檔案活動錯誤，該錯誤阻止工作流導入檔案(CAMP-27068)。
* 已修復在服務摘要報告(CAMP-25587)中顯示訂閱數錯誤的問題。
* 解決了Adobe Analytics和Adobe Campaign報告之間資料差異的問題。 (CAMP-25393)
* 已修復可能阻止有限訪問用戶登錄的問題。 (CAMP-27381)
* 已修復一個問題，該問題可能會阻止在使用Creative Designer編輯電子郵件時顯示Adobe Experience Manager內容清單。 (CAMP-27181)
* 已修復可能阻止Creative Designer開啟的問題，導致錯誤。 (CAMP-27304)
* 修復了在使用Internet Explorer 11時，阻止拖放在Creative Designer中正常工作的問題。
* 修復了導致從相機上傳並以縱向模式拍攝的圖片以在不需要的旋轉位置顯示的問題。
* 修復了在使用Creative Designer中的查詢編輯器介面時顯示不明確選擇資訊的問題。
* 修復了在使用Creative Designer中的查詢編輯器介面時無法正確複製元素的問題。
* 修復了一個問題，該問題一直在將SMS消息傳遞給denylist上的收件人，即使他們已通過自動答復取消訂閱。 (CAMP-27128)
* 已修復無法顯示導致 **資料庫清理** 工作流失敗。 (CAMP-26876)
* 已修復可能阻止刪除推送通知定義中的自定義欄位的問題。 (CAMP-25588)

## 發行版本 18.7 – 2018 年 7 月 {#release-18-7---july-2018}

**有哪些新功能？**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Android推送通知的高優先順序標誌<br /> </td> 
   <td> Android的高優先順序標誌 — 為Android應用提供高優先順序推送通知，使睡眠設備喚醒並運行一些有限的處理。 請注意，預設優先順序為「正常」，這可能會延遲消息傳遞以節省電池。 <br /> 有關詳細資訊，請參閱 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 用於移動應用訂閱者的類型過濾器<br /> </td> 
   <td> 支援類型篩選器中的訂閱 — 當為類型規則指定篩選條件時，可以選擇應用程式訂閱作為篩選和目標維，從而為具有或沒有配置檔案的用戶提供篩選屬性的能力。 <br /> 有關詳細資訊，請參閱 <a href="../../sending/using/about-typology-rules.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 在消息準備期間從URL自動導入內容<br /> </td> 
   <td> 現在，在準備階段可以從URL導入電子郵件內容。 對於定期發送的電子郵件，每次準備郵件時都會檢索最新的HTML內容，確保在發送電子郵件時內容始終是最新的。 此功能還允許您使用URL中的內容建立計畫交付，即使內容尚未準備好。<br /> 有關詳細資訊，請參閱 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 市場活動發放通知消息<br /> </td> 
   <td> 當用戶在實例升級到新版本後登錄時，現在會出現彈出消息。 該消息指示版本號，並包括到發行說明的連結。 您可以選擇在下一版本之前隱藏消息。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 用戶管理<br /> </td> 
   <td> 現在，新Campaign Standard實例和現有未建立地理單位的實例都無法使用地理單位功能，從18.7版開始。<br /> 有關詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hant#release-notes">頁</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* 現在，Adobe Campaign和Adobe Target的整合使您能夠 [權限](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html) 的子菜單。 在電子郵件中包含來自Adobe Target的動態映像時，現在可以指定目標屬性（at_property代碼）。
* GDPR隱私訪問/刪除請求現在將具有到配置檔案資源的自複製連結的自定義資源考慮在內。 對於1個基數簡單連結和N個基數收集連結，您需要在自定義資源中選擇「刪除/複製目標籤錄意味著刪除/複製連結引用的記錄」。 對於0或1基數簡單連結，選擇「刪除/複製記錄意味著刪除/複製連結引用的目標籤錄」。

**其他變更**

* 報告共用超時時間已從1分鐘增加到4分鐘，以避免任何超時錯誤。
* 編輯電子郵件內容時，新的Creative Designer將預設開啟。 如果需要，在保存更改後，您仍可隨時返回預設內容編輯器。 有關詳細資訊，請參閱 [詳細文檔](../../designing/using/designing-content-in-adobe-campaign.md)。
* 在Creative Designer中，現在可以將新內容元件添加到電子郵件中：旋轉木馬。 有關詳細資訊，請參閱 [詳細文檔](../../designing/using/designing-from-scratch.md#about-content-components)。
* 在事務性消息中，按一下 **更改配置檔案** 按鈕，現在只列出連結到您為事務性消息定義的事件的test配置檔案。

**修補程式**

* 修復了byEmail查詢篩選器無法返回任何結果的問題。 (CAMP-23420)
* 修復了允許標準用戶訪問限於管理員的某些功能或螢幕的問題(/rest/head/&#42; 端點、事務性消息傳遞螢幕、配置檔案和訪問群集導入螢幕)。
* 修復了一個問題，如果GDPR隱私刪除請求的名稱由數字啟動，則它將無法處理自定義資源。
* 已修復一個錯誤，該錯誤阻止「保存受眾」活動在Adobe Experience Cloud共用應用程式訂閱者。
* 修復了當檔案名包含空格時可能發生的「檔案傳輸」活動問題。 (CAMP-25936)
* 修復了在會話過期後使用重新連接按鈕時可能發生的問題。 (CAMP-25560)
* 已修復在發送與已修改的規則關聯的時區優化時可能導致排除的問題。 (CAMP-25425)
* 修復了使用API GDPR功能時的問題，該問題可能會阻止使用0-1類型連結刪除資料。
* 已修復在取消疲勞類型規則版本時可能導致錯誤消息的問題。
* 已修復在編輯交貨內容後預覽交貨內容時可能出現的問題。
* 已修復使用解壓縮選項處理CSV zip檔案時可能出現的問題。
* 修復了Creative Designer中的問題，在將帶有內置樣式的某些文本更改為連結或編輯該連結時，這些問題導致了不需要的顏色字型和格式設定。 (CAMP-26001)
* 修復了阻止熱按一下報告顯示包含動態內容的遞送中每個條件的百分比的問題。 以前，只顯示對預設變型的按一下。

## 發行版本 18.6 – 2018 年 6 月 {#release-18-6---june-2018}

**功能改進**

* 的 **[!UICONTROL History]** API已添加到Adobe.IO。 它允許您訪問與配置檔案的市場營銷歷史記錄相關的資訊：觸碰點數、已發送交貨、鏡像頁URL等。 有關詳細資訊，請參閱 [專用用例](../../api/using/interacting-with-marketing-history.md) 。
* 的 **[!UICONTROL Database cleanup]** 為確保資料庫備份的效能更佳，對技術工作流進行了優化。
* Creative Designer for E-mail現在也有法文和德文版本。

**其他變更**

* A **[!UICONTROL Compute stats]** 按鈕 **[!UICONTROL Deployment]** 已發送交貨的窗口。 它允許您檢索最新的KPI，例如，如果發送的結果需要太長時間才能更新或尚未考慮。 如需詳細資訊，請參閱本[區段](../../sending/using/confirming-the-send.md)。
* 在 **更新可交付性** 現在，功能管理員可以定義要在 **更新規則** javascript活動。 預設情況下，欄位值設定為0，這意味著將忽略所有錯誤。
* 管理設備訪問限制條件時生成的SQL已優化。
* 的 **[!UICONTROL Update]** 活動現在允許您添加、更新或刪除與預訂相關的資料（nms:appSubscriptionRcp表）。
* 的 **[!UICONTROL Update delivery execution]** 為了優化效能，將技術工作流分為兩個工作流：- **[!UICONTROL Update delivery execution]**:更新交貨的跟蹤。 預設情況下，每10分鐘啟動一次。 **[!UICONTROL Update delivery indicators]**:更新交貨的KPI，預設情況下每小時啟動一次。 有關技術工作流的詳細資訊，請參閱此 [節](../../administration/using/technical-workflows.md#list-of-technical-workflows)。
* 當傳遞正在發送消息時， **[!UICONTROL Deployment]** 部分現在可以有兩個值： **[!UICONTROL Sending]**:正在發送消息。 **[!UICONTROL Sending (retry)]**:重試過程正在進行。
* 具有 **[!UICONTROL Delivery preparation]** 角色現在能夠發送證據。 (CAMP-24313)
* 的 **通過SMPP啟用TLS** 已添加到 **通過SMPP的SMS路由** 外部帳戶。 有關此內容的詳細資訊，請參閱 [節](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)。

**修補程式**

* 修復了在包含來自Adobe Target的動態影像(CAMP-24848)時可能無法發送電子郵件的問題。
* 已修復 **[!UICONTROL Privacy Access/Delete Request]** 技術工作流，如果任何請求失敗，則未完成。
* 已修復阻止隱私核心服務從市場活動接收請求狀態更新的問題。
* 已修復可能阻止 **[!UICONTROL Import shared audience]** (CAMP-25465)。
* 已修復一個問題，使市場活動隱私請求無法在核心Privacy Service中標籤為已完成。
* 解決了在Adobe ID過長時，某些用戶無法通過IMS身份驗證登錄Campaign Standard的問題。 (CAMP-24095)
* 修復了刪除內容模組時可能出現的問題。 (CAMP-25242)
* 為資料庫中沒有配置檔案的訂閱者使用推送通知疲勞規則時，已修復問題。 (CAMP-25344)
* 已修復訪問遞送排除日誌時可能顯示錯誤消息的問題。 (CAMP-24724)
* 修復了在具有擴展發送日誌的情況下無法準備證據的問題。
* 修復了在與 **[!UICONTROL Sending log]** 已激活擴展。
* 修復了在重複交貨中未考慮交貨期限時可能發生的問題。
* 修復了在中對資料排序時可能出現的問題 **[!UICONTROL Client data]** 的子菜單。 (CAMP-24308)
* 修復了在動態報告中使用搜索函式時未考慮的自定義配置檔案維的問題。
* 在動態報表中顯示帳戶級別的國際資料時解決了問題。
* 現在，可以建立沒有訂閱或取消訂閱確認消息的服務。

## 發行版本 18.5 – 2018 年 5 月 {#release-18-5---may-2018}

**有哪些新功能？**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR:核心服務整合<br /> </td> 
   <td> Privacy Core Service Integration允許您通過單個JSON API調用在多解決方案上下文中自動執行GDPR請求。 <br /> 從隱私核心服務推送到所有Experience Cloud解決方案的GDPR請求現在由活動自動處理。 <br /> 有關詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送改進 — 詳細的交付反饋<br /> </td> 
   <td> Adobe Campaign公司現在通過MCPNS從提供商(APNS/GCM)接收推送消息的詳細反饋（發送日誌和排除日誌）。<br /> 有關詳細資訊，請參閱 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付日誌擴展<br /> </td> 
   <td> 傳遞日誌擴展允許您使用配置檔案資料和來自工作流的段代碼擴展發送日誌。 此資訊隨後可用於動態報告中，並允許您在傳送時保留某些資訊的快照。<br /> 還有2個使用案例：<br /> 
    <ul> 
     <li> 使用「凍結」資料導出擴展廣播：作為營銷人員，我要導出段代碼等於「A」（來自工作流引擎）的所有配置檔案。 </li> 
     <li> 對「凍結」資料進行分段：作為營銷員，我想 <strong>重定位</strong> 自上次發送以來已獲得1000個會員積分或段代碼等於「A」的所有配置檔案。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用自定義配置檔案資料進行動態報告<br /> </td> 
   <td> 此功能允許您根據在配置檔案資源擴展期間建立的自定義配置檔案資料建立和管理報告。 您可以按配置檔案屬性（如會員計畫、首選渠道等）分解報表。<br /> 有關詳細資訊，請參閱 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細文檔</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* 應用程式的總記憶體和CPU使用率已增強

**其他變更**

* 「讀取受眾」工作流活動現在可以讀取Experience Cloud受眾。 以前，此活動只能讀取查詢和列出受眾。 請參閱 [詳細文檔](../../automating/using/read-audience.md)。 (CAMP-23623)
* 預設共用資料源的標識符現在處於只讀模式，無法再更改。 更改此標識符可能會導致與Experience Cloud共用受眾時出現一些問題。
* 現在，從Audience Manager導入受眾可以處理拆分檔案。 以前，只有段的最後一個檔案是由importSharedAuvience技術工作流導入的。
* AWSS3外部帳戶現在支援區域和版本4驗證機制。 請參閱 [詳細文檔](../../administration/using/external-accounts.md)。
* 現在，「資產選擇」窗口應加快載入速度，並允許選擇資產，然後退出該窗口而不出現任何問題。
* 技術工作流的屬性和結構現在可由具有管理權限且屬於「全部」組織和地理單位的用戶修改。
* 在建立新段時，在「分段」活動介面中進行了增強：現在，在添加限制後，「限制」(Limitation)頁籤會直接顯示。 新段的名稱現在會遞增（「段1」、「段2」等）。
* 將「nextProcessingDate」欄位添加到工作流資源。 此欄位僅通過REST API調用可見，它允許您可視化工作流下一處理日期。
* 「sourceId」欄位現在在跟蹤日誌資源(nms:trackingLog)中公開。
* 「總開啟量」和「總點擊量」值現在可以通過工作流在平面檔案中導出。 (CAMP-24186)
* 「英語 — Danmark」現在可在配置檔案的「首選語言」清單中找到。 (CAMP-23728)
* 當將分段活動與附加資料(targetData)連結一起使用時，現在會顯示一條消息，通知您該資料在工作流之外不可用。 按一下「分段」活動中的「計數」或「預覽」按鈕時，將顯示此消息。 (CAMP-23651)
* 已對工作流使用的磁碟空間進行了增強：(CAMP-21979):「載入檔案」活動處理的檔案現在預設情況下將被刪除。 一個選項允許您根據特定需要保留它們。 刪除工作流時，其專用資料夾會自動從伺服器目錄中取消。

**修補程式**

* 修復了某些原始報告事件沒有關聯跟蹤事件的問題，因為eventDate欄位未正確填充。
* 已修復阻止個性化欄位在推送通知傳遞的預覽窗口中顯示的問題。
* 修復了阻止文本在預覽窗口中對推送通知的消息正文進行字包裝的問題。
* 當主目標為空時，從工作流發送重複傳遞時已修復問題。
* 已修復一個問題，如果目標映射連結到不存在的架構，則它將無法訪問該映射。
* 已修復通過檔案載入活動導入zip檔案時可能出現的問題。 (CAMP-24309)
* 已修復在發送循環傳遞時導致PostgreSQL錯誤的問題。 (CAMP-23613)
* 已修復在發送具有空JSON屬性的REST API請求時顯示錯誤消息的問題。 (CAMP-23506)
* 已修復配置檔案中的問題，該配置檔案設定為「ß」字元後的字元大寫。 (CAMP-23136)
* 在發送與個性化或動態內容塊的資格條件一起使用的遞送時使用連結配置檔案架構的屬性時，已修復問題。 (CAMP-22751)
* 已修復無法刪除服務的問題。 (CAMP-22050)
* 已修復無法更改Test配置檔案中的國家/地區或國家/地區值的問題。 (CAMP-20426)
* 已修復可能阻止Creative Designer載入的問題。 (CAMP-24573)
* 已修復刪除電子郵件主題中個性化欄位後添加的字元的問題。 (CAMP-24113)

## 發行版本 18.4 – 2018 年 4 月 {#release-18-4---april-2018}

**修補程式**

_平台_

* 修復了一個錯誤，該錯誤可能會阻止正確處理GDPR訪問或刪除請求。 在提取的資料包含以下字元之一的少數情況下，觀察到了此行為：&amp; &lt; > 「 」。

_電子郵件、簡訊和直郵_

* 如果寬日誌同步花費了一個多小時，則修復問題可能導致KPI被錯誤值覆蓋。

_工作流程_

* 改進了記憶體管理並優化了工作流中的效能。

_報告_

* KPI共用工作流現在檢索過去2個月而不是過去6個月的交貨值。 已修復KPI共用顯示截斷日期的外部帳戶的問題。
* 已修復可能導致某些郵件未在中考慮的問題 **已發送**。 **已交付** 和 **彈跳**&#x200B;度量。
* 修復了在以下時間範圍內選擇的時間範圍時發生的錯誤 **交貨摘要報告** 太長了。

_自訂資源_

* 已修復導致自定義資源準備失敗的錯誤。

## 發行版本 18.3 – 2018 年 3 月 {#release-18-3---march-2018}

**新功能**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 歐盟一般資料保護條例(GDPR)<br /> </td> 
   <td> GDPR是歐盟(EU)的新隱私法，它協調並現代化將於2018年5月25日生效的資料保護要求。 GDPR 適用於所持有資料的主體居住於歐盟的 Adobe Campaign 客戶。<br /> 除了Adobe Campaign已經提供的隱私功能（包括同意管理、資料保留設定和用戶角色）外，我們還將利用此機會作為資料處理器角色加入其他功能，以幫助您作為資料控制器就緒，滿足某些GDPR請求：<br /> 
    <ul> 
     <li> 訪問權限：允許資料主題接收由資料控制器捕獲的個人資料的副本，可能包括儲存在Adobe Campaign的資料。 </li> 
     <li> 刪除權限：資料使用者有權擦除其資料控制器捕獲的個人資料，可能包括儲存在Adobe Campaign的資料。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for E-mail(Beta)<br /> </td> 
   <td> Adobe Campaign的新創意設計師在活動中提供了完全整合的創作體驗，能夠快速而輕鬆地直觀地建立迷人的個性化電子郵件，而無需編寫一行代碼。 Creative Designer通過其強大的拖放介面幫助擴展電子郵件建立，無論用戶是從空白的白板開始，還是利用現有內容片段或模板。 <br /> 關鍵功能包括：<br /> 
    <ul> 
     <li> 通過拖放介面直觀地設計和建立完全個性化且響應迅速的電子郵件，並通過本機Creative Cloud整合增強 </li> 
     <li> 建立和保存電子郵件內容模板並利用保存的模板來幫助擴展電子郵件建立 </li> 
     <li> 建立和保存內容片段（如頁眉、頁腳、文章等） 優化內容建立並確保品牌一致性 </li> 
     <li> 在拖放介面中建立電子郵件和按一下按鈕直接編輯電子郵件HTML之間進行無縫切換 </li> 
    </ul> Creative Designer for E-mail僅提供英文版。<br /> 有關詳細資訊，請參閱 <a href="../../designing/using/designing-content-in-adobe-campaign.md">詳細文檔</a> 看這個 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">視頻</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 多語言推送交付<br /> </td> 
   <td> 電子郵件和SMS通道中已經存在的同一簡單多語言介面，已添加到推送通道中，幫助您與客戶接洽，而不管客戶喜歡什麼語言。<br /> 此功能為那些管理跨多個區域的推式營銷活動並希望以其首選語言為目標的用戶提供了可擴展的自動解決方案。 它允許您通過模板化電子錶格將所有語言變體上載到單個推送交付，只需按一下一次。 Adobe Campaign隨後根據用戶的語言偏好執行自動分段，通過簡化工作流和報告來減少冗餘。<br /> 有關詳細資訊，請參閱 <a href="../../channels/using/creating-a-multilingual-push-notification.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事務性消息傳遞中自定義資源的使用<br /> </td> 
   <td> 除了現成欄位之外，事務性消息服務現在允許您使用自定義資源來豐富消息的內容。<br /> 例如：<br /> 
    <ul> 
     <li> 利用自定義欄位作為協調標準，將事務性消息與配置檔案匹配 </li> 
     <li> 利用完整的配置檔案、服務和連結資料進一步個性化事務性消息 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 已修復無法從清單中導出5000多條記錄的問題。
* 將資料導出到使用個性化欄位命名的檔案時解決了問題。

_電子郵件、簡訊和直郵_

* 已修復導致多部件SMS被截斷的問題，因為部件大小是以字元而不是位元組計算的。
* 添加了一個選項，允許 **[!UICONTROL Delivered]** 或 **[!UICONTROL Bounces + Errors]** 發送交貨後要即時更新的KPI。 它們直接從從提供程式接收的SR（狀態報告）中重新計算。
* 已修復傳遞計畫程式中日曆小部件的問題。
* 在已發送的遞送中第二次開啟目標時解決了顯示問題。
* 修復了建立具有延遲發送日期的電子郵件模板時導致請求開始日期的錯誤消息的問題。
* 修復了編輯遞送內容時可能導致影像呈現問題的問題。
* 在複製市場活動時修復了帶證據的問題。
* 在向工作流添加傳遞後，通過導航欄訪問市場活動模板時修復了導致錯誤消息的問題。
* 已修復一個問題，該問題可能會阻止自動選擇A/Btest電子郵件的獲勝者，導致未發送該電子郵件。 如果交貨在 **[!UICONTROL retryInProgress]** 狀態。
* 修復了在重新開啟A/Btest電子郵件的參數時可能導致出現錯誤消息的問題。

_受眾和查詢_

* 修復了無法訪問資料和設定從Adobe Campaign Classic複製到標準的收件人查詢的問題。
* 在使用 **計數** 或 **預覽** 按鈕。

_工作流程_

* 的 **計費** 優化了工作流，改善了交貨準備延遲。
* 修復了在使用循環傳遞活動時阻止在出站轉換中顯示人口資料的問題。
* 修復了在轉換後阻止拒絕記錄顯示的問題 **更新資料** 的子菜單。
* 已修復可能導致 **deliverabilityUpdate** 技術工作流失敗。

_整合_

* 已修復阻止將國際字元正確發送到Adobe Analytics的問題。
* 現在，當嘗試在消息中插入Experience Cloud資產庫中的影像時，應加快載入資產。
* 已修復某個問題，在某些情況下，該問題可能會阻止關閉資產選擇窗口。
* 現在，您可以通過資料源詳細資訊直接訪問其相關工作流以檢查工作流的狀態。
* 現在，在定義或編輯觸發器事件時，可以直接更新觸發器架構。 通過此更改，您不再需要取消發佈觸發器並建立另一個觸發器。

_異動訊息_

* 在擴展傳遞資源時修復事務性消息模板錯誤。
* 現在可以刪除事務性消息。

## 發行版本 18.2 – 2018 年 2 月 {#release-18-2---february-2018}

**新功能**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 訂閱 — 訂閱或取消訂閱多個服務的配置檔案清單<br /> </td> 
   <td> 的 <strong>訂閱服務</strong> 工作流活動現在允許您預訂或取消預訂多個服務的配置檔案清單。 在工作流中，導入包含配置檔案的檔案，並為每個配置檔案導入操作類型和服務。 的 <strong>訂閱服務</strong> 活動將能夠使用此資訊並同時動態處理所有配置檔案訂閱和取消訂閱。<br /> 有關詳細資訊，請參閱 <a href="../../automating/using/subscription-services.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 富集活動 — 根據先前的過渡來豐富資料<br /> </td> 
   <td> 新 <span class="uicontrol">濃縮</span> 工作流活動允許您利用入站轉換並使用其他資料完成輸出轉換。 如果以配置式為目標，則富集活動允許您使用資料庫中未儲存的其他資料（例如，來自導入的檔案）來豐富配置式資訊。<br /> 有關詳細資訊，請參閱 <a href="../../automating/using/enrichment.md">詳細文檔</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* Adobe Campaign介面的頂欄已用新Experience Cloud菜單更新。
* 已修復阻止連結到的問題 **[!UICONTROL Offers]** 中。

_電子郵件、簡訊和直郵_

* 已增強遞送準備階段以改進效能。
* 已修復了若干問題，這些問題可能導致跟蹤日誌在某些特定情況下損壞。
* 修復了在交貨準備和確認之間更改聯繫日期時發生的聯繫日期更新問題。 現在，當您在準備後更改聯繫日期時，需要在確認發送之前再次準備交貨。 查看 [詳細文檔](../../sending/using/preparing-the-send.md)。

_推播通知_

* 已修復一個錯誤，該錯誤阻止某些個性化欄位在iOS推送通知中工作。
* 修復了在推送通知儀表板中將按一下和開啟速率顯示為0%的錯誤。

_報告_

* 已修復某些瀏覽器中顯示報表清單為空的錯誤。
* 修復了在 **[!UICONTROL Report sharing]** 技術工作流在達到其過期限制之前。

_工作流程_

* 修復了在拖放活動後無法訪問的問題。
* 已修復可能導致輸出轉換順序的問題 **[!UICONTROL Segmentation]** 活動。
* 修復讀取包含枚舉類型欄位且先前已從工作流中保存的訪問群體時發生的錯誤
* 已修復導致 **[!UICONTROL Request confirmation before sending messages]** 選項，即使在定義在工作流中建立的交貨的計畫屬性時取消選中該選項後仍保持選中狀態。
* 現在，可以在中禁用自動刪除重複行（DISTINCT子句） **[!UICONTROL Query]** 活動，通過位於 **[!UICONTROL Additional data]** 頁籤。 出於效能原因，在定義許多（超過100個）附加元素時，建議禁用此選項。

_整合_

* 對C-C-C-H-C-H-C-H-H-H-C-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H-H **[!UICONTROL Data sources]** 配置螢幕。

_已知問題_

由於可能的顯示問題，建議您不要使用Internet Explorer版本11。

使用「市場活動」介面的上下文幫助連結時可能會出現一些問題。 18.3號。

## 發行版本 18.1 – 2018 年 1 月 {#release-18-1---january-2018}

**新功能**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 疲勞管理報告<br /> </td> 
   <td> Reporting for Fatigue Management是一個專用的可配置報告，顯示在發送前指定日期範圍內電子郵件、推送、SMS和直郵通道之間的遞送影響疲勞規則。 通過能夠在單個視圖中快速查看所有衝突的市場活動這一新增的洞察力，營銷人員能夠根據疲勞規則的設定更有效地計畫市場活動，並排定通信的優先順序。<br /> 有關詳細資訊，請參閱 <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 報告共用<br /> </td> 
   <td> 報告共用允許您以電子郵件附件的形式與Adobe Campaign用戶共用報告，包括自動重複。 接收定期報告的用戶能夠通過每個電子郵件中的專用連結取消訂閱這些通信。<br /> 有關詳細資訊，請參閱 <a href="../../reporting/using/reporting-interface.md#share-tab">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送新功能<br /> </td> 
   <td> 推送消息預覽 — 從推送通知內容編輯器中預覽iOS和Android設備上的推送通知，以在測試或執行傳送之前，準確查看收件人將看到的內容。<br />如需詳細資訊，請參閱<a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">詳細文件</a>以瞭解詳情。<br /> 內容可用 — 當應用程式在較長的時間段內未開啟時，其資料可能會過時。 這導致在用戶最終開啟應用時必須更新或替換資料，這可能導致應用的使用延遲。 有了「可用內容」的額外支援，Adobe Campaign用戶可以在發送推送通知時喚醒其應用以刷新其後台資料，從而實現更一致性，並控制用戶的應用內體驗。<br /> 可變內容 — 通過增加對可變內容的支援，Adobe Campaign用戶現在可以利用其移動應用擴展來進一步修改從Adobe Campaign發送的到達推送通知的內容或演示。 例如，用戶可以利用可變內容： <br /> 
    <ul> 
     <li> 解密以加密格式傳送的資料 </li> 
     <li> 下載影像或其他媒體檔案，並將其作為附件添加到通知 </li> 
     <li> 更改通知的正文或標題文本 </li> 
     <li> 將線程標識符添加到通知 </li> 
    </ul> 有關「可用內容」和「可變內容」的詳細資訊，請參閱 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">詳細文檔</a>。<br /> <strong>警告：</strong> 這些推送通知更新要求客戶升級其移動應用程式。 請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html">這種技術</a> 的子菜單。<br /> </td> 
  </tr> 
  <tr> 
   <td> 時區優化交貨<br /> </td> 
   <td> 安排在每個收件人的時區中的特定日/時間傳遞的定期電子郵件、SMS和推送通知，確保您的郵件在正確的時間傳遞，而不設定多個傳遞。 <br /> 有關詳細資訊，請參閱 <a href="../../automating/using/scheduler.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> API信號活動觸發<br /> </td> 
   <td> 現在，可以直接從Adobe Campaign StandardAPI觸發工作流的信號活動。<br /> 有關詳細資訊，請參閱 <a href="/help/api/using/triggering-a-signal-activity.md">詳細文檔</a> 。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 已優化配置檔案搜索以提高效能。
* 預設安全組的內部標識符現在處於標準用戶的只讀模式。

_電子郵件、簡訊和直郵_

* 已修復將emoji插入交付內容時出現的顯示問題。
* 修復了允許用戶在傳遞仍在版本中時訪問發送日誌的問題。
* 的 **[!UICONTROL Scheduler]** 活動現在允許您根據收件人的時區發送交貨。
* 簡訊：選項 **[!UICONTROL Store incoming MO]** 已將資料庫中的內容添加到外部帳戶。 選中後，所有傳入的SMS都將儲存到 **在** 的子菜單。
* 簡訊：服務現在附加到事件而不是事務模板。
* 簡訊：預設SMTP連接超時已減少到30秒。

_推播通知_

* 已修復阻止推送通知傳遞停止的錯誤。
* 在推送通知中添加了一個選項高級選項，以用推送通知喚醒應用程式。
* 已為推送通知預覽視頻添加暫停按鈕。
* 推送通知預覽現在可用於iPhone、安卓、平板電腦等不同設備。

_報告_

* 已修復顯示率超過100%的錯誤。
* 已修復阻止用戶以CSV格式下載報告的問題。
* 添加新 **[!UICONTROL Report]** 的子菜單。

_工作流程_

* 修復了在查詢中使用附加資料和添加包含空格的別名時導致錯誤消息的問題。 非字母數字字元現在由「_」替換。
* 修復了在某些情況下預設可以停止計算KPI的技術工作流的問題。

_設定檔與對象_

* 已修復在受眾查詢中添加多個篩選器時發生的錯誤。
* 已修復更改配置檔案圖片時出現的顯示問題。
* 已添加工具提示，顯示查詢填充計數後的確切結果編號。
* 已修復可能阻止用戶選擇受眾或關閉受眾選取器窗口的問題。
* 表達式編輯器中可用函式的清單已更新。 的 **格式貨幣** 和 **轉換貨幣** 已刪除函式。
