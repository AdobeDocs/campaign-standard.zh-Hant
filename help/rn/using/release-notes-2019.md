---
title: 發行說明 2019 年
description: 本頁列出2019年版本的所有Adobe Campaign Standard。
page-status-flag: never-activated
uuid: 99f92a54-4b3d-48b9-b08d-e98b24e75f62
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: e54f8305-7e32-4193-8e5a-b5d87b03038c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 85dc2b3ba9a781483f88238fbf5a9208a0c18c37
workflow-type: tm+mt
source-wordcount: '7626'
ht-degree: 3%

---


# 發行說明 2019 年{#release-notes-2019}

[發行計畫](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) |控 [制面板版本](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |文 [件更新](../../rn/using/documentation-updates.md) |最 [新發行說明](../../rn/using/release-notes.md) |已過 [時的功能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## 發行版本19.4 - 2019年12月 {#release-19-4---october-2019}

**新增功能?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>加州消費者隱私法(CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA是加州新推出的隱私法，協調並現代化2020年1月1日生效的資料保護要求。 CCPA適用於持有居住在加州之資料主體資料的Adobe Campaign客戶。</p>
   <p>除了Adobe Campaign中已提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）外，我們還將利用這個機會加入其他功能，以協助您做好CCPA的準備：</p>
   <ul>
    <li>存取權與刪除權： 我們運用了為GDPR新增的功能。 <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">進一步瞭解</a> </li>
    <li><p>在建立隱私權要求時，隱私權核心服務中已新增規則類型（GDPR或CCPA）。 此方法應用於所有存取和刪除請求。 不建議使用促銷活動API和介面來存取和刪除請求。  請參閱「已過 <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">時和已移除的功能」文章</a>。</p></li>
    <li>「設 <strong>定檔」資源已新增「CCPA選擇退出</strong> 」欄位，讓Adobe Campaign使用者追蹤消費者是否選擇退出個人資訊銷售。 <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#ccpa">進一步瞭解</a>。</li>
  </ul>
    <p>請參閱 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">how-to影片</a>。</p>
</td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Dynamics 365整合(GA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>Adobe Campaign Standard和Microsoft Dynamics 365之間的整合現已推出。 您將能夠將您的連絡人和自訂實體記錄從Dynamics 365傳輸至Campaign，並從Campaign將電子郵件事件資料傳回Dynamics 365，以便更好地協調銷售／行銷。</p>
    <p>請參閱詳 <a href="../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md">細檔案</a> ，以設定此整合併檢 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/campaign-and-microsoft-dynamics-365/working-with-campaign-standard-and-microsoft-dynamics-365.html">視操作視訊</a>。</p>
  </td>
  </tr> 
 </tbody> 
</table>

**改進**

* 動態報告的同意彈出式選單已更新，加入Adobe Campaign Standard和Microsoft Dynamics 365整合。 接受條款後，使用Adobe Campaign Standard / Microsoft Dynamics 365整合和動態報告時，將會包含描述檔資料。 [閱讀詳細內容](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* 修正在接收傳送警報時顯示錯誤聯絡日期的問題。
* 當使用未知的上下文參數提交交易訊息事件時，Campaign現在會傳回&quot;400&quot;錯誤訊息，而非&quot;500&quot;。 (CAMP-28632)
* 動態報 **表中已新增** 「排除」校樣區段。 現在預設會選取此區段來篩選報表。 [詳細內容](../../reporting/using/list-of-components-.md#segments)
* 「 **訊息過期** 」選項已新增至推播通知。 它可讓您指定訊息不再由Apple(APNS)或Android(FCM)傳送的到期日。 [詳細內容](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* 已對「載入檔案」活 **動進行改** 進： 工作流程記錄檔已更清楚、更詳細地說明在無法載入檔案時發生的錯誤。 啟用「保留檔案中的拒 **絕」選項時產生的去話轉場** ，已重新命 **名為「拒絕」**。 [詳細內容](../../automating/using/load-file.md)
* 已將多語言相關記錄檔新增至傳送記錄檔，以更清楚瞭解因已上傳CSV檔案中缺少語言而造成的傳送失敗。

**安全性增強功能**

* 修正透過隱私權要求刪除量化描述檔資訊時，會移除隔離清單中除電子郵件地址以外的所有資料的問題。
* 已增強安全性，以防止在電子郵件標題中插入。
* 已增強安全性，以防範可使用xtk運算式（電子郵件HTML、文字內容與主題、簡訊和推播通知內容）的SSRF攻擊。

**電子郵件設計人員增強功能**

* 修正在電子郵件中插入時，無法追蹤取消訂閱、訂閱和登陸頁面連結的問題。 (CAMP-37809)
* 修正建立新電子郵件和選取範本時，可能會導致錯誤的問題。 (CAMP-38000)
* 使用「電子郵件設計器」編輯連結時，您現在可以使用「底線」 **連結選項** 。 此外， **Target** 屬性已新增，預設值設為 **None**。 [詳細內容](../../designing/using/styles.md#about-styling-links)
* 修正電子郵件內文文字元件中連結的色彩問題。 (CAMP-37330)
* 修正刪除影像時無法移除相關連結的問題。 (CAMP-37234)
* 修正無法在條件中儲存動態內容 **「順序** 」設定的修改的問題。 (CAMP-36883)
* 已修正搜尋著陸頁面時的問題。 搜索已從最初建立的50個擴展到所有資料庫。 (CAMP-36839)
* 修正在「寄件者」中儲存電子郵件傳送者修改的 **問題： 名稱** 欄位。 (CAMP-36606)
* 轉盤元件相容性警告已修改，以反映支援的電子郵件用戶端。
* 修正行動裝置上的顯示問題。 height屬性現在一律設為「height: auto」。 (CAMP-35497)
* 修正從結構元件刪除片段時，HTML中保留樣式和中繼標籤的問題。 (CAMP-35390)
* 修正更新可重複使用內容時的片段問題。 (CAMP-35186)
* 修正在電子郵件中僅顯示行動裝置條件式內容的問題。 (CAMP-35155)
* 修正隨機顯示零寬無斷格的問題。 (CAMP-35116)
* 修正「另存為片段」對話方塊中按 **鈕位置的問題** 。
* 修正在影像標題和替代文字中新增HTML標籤時的預覽問題。
* 修正在電子郵件設計工具中編輯舊版編輯器電子郵件中建立之連結時的問題。
* 修正內容中留下重複樣式標籤的問題。
* 修正在電子郵件中插入個人化欄位時，日期格式的問題。
* 修正從HTML模式切換為純文字時的儲存問題。
* 修正按一下在內嵌樣式屬性面板中新增邊界值的鎖定和解除鎖定選項的問題。
* 修正行動預覽大小的問題，以提高演算效果。
* 修正範本和片段中按鈕大小的問題。
* 已修正插入按鈕元件時影像大小的問題。

**其他變更**

* 已對齊傳送KPI頁面和動態報告頁面上顯示資料的預設時間範圍，以防止報告結果不一致。 (CAMP-35148)
* 當應用程式憑證過期時，記錄檔中已新增錯誤訊息。
* 裝載計算預覽現在包含自訂欄位大小，以防止推播通知失敗。 (CAMP-35303)
* 現在，「載入 **檔案** 」活動中的「拒絕檔案 **」檔案名稱可以與「檔案匯出****** 」活動相同地個人化。
* 所有未連結至任何現成可用實體的自訂實體現在都可透過API存取。
* 已改善大型資源的資料庫效能。
* 傳送SMS訊息時發生的一些錯誤說明已更清楚。 (CAMP-36558)
* 現在，在執行直接或通過多個活動連接到自身的工作流的 **Scheduler** activity時，會顯示一條錯誤消息，因為這可能導致實例的工作流伺服器卡住。
* 已做出改進，幫助排除事務性消息傳送故障： 「資料」連結在事件設定畫面中已重新命名為「上次交易事件」，現在會以遞減順序列出已接收的事件。 此外，還建立了新的事務事件狀態： &quot;targetingFailed&quot;。 當事務性消息傳遞模組無法豐富用於消息定位的連結時，事務性事件現在將處於此新狀態（而不是「routingFailed」狀態）。
* 已對介面進行改良，以限制對特定地理或組織單位的著陸頁面存取。 其目的是警告著陸頁面可能受可見性條件所限： 現在，在建立著陸頁面時，必須選擇地理單位和組織單位。 選取裝置後，現在會顯示包含相關資訊的橫幅。 測試著陸頁面時顯示的錯誤訊息已變得更清楚。
* 在Campaign Standard API中，如果索引鍵值與原始索引鍵不同，或您使用自己的商業索引鍵作為URI而非Adobe提供的商業索引鍵，則無法使用PATCH操作來修改自訂索引鍵。
* &quot;阿爾巴尼亞——馬其頓&quot;語已添加到首選語言下拉清單中。 (CAMP-35396)

**修補程式**

* 修正排程報表無法排序或搜尋的問題。
* 修正觸發器規則造成AND和OR規則混合的問題。
* 修正Mobile屬性在啟動中顯示為「已刪除」的問題。 (CAMP-35382)
* 修正Adobe Launch行動裝置屬性無法在Adobe Campaign中同步的問題。 (CAMP-35411、CAMP-35089、CAMP-35014、CAMP-35487)
* 修正當事件富含描述檔資料時，交易推播訊息失敗的問題。 (CAMP-34385)
* 修正行動裝置屬性無法在多個環境上同步的問題。 (CAMP-37060)
* 修正在推播通知中使用連絡人日期公式選取範本的問題。 (CAMP-35300)
* 修正訊息傳送服務可能當機的問題。 (CAMP-35287)
* 已修正重複性直接郵件的問題，這些郵件全都以第一個事件日期定義。 (CAMP-35139)
* 修正新擴充的描述檔 **自訂資源** ，無法用於查詢的問題。 (CAMP-35119)
* 已修正啟 **用「共用配置** 」的實例的「修復」資料庫結構模式。 (CAMP-35118)
* 修正在Broadlogs上新增匯整資料時，導致SQL記錄檔錯誤的問題。 (CAMP-35034)
* 修正建立區段活動時的轉場 **問題** 。 (CAMP-35033)
* 修正 **Query** 活動中， **encryption_aescbcDecrypt函式無法解密****** encryption_aescbcEncrypt函式的問題。 (CAMP-34952)
* 修正無法在傳送中顯 **示追蹤記錄** 的問題。 (CAMP-34855)
* 修正使用「傳送時間最佳化」自訂日期公式時 **** ，由於工作流程的其他資料發生錯誤，推播通知無法傳送的問題。 (CAMP-30336)
* 修正無法發佈自訂資源的問題。 (CAMP-37425)
* 修正管理員使用者無法修改匯入封裝的問題。  (CAMP-37176)
* 修正當傳送活動連結至空白的「讀取」對象活動時，工作流中無法傳送校樣 **的問題** 。 (CAMP-37164)
* 修正自訂資源無法匯入新環境的問題。 (CAMP-36506)
* 修正Hot Click報表中，可能導致百分比被影像隱藏的問題(CAMP-36407)
* 修正嘗試匯出傳送說明欄位時發生的問題。 (CAMP-35467)
* 修正雖然傳送完成，但傳送狀態仍可能維持為「開始擱置中」的問題。 (CAMP-35355)
* 修正在啟用後，再停用SQL記錄檔後，無法顯示工作流程記錄檔的問題。

## 發行版本19.3 - 2019年7月 {#release-19-3---july-2019}

**新增功能?**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 外部API活動（公開測試版）<br /> </td> 
   <td> <p>為了更深入的個人化，「外部API活動」可讓您透過REST API呼叫，將外部系統的資料匯入工作流程。 REST端點可以是客戶管理系統、Adobe I/O Runtime或Adobe Experience Cloud REST端點（例如資料平台、Target、Analytics、Campaign）。</p><p>此功能目前為公開測試版。</p><p>如需詳細資訊，請參 <a href="../../automating/using/external-api.md">閱詳細說明</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">檔案和操作視訊</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流程區段報告<br /> </td> 
   <td> <p>此功能可讓行銷人員依區段代碼來劃分其傳送效能。 當您建立工作流程並使用區段活動將區段指派給傳送人口時，這些區段現在可以進入相同的傳送。 這可讓您根據單一傳送中的多個區段來顯示開啟／點按統計資料。</p><p>如需詳細資訊，請參 <a href="../../reporting/using/creating-a-report-workflow-segment.md">閱詳細說明</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">檔案和操作視訊</a>。</p></td>
  </tr> 
 </tbody> 
</table>

**安全性增強功能**

* 已修正安全性問題，以防止拒絕服務(DoS)攻擊無效請求以取得影像。 (CAMP-33454)

**電子郵件設計人員增強功能**

* 修正每次新增元件時，都會新增其他HTML樣式標籤至HTML範本的問題，此問題可能會大幅增加範本的大小。 (CAMP-34694)
* 修正某些右上方工具列功能表選項無法使用的問題。 (CAMP-34577)
* 修正將「鏡像頁面URL」內容區塊插入電子郵件內容時發生的問題。 (CAMP-34779)
* 修正在電子郵件中使用JSPP程式碼時發生的問題，使編輯內容變得困難。 (CAMP-34574)
* 修正當超連結新增至影像時，影像頂端會截斷的問題。 (CAMP-34382)
* 修正搭配Firefox使用電子郵件設計工具時的顯示問題。 (CAMP-34364)
* 修正在電子郵件中定義動態內容時，「進階」模式發生的數個問題。 (CAMP-34351,CAMP-34333,CAMP-34331)
* 修正動態內容規則編輯器(CAMP-34304、CAMP-34303)發生的數個問題。
* 修正「電子郵件設計人員設定」窗格中無法顯示「連結」欄位的問題(CAMP-33749)。
* 已修正YouTube圖示在傳送電子郵件中過大的問題。 (CAMP-33726)
* 修正讓鏡像頁面內容可編輯的安全性問題。 (CAMP-33691)
* 修正動態內容中使用大於符號時，HTML輸出中斷的問題。 (CAMP-33688)
* 修正在「電子郵件設計器」中編輯文字時，使用「復原」選項時發生的問題。 (CAMP-32565)
* 修正復原樣式（而非移除樣式）時，會建立額外標籤的問題。 (CAMP-32359)
* 您現在可以定義電子郵件中使用的每個元件是否只會顯示在桌上型裝置上，或只會顯示在行動裝置上。
* 您現在可以設定Social內容元件的寬度和高度。
* 修正刪除動態內容後，無法移除動態內容舊原始程式碼的問題。
* 修正修改電子郵件後，無法更新其主題的問題。
* 修正將n:n欄結構拖放至工作區後無法選取的問題。
* 修正電子郵件儀表板中訊息縮圖模糊的問題。
* 修正Outlook中收到的電子郵件無法正確顯示背景的問題。
* 已修正「電子郵件設計器」首頁的排序問題。
* 修正使用動態內容時，複製變數時發生的問題。
* 「電子郵件設計器設定」窗格中已移除一些不需要的欄位。

**其他改善項目**

* 透過與Adobe Experience Platform Location Services的整合，Adobe Campaign現在可相容，透過Experience Platform SDK，將以位置為基礎的行銷訊息傳送給行動應用程式的用戶。 如需詳細資訊，請參閱[詳細文件](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)。
* 報告功能已經改善，以提供更佳的體驗。 若要使用此功能，您必須接受動態報表使用合約。 For more on this, refer to the [detailed documentation](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* 在工作流程中，已新增一個新選項，以預覽工作流程的下十個執行。 For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* 在「排程器」活動中，新選項允許您為每月傳送選擇特定周的特定日期。 For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* 在建立不含匯總期間的週期性傳送時，傳送控制面板現在可讓您在傳送傳送前要求確認。 For more on this, refer to the [detailed documentation](../../sending/using/confirming-the-send.md).
* 您現在可以使用已在工作流程外部訊號活動中宣告的事件變數，個人化傳送的標籤。 For more on this, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md).
* GDPR刪除查詢已改進，以獲得更佳的效能。 (CAMP-33504)
* 「ftp」選項已從外部帳戶設定介面中移除。 (CAMP-34472)
* 您現在可以為每個電子郵件啟用和禁用SMTP測試模式選項。 For more on this, refer to the [detailed documentation](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**其他變更**

* 傳送屬性介面中新增警告。 它會指定遞送是根據其匯總期間準備的，並解凍，以便每天多次呼叫工作流程，您應確保沒有任何期間。 (CAMP-34393)
* 自訂資源設定畫面中已新增警告。 我們建議對自訂資源ID使用最多30個字元。 這也適用於自訂資源欄位、索引和連結。
* 現在，當嘗試刪除著陸頁面使用的交易性訊息做為確認訊息時，會顯示訊息。
* 當活動已執行超過6小時時，現在工作流程記錄檔中會出現警告。 這不適用於推播通知、傳送、訊號、開始、結束、分叉、AND-joint、排程和等待活動。
* 當您達到同時執行的最大工作流程數時，現在工作流程記錄檔中會出現警告。
* 已暫停或失敗狀態超過7天的工作流程現在會停止，以減少磁碟空間。 清除任務顯示在工作流日誌中。
* 使用「傳輸檔案」活動時，如果檔案大小超過可用磁碟空間，現在會記錄錯誤。
* 「重新導向至目標URL」動作無法再針對應用程式內訊息中的次要按鈕選取。

**修補程式**

* 修正可能導致GDPR存取要求失敗的問題。
* 修正當針對獨特描述檔收到多個觸發器時，可能導致觸發器被捨棄的問題。
* 修正登入後可能導致自訂資源發佈錯誤訊息的問題。
* 修正建立或擴充自訂資源時顯示空白頁面的問題。
* 已修正以appSubscriptionrcp為定位維度的對象無法在行動傳送中定位的問題。
* 修正無法將硬性彈回數電子郵件地址放入隔離的錯誤。 (CAMP-24587)
* 修正新增排版規則，然後在儲存排版規則之前先加以刪除時所發生的問題。 (CAMP-32789)
* 修正停用動態內容時無法顯示著陸頁面內容的問題。 (CAMP-32924)
* 修正在主傳送屬性上使用個人化時，經常傳送的問題。 (CAMP-32983)
* 修正工作流程中無法從包含傳入之SMS訊息資料的轉場中讀取結果的問題。 (CAMP-33134)
* 修正結合分叉與排除活動以建立觀眾時，在工作流程中發生的問題。 (CAMP-33401)
* 修正無法顯示鏡像頁面內容，以及無法傳送重複傳送之證明訊息的問題。 (CAMP-33413)
* 修正在設定檔與觀眾之間使用「聯合」活動時，會導致錯誤的問題。 此問題是由於識別鍵在輸入轉換中不相容所造成。 (CAMP-33713)
* 修正在「測試」活動中，連按兩下&quot;recCount&quot;運算式時，無法使用正確語法的問題。 (CAMP-33756)
* 修正開啟「帳單」技術工作流程記錄檔時，可能導致錯誤訊息的問題。 (CAMP-34313)
* 修正在著陸頁面中，設定含訂閱的核取方塊欄位時可能發生的問題。 (CAMP-34369)
* 修正設定清單並新增「圖示」欄位時發生的問題。 (CAMP-34585)
* 修正無法在「載入檔案」工作流程活動中使用「|」和「%」符號作為日期或時間分隔符號的問題。 (CAMP-34706)
* 修正在著陸頁面中使用可見性條件與核取方塊時所發生的問題。 (CAMP-34802)
* 修正「擴充」活動中，如果篩選維度設定為追蹤記錄檔，而目標維度設定為描述檔，則欄位無法顯示在「其他資料」標籤中的問題。
* 修正匯出「workflowTemplate」資源時導致錯誤訊息的問題。
* 修正建立新描述檔時，如果從對話方塊選取「國家／地區代碼」欄位，則無法儲存該欄位的問題。
* 修正使用Direct Mail匯入範本(updateRegainesDeliveryLogsDirectMail)時發生的數個問題。
* 修正與隨選資產整合相關的問題。
* 修正在時間軸檢視上放大時發生的問題。 (CAMP-33628)
* 修正無法針對排程日期和時間的電子郵件訊息立即傳送校樣的問題。 (CAMP-33723)
* 修正當使用者登出時，產生錯誤記錄的交易訊息相關問題。 (CAMP-31698)
* 修正排程電子郵件訊息時，在特定環境中可能發生的錯誤。
* 修正「更新傳送」執行工作流程失敗的問題。
* 修正當主旨包含多行時，造成電子郵件內容中斷的安全性問題。


## 發行版本19.2.7 - 2019年7月 {#release-19-2-7---july-2019}

**改進**

* GDPR刪除查詢已改進，以獲得更佳的效能。
* 修正19.2升級後可能導致網頁當機的問題。 (CAMP-34862)
* 修正非管理員使用者無法儲存或排程報表的問題。 (CAMP-31133)
* 修正在「載入檔案」工作流程活動中使用「|」作為日期分隔符號的問題。 (CAMP-34706)

## 發行版本19.2.4 - 2019年6月 {#release-19-2-4---june-2019}

**電子郵件設計人員**

* 修正當HTML中使用空樣式標籤時，使用者無法編輯片段的問題。 這是19.2.3中CAMP-33778的後續修正。

## 發行版本19.2.3 - 2019年6月 {#release-19-2-3---june-2019}

**電子郵件設計人員**

在19.2版中引入了一系列改進和修正，以最佳化片段。 新建立的片段將能順暢運作。 先前建立的片段已變灰，需要移轉至新格式。 若要這麼做，請按一下每個片段並驗證其移轉至新格式。 我們建議您先測試幾個片段，然後再將其全部移轉。

* 修正使用者在解除鎖定片段後無法編輯片段的問題。 這會在更新至19.2時影響現有的片段。 (CAMP-33778)
* 修正使用動態內容時的問題。 HTML中新增了額外的空格。

**其他改善項目**

* 修正SMS連接器斷線後，SMS傳送無法繼續的問題。
* 修正啟用TLS時可能會關閉SMPP連線的問題。
* 修正啟用TLS時可能會關閉SMPP連線的問題。
* Campaign中已新增「Launch_URL_Campaign」選項，以管理使用Adobe Experience Platform Mobile SDK建立之行動應用程式的屬性。
* 修正在上傳新建立行動屬性的憑證並退出行動應用程式屬性頁面後，「沙盒環境」選項未勾選的錯誤。
* 修正無法使用「服務」資源的資訊豐富交易訊息內容的問題。 (CAMP-33707)
* 修正當嘗試從服務取消訂閱描述檔時，區塊清單著陸頁面中發生的問題。

## 發行版本19.2 - 2019年5月 {#release-19-2---may-2019}

**新增功能?**

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
   <td> <p>為協助提高管理員使用者的工作效率，您可以輕鬆監控容量並管理執行個體的設定（從SFTP伺服器管理開始）。</p><p>如需詳細資訊，請參 <a href="https://docs.adobe.com/content/help/zh-Hant/control-panel/using/control-panel-home.html">閱詳細說明</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/control-panel/control-panel-overview.html">檔案和操作視訊</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 本機通知<br /> </td> 
   <td> <p>本端通知訊息可讓您在使用者的行動應用程式中有新資料可用時，通知使用者，即使您無法存取前景中執行的網際網路或行動應用程式。 行動應用程式會在特定時間觸發本機通知，並視事件而定。</p><p>如需詳細資訊，請參閱<a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">詳細文件</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流程增強功能——將負載新增至外部訊號活動<br /> </td> 
   <td> <p>當從其他工作流程或REST API呼叫中成功符合定義的條件以與外部系統整合時，啟動具有裝載的工作流程。 此外，還包含新 <strong>的測試</strong> 活動，您可在其中執行此功能的測試。</p><p>如需詳細資訊，請參 <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">閱詳細說明</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">檔案和操作視訊</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 著陸頁面增強功能- Google reCAPTCHA<br /> </td> 
   <td> <p>運用Google reCAPTCHA來防止您的登陸頁面出現垃圾訊息，而不需要客戶採取任何動作。</p><p>如需詳細資訊，請參閱<a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">詳細文件</a>。</p></td> 
  </tr> 
 </tbody> 
</table>

**安全性增強功能**

* 修正報告工作區中的潛在點按劫持安全性問題。

**電子郵件設計人員增強功能**

* 修正復製片段並嘗試在「電子郵件設計器」中使用片段時發生的問題。 (CAMP-33193)
* 修正在「電子郵件設計器」介面中使用內嵌元素時，會建立不需要的空格的問題。 (CAMP-32163)
* 修正在「電子郵件設計器」中儲存電子郵件內容後，刪除使用者新增的其他HTML標籤屬性的問題。 (CAMP-32162)
* 修正即使移除Microsoft Office標籤後，仍會在「電子郵件設計人員HTML」模式中顯示該標籤的問題。 (CAMP-32141)
* 如果您使用舊版電子郵件設計工具建立電子郵件，在開啟此電子郵件內容時，現在會出現快顯視窗提示使用者更新為最新版本。 (CAMP-31529)
* 修正當傳送給某些訊息傳送用戶端時，使用電子郵件設計工具建立的電子郵件會扭曲影像的問題。 (CAMP-31407)
* 修正在HTML模式中建立時，某些元素（例如清單或按鈕）無法在純文字模式中正確顯示的問題。 (CAMP-32582、CAMP-32542)
* 修正內容範本或片段屬性中無法顯示超過50個組織單位的問題。 (CAMP-32932)
* 修正當收到使用Outlook上的「電子郵件設計器」建立的電子郵件時，檢視區背景顏色的問題。 (CAMP-31402)
* 修正在Outlook中開啟時，使用「電子郵件設計器」建立的電子郵件內容無法回應的問題。 (CAMP-31400)
* 修正動態內容在電子郵件主旨中使用時無法正常運作的問題。 (CAMP-32837)
* 修正與未正確逸出的電子郵件主旨相關的問題。
* 修正無法將片段載入「電子郵件設計器」左側浮動視窗的問題。
* 修正重新整理片段清單時，電子郵件內容版本期間建立的片段無法顯示在「電子郵件設計器」左側浮動視窗中的問題。
* 已修正在電子郵件中使用動態內容時發生的數個問題。
* 修正嘗試使用RGB值定義顏色時，檢色器發生的問題。
* 修正在行動裝置上接收電子郵件時，鏡像頁面無法回應的問題。

**交易式訊息增強功能**

為了優化操作和效能，已在事務性消息傳遞通道中添加了幾項改進。

* 事務性消息持續時間已延長，以確保所有消息在過期之前發送，尤其是在執行重試時。
* 通過在不同發送線程上分配負載，事務性消息傳遞效能得到了提高。
* 事務性消息傳遞流程已經優化，能夠同時對同一消息進行多重分析。
* 修正交易推播通知的吞吐量和延遲可能不一致的問題。
* 修正交易訊息執行傳送的目標對象顯示錯誤的問題。
* 修正匯入包含事件設定和相關交易訊息的套件時所發生的問題。 For more on this, refer to the [detailed documentation](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* 修正從為包含產品清單的交易式訊息建立的測試設定檔中刪除收集資料的問題。

**其他變更**

* SMS外部帳戶已新增一個選項。 它可以限制發送SMS的MTA進程的最大數量，以便更好地控制並行連接的數量。 如需詳細資訊，請參閱 [SMS連接器通訊協定和設定技術](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) 。
* 使用API擴充功能發佈資源時，如果API已發佈，現在每次重新發佈時都會自動更新。 先前此動作是手動的，且無法更新API可能會中斷此API的描述檔或服務資源。 For more on this, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* 郵遞區號維度已從動態報表中移除。 我們建議改用「城市」、「國家」、「州」維度。
* 已移除應用程式內訊息的「首次啟動」生命週期事件觸發器。
* 導出包含安全組的包時，它現在包含分配給每個組的角色。 (CAMP-32960)
* 在「載入檔案」活動中，新選項可讓您檢查您要上載的檔案欄是否符合欄定義。 如需詳細資訊，請參閱[詳細文件](../../automating/using/load-file.md)。(CAMP-32229)
* 工作流程現在可以從裝載開始，讓您在工作流程中的活動之間使用和共用外部參數。 如需詳細資訊，請參閱[詳細文件](../../automating/using/calling-a-workflow-with-external-parameters.md)。（CAMP-29412和CAMP-29413）
* Campaign Standard API現在可讓您使用裝載來更新描述檔的地理和組織單位。 如需詳細資訊，請參閱[詳細文件](../../api/using/get-started-apis.md)。
* 當無法存取資料庫中的物件時，會有更清楚的錯誤訊息，以供您瞭解。
* 在「擷取檔案」活動中，定義要匯出的檔案名稱時，已更新Javascript功能。 現在，「輸出」欄位中只能使用formatDate函式。 如需詳細資訊，請參閱[詳細文件](../../automating/using/extract-file.md)。
* 自訂資源的自動序列ID產生功能已改良。 新自訂資源的主鍵現在預設為64位。
* 自訂資源發佈測試模式已改進。 如果上次自訂資源發佈失敗且未修正，現在會向使用者顯示警告訊息。 在自定義資源發佈失敗後，可以回滾到上一個工作版本。 如需詳細資訊，請參閱[詳細文件](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。
* 在「傳輸檔案」活動中添加了新選項。 它允許您在SFTP模式下使用「檔案下載」操作時對檔案進行排序。 如需詳細資訊，請參閱[詳細文件](../../automating/using/transfer-file.md)。(CAMP-33109)

**修補程式**

* 修正重新載入SMS設定時，可能導致記憶體洩漏至MTA的問題。
* 修正無法在修復模式下發佈資料庫更新的問題。
* 修正造成Adobe Analytics報表與Adobe Campaign動態報表不一致的問題。 (CAMP-25393)
* 修正造成報表共用工作流程失敗的錯誤。
* 修正使用者無法僅使用媒體URL傳送應用程式內訊息的錯誤。
* 修正即使行動應用程式的憑證未上傳至執行個體，仍顯示該應用程式的問題。
* 修正當使用Mobile應用程式範本的「目標」所有使用者時，個 **人化欄位無法運作的錯誤** 。
* 已布建新的促銷活動標準例項。 （CAMP-32635和CAMP-32344）
* 修正無法自訂工作流程中日期公式的錯誤。 (CAMP-30336)
* 修正定義自訂日期公式時，「其他資料」和「區段代碼」欄位無法在下拉式清單中使用的問題。 (CAMP-32383)
* 修正「傳輸檔案」和「擷取檔案」活動在加密時無法找到檔案遭拒的問題。 (CAMP-32377)
* 修正API中，lineCount篩選器無法產生精確總計數的問題。 (CAMP-31424)
* 修正著陸頁面中，輸入欄位一旦修改後，便無法顯示更新值的問題。 (CAMP-31401)
* 修正可能導致訊號活動意外啟動的問題。
* 修正當對象為空時，無法顯示電子郵件預覽的問題。
* 修正「擷取檔案」活動中，在啟用「如果傳入轉場為空，請勿產生檔案」選項時，可能會產生檔案的問題。
* 修正「傳遞性」工作流程未成功完成時關閉的問題。
* 修正使用者無法儲存或排程報表的問題。 (CAMP-31133)

## 發行版本19.1.3 - 2019年3月 {#release-19-1-3---march-2019}

**電子郵件設計人員增強功能**

* 修正在儲存範本後無法修改範本的問題。
* 修正在電子郵件中使用先前建立的範本時的各種問題。
* 修正無法在匯入的範本中隱藏元件的問題。

**其他改善項目**

* 修正檢視排版規則時的錯誤。 （CAMP-32059和CAMP-31849）
* 修正無法編輯排版規則的問題。 (CAMP-31750)
* 修正inMail程式可能意外停止的問題。 (CAMP-31238)

## 發行版本19.1 - 2019年2月 {#release-19-1---february-2019}

**新增功能?**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 推播頻道報表改進<br /> </td> 
   <td> <p>推播頻道報表已新增數項增強功能，讓您以更直覺的方式測量使用者參與度。 在此版本中，我們將推播渠道量度的清單擴充為三個不同的量度： 印象、點按、開啟（應用程式開啟）可協助您更有效率地測量和分析使用者與推播通知的互動。 此外，我們也標準化這些量度的定義與實作。 推播通知內建報表也已改良，常用的視覺化和量度也已改善。</p><p> 如需詳細資訊，請參閱<a href="../../reporting/using/push-notification-report.md">詳細文件</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式的啟動整合<br /> </td> 
   <td> <p>此版本包含Adobe Campaign與Adobe Experience Platform Launch和Mobile SDK中Adobe Campaign Standard的GA版Android和iOS擴充功能的整合。 這些擴充功能支援推播訊息、應用程式內訊息和行動應用程式設定檔更新。</p><p> 如需詳細資訊，請參閱<a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">詳細文件</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式內訊息<br /> </td> 
   <td> <p>此發行包含Campaign中的GA版應用程式內渠道。 從功能角度來看，測試版中最值得注意的新增功能是「應用程式內通道動態報表」，以及Mobile SDK與MCIAS（為SDK提供應用程式內規則的Marketing Cloud應用程式內訊息服務）之間的安全握手。 安全握手可確保使用者的PII資料不會落入惡意手中，並可讓您在使用者每次登出時清除訊息快取，以維護使用者在共用裝置上的隱私權。</p><p>如需詳細資訊，請參閱詳 <a href="../../channels/using/about-in-app-messaging.md">細說明檔案</a> ，以及專 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">用的應用程式內教學課程</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 工作流程增強功能<br /> </td> 
   <td> <p>已新增下列工作流程功能：</p> 
    <ul> 
     <li> 您現在可以從同一個促銷活動例項，複製或貼上工作流程或其他工作流程中的活動。 如此，您就可輕鬆複製整個工作流程或特定活動，並保留最初定義的設定。 如需詳細資訊，請參閱<a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">詳細文件</a>。(CAMP-20014) </li> 
     <li> 使用「載 <strong>入檔案</strong> 」活動時，您現在可以在包含已拒絕記錄的檔案名稱中新增時間戳記。 如需詳細資訊，請參閱<a href="../../automating/using/load-file.md#configuration">詳細文件</a>。 </li> 
     <li> <strong>查詢</strong> 和 <strong></strong> 劃分活動現在可讓您啟用傳出轉移（如果活動未擷取任何資料）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**安全性增強功能**

* 已更新產生的著陸頁面HTML程式碼，以防止搜尋引擎建立索引。

**電子郵件設計人員增強功能**

* Behance藝術家設計的4種同級最佳回應式電子郵件範本現已推出。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/using-reusable-content.md#content-templates)。

* 我們的全新入門體驗將協助您更快開始建立電子郵件，並讓您更輕鬆地存取檔案和教學課程。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)。

* 您現在可以根據需求，靈活設定欄數和寬度。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

* 在行動檢視中編輯時，您可以僅在行動顯示中隱藏某些元件，以有效利用空間。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

* 您現在可以將自訂的社交管道新增至電子郵件範本，而不是已可用的管道。
* 修正當使用超過18種結構時，無法向下捲動結構選單的問題。 (CAMP-31173)
* 修正轉送包含隨Adobe Campaign傳送之預先標題的電子郵件時，在內容之上顯示預先標題的問題。 (CAMP-30736)
* 修正在Adobe Experience Manager中修改主旨後，按一下「重新整理 **** AEM內容」選項時，無法更新主旨行的問題。 (CAMP-29984)
* 已修正數個無法從Adobe Target使用動態影像的問題。
* 修正如果先前已從URL匯入內容，在準備時擷取內容時無法更新預覽的問題。
* YouTube圖示已新增至 **Social內容元** 件。
* 已針 **對「電子郵件設計** 器」浮動視窗中顯示的內容元件和片段新增「清單」檢視。

**其他改善項目**

* Adobe Campaign現在完全符合SDK V4和AEP SDK應用程式的FCM規範。
* Adobe Campaign支援Android搭配Wear OS和Apple搭配WatchOS的推播通知。
* 在介面中導覽時可能顯示的警告和錯誤訊息已變得清晰易懂。
* 您現在可以新增至與選擇加入和選擇退出相關的描述檔清單欄位（「不再連絡……」欄位）。
* 「描述檔建立」畫面中的「時區」下拉式清單已從「位址」區段移至介面的上方區段。
* 您現在可以在設定自訂資源畫面時新增分隔符號，讓您將欄位組織到類別中。

   如需詳細資訊，請參閱[詳細文件](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)。

**其他變更**

* Adobe Campaign和Adobe Experience Cloud將從2019年春季起停止支援Microsoft Internet Explorer 11和Campaign Standard 19.2版本。 請切換至Microsoft Edge或其他支援的瀏覽器。 請參 [閱「已過時和已移除的功能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) 」頁面。
* 描述 **檔資源的** 「國家／地區」代碼欄位已重新命 **名為「國家／地區」代碼**。

**修補程式**

* 修正將測試設定檔新增至電子郵件交易訊息時，無法傳送訊息的問題。 (CAMP-29854)
* 修正當同時觸發從所有頻道傳送訊息時，單一頻道的傳送量較低時，其他頻道傳送訊息的速度變慢的問題。
* 修正當外部帳戶連線尚未建立時，MTA開始傳送SMS訊息的問題。
* 修正「排程器」活動執行頻率和開始時間發生的問題。 (CAMP-30745)
* 修正使用擴充的描述檔資源時，產生PKEY時可能發生的問題。 (CAMP-30285)
* 修正基於日曆日的疲乏規則可能發生的問題。 (CAMP-30136)
* 修正嘗試存取名稱以&quot;Base&quot;結尾的自訂資源時可能發生的問題。 (CAMP-30109)
* 修正無法使用PATCH呼叫將描述檔訂閱至服務的問題。 (CAMP-29728)
* 修正透過「載入檔案」活動匯入XML檔案時，可能會損毀工作流程的問題。 （CAMP-29208和CAMP-28205）
* 修正連結自訂資源時，無法產生反向基數連結的問題。 (CAMP-30476)
* 修正僅使用區段代碼時無法擴充傳送記錄檔的問題。
* 修正在工作流程中使用檔案傳輸活動時，可能會複製列的問題。
* 修正無法在選擇的時間傳送排程報表的問題。
* 修正工作流程中應用程式內傳送的「要傳送」和「已傳送」KPI之間不一致的問題。
* 修正使用自訂HTML製作的「應用程式內」訊息無法使用追蹤的問題。
* 修正在工作流程中使用應用程式內傳送內容時無法儲存的問題。
* 修正無法為管理員顯示行動應用程式的問題。
* 修正導致「傳送能力更新」技術工作流程失敗的問題。 (CAMP-26387)
* 修正建立應用程式內傳送時，定位的描述檔與傳送控制面板中顯示的描述檔不一致的問題。 (CAMP-28722)
* 修正促銷活動與資產核心服務整合的問題，此問題可能會導致您無法在電子郵件中選取共用資產。

## 發行版本19.0 - 2019年1月 {#release-19-0---january-2019}

**新增功能?**

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
   <td> 電子郵件設計人員一般可用性<br /> </td> 
   <td> <p>全新的直覺式電子郵件設計工具（之前稱為Creative Designer）已推出。 它現在支援舊版內容編輯器的所有功能，包括：</p> 
    <ul> 
     <li> 使用Adobe Target <a href="../../integrating/using/adding-target-dynamic-content.md">的動態影像</a> </li> 
     <li> 能夠在準 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">備時自動從URL擷取內容</a> </li> 
     <li> 完全 <a href="../../designing/using/using-reusable-content.md#content-templates">符合現成可用的內容範本</a>。 </li> 
    </ul> 
    <p>如需詳細資訊，請參 <a href="../../designing/using/designing-content-in-adobe-campaign.md">閱詳細說明</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">檔案和操作視訊</a>。 以下列出改進和修正。</p><p>因此，舊版電子郵件內容編輯器現已過時。 For more information, refer to this <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 交易電子郵件中的產品清單<br /> </td> 
   <td> <p>您現在可以在交易電子郵件訊息中參考一或多個產品集合。 例如，您可以自動傳送購物車放棄電子郵件，列出使用者購物車中包含影像、價格和每個產品的連結的所有產品。</p><p>如需詳細資訊，請參 <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">閱詳細說明</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">檔案和操作視訊</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件設計人員中的行動裝置檢視<br /> </td> 
   <td> <p>編輯電子郵件內容時，您現在可以切換至專用的行動檢視。 這可讓您個別編輯行動顯示的所有樣式選項，例如調整邊界、較小的字型大小、不同的背景顏色等，以微調電子郵件的互動式設計。</p><p> 如需詳細資訊，請參閱<a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">詳細文件</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內訊息測試版改進<br /> </td> 
   <td> <p>應用程式內訊息測試版功能已增強，具備下列功能：</p> 
    <ul> 
     <li> 應用程式內Beta頻道符合GDPR規範 </li> 
     <li> 與Analytics API整合，以填入觸發器下拉式清單 </li> 
     <li> 傳送範本的直覺式外觀和說明 </li> 
     <li> 從可用性的角度增強製作介面 </li> 
    </ul> <p>如需詳細資訊，請參閱<a href="../../channels/using/about-in-app-messaging.md">詳細文件</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

**改進**

* 「載入資料」活動中的新選項現在可讓您將後處理階段套用至包含已拒絕記錄的檔案(例如： 壓縮郵遞區號格式)。 (CAMP-24521)
* 「更新資料」活動中的新選項現在可讓您設定要上傳之資料的最大批次大小。 (CAMP-28400)
* 已改善描述檔的位址狀態選擇。 選取國家時，「狀態」下拉式清單現在會自動更新為相關的狀態值。 (CAMP-28874)
* 「擷取檔案」活動中的新選項現在會防止在傳入轉場為空白時產生檔案。 如此可避免在SFTP伺服器上建立和上傳空白檔案。
* 「傳送摘要」報表已改善。
* 定義描述檔位址時可用的國家／地區清單已豐富。 (CAMP-26707)
* 現在，嘗試匯入內建工作流程時會顯示錯誤訊息。

**電子郵件設計人員**

* 修正即使在Adobe Campaign中停用此功能，但電子郵件範本或使用電子郵件設計工具建立的內容片段上啟用地理單位功能的問題，此問題會讓範本或片段在再次嘗試存取時無法使用。 (CAMP-28174)
* 修正使用電子郵件設計工具編輯內容時無法儲存動態內容條件的問題。 (CAMP-27905)
* 修正在編輯訊息的純文字版本並中斷「電子郵件設計器」中的HTML同步後，從電子郵件內容移除HTML版本的問題。 (CAMP-28507)
* 修正使用Internet Explorer 11時無法開啟「電子郵件設計器」介面的問題。 (CAMP-28273)
* 修正Microsoft Outlook轉換套用至「電子郵件設計器」按鈕的樣式設定時發生扭曲的問題。
* 修正「電子郵件設計人員」中，從電子郵件中使用的內容片段編輯URL的問題，因為預設會鎖定該片段，所以不預期會出現此問題。
* 修正Microsoft Office中無法顯示Email Designer分隔元件的問題。
* 修正當使用舊版電子郵件內容編輯器檢視與AEM同步的內容時，某些網際網路瀏覽器會導致頁面凍結的問題。 (CAMP-29068)
* 修正使用舊版電子郵件內容編輯器按一下電子郵件中任何影像時發生的錯誤。 (CAMP-30424)
* 修正使用「電子郵件設計器」編輯電子郵件時，無法顯示新建立之片段的問題。 (CAMP-29928)
* 修正在使用「電子郵件設計器」建立並使用Outlook網頁郵件用戶端收到的電子郵件中，無法正確顯示按鈕文字的問題。
* 現在，可以使用電子郵件設計器建立配置檔案事務性消息。 (CAMP-28900)
* 修正「電子郵件設計人員」中，當從URL自動擷取內容時，當內容應鎖定時，會讓內容可編輯的錯誤。

**修補程式**

* 修正動態報表中顯示錯誤傳送記錄的問題。 (CAMP-23446)
* 修正可能影響反彈摘要報表數字的問題(CAMP-28703)
* 修正促銷活動與資產核心服務整合的問題，此問題可能會導致在電子郵件中選取資產 **[!UICONTROL Image shared from Adobe Experience Cloud]** 時無法顯示資產(CAMP-28732)。
* 修正即使在SMPP外部帳戶中授權音譯，仍無法傳送包含「oe」字元的SMS訊息的問題。 (CAMP-29041)
* 修正在工作流程中使用「區段」活動時，可能顯示重複記錄的問題。 (CAMP-28743)
* 修正無法刪除工作流程活動中欄上其中一個值映射的問題。 (CAMP-28708)
* 修正使用萬用字元搭配「測試以查看檔案是否存在」選項時，檔案傳輸活動中的問題。 (CAMP-28977)
* 修正「檔案傳輸」活動中，更新外部帳戶設定時可能發生的問題。 (CAMP-28894)
* 修正使用「電子郵件不為空」條件時，查詢編輯器中自訂篩選器的問題。 (CAMP-28741)
* 修正匯出具有超過100k記錄的自訂資源表格時可能發生的問題。 (CAMP-28150)
* 修正無法刪除連結至觸發器的交易訊息的問題。 (CAMP-28385)
* 已移除某些SMS記錄檔中無法安全顯示的密碼。
* 修正由於Adobe Campaign傳送的空密碼，導致SMPP模擬器連線失敗的問題。
* 修正當SMS連線不穩定時，無法傳送促銷活動的問題。
* 修正在動態報表中顯示已刪除傳送的問題。
* 修正在工作流程中使用「擴充」活動時，無法從傳送記錄檔、追蹤記錄檔和排除記錄檔表格擷取其他資料的問題。
* 修正當使用「N個基數收集連結」連結類型和「刪除目標籤錄意味著刪除連結的記錄參考」選項時，GDPR刪除請求的問題。
* 修正報表共用的問題。
* 修正傳送推播通知時，可能導致吞吐量問題的問題。
* 修正直接郵件輸出檔案遺失欄位的問題。
* 修正使用者可修改內建工作流程的問題。
* 修正根據促銷活動範本建立促銷活動時的問題，該促銷活動範本包含已設定擷取活動的工作流程。 (CAMP-29198)
* 修正「檔案擷取」活動無法對數個元素使用相同運算式的問題。 (CAMP-29182)
* 修正在查詢編輯器中，broadlog和rtEvent追蹤記錄檔之間出現連結條件的問題。 (CAMP-28780)
* 修正無法儲存「特定動作」著陸頁面選項之修改的問題。 (CAMP-29422)
* 修正無法匯出工作流程中事件的裝載的問題。 (CAMP-29029)
* 修正阻止塊清單上的SMS號碼被排除在SMS消息中的問題。 (CAMP-28898)
* 修正處理傳入訊息時，SMPP提供者無法收到通知的問題。 (CAMP-29804)
* 修正允許刪除具有關聯傳送之外部帳戶的問題。 (CAMP-29738)
* SMS消息的發送吞吐量已得到改進和穩定。
* 修正SMS訊息中無法使用「~」字元的問題。 (CAMP-29172)
* 修正傳送時間最佳化選項的傳送問題。 (CAMP-29231)

