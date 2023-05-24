---
title: 發行說明 2019 年
description: 本頁列出 2019 年的所有 Adobe Campaign Standard 版本。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 6a53e6f5-9b69-4068-ab7d-10e22e266277
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '7556'
ht-degree: 8%

---

# 發行說明 2019 年{#release-notes-2019}

## 第19.4版 — 2019年12月 {#release-19-4---october-2019}

**有哪些新功能？**

<table> 
 <thead> 
  <tr> 
   <th> <strong>加利福尼亞消費者隱私法(CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA是加利福尼亞州新的隱私法，它協調並現代化將於2020年1月1日生效的資料保護要求。 CCPA適用於Adobe Campaign客戶，這些客戶持有位於加利福尼亞的資料主題資料。</p>
   <p>除了Adobe Campaign已經提供的隱私功能（包括同意管理、資料保留設定和用戶角色）外，我們還將利用此機會包括其他功能，以幫助您做好CCPA的準備：</p>
   <ul>
    <li>訪問權和刪除權：我們正在利用為GDPR添加的功能。 <a href="https://helpx.adobe.com/content/help/tw/campaign/kb/acs-privacy.html#righttoaccess">了解更多</a> </li>
    <li><p>建立隱私請求時，已在隱私核心服務中添加了規則類型（GDPR或CCPA）。 此方法是您應該用於所有存取和刪除請求的方法。不建議使用促銷活動 API 和介面來存取和刪除請求。請參閱「<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hant#release-notes">已過時和已移除的功能</a>」文章。</p></li>
    <li>A <strong>CCPA選擇退出</strong> 已將欄位添加到Profiles資源中，以便Adobe Campaign用戶跟蹤消費者是否已選擇出售個人資訊。 <a href="https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ccpa">了解更多</a>。</li>
  </ul>
    <p>請參閱<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">作法影片</a>。</p>
</td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>MicrosoftDynamics 365整合(GA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>Adobe Campaign Standard與Microsoft動力365的整合現已推出。 您將能夠將聯繫人和自定義實體記錄從Dynamics 365轉移到Campaign ，並將電子郵件事件資料從Campaign返回Dynamics 365，以便更好地進行銷售/市場營銷協調。</p>
    <p>請參閱 <a href="../../integrating/using/d365-acs-get-started.md">詳細文檔</a> 來設定整合。</p>
  </td>
  </tr> 
 </tbody> 
</table>

**功能改進**

* 動態報告的同意彈出窗口已更新，將Adobe Campaign Standard和Microsoft動力365整合納入其中。 通過接受條款，在使用Adobe Campaign Standard/MicrosoftDynamics 365整合和動態報告時將包括配置檔案資料。 [閱讀更多內容](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* 已修復在接收交貨預警時顯示不正確聯繫日期的問題。
* 當使用未知上下文參數提交事務性消息事件時，市場活動現在會返回「400」錯誤消息，而不是「500」。 (CAMP-28632)
* 新 **排除證明** 段已添加到動態報告中。 現在，預設情況下選擇此段以篩選報表。 [深入了解](../../reporting/using/list-of-components-.md#segments)
* 的 **消息過期** 已添加到推送通知。 它允許您指定消息不再由Apple(APNS)或Android(FCM)發送的過期日期。 [深入了解](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* 對 **載入檔案** 活動：工作流日誌已更清晰，並更詳細地說明了在檔案載入失敗時發生的錯誤。 激活出站轉換時生成的 **將拒絕項保留在檔案中** 選項已更名 **拒絕**。 [深入了解](../../automating/using/load-file.md)
* 已將多語言相關日誌添加到發送日誌中，以便更好地瞭解由於上載的CSV檔案中缺少語言而導致的發送失敗。

**安全性改善功能**

* 通過隱私請求刪除量化配置檔案的資訊時解決了問題，該請求刪除了隔離清單中除電子郵件地址之外的所有資料。
* 已增強安全性，以防止電子郵件頭中的注入。
* 加強了安全性，以防範可使用xtk表達式(電子郵件HTML、文本內容和主題、SMS和推送通知內容)的SSRF攻擊。

**電子郵件設計工具增強功能**

* 修復了在插入電子郵件時無法跟蹤取消訂閱、訂閱和登錄頁連結的問題。 (CAMP-37809)
* 修復了在建立新電子郵件和選擇模板時可能導致錯誤的問題。 (CAMP-38000)
* 使用電子郵件設計器編輯連結時，現在可以使用 **下划線連結** 的雙曲餘切值。 另外， **目標** 屬性已添加，預設值設定為 **無**。 [深入了解](../../designing/using/styles.md#about-styling-links)
* 修復了電子郵件正文文本元件中連結的顏色問題。 (CAMP-37330)
* 修復了刪除影像時阻止刪除關聯連結的問題。 (CAMP-37234)
* 修復了一個問題，這樣就無法保存對 **訂單** 動態內容的設定。 (CAMP-36883)
* 已修復搜索登錄頁時的問題。 搜索已從最初建立的50擴展到所有資料庫。 (CAMP-36839)
* 在中保存對電子郵件發件人的修改時修復了問題 **發件人：名稱** 的子菜單。 (CAMP-36606)
* 已修改傳送器元件相容性警告以反映支援的電子郵件客戶端。
* 已修復移動設備上的顯示問題。 height屬性現在始終設定為「height:auto」。 (CAMP-35497)
* 修復了從結構元件刪除片段時HTML中保留樣式和元標籤的問題。 (CAMP-35390)
* 在更新可重用內容時修復了帶片段的問題。 (CAMP-35186)
* 在電子郵件中僅顯示移動條件內容時，已修復問題。 (CAMP-35155)
* 已修復隨機顯示零寬度非斷開空格的問題。 (CAMP-35116)
* 修復了按鈕在 **另存為片段** 對話框。
* 在影像標題和可選文本中添加HTML標籤時，已修復預覽問題。
* 在電子郵件設計器中編輯在舊版編輯器的電子郵件中建立的連結時，已修復問題。
* 已修復內容中留有重複樣式標籤的問題。
* 在電子郵件中插入個性化欄位時，使用日期格式解決了問題。
* 解決了從HTML模式切換為純文字檔案時的保存問題。
* 按一下在內聯樣式屬性面板中添加邊距值的鎖定和解鎖選項時，已修復問題。
* 解決了移動預覽大小的問題，以便更好地呈現。
* 解決了模板和片段中按鈕大小的問題。
* 在插入按鈕元件時修復了影像大小問題。

**其他變更**

* 在交貨KPI頁和「動態報告」頁上顯示資料的預設時間範圍已對齊，以防止報告結果中出現差異。 (CAMP-35148)
* 應用程式證書過期時，日誌中已添加錯誤消息。
* 負載計算預覽現在包括自定義欄位大小，以防止推送通知失敗。 (CAMP-35303)
* 名稱 **拒絕檔案** 的 **載入檔案** 活動現在可以與 **檔案導出** 的子菜單。
* 所有未連結到任何現成實體的自定義實體現在都可以通過API訪問。
* 提高了大型資源上的資料庫效能。
* 對發送SMS消息時出現的一些錯誤的描述已經更清楚。 (CAMP-36558)
* 執行工作流時，現在顯示一條錯誤消息 **調度程式** 直接或通過多個活動連接到自身的活動，因為這可能導致實例的工作流伺服器被卡住。
* 對幫助排除事務性消息傳遞的問題進行了改進：「資料」連結已在事件配置螢幕中更名為「上次事務事件」，它現在按降序列出接收的事件。 此外，還建立了新的事務性事件狀態：&quot;目標失敗&quot;。 當事務性消息傳遞模組未能豐富用於消息目標的連結時，事務性事件現在將處於此新狀態（而不是「routingFailed」狀態）。
* 在限制登錄頁訪問特定地理或組織單位時對介面進行了改進。 目的是警告登錄頁可能受可見性條件的影響：建立登錄頁時必須選擇地理和組織單位。 一旦選擇了設備，就會顯示包含相關資訊的標題。 測試登錄頁時顯示的錯誤消息已更清晰。
* 在Campaign StandardAPI中，如果鍵值與源鍵不同，或者您使用自己的業務鍵作為URI而不是Adobe提供的業務鍵，則無法使用PATCH操作修改自定義鍵。
* &quot;阿爾巴尼亞語 — 馬其頓語&quot;已添加到首選語言下拉清單中。 (CAMP-35396)

**修補程式**

* 修復了阻止對計畫報告進行排序或搜索的問題。
* 已修復導致AND和OR規則混合的Triggers規則問題。
* 已修復在啟動中將Mobile屬性顯示為「已刪除」的問題。 (CAMP-35382)
* 已修復阻止Adobe啟動移動屬性在Adobe Campaign同步的問題。 (CAMP-35411、CAMP-35089、CAMP-35014、CAMP-35487)
* 修復了在事件富集配置檔案資料時事務推送消息失敗的問題。 (CAMP-34385)
* 解決了移動屬性未在多個環境上同步的問題。 (CAMP-37060)
* 在推送通知中使用聯繫人日期公式選擇模板時，已修復問題。 (CAMP-35300)
* 已修復可能導致消息發送服務崩潰的問題。 (CAMP-35287)
* 已修復具有循環直接郵件的問題，這些郵件都是使用第一個事件日期定義的。 (CAMP-35139)
* 已修復新擴展的問題 **配置檔案** 無法用於查詢的自定義資源。 (CAMP-35119)
* 已修復 **修復資料庫結構** 已激活「共用」配置的實例的模式。 (CAMP-35118)
* 已修復在廣播上添加聚合資料時導致SQL日誌錯誤的問題。 (CAMP-35034)
* 在建立 **分段** 的子菜單。 (CAMP-35033)
* 已修復 **查詢** 阻止 **加密_aescbc解密** 函式 **加密_aescbc加密** 的子菜單。 (CAMP-34952)
* 已修復可能阻止 **跟蹤日誌** 在交貨中顯示。 (CAMP-34855)
* 修復問題，使用 **發送時間優化** 自定義日期公式，它可以防止由於工作流的其他資料出錯而發送推送通知。 (CAMP-30336)
* 已修復可能阻止發佈自定義資源的問題。 (CAMP-37425)
* 已修復阻止管理員用戶修改導入包的問題。  (CAMP-37176)
* 已修復工作流中的問題，如果傳遞活動連接到空，則無法發送證據 **閱讀受眾** 的子菜單。 (CAMP-37164)
* 已修復阻止將自定義資源導入到新環境中的問題。 (CAMP-36506)
* 修復了熱點按一下報告中可能導致百分比被影像隱藏的問題(CAMP-36407)
* 已修復嘗試導出交貨說明欄位時出現的問題。 (CAMP-35467)
* 已修復一個問題，該問題可能使交貨狀態在交貨完成後仍為「開始掛起」。 (CAMP-35355)
* 修復了在啟用後禁用SQL日誌後無法顯示工作流日誌的問題。

## 發行版本 19.3 – 2019 年 7 月 {#release-19-3---july-2019}

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
   <td> 外部API活動(Public Beta)<br /> </td> 
   <td> <p>為了實現更深入的個性化，「外部API活動」允許您通過REST API調用將來自外部系統的資料帶入工作流。 REST端點可以是客戶管理系統、Adobe I/O Runtime或Adobe Experience CloudREST端點（例如資料平台、目標、分析、市場活動）。</p><p>此功能目前處於公共測試版。</p><p>如需詳細資訊，請參閱<a href="../../automating/using/external-api.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">作法影片</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流段報告<br /> </td> 
   <td> <p>此功能使營銷人員能夠按段代碼細分其交付效能。 當您建立工作流並使用分段活動將段分配給交貨總量時，這些段現在可以進入相同的交貨。 這允許您根據單個交貨中的多個段顯示開啟/按一下統計資訊。</p><p>如需詳細資訊，請參閱<a href="../../reporting/using/creating-a-report-workflow-segment.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">作法影片</a>。</p></td>
  </tr> 
 </tbody> 
</table>

**安全性改善功能**

* 已修復安全問題以防止拒絕服務(DoS)攻擊獲取映像的無效請求。 (CAMP-33454)

**電子郵件設計工具增強功能**

* 已修復每次添加元件時向HTML模板添加附加HTML樣式標籤的問題，這可能會顯著增加模板的大小。 (CAMP-34694)
* 已修復可能阻止某些右上工具欄菜單選項可用的問題。 (CAMP-34577)
* 已修復將鏡像頁URL內容塊插入電子郵件內容時出現的問題。 (CAMP-34779)
* 修復了在電子郵件中使用JSPP代碼時出現的問題，使內容難以編輯。 (CAMP-34574)
* 修復了在將超連結添加到影像上時導致影像在頂部截斷的問題。 (CAMP-34382)
* 已解決將電子郵件設計器與Firefox配合使用時的顯示問題。 (CAMP-34364)
* 修復了在電子郵件中定義動態內容時高級模式出現的幾個問題。 (CAMP-34351、CAMP-34333、CAMP-34331)
* 修復了動態內容規則編輯器(CAMP-34304、CAMP-34303)出現的幾個問題。
* 已修復可能阻止「電子郵件設計器設定」窗格(CAMP-33749)中顯示「連結」欄位的問題。
* 已解決發送電子郵件中超大的YouTube表徵圖的問題。 (CAMP-33726)
* 已修復使鏡像頁面內容可編輯的安全問題。 (CAMP-33691)
* 已修復在動態內容中使用大於符號時中斷HTML輸出的問題。 (CAMP-33688)
* 修復了在電子郵件設計器中編輯文本時使用「撤消」選項時出現的問題。 (CAMP-32565)
* 修復在撤消樣式而不是刪除樣式時建立額外標籤的問題。 (CAMP-32359)
* 您現在可以定義電子郵件中使用的每個元件是否僅顯示在案頭設備上或僅在移動設備上。
* 現在可以設定社交內容元件的寬度和高度。
* 修復了刪除動態內容後阻止刪除動態內容舊原始碼的問題。
* 已修復一個問題，該問題可能會阻止修改電子郵件主題後對其進行更新。
* 已修復一旦將n:n列結構拖放到工作區中就無法選擇的問題。
* 已修復導致電子郵件縮略圖在電子郵件儀表板中顯示模糊的問題。
* 已修復一個問題，該問題使Outlook中接收的電子郵件無法正確顯示背景。
* 已修復電子郵件設計器首頁上的某些排序問題。
* 已修復在使用動態內容時複製變型上出現的問題。
* 已從「電子郵件設計器設定」窗格中刪除一些不需要的欄位。

**其他改善項目**

* 通過與Adobe Experience Platform定位服務的整合，Adobe Campaign現在可相容，通過Experience PlatformSDK向移動應用程式的訂戶發送基於位置的營銷消息。 如需詳細資訊，請參閱[詳細文件](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)以瞭解詳情。
* 已改進報告功能以獲得更好的體驗。 要使用此功能，您需要接受動態報告使用協定。 有關詳細資訊，請參閱 [詳細文檔](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。
* 在工作流中，已添加一個新選項來預覽工作流的下一個十個執行。 有關詳細資訊，請參閱 [詳細文檔](../../automating/using/scheduler.md)。
* 在「計畫程式」活動中，新選項允許您為每月交貨選擇特定周的特定日期。 有關詳細資訊，請參閱 [詳細文檔](../../automating/using/scheduler.md)。
* 在建立沒有匯總期間的循環交貨時，交貨控制面板現在允許您在發送交貨之前請求確認。 有關詳細資訊，請參閱 [詳細文檔](../../sending/using/confirming-the-send.md)。
* 現在，您可以使用工作流外部信號活動中聲明的事件變數對遞送的標籤進行個性化設定。 有關詳細資訊，請參閱 [詳細文檔](../../automating/using/calling-a-workflow-with-external-parameters.md)。
* GDPR刪除查詢已得到改進，以獲得更好的效能。 (CAMP-33504)
* 已從外部帳戶配置介面中刪除「ftp」選項。 (CAMP-34472)
* 現在，您可以為每個電子郵件啟用和禁用SMTPtest模式選項。 有關詳細資訊，請參閱 [詳細文檔](../../administration/using/configuring-email-channel.md#smtp-test-mode)。 (CAMP-34602)

**其他變更**

* 在傳遞屬性介面中添加了警告。 它指定交貨是根據其聚合期間準備的，並解凍以每天多次調用工作流，您應確保它們沒有任何期間。 (CAMP-34393)
* 已在自定義資源配置螢幕中添加警告。 我們建議對自訂資源 ID 使用最多 30 個字元。這也適用於自訂資源欄位、索引和連結。
* 嘗試刪除登錄頁用作確認消息的事務性消息時，現在會顯示一條消息。
* 當活動已運行超過6小時時，工作流日誌中現在會顯示警告。 這不適用於推送通知、傳遞、信號、開始、結束、分叉、AND-joint、調度和等待活動。
* 當達到同時運行的最大工作流數時，工作流日誌中現在會出現警告。
* 已暫停或失敗狀態超過7天的工作流現在將停止，以減少磁碟空間的消耗。 清除任務顯示在工作流程記錄檔中。
* 使用「傳輸檔案」活動時，如果檔案大小超過可用磁碟空間，則現在將記錄錯誤。
* 無法再為In-App消息中的輔助按鈕選擇「重定向到目標URL」操作。

**修補程式**

* 已修復可能導致GDPR訪問請求失敗的問題。
* 修復了一個問題，該問題可能導致在為唯一配置檔案接收多個觸發器時丟棄觸發器。
* 已修復導致登錄後出現錯誤的自定義資源發佈錯誤消息的問題。
* 修復在建立或擴展自定義資源時顯示空白頁的問題。
* 已修復一個問題，該問題阻止將appSubscriptionrcp作為目標維度的受眾在移動交付中用於目標。
* 已修復一個錯誤，該錯誤阻止硬回放電子郵件地址被隔離。 (CAMP-24587)
* 已修復添加類型規則時出現的問題，然後在保存類型規則之前將其刪除。 (CAMP-32789)
* 修復了在禁用動態內容時可能阻止顯示登錄頁內容的問題。 (CAMP-32924)
* 修復了在主要交貨的屬性上使用個性化時發生的重複交貨問題。 (CAMP-32983)
* 已修復工作流中的問題，該問題阻止讀取包含傳入SMS消息資料的轉換的結果。 (CAMP-33134)
* 修復了將分叉和排除活動組合以建立受眾時在工作流中出現的問題。 (CAMP-33401)
* 已修復可能阻止顯示鏡像頁面內容和發送證明消息以進行定期傳遞的問題。 (CAMP-33413)
* 修復了在配置檔案和受眾之間使用聯合活動時導致錯誤的問題。 此問題是由於輸入轉換中的標識鍵不相容所致。 (CAMP-33713)
* 修復了Test活動中的問題，該問題阻止了按兩下&quot;recCount&quot;表達式時使用正確的語法。 (CAMP-33756)
* 已修復開啟計費技術工作流日誌時可能導致錯誤消息的問題。 (CAMP-34313)
* 已修復登錄頁中在配置包含預訂的複選框欄位時可能發生的問題。 (CAMP-34369)
* 修復了配置清單和向其添加「表徵圖」欄位時出現的問題。 (CAMP-34585)
* 修復了無法在「載入檔案」工作流活動中使用「|」和「%」符號作為日期或時間分隔符的問題。 (CAMP-34706)
* 已修復在登錄頁中使用帶有複選框的可見性條件時出現的問題。 (CAMP-34802)
* 修復了「富集」活動中的一個問題，如果篩選維設定為跟蹤日誌和目標維設定為要分析，則該問題會阻止欄位顯示在「其他資料」頁籤中。
* 已修復導出「workflowTemplate」資源時導致錯誤消息的問題。
* 已修復建立新配置檔案時的問題，如果從對話框中選擇了「國家/地區代碼」欄位，則無法保存該欄位。
* 已修復使用Direct Mail導入模板(updateQuarinesDeliveryLogsDirectMail)時出現的幾個問題。
* 已修復與按需資產整合相關的問題。
* 修復了放大時間軸視圖時出現的問題。 (CAMP-33628)
* 已修復一個問題，該問題防止以預定日期和時間為電子郵件即時發送證據。 (CAMP-33723)
* 已修復與事務性消息相關的問題，該消息在用戶註銷時生成錯誤日誌。 (CAMP-31698)
* 修復了計畫電子郵件時在特定環境中可能發生的錯誤。
* 已修復導致更新交付執行工作流失敗的問題。
* 已修復當主題包含多行時損壞電子郵件內容的安全問題。


## 發行版本 19.2.7 – 2019 年 7 月 {#release-19-2-7---july-2019}

**功能改進**

* GDPR刪除查詢已得到改進，以獲得更好的效能。
* 修復了在19.2升級後可能導致Web崩潰的問題。 (CAMP-34862)
* 已修復一個問題，該問題可能會阻止非管理員用戶保存或計畫報告。 (CAMP-31133)
* 使用「|」作為「載入檔案」工作流活動中的日期分隔符時，已修復問題。 (CAMP-34706)

## 發行版本 19.2.4 – 2019 年 6 月 {#release-19-2-4---june-2019}

**電子郵件設計工具**

* 修復了在HTML中使用空樣式標籤時防止用戶編輯片段的問題。 這是2014年CAMP-33778的後續修19.2.3。

## 發行版本 19.2.3 – 2019 年 6 月 {#release-19-2-3---june-2019}

**電子郵件設計工具**

介紹了對19.2版本中的片段進行優化的一系列改進和修復。 新建立的片段將無縫工作。 以前生成的片段已灰顯，需要遷移到新格式。 為此，請按一下每個片段並驗證其遷移到新格式。 我們建議您在遷移所有碎片之前test幾個碎片。

* 已修復在解鎖片段後阻止用戶編輯片段的問題。 這在更新到19.2時影響了現有碎片。 (CAMP-33778)
* 使用動態內容時已修復問題。 在HTML中添加了額外的空格。

**其他改善項目**

* 已修復SMS連接器斷開後可能阻止SMS發送恢復的問題。
* 已修復啟用TLS時可能關閉SMPP連接的問題。
* 已修復啟用TLS時可能關閉SMPP連接的問題。
* 「Launch_URL_Campaign」選項已添加到「Campaign」（市場活動）中，以管理使用Adobe Experience Platform移動軟體開發工具包建立的移動應用程式的屬性。
* 修復了在上載新建立的移動屬性的證書並退出移動應用程式屬性頁後導致取消選中「沙盒環境」選項的錯誤。
* 已修復一個問題，該問題阻止您使用來自服務資源的資訊來豐富事務性消息內容。 (CAMP-33707)
* 修復了當嘗試從服務中取消訂閱配置檔案時發生的denylist登錄頁中的問題。

## 發行版本 19.2 – 2019 年 5 月 {#release-19-2---may-2019}

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
   <td> 控制面板<br /> </td> 
   <td> <p>為了幫助提高您作為管理員用戶的工作效率，您可以輕鬆監控容量並管理實例的設定（從SFTP伺服器管理開始）。</p><p>如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=zh-Hant">作法影片</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 本地通知<br /> </td> 
   <td> <p>本地通知消息允許您在新資料在其移動應用程式內可用時通知用戶，即使您無法訪問在前台運行的網際網路或移動應用程式。 本地通知由移動應用程式在特定時間和根據事件觸發。</p><p>如需詳細資訊，請參閱<a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">詳細文件</a>以瞭解詳情。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流增強 — 將負載添加到外部信號活動<br /> </td> 
   <td> <p>當從另一個工作流或REST API調用成功滿足定義的條件以與外部系統整合時，使用負載啟動工作流。 這還包括一個 <strong>test</strong> 活動，您可以在此功能上運行test。</p><p>如需詳細資訊，請參閱<a href="../../automating/using/calling-a-workflow-with-external-parameters.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">作法影片</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 登錄頁增強 — GooglereCAPTCHA<br /> </td> 
   <td> <p>利用GooglereCAPTCHA防止登錄頁上的垃圾郵件，而無需客戶採取任何操作。</p><p>如需詳細資訊，請參閱<a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">詳細文件</a>以瞭解詳情。</p></td> 
  </tr> 
 </tbody> 
</table>

**安全性改善功能**

* 修復了報告工作區中可能的點擊式安全問題。

**電子郵件設計工具增強功能**

* 已修復複製碎片並嘗試在電子郵件設計器中使用碎片時發生的問題。 (CAMP-33193)
* 修復了在電子郵件設計器介面中使用內嵌元素時建立不需要的空間的問題。 (CAMP-32163)
* 已修復在電子郵件設計器中保存電子郵件內容後刪除用戶添加的某些附加HTML標籤屬性的問題。 (CAMP-32162)
* 已修復在「電子郵件設計器」HTML模式下顯示MicrosoftOffice標籤的問題，即使在刪除該標籤後也是如此。 (CAMP-32141)
* 如果您使用電子郵件設計器的早期版本建立電子郵件，則開啟此電子郵件內容時，彈出窗口將提示用戶更新為最新版本。 (CAMP-31529)
* 修復了在將影像從電子郵件設計器建立的電子郵件中傳送到某些消息客戶端時可能會扭曲影像的問題。 (CAMP-31407)
* 修復了在HTML模式下建立時無法在純文字檔案模式下正確顯示某些元素的問題。 (CAMP-32582, CAMP-32542)
* 已修復阻止在內容模板或片段屬性中顯示50多個組織單位的問題。 (CAMP-32932)
* 在接收使用Outlook上的電子郵件設計器建立的電子郵件時，使用視區背景色解決了問題。 (CAMP-31402)
* 修復了在Outlook中開啟時可能阻止使用電子郵件設計器建立的電子郵件內容響應的問題。 (CAMP-31400)
* 修復了在電子郵件主題中使用動態內容時無法正常工作的問題。 (CAMP-32837)
* 已修復與未正確轉義的電子郵件主題相關的問題。
* 已修復阻止在電子郵件設計器左側調色板中載入片段的問題。
* 修復了在刷新片段清單時阻止在電子郵件內容編輯期間建立的片段顯示在電子郵件設計器左側調色板中的問題。
* 已修復在電子郵件中使用動態內容時出現的幾個問題。
* 修復了嘗試使用RGB值定義顏色時拾色器出現的問題。
* 修復了在手機上接收電子郵件時阻止鏡像頁面響應的問題。

**事務性消息傳遞增強**

事務性消息傳送通道中添加了幾項改進，以優化操作和效能。

* 事務性消息持續時間已延長，以確保所有消息在過期之前發送，尤其是在執行重試時。
* 通過在不同發送線程上分配負載，提高了事務性消息傳送效能。
* 事務性消息傳遞過程已經優化，以便能夠並行地對同一消息進行多次分析。
* 已修復可能導致事務推送通知的吞吐量和延遲不一致的問題。
* 已修復顯示事務性消息執行交付的不正確目標受眾的問題。
* 已修復導入包含事件配置和關聯事務消息的包時出現的問題。 有關詳細資訊，請參閱 [詳細文檔](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages)。
* 修復了從為包含產品清單的事務性消息建立的test配置檔案中刪除收集資料的問題。

**其他變更**

* 已將新選項添加到SMS外部帳戶。 它能夠限制發送SMS的MTA進程的最大數量，以便更好地控制並行連接的數量。 有關詳細資訊，請參閱 [SMS連接器協定和設定](https://helpx.adobe.com/tw/campaign/kb/sms-connector-protocol-and-settings.html) 技術。
* 在發佈具有API擴展的資源時，如果API已發佈，則它現在會在每次重新發佈時自動更新。 以前此操作是手動的，如果無法更新API，則可能會中斷此API的配置檔案或服務資源。 有關詳細資訊，請參閱 [詳細文檔](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)。
* 已從Dynamic Reporting中刪除郵遞區號維。 我們建議改用「城市」、「國家」、「州」尺寸。
* 已刪除In-App消息的「首次啟動」生命週期事件觸發器。
* 導出具有安全組的包時，它現在包含分配給每個組的角色。 (CAMP-32960)
* 在「載入檔案」(Load file)活動中，新選項允許您檢查要上載的檔案的列是否與列定義匹配。 如需詳細資訊，請參閱[詳細文件](../../automating/using/load-file.md)以瞭解詳情。(CAMP-32229)
* 現在可以使用負載啟動工作流，允許您在工作流中的活動之間使用和共用外部參數。 如需詳細資訊，請參閱[詳細文件](../../automating/using/calling-a-workflow-with-external-parameters.md)以瞭解詳情。（CAMP-29412和CAMP-29413）
* Campaign StandardAPI現在允許您使用負載更新配置檔案的地理單位和組織單位。 如需詳細資訊，請參閱[詳細文件](../../api/using/get-started-apis.md)以瞭解詳情。
* 當無法訪問資料庫中的對象時，已更清楚地瞭解錯誤消息。
* 在「提取檔案」活動中，在定義要導出的檔案名時已更新Javascript功能。 現在，「輸出」(Output)欄位中只能使用formatDate函式。 如需詳細資訊，請參閱[詳細文件](../../automating/using/extract-file.md)以瞭解詳情。
* 對自定義資源的自動序列ID生成進行了改進。 新自定義資源的主鍵現在預設為64位。
* 自定義資源發佈test模式已得到改進。 如果上次自定義資源發佈失敗且未修復，則現在將向用戶顯示警告消息。 自定義資源發佈失敗後，可以回滾到上一個工作版本。 如需詳細資訊，請參閱[詳細文件](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)以瞭解詳情。
* 在「傳輸檔案」活動中添加了新選項。 它允許您在SFTP模式下使用「檔案下載」操作時對檔案進行排序。 如需詳細資訊，請參閱[詳細文件](../../automating/using/transfer-file.md)以瞭解詳情。(CAMP-33109)

**修補程式**

* 已修復在重新載入SMS設定時可能導致記憶體洩漏到MTA的問題。
* 已修復可能阻止在修復模式下發佈資料庫更新的問題。
* 修復了導致Adobe Analytics報告和Adobe Campaign動態報告之間差異的問題。 (CAMP-25393)
* 已修復導致報告共用工作流失敗的錯誤。
* 已修復一個錯誤，該錯誤阻止用戶僅使用媒體URL發送In-App消息。
* 修復了顯示移動應用的問題，即使其證書未上載到實例。
* 修復了在使用 **瞄準Mobile應用的所有用戶** 的下界。
* 已設定新的市場活動標準實例。 （CAMP-32635和CAMP-32344）
* 修復了阻止在工作流中自定義日期公式的錯誤。 (CAMP-30336)
* 在定義自定義日期公式時，解決了一個問題，該公式可能會阻止下拉清單中的「附加資料」和「段代碼」欄位可用。 (CAMP-32383)
* 已修復一個問題，如果「傳輸檔案」和「提取檔案」活動已加密，則它們將無法發現檔案被拒絕。 (CAMP-32377)
* 已修復API中的問題，該問題可能會阻止lineCount篩選器呈現確切的總計數。 (CAMP-31424)
* 已修復登錄頁中的問題，該問題可能會阻止輸入欄位在修改後顯示更新的值。 (CAMP-31401)
* 已修復可能導致信號活動意外激活的問題。
* 修復了當受眾為空時可能阻止顯示電子郵件預覽的問題。
* 已修復「提取檔案」活動中的問題，該問題可在激活「入站轉換為空時不生成檔案」選項時生成檔案。
* 修復了導致「交付性」工作流未成功完成時關閉的問題。
* 已修復可能阻止用戶保存或計畫報告的問題。 (CAMP-31133)

## 發行版本 19.1.3 – 2019 年 3 月 {#release-19-1-3---march-2019}

**電子郵件設計工具增強功能**

* 已修復在保存模板後無法修改的問題。
* 在電子郵件中使用以前建立的模板時已修復各種問題。
* 已修復阻止在導入模板中隱藏元件的問題。

**其他改善項目**

* 已修複查看類型規則時的錯誤。 （CAMP-32059和CAMP-31849）
* 已修復阻止編輯類型規則的問題。 (CAMP-31750)
* 修復了inMail進程可能意外停止的問題。 (CAMP-31238)

## 發行版本 19.1 – 2019 年 2 月 {#release-19-1---february-2019}

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
   <td> 推送渠道報告改進<br /> </td> 
   <td> <p>Push頻道報告中添加了幾項增強功能，使您能夠更直觀地衡量用戶的參與程度。 在此版本中，我們將推送渠道度量清單擴展到三個不同的度量：印象、按一下、開啟（應用開啟），幫助您更有效地測量和分析用戶與推送通知的交互。 與此同時，我們也在規範這些指標的定義和實施。 推送通知內置報告也通過常用可視化和度量進行了改進。</p><p> 如需詳細資訊，請參閱<a href="../../reporting/using/push-notification-report.md">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
  <tr> 
   <td> 啟動Mobile App的整合<br /> </td> 
   <td> <p>本版本包含Adobe Campaign與Adobe Experience Platform Launch的Android和iOS擴展的GA版本以及移動軟體開發工具包的整合。 這些擴展支援推送消息、應用內消息和移動應用配置檔案更新。</p><p> 如需詳細資訊，請參閱<a href="https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
  <tr> 
   <td> 移動應用內消息<br /> </td> 
   <td> <p>此版本包含市場活動中In-App渠道的GA版本。 從功能角度看，Beta版本最顯著的補充是Mobile SDK與MCIAS(Marketing CloudIn-App Messaging Service，為SDK提供In-App規則)之間的In-App通道動態報告和安全握手。 安全握手可確保用戶的PII資料不會落入惡意手中，並使您能夠在用戶每次註銷時清除消息快取來維護共用設備上的用戶隱私。</p><p>有關詳細資訊，請參閱 <a href="../../channels/using/about-in-app-messaging.md">詳細文檔</a> 和 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">應用程式內教程</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 工作流增強<br /> </td> 
   <td> <p>已添加以下工作流功能：</p> 
    <ul> 
     <li> 現在，您可以從同一「市場活動」實例複製或貼上工作流或另一個工作流中的活動。 這樣，您可以輕鬆複製整個工作流或特定活動，並保留最初定義的設定。 如需詳細資訊，請參閱<a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">詳細文件</a>以瞭解詳情。(CAMP-20014) </li> 
     <li> 使用 <strong>載入檔案</strong> 活動，現在可以將時間戳添加到包含被拒絕記錄的檔案的名稱中。 如需詳細資訊，請參閱<a href="../../automating/using/load-file.md#configuration">詳細文件</a>以瞭解詳情。 </li> 
     <li> <strong>查詢</strong> 和 <strong>分段</strong> 活動現在允許您在活動檢索不到資料時啟用出站轉移。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**安全性改善功能**

* 已更新生成的登錄頁HTML代碼，以防止搜索引擎索引。

**電子郵件設計工具增強功能**

* 由Behance藝術家設計的一套四款響應速度最佳的電子郵件模板現已推出。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/using-reusable-content.md#content-templates)以瞭解詳情。

* 我們新的入門體驗可幫助您更快地開始建立電子郵件，並讓您更容易訪問文檔和教程。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)以瞭解詳情。

* 您現在可以根據需要靈活配置列數和寬度。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)以瞭解詳情。

* 在移動視圖中編輯時，您可以僅在移動顯示中隱藏某些元件，以有效利用空間。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)以瞭解詳情。

* 現在，您可以在現有電子郵件模板的基礎上，將自定義社交頻道添加到電子郵件模板中。
* 已修復在使用18個以上結構時無法向下滾動結構菜單的問題。 (CAMP-31173)
* 修復了在轉發包含與Adobe Campaign一起發送的預報頭的電子郵件時，在內容頂部顯示預報頭的問題。 (CAMP-30736)
* 修復了在按一下 **刷新內AEM容** 選項。 (CAMP-29984)
* 已修復了幾個妨礙使用Adobe Target動態影像的問題。
* 修復了在準備時檢索內容時阻止預覽更新的問題（如果內容以前是從URL導入的）。
* 已將YouTube表徵圖添加到 **社會** 內容元件。
* 的 **清單** 已為「電子郵件設計器」元件面板中顯示的內容元件和片段添加了視圖。

**其他改善項目**

* Adobe Campaign現在完全符合SDK V4和AEP SDK應用程式的FCM。
* Adobe Campaign支援Android作業系統的Wear OS推送通知以及Apple的watchOS推送通知。
* 在介面中導航時可能顯示的警告和錯誤消息已變得更清晰，更易於理解。
* 現在，您可以添加到與選擇加入和選擇退出相關的配置檔案清單列（「不再聯繫……」欄位）。
* 「配置檔案建立」螢幕中的「時區」下拉清單已從「地址」部分移到介面的上部。
* 現在，在配置自定義資源螢幕時可以添加分隔符，從而將欄位組織為類別。

   如需詳細資訊，請參閱[詳細文件](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)以瞭解詳情。

**其他變更**

* Adobe Campaign和Adobe Experience Cloud將從2019年春季起放棄對MicrosoftInternet Explorer 11和第19.2號Campaign Standard的支援。 請切換至 Microsoft Edge 或其他支援的瀏覽器。請參閱 [已棄用和已刪除的功能](../../rn/using/deprecated-features.md) 的子菜單。
* 的 **國家/地區代碼** 配置檔案資源中的欄位已更名為 **國家/地區代碼**。

**修補程式**

* 已修復在將test配置檔案添加到電子郵件事務性消息時阻止發送消息的問題。 (CAMP-29854)
* 修復了在同時觸發從所有通道發送的消息時，如果一個通道的發送量較低，則會減慢從其他通道發送消息的速度的問題。
* 修復了導致MTA在尚未建立外部帳戶連接時開始發送SMS消息的問題。
* 已修復計畫程式活動執行頻率和開始時間出現的問題。 (CAMP-30745)
* 修復了使用擴展配置檔案資源時PKEY生成可能出現的問題。 (CAMP-30285)
* 已修復基於日曆日的已多次聯繫的規則可能出現的問題。 (CAMP-30136)
* 已修復嘗試訪問名稱以&quot;Base&quot;結尾的自定義資源時可能出現的問題。 (CAMP-30109)
* 修復了無法使用PATCH呼叫將配置檔案訂閱到服務的問題。 (CAMP-29728)
* 修復了通過「載入檔案」活動導入XML檔案時可能損壞工作流的問題。 （CAMP-29208和CAMP-28205）
* 已修復連結自定義資源時的問題，這可能會阻止生成反向基數連結。 (CAMP-30476)
* 已修復僅使用段代碼時無法擴展交貨日誌的問題。
* 已修復在工作流中使用「檔案傳輸」活動時可能會重複行的問題。
* 已修復在選定時間無法發送計畫報告的問題。
* 已修復導致工作流中應用內交付的「要交付」和「已發送」KPI之間差異的問題。
* 已修復無法跟蹤使用自定義HTML創作的In-App消息的問題。
* 修復了在工作流中使用時阻止保存In-App傳遞內容的問題。
* 修復了阻止管理員顯示移動應用程式的問題。
* 已修復導致「可交付性更新」技術工作流失敗的問題。 (CAMP-26387)
* 修復了在建立In-App傳遞時導致目標配置檔案與在傳遞儀表板中顯示的配置檔案之間的差異的問題。 (CAMP-28722)
* 已解決市場活動和資產核心服務整合問題，這可能會阻止您在電子郵件中選擇共用資產。

## 發行版本 19.0 – 2019 年 1 月 {#release-19-0---january-2019}

**有哪些新功能？**

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 電子郵件設計器一般可用性<br /> </td> 
   <td> <p>新的直觀電子郵件設計器（以前稱為Creative Designer）已遷至GA。 它現在支援舊式內容編輯器的所有功能，包括：</p> 
    <ul> 
     <li> 使用 <a href="../../integrating/using/adding-target-dynamic-content.md">Adobe Target動態影像</a> </li> 
     <li> 能夠 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">在準備時自動從URL檢索內容</a> </li> 
     <li> 完全相容 <a href="../../designing/using/using-reusable-content.md#content-templates">現成內容模板</a>。 </li> 
    </ul> 
    <p>如需詳細資訊，請參閱<a href="../../designing/using/designing-content-in-adobe-campaign.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">作法影片</a>。下面列出了改進和修復。</p><p>因此，現在不建議使用舊式電子郵件內容編輯器。 有關詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hant#release-notes">頁</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 事務性電子郵件中的產品清單<br /> </td> 
   <td> <p>您現在可以在事務性電子郵件中引用一個或多個產品集合。 例如，您可以自動發送購物車放棄電子郵件，其中列出用戶購物車中的所有產品，並包含影像、價格和指向每個產品的連結。</p><p>如需詳細資訊，請參閱<a href="../../designing/using/using-product-listings.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">作法影片</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件設計器中的移動視圖<br /> </td> 
   <td> <p>現在，您可以在編輯電子郵件內容時切換到專用的移動視圖。 這允許您通過單獨編輯移動顯示的所有樣式選項來微調電子郵件的響應設計，如調整邊距、較小字型大小、不同背景顏色等。</p><p> 如需詳細資訊，請參閱<a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
  <tr> 
   <td> 應用內消息測試版改進<br /> </td> 
   <td> <p>In-App消息傳遞測試版功能已通過以下功能得到增強：</p> 
    <ul> 
     <li> In-App Beta通道符合GDPR </li> 
     <li> 與Analytics API整合以填充觸發器下拉清單 </li> 
     <li> 交貨模板的直觀外觀和描述 </li> 
     <li> 從可用性角度對創作介面的增強 </li> 
    </ul> <p>如需詳細資訊，請參閱<a href="../../channels/using/about-in-app-messaging.md">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* 現在，「載入資料」活動中的一個新選項允許您將後處理階段應用於包含拒絕記錄的檔案(例如 壓縮郵遞區號格式)。(CAMP-24521)
* 「更新資料」活動中的一個新選項現在允許您配置要上載的資料的最大批處理大小。 (CAMP-28400)
* 已改進配置檔案的地址狀態選擇。 選擇國家（地區）時，「狀態」(State)下拉清單現在將自動更新為相關的狀態值。 (CAMP-28874)
* 如果入站轉換為空，則「提取檔案」活動中的一個新選項現在會阻止生成檔案。 這樣可避免在SFTP伺服器上建立和上載空檔案。
* 「交付摘要」報告已改進。
* 定義配置檔案地址時可用的國家/地區清單已經豐富。 (CAMP-26707)
* 嘗試導入內置工作流時，現在會顯示錯誤消息。

**電子郵件設計工具**

* 修復了在電子郵件模板或使用電子郵件設計器建立的內容片段上啟用地理單元功能的問題，儘管在Adobe Campaign禁用了此功能，這使得在嘗試再次訪問時模板或片段不可用。 (CAMP-28174)
* 修復了在使用電子郵件設計器編輯內容時無法保存動態內容條件的問題。 (CAMP-27905)
* 修復了在電子郵件設計器中編輯消息的純文字檔案版本並中斷HTML同步後從電子郵件內容中刪除HTML版本的問題。 (CAMP-28507)
* 修復了在使用Internet Explorer 11時阻止開啟電子郵件設計器介面的問題。 (CAMP-28273)
* 修復了使用電子郵件設計器的按鈕應用的樣式設定的MicrosoftOutlook呈現失真的問題。
* 修復了電子郵件設計器中的一個問題，該問題使URL可以從電子郵件中使用的內容片段進行編輯，而該內容片段在預設情況下處於鎖定狀態，因此不預期會出現。
* 已修復導致Email Designer分隔元件無法顯示在Microsoft辦公室的問題。
* 修復了在使用舊式電子郵件內容編輯器查看從同步的內容時導致某些Internet瀏覽器AEM頁面凍結的問題。 (CAMP-29068)
* 修復了使用舊式電子郵件內容編輯器時按一下電子郵件中任何影像時出現的錯誤。 (CAMP-30424)
* 修復了在使用電子郵件設計器編輯電子郵件時阻止顯示新建立的片段的問題。 (CAMP-29928)
* 已修復一個問題，該問題阻止按鈕文本在使用電子郵件設計器建立的電子郵件中正確顯示，並且使用Outlook Webmail客戶端接收。
* 現在，可以使用電子郵件設計器建立配置檔案事務性消息。 (CAMP-28900)
* 修復了電子郵件設計器中的一個錯誤，該錯誤使內容在準備時從URL自動檢索內容時處於可編輯狀態，但應將其鎖定。

**修補程式**

* 修復了動態報告中顯示不正確的傳遞日誌的問題。 (CAMP-23446)
* 已修復可能影響彈出摘要報告數字的問題(CAMP-28703)
* 已解決市場活動和資產核心服務整合問題，這可能會在選擇時阻止顯示資產 **[!UICONTROL Image shared from Adobe Experience Cloud]** 28732)。
* 已修復一個問題，該問題阻止發送包含「oe」字元的SMS消息，即使在SMPP外部帳戶中已授權音譯。 (CAMP-29041)
* 已修復在工作流中使用分段活動時可能顯示重複記錄的問題。 (CAMP-28743)
* 修復了無法刪除工作流活動中某列上的值映射之一的問題。 (CAMP-28708)
* 在使用帶有「Test以查看檔案是否存在」選項的通配符時，修復了「檔案傳輸」活動中的問題。 (CAMP-28977)
* 已修復「檔案傳輸」活動中更新外部帳戶設定時可能發生的問題。 (CAMP-28894)
* 使用「電子郵件不為空」條件時，已修複查詢編輯器中自定義篩選器的問題。 (CAMP-28741)
* 已修復導出具有超過100k記錄的自定義資源表時可能出現的問題。 (CAMP-28150)
* 已修復阻止刪除連結到觸發器的事務性消息的問題。 (CAMP-28385)
* 已刪除某些SMS日誌中不安全顯示的密碼。
* 已修復因Adobe Campaign發送的空密碼而導致與SMPP模擬器的連接失敗的問題。
* 已修復在SMS連接不穩定時阻止發送市場活動的問題。
* 已修復在動態報告中顯示已刪除交貨的問題。
* 修復了在使用工作流中的「富集」活動時，無法從傳遞日誌、跟蹤日誌和排除日誌表中檢索其他資料的問題。
* 已修復GDPR刪除請求的問題，該請求在使用「N基數收集連結」連結類型和「刪除目標籤錄意味著刪除連結的記錄引用」選項時可能發生。
* 已解決報告共用問題。
* 已修復在發送推送通知時可能導致吞吐量問題的問題。
* 已修復直接郵件輸出檔案缺少欄位的問題。
* 已修復允許用戶修改內置工作流的問題。
* 基於包括具有已配置提取活動的工作流的市場活動模板建立市場活動時，已修復問題。 (CAMP-29198)
* 修復了「檔案提取」活動的問題，該活動阻止對多個元素使用同一表達式。 (CAMP-29182)
* 在查詢編輯器中修復了rtEvent的broadlog和跟蹤日誌之間的連接條件。 (CAMP-28780)
* 已修復一個問題，該問題阻止保存對「特定操作」登錄頁選項的修改。 (CAMP-29422)
* 已修復阻止在工作流中導出事件負載的問題。 (CAMP-29029)
* 已修復阻止在SMS消息中排除denylist上的SMS號的問題。 (CAMP-28898)
* 已修復一個問題，該問題可能會阻止SMPP提供程式在處理傳入消息時出錯時收到通知。 (CAMP-29804)
* 已修復允許刪除關聯交貨的外部帳戶的問題。 (CAMP-29738)
* SMS消息的發送吞吐量已得到改善和穩定。
* 已修復阻止SMS消息中使用「~」字元的問題。 (CAMP-29172)
* 使用「發送時間優化」選項修復交貨中的問題。 (CAMP-29231)
