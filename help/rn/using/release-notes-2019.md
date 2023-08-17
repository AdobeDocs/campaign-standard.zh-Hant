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

## 發行版本19.4 - 2019年12月 {#release-19-4---october-2019}

**有哪些新功能？**

<table> 
 <thead> 
  <tr> 
   <th> <strong>加州消費者隱私保護法(CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA是加州新推出的隱私權法案，調和了2020年1月1日起生效的資料保護要求，並落實現代化標準。 CCPA適用於位在加州，並為個人資料主體保管資料的Adobe Campaign客戶。</p>
   <p>除了Adobe Campaign中已提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）之外，我們還將利用此機會加入其他功能，以協助您為CCPA做好準備：</p>
   <ul>
    <li>存取權與刪除權：我們妥善運用針對GDPR新增的功能。 <a href="https://helpx.adobe.com/content/help/tw/campaign/kb/acs-privacy.html#righttoaccess">了解更多</a> </li>
    <li><p>建立隱私權要求時，隱私權核心服務已新增規則型別（GDPR或CCPA）。 此方法是您應該用於所有存取和刪除請求的方法。不建議使用促銷活動 API 和介面來存取和刪除請求。請參閱「<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hant#release-notes">已過時和已移除的功能</a>」文章。</p></li>
    <li>A <strong>CCPA選擇退出</strong> 「設定檔」資源已新增欄位，以允許Adobe Campaign使用者追蹤消費者是否已選擇退出個人資訊銷售。 <a href="https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ccpa">了解更多</a>。</li>
  </ul>
    <p>請參閱<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">作法影片</a>。</p>
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
    <p>現已推出Adobe Campaign Standard與Microsoft Dynamics 365的整合。 您將能夠將連絡人和自訂實體記錄從Dynamics 365傳輸至Campaign，並從Campaign將電子郵件事件資料傳回Dynamics 365，以更好地協調銷售/行銷。</p>
    <p>請參閱 <a href="../../integrating/using/d365-acs-get-started.md">詳細檔案</a> 以設定此整合。</p>
  </td>
  </tr> 
 </tbody> 
</table>

**功能改進**

* 動態報告的同意快顯視窗已更新，其中包含Adobe Campaign Standard和Microsoft Dynamics 365整合。 一旦接受條款，使用Adobe Campaign Standard / Microsoft Dynamics 365整合和動態報告時，便會計入設定檔資料。 [閱讀全文](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* 修正接收傳遞警報時顯示錯誤聯絡日期的問題。
* 當使用未知的內容引數提交交易式訊息事件時，Campaign現在會傳回「400」錯誤訊息，而不是「500」。 (CAMP-28632)
* 新 **排除證明** 區段已新增至動態報告中。 現在預設會選取此區段來篩選您的報表。 [深入了解](../../reporting/using/list-of-components-.md#segments)
* 此 **訊息過期** 選項已新增至推播通知。 它可讓您指定到期日，Apple (APNS)或Android (FCM)將不再傳送訊息。 [深入了解](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* 已對「 」進行改善 **載入檔案** 活動：工作流程記錄檔已變得更清晰，且更詳細地說明檔案載入失敗時發生的錯誤。 啟用時產生的出站轉變 **將拒絕專案保留在檔案中** 選項已重新命名 **拒絕**. [深入了解](../../automating/using/load-file.md)
* 已將多語言相關記錄檔新增至傳送記錄檔，以更能瞭解由於上傳CSV檔案中缺少語言而導致的傳送失敗。

**安全性改善功能**

* 修正透過隱私權請求刪除隔離設定檔的資訊時，會移除隔離清單中電子郵件地址以外的所有資料的問題。
* 已增強安全性，以防止電子郵件標頭中的插入。
* 已增強安全性，以防止可使用xtk運算式(電子郵件HTML、文字內容和主旨、簡訊和推播通知內容)的SSRF攻擊。

**電子郵件設計工具增強功能**

* 修正插入電子郵件時，無法追蹤取消訂閱、訂閱和登入頁面連結的問題。 (CAMP-37809)
* 修正建立新電子郵件和選取範本時，可能導致錯誤的問題。 (CAMP-38000)
* 使用電子郵件設計工具編輯連結時，您現在可以使用 **將連結加底線** 選項。 此外， **Target** 已新增屬性，預設值設為 **無**. [深入了解](../../designing/using/styles.md#about-styling-links)
* 修正電子郵件內文文字元件中連結的色彩問題。 (CAMP-37330)
* 修正刪除影像時，無法移除關聯連結的問題。 (CAMP-37234)
* 修正無法將修改儲存在 **訂購** 條件中動態內容的設定。 (CAMP-36883)
* 修正搜尋登入頁面時的問題。 搜尋範圍已由最初建立的50個擴充至所有資料庫。 (CAMP-36839)
* 修正將修改儲存至中的電子郵件寄件者時的問題 **寄件者：名稱** 欄位。 (CAMP-36606)
* 已修改轉盤元件相容性警告，以反映支援的電子郵件使用者端。
* 修正行動裝置上的顯示問題。 在電子郵件中新增或上傳新影像時，height屬性現在一律設為「height： auto」。 (CAMP-35497)
* 修正從結構元件刪除片段時，在HTML中留下樣式和中繼標籤的問題。 (CAMP-35390)
* 修正片段在更新可重複使用內容時的問題。 (CAMP-35186)
* 修正了在電子郵件中僅顯示行動條件式內容的問題。 (CAMP-35155)
* 修正隨機顯示零寬度且不斷行空格的問題。 (CAMP-35116)
* 修正中按鈕位置的問題 **另存為片段** 對話方塊。
* 修正在影像標題和替代文字中新增HTML標籤時的預覽問題。
* 修正在電子郵件設計工具中，從舊版編輯器編輯在電子郵件中建立的連結時的問題。
* 修正內容中保留重複樣式標籤的問題。
* 修正在電子郵件中插入個人化欄位時的日期格式問題。
* 修正從HTML模式切換為純文字時的儲存問題。
* 修正按一下鎖定和解鎖選項，在內嵌樣式屬性面板中新增邊界值的問題。
* 修正行動裝置預覽的大小問題，以改善呈現。
* 修正範本和片段中按鈕大小的問題。
* 修正插入按鈕元件時的影像大小問題。

**其他變更**

* 資料在傳遞KPI頁面和動態報告頁面上顯示的預設時間範圍已保持一致，以防止報告結果不一致。 (CAMP-35148)
* 當應用程式憑證過期時，已在記錄中新增錯誤訊息。
* 裝載計算預覽現在包含自訂欄位大小，以防止推送通知失敗。 (CAMP-35303)
* 的名稱 **拒絕檔案** 在 **載入檔案** 活動現在可以在中的相同進行個人化 **檔案匯出** 活動。
* 未連結至任何現成可用實體的所有自訂實體現在可以透過API存取。
* 改善大型資源的資料庫效能。
* 傳送SMS訊息時發生的一些錯誤的說明已變得更清晰。 (CAMP-36558)
* 執行工作流程時，現在會顯示錯誤訊息 **排程器** 直接或透過數個活動連線到自己的活動，因為這會導致執行個體的工作流程伺服器卡住。
* 已進行改善以協助疑難排解異動訊息：「資料」連結已在事件設定畫面中重新命名為「上次異動事件」，現在會以遞減順序列出已接收的事件。 此外，已建立新的交易式事件狀態：「targetingFailed」。 當異動訊息模組無法擴充用於訊息鎖定的連結時，異動事件現在將處於此新狀態（而不是「routingFailed」狀態）。
* 限制登入頁面存取特定地理或組織單位時，已改良介面。 目的是警告登入頁面可能受可見性條件的約束：建立登入頁面時，現在必須選取地理和組織單位。 現在選取單位後，會顯示包含相關資訊的橫幅。 測試登入頁面時顯示的錯誤訊息已變得更清晰。
* 在Campaign Standard API中，如果金鑰值與原始金鑰不同，或您使用自己的商業金鑰作為URI而不是Adobe提供的商業金鑰，則無法使用PATCH操作修改自訂金鑰。
* 「阿爾巴尼亞文 — 馬其頓」語言已新增至偏好語言下拉式清單。 (CAMP-35396)

**修補程式**

* 修正無法排序或搜尋排程報表的問題。
* 修正觸發器規則造成AND和OR規則混合的問題。
* 修正在Launch中將行動屬性顯示為「已刪除」的問題。 (CAMP-35382)
* 修正無法在Adobe Campaign中同步Adobe Launch行動屬性的問題。 (CAMP-35411， CAMP-35089， CAMP-35014， CAMP-35487)
* 修正當事件包含設定檔資料擴充時，異動推播訊息失敗的問題。 (CAMP-34385)
* 已修正行動屬性未在多個環境中同步的問題。 (CAMP-37060)
* 修正在推播通知中選取使用聯絡日期公式的範本時的問題。 (CAMP-35300)
* 修正可能導致訊息傳送服務當機的問題。 (CAMP-35287)
* 修正全部定義有第一個事件日期的定期直接郵件的問題。 (CAMP-35139)
* 修正新擴充功能的問題 **設定檔** 無法用於查詢的自訂資源。 (CAMP-35119)
* 已修正 **修復資料庫結構** 已啟用「分片」設定的例項模式。 (CAMP-35118)
* 修正在broadlog上新增彙總資料時，導致SQL記錄錯誤的問題。 (CAMP-35034)
* 修正建立時轉換的問題 **細分** 活動。 (CAMP-35033)
* 修正的問題： **查詢** 活動導致 **encryption_aescbcDecrypt** 函式來解密 **encryption_aescbcEncrypt** 函式。 (CAMP-34952)
* 修正了可能導致 **追蹤記錄** 以免在傳遞中顯示。 (CAMP-34855)
* 修正使用時的問題 **傳送時間最佳化** 自訂日期公式，該公式可防止推播通知因工作流程其他資料錯誤而傳送。 (CAMP-30336)
* 修正可能導致自訂資源無法發佈的問題。 (CAMP-37425)
* 修正管理員使用者無法修改匯入套件的問題。  (CAMP-37176)
* 修正工作流程中，如果傳送活動連線至空白，無法傳送校樣的問題 **讀取對象** 活動。 (CAMP-37164)
* 修正無法將自訂資源匯入新環境的問題。 (CAMP-36506)
* 修正熱門點選報表中，影像可能隱藏百分比的問題(CAMP-36407)
* 修正嘗試匯出傳遞說明欄位時發生的問題。 (CAMP-35467)
* 修正了傳送完成時，傳送狀態仍可能為「開始擱置」的問題。 (CAMP-35355)
* 修正啟用，然後停用SQL記錄後無法顯示工作流程記錄的問題。

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
   <td> 外部API活動（公開測試版）<br /> </td> 
   <td> <p>為更深度個人化，外部API活動可讓您透過REST API呼叫，將資料從外部系統帶入工作流程。 REST端點可以是客戶管理系統、Adobe I/O Runtime或Adobe Experience Cloud REST端點（例如資料平台、Target、Analytics、Campaign）。</p><p>此功能目前仍在公開測試中。</p><p>如需詳細資訊，請參閱<a href="../../automating/using/external-api.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">作法影片</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流程區段報表<br /> </td> 
   <td> <p>此功能可讓行銷人員依區段代碼來劃分其傳遞效能。 當您建立工作流程，並使用分段活動將區段指派給傳遞人口時，這些區段現在可以進入相同的傳遞。 這可讓您根據單一傳送內的多個區段，顯示開啟數/點按數統計資料。</p><p>如需詳細資訊，請參閱<a href="../../reporting/using/creating-a-report-workflow-segment.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">作法影片</a>。</p></td>
  </tr> 
 </tbody> 
</table>

**安全性改善功能**

* 修正安全性問題，以防止對取得影像的無效請求進行拒絕服務(DoS)攻擊。 (CAMP-33454)

**電子郵件設計工具增強功能**

* 修正每次新增元件時，都在HTML範本中新增其他HTML樣式標籤的問題，此問題可能會大幅增加範本的大小。 (CAMP-34694)
* 修正無法使用某些右上角工具列功能表選項的問題。 (CAMP-34577)
* 修正將映象頁面URL內容區塊插入電子郵件內容時所發生的問題。 (CAMP-34779)
* 修正了在電子郵件中使用JSPP程式碼時，導致難以編輯內容的問題。 (CAMP-34574)
* 修正當超連結新增至影像時，導致影像在頂端截斷的問題。 (CAMP-34382)
* 修正搭配Firefox使用電子郵件設計工具時的顯示問題。 (CAMP-34364)
* 修正在電子郵件中定義動態內容時，進階模式發生的幾個問題。 (CAMP-34351、CAMP-34333、CAMP-34331)
* 修正動態內容規則編輯器發生的幾個問題(CAMP-34304、CAMP-34303)。
* 修正電子郵件設計工具設定窗格中無法顯示連結欄位的問題(CAMP-33749)。
* 修正已傳送電子郵件中YouTube圖示過大的問題。 (CAMP-33726)
* 修正使映象頁面內容可編輯的安全性問題。 (CAMP-33691)
* 修正在動態內容中使用大於符號時中斷HTML輸出的問題。 (CAMP-33688)
* 修正在電子郵件設計工具中編輯文字時，使用還原選項發生的問題。 (CAMP-32565)
* 修正復原樣式而非移除樣式時，會建立額外標籤的問題。 (CAMP-32359)
* 您現在可以定義電子郵件中使用的每個元件是否只會在桌上型裝置上顯示，或只會在行動裝置上顯示。
* 您現在可以設定社交內容元件的寬度和高度。
* 修正刪除動態內容後，無法移除動態內容舊原始程式碼的問題。
* 修正修改電子郵件後，無法更新主旨的問題。
* 修正將n：n欄結構拖放至工作區後無法選取的問題。
* 修正電子郵件控制面板中訊息縮圖模糊的問題。
* 修正在Outlook中接收的電子郵件無法正確顯示背景的問題。
* 修正電子郵件設計工具首頁的部分排序問題。
* 修正使用動態內容時複製變體時發生的問題。
* 一些不想要的欄位已從[電子郵件設計工具設定]窗格中移除。

**其他改善項目**

* 透過與Adobe Experience Platform定位服務整合，Adobe Campaign現在相容於透過Experience Platform SDK傳送位置型行銷訊息給行動應用程式的訂閱者。 如需詳細資訊，請參閱[詳細文件](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)以瞭解詳情。
* 報告功能已改善，獲得更好的體驗。 若要使用此功能，您必須接受「動態報告使用協定」。 有關詳細資訊，請參閱 [詳細檔案](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* 在工作流程中，已新增新選項以預覽工作流程後續的十個執行。 有關詳細資訊，請參閱 [詳細檔案](../../automating/using/scheduler.md).
* 在排程器活動中，新選項可讓您為每月傳送選取特定周的特定日期。 有關詳細資訊，請參閱 [詳細檔案](../../automating/using/scheduler.md).
* 建立無彙總期間的循環傳送時，傳送控制面板現在可讓您在傳送傳送之前要求確認。 有關詳細資訊，請參閱 [詳細檔案](../../sending/using/confirming-the-send.md).
* 您現在可以使用已在工作流程外部訊號活動中宣告的事件變數，個人化傳送的標籤。 有關詳細資訊，請參閱 [詳細檔案](../../automating/using/calling-a-workflow-with-external-parameters.md).
* 已改善GDPR刪除查詢，以提升效能。 (CAMP-33504)
* 「ftp」選項已從外部帳戶設定介面中移除。 (CAMP-34472)
* 您現在可以為每封電子郵件啟用和停用SMTP測試模式選項。 有關詳細資訊，請參閱 [詳細檔案](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**其他變更**

* 在傳遞屬性介面中新增警告。 它會指定傳遞根據其彙總期間進行準備，並解凍以每天多次呼叫工作流程，您應確保他們沒有任何期間。 (CAMP-34393)
* 已在自訂資源設定畫面中新增警告。 我們建議對自訂資源 ID 使用最多 30 個字元。這也適用於自訂資源欄位、索引和連結。
* 嘗試刪除登入頁面用作確認訊息的交易式訊息時，現在會顯示訊息。
* 當活動執行超過6小時時，工作流程記錄中現在會出現警告。 這不適用於推播通知、傳送、訊號、開始、結束、分支、 AND-joint、排程和等待活動。
* 當您達到同時執行的工作流程數量上限時，工作流程記錄中現在會出現警告。
* 已暫停或失敗狀態超過7天的工作流程現在已停止，以減少使用的磁碟空間。 清除任務顯示在工作流程記錄檔中。
* 使用「傳輸檔案」活動時，如果檔案大小超過可用磁碟空間，現在會記錄錯誤。
* 無法再為應用程式內訊息中的次要按鈕選取重新導向至目的地URL動作。

**修補程式**

* 修正可能導致GDPR存取請求失敗的問題。
* 修正當收到唯一設定檔的多個觸發器時，可能導致觸發器被捨棄的問題。
* 修正登入後可能導致錯誤自訂資源發佈錯誤訊息的問題。
* 修正建立或擴充自訂資源時顯示空白頁面的問題。
* 修正讓具有appSubscriptionrcp作為目標維度的對象無法用於行動傳送中目標定位的問題。
* 修正無法將硬退信電子郵件地址置於隔離的錯誤。 (CAMP-24587)
* 修正新增型別規則，然後在儲存型別前刪除規則時發生的問題。 (CAMP-32789)
* 修正停用動態內容時，無法顯示登入頁面內容的問題。 (CAMP-32924)
* 修正在主要傳遞的屬性上使用個人化時發生的週期性傳遞問題。 (CAMP-32983)
* 修正工作流程中無法從包含傳入SMS訊息資料的轉換讀取結果的問題。 (CAMP-33134)
* 修正工作流程結合分叉和排除活動以建立對象時發生的問題。 (CAMP-33401)
* 修正了無法顯示映象頁面內容，以及無法針對循環傳遞傳送校樣訊息的問題。 (CAMP-33413)
* 修正在設定檔與對象之間使用聯合活動時，導致錯誤的問題。 此問題是因為輸入轉變中的識別鍵不相容所導致。 (CAMP-33713)
* 修正在Test活動中按兩下「recCount」運算式時，無法使用正確語法的問題。 (CAMP-33756)
* 修正開啟帳單技術工作流程記錄檔時，可能導致錯誤訊息的問題。 (CAMP-34313)
* 修正登陸頁面中，使用訂閱設定核取方塊欄位時可能發生的問題。 (CAMP-34369)
* 修正設定清單並新增「圖示」欄位時發生的問題。 (CAMP-34585)
* 修正無法在載入檔案工作流程活動中使用「|」和「%」符號作為日期或時間分隔符號的問題。 (CAMP-34706)
* 修正將可見性條件與登入頁面中的核取方塊搭配使用時發生的問題。 (CAMP-34802)
* 修正了在擴充活動中，如果篩選維度設為追蹤記錄，且目標維度設為設定檔，則欄位無法在「其他資料」索引標籤中顯示的問題。
* 修正匯出「workflowTemplate」資源時導致錯誤訊息的問題。
* 修正建立新設定檔時，若從對話方塊選取「國家/地區代碼」欄位，則無法儲存的問題。
* 修正使用直接郵件匯入範本(updateQuarantinesDeliveryLogsDirectMail)時發生的幾個問題。
* 修正與「隨選資產」整合相關的問題。
* 修正在「時間軸」檢視上放大時發生的問題。 (CAMP-33628)
* 修正無法立即傳送排程日期和時間之電子郵件訊息的校樣的問題。 (CAMP-33723)
* 修正交易式訊息的問題，此問題會在使用者登出時產生錯誤記錄。 (CAMP-31698)
* 修正排程電子郵件訊息時，特定環境可能發生的錯誤。
* 修正造成更新傳送執行工作流程失敗的問題。
* 修正當主旨包含多行時破壞電子郵件內容的安全性問題。


## 發行版本 19.2.7 – 2019 年 7 月 {#release-19-2-7---july-2019}

**功能改進**

* 已改善GDPR刪除查詢，以提升效能。
* 修正19.2升級後可能導致Web當機的問題。 (CAMP-34862)
* 修正非管理員使用者無法儲存或排程報表的問題。 (CAMP-31133)
* 修正在「載入檔案」工作流程活動中使用「|」作為日期分隔符號的問題。 (CAMP-34706)

## 發行版本 19.2.4 – 2019 年 6 月 {#release-19-2-4---june-2019}

**電子郵件設計工具**

* 修正在HTML中使用空白樣式標籤時，使用者無法編輯片段的問題。 這是19.2.3中CAMP-33778的後續修正。

## 發行版本 19.2.3 – 2019 年 6 月 {#release-19-2-3---june-2019}

**電子郵件設計工具**

在19.2版本中引進了一系列改善和修正，以最佳化片段。 新建立的片段將順暢地運作。 先前建立的片段已變成灰色，需要移轉到新格式。 若要這麼做，請按一下每個片段，然後驗證其是否移轉至新格式。 建議您在移轉所有片段之前先測試一些片段。

* 修正解除鎖定片段後，使用者無法編輯片段的問題。 更新至19.2時，這會影響現有的片段。 (CAMP-33778)
* 修正使用動態內容時的問題。 HTML中新增了額外的空格。

**其他改善項目**

* 修正了在SMS聯結器中斷後無法繼續SMS傳送的問題。
* 修正啟用TLS時，可能關閉SMPP連線的問題。
* 修正啟用TLS時，可能關閉SMPP連線的問題。
* Campaign已新增「Launch_URL_Campaign」選項，以管理使用Adobe Experience Platform Mobile SDK建立的行動應用程式屬性。
* 修正在上傳新建立的行動屬性的憑證並退出行動應用程式屬性頁面後，導致沙箱環境選項取消核取的錯誤。
* 修正無法使用服務資源的資訊擴充交易式訊息內容的問題。 (CAMP-33707)
* 修正嘗試從服務取消訂閱設定檔時，封鎖清單登陸頁面發生的問題。

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
   <td> <p>為了協助提高身為管理員使用者的工作效率，您可以輕鬆監控容量和管理執行個體的設定（從SFTP伺服器管理開始）。</p><p>如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=zh-Hant">作法影片</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 本機通知<br /> </td> 
   <td> <p>本機通知訊息可讓您在行動應用程式中有新資料可用時通知您的使用者，即使沒有網際網路存取權或行動應用程式在前景執行。 行動應用程式會在特定時間並根據事件觸發本機通知。</p><p>如需詳細資訊，請參閱<a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">詳細文件</a>以瞭解詳情。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流程增強功能 — 將裝載新增至外部訊號活動<br /> </td> 
   <td> <p>其他工作流程或REST API呼叫符合定義的條件時，即啟動具備裝載的工作流程，以便與外部系統整合。 這也包括新的 <strong>測試</strong> 活動，您可在此功能上執行測試。</p><p>如需詳細資訊，請參閱<a href="../../automating/using/calling-a-workflow-with-external-parameters.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">作法影片</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 登陸頁面增強功能 — Google reCAPTCHA<br /> </td> 
   <td> <p>利用Google reCAPTCHA防止登陸頁面上出現垃圾郵件，無需客戶採取任何行動。</p><p>如需詳細資訊，請參閱<a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">詳細文件</a>以瞭解詳情。</p></td> 
  </tr> 
 </tbody> 
</table>

**安全性改善功能**

* 修正報告工作區中潛在的點選劫持安全性問題。

**電子郵件設計工具增強功能**

* 修正復製片段並嘗試在電子郵件設計工具中使用片段時發生的問題。 (CAMP-33193)
* 修正在電子郵件設計工具介面中使用內嵌元素時，造成不必要空格的問題。 (CAMP-32163)
* 修正在「電子郵件設計工具」中儲存電子郵件內容後，刪除使用者新增的額外HTML標籤屬性的問題。 (CAMP-32162)
* 修正在電子郵件設計工具HTML模式中顯示Microsoft Office標籤（即使移除後亦然）的問題。 (CAMP-32141)
* 如果您使用舊版「電子郵件設計工具」建立電子郵件，在開啟此電子郵件內容時，快顯視窗現在會提示使用者更新至最新版本。 (CAMP-31529)
* 修正當傳送至某些傳訊使用者端時，可能扭曲使用電子郵件設計工具建立的電子郵件影像的問題。 (CAMP-31407)
* 修正在HTML模式中建立時，部分元素（例如清單或按鈕）無法以純文字模式正確顯示的問題。 (CAMP-32582, CAMP-32542)
* 修正無法在內容範本或片段屬性中顯示超過50個組織單位的問題。 (CAMP-32932)
* 修正在Outlook上接收使用「電子郵件設計工具」建立的電子郵件時，檢視區背景顏色的問題。 (CAMP-31402)
* 修正在Outlook中開啟時，使用電子郵件設計工具建立的電子郵件內容無法回應的問題。 (CAMP-31400)
* 修正在電子郵件主旨中使用動態內容時，無法正常運作的問題。 (CAMP-32837)
* 修正與電子郵件主旨相關且未妥善逸出的問題。
* 修正無法將片段載入電子郵件設計工具左側浮動視窗的問題。
* 修正當重新整理片段清單時，在電子郵件內容版本期間建立的片段無法顯示在電子郵件設計工具左側浮動視窗中的問題。
* 修正在電子郵件中使用動態內容時發生的幾個問題。
* 修正嘗試使用RGB值定義顏色時，檢色器發生的問題。
* 修正映象頁面在行動裝置上接收電子郵件時無法回應的問題。

**異動訊息增強功能**

「異動訊息傳送」通道已新增數項改善專案，以最佳化運作和效能。

* 交易式訊息持續時間已延長，以確保所有訊息在過期前傳送，尤其是執行重試時。
* 透過將負載分配給不同的傳送執行緒，提高了異動訊息傳送效能。
* 交易式訊息流程已最佳化，以便能夠並行開始相同訊息的多個分析。
* 修正可能導致異動推播通知的輸送量和延遲不一致的問題。
* 修正異動訊息執行傳送中顯示錯誤目標對象的問題。
* 修正匯入包含事件設定和相關交易式訊息的套件時發生的問題。 有關詳細資訊，請參閱 [詳細檔案](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* 修正了從為包含產品清單的交易式訊息建立的測試設定檔中刪除集合資料的問題。

**其他變更**

* SMS外部帳戶已新增一個選項。 這可限制傳送SMS的MTA流程數上限，以更好地控制平行連線的數量。 如需詳細資訊，請參閱 [SMS聯結器通訊協定及設定](https://helpx.adobe.com/tw/campaign/kb/sms-connector-protocol-and-settings.html) 技術備忘稿。
* 使用API擴充功能發佈資源時，如果API已發佈，現在每次再次發佈時都會自動更新。 以前此動作是手動的，若未更新API，可能會破壞此API的設定檔或服務資源。 有關詳細資訊，請參閱 [詳細檔案](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* 已從動態報告中移除郵遞區號維度。 我們建議改用城市、國家/地區、州別維度。
* 應用程式內訊息的「首次啟動」生命週期事件觸發器已移除。
* 匯出具有安全性群組的套件時，它現在會包含指派給每個群組的角色。 (CAMP-32960)
* 在「載入檔案」活動中，新選項可讓您檢查要上傳的檔案的列是否與列定義相符。 如需詳細資訊，請參閱[詳細文件](../../automating/using/load-file.md)以瞭解詳情。(CAMP-32229)
* 工作流程現在可以使用裝載啟動，讓您在工作流程內的活動之間使用和共用外部引數。 如需詳細資訊，請參閱[詳細文件](../../automating/using/calling-a-workflow-with-external-parameters.md)以瞭解詳情。(CAMP-29412和CAMP-29413)
* Campaign Standard API現在可讓您使用裝載更新設定檔的地理和組織單位。 如需詳細資訊，請參閱[詳細文件](../../api/using/get-started-apis.md)以瞭解詳情。
* 無法存取資料庫中的物件時的錯誤訊息已更清楚瞭解。
* 在擷取檔案活動中，定義要匯出的檔案名稱時，已更新Javascript功能。 現在只有formatDate函式可用於「輸出」欄位。 如需詳細資訊，請參閱[詳細文件](../../automating/using/extract-file.md)以瞭解詳情。
* 自訂資源的自動序列ID產生功能已有所改善。 新自訂資源的主鍵現在預設為64位元。
* 已改善自訂資源發佈測試模式。 如果上次自訂資源發佈失敗且未修正，現在會向使用者顯示警告訊息。 自訂資源發佈失敗後，您可以復原到上一個工作版本。 如需詳細資訊，請參閱[詳細文件](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)以瞭解詳情。
* 已在傳輸檔案活動中新增選項。 它可讓您在使用SFTP模式的檔案下載動作時排序檔案。 如需詳細資訊，請參閱[詳細文件](../../automating/using/transfer-file.md)以瞭解詳情。(CAMP-33109)

**修補程式**

* 修正重新載入SMS設定時，可能會導致記憶體洩漏至MTA的問題。
* 修正了無法在修復模式下發佈資料庫更新的問題。
* 已修正Adobe Analytics報表與Adobe Campaign動態報表之間不一致的問題。 (CAMP-25393)
* 修正造成報告共用工作流程失敗的錯誤。
* 修正使用者無法只傳送包含媒體URL的應用程式內訊息的錯誤。
* 修正即使行動應用程式的憑證未上傳至執行個體，仍顯示其憑證的問題。
* 修正使用時，個人化欄位無法運作的錯誤 **鎖定行動應用程式的所有使用者** 範本。
* 已布建新的Campaign Standard執行個體。 (CAMP-32635和CAMP-32344)
* 修正無法在工作流程中自訂日期公式的錯誤。 (CAMP-30336)
* 修正定義自訂日期公式時，下拉式清單中無法提供「其他資料」和「區段代碼」欄位的問題。 (CAMP-32383)
* 修正了「傳輸檔案」和「擷取檔案」活動在檔案加密後無法找到檔案拒絕的問題。 (CAMP-32377)
* 修正API中可能導致lineCount篩選器無法呈現確切總計數的問題。 (CAMP-31424)
* 修正登入頁面中，在修改輸入欄位後，無法顯示更新值的問題。 (CAMP-31401)
* 修正可能導致訊號活動意外啟動的問題。
* 修正當對象為空白時，無法顯示電子郵件預覽的問題。
* 修正「擷取檔案」活動啟動「如果入站轉變為空白，則不產生檔案」選項時，可能產生檔案的問題。
* 修正了傳送工作流程未成功完成時關閉工作流程的問題。
* 修正使用者無法儲存或排程報表的問題。 (CAMP-31133)

## 發行版本 19.1.3 – 2019 年 3 月 {#release-19-1-3---march-2019}

**電子郵件設計工具增強功能**

* 修正儲存範本後無法修改範本的問題。
* 修正了在電子郵件中使用先前建立範本的各種問題。
* 修正匯入範本中無法隱藏元件的問題。

**其他改善項目**

* 修正檢視型別規則時的錯誤。 (CAMP-32059和CAMP-31849)
* 修正無法編輯型別規則的問題。 (CAMP-31750)
* 修正inMail處理序可能意外停止的問題。 (CAMP-31238)

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
   <td> 推播通道報告改進<br /> </td> 
   <td> <p>推播頻道報告已新增幾個增強功能，讓您更直覺地測量使用者參與。 透過此版本，我們將推播頻道量度清單擴展為三個不同的量度：曝光數、點按數、開啟次數（應用程式開啟），以協助您更有效地測量和分析使用者與推播通知的互動。 除此之外，我們也在標準化這些量度的定義與實作。 推播通知內建報表也已經過改善，並包含常用的視覺效果和量度。</p><p> 如需詳細資訊，請參閱<a href="../../reporting/using/push-notification-report.md">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式的啟動整合<br /> </td> 
   <td> <p>此發行版本包含Adobe Campaign與Adobe Experience Platform Launch和Mobile SDK中Adobe Campaign Standard的Android和iOS擴充功能GA版本的整合。 這些擴充功能支援推送訊息、應用程式內訊息和行動應用程式設定檔更新。</p><p> 如需詳細資訊，請參閱<a href="https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式內傳訊<br /> </td> 
   <td> <p>此發行版本包含Campaign應用程式內頻道的GA版本。 從功能的角度來看，Beta版最值得關注的新增功能是應用程式內管道的動態報表，以及Mobile SDK與MCIAS之間的安全交握(提供應用程式內規則至SDK的Marketing Cloud應用程式內傳訊服務)。 安全交握可確保使用者的PII資料不會落入惡意之手，並可讓您在每次使用者登出時清除訊息快取，進而維護使用者在共用裝置上的隱私權。</p><p>如需詳細資訊，請參閱 <a href="../../channels/using/about-in-app-messaging.md">詳細檔案</a> 以及專屬的 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">應用程式內教學課程</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 工作流程增強功能<br /> </td> 
   <td> <p>已新增下列工作流程功能：</p> 
    <ul> 
     <li> 您現在可以在工作流程或其他工作流程中，從相同的Campaign執行個體複製貼上活動。 如此一來，您便可輕鬆複製整個工作流程或特定活動，同時保留最初定義的設定。 如需詳細資訊，請參閱<a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">詳細文件</a>以瞭解詳情。(CAMP-20014) </li> 
     <li> 使用時 <strong>載入檔案</strong> 活動，您現在可以將時間戳記新增至包含拒絕記錄的檔案名稱。 如需詳細資訊，請參閱<a href="../../automating/using/load-file.md#configuration">詳細文件</a>以瞭解詳情。 </li> 
     <li> <strong>查詢</strong> 和 <strong>細分</strong> 活動現在可讓您在活動未擷取任何資料時啟用出站轉變。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**安全性改善功能**

* 已更新產生的登陸頁面HTML程式碼，以防止搜尋引擎編制索引。

**電子郵件設計工具增強功能**

* 現提供Behance藝人設計的四組同級最佳回應式電子郵件範本。

  如需詳細資訊，請參閱[詳細文件](../../designing/using/using-reusable-content.md#content-templates)以瞭解詳情。

* 我們新的上線體驗可幫助您更快地開始建立電子郵件，並讓您更輕鬆地存取檔案和教學課程。

  如需詳細資訊，請參閱[詳細文件](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)以瞭解詳情。

* 您現在可以彈性地根據需求設定欄數和寬度。

  如需詳細資訊，請參閱[詳細文件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)以瞭解詳情。

* 在行動檢視中進行編輯時，您可以只隱藏行動顯示中的特定元件，以有效使用空間。

  如需詳細資訊，請參閱[詳細文件](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)以瞭解詳情。

* 您現在可以在已可用的社交管道上方，新增自訂社交管道至電子郵件範本。
* 修正當使用超過18個結構時無法向下捲動結構功能表的問題。 (CAMP-31173)
* 修正轉寄包含透過Adobe Campaign傳送之預覽標題的電子郵件時，在內容上方顯示預覽標題的問題。 (CAMP-30736)
* 修正在按一下「 」時，無法更新主旨行的問題 **重新整理AEM內容** 在Adobe Experience Manager中修改主題後的選項。 (CAMP-29984)
* 修正無法從使用Adobe Target動態影像的數個問題。
* 修正了在準備時擷取內容時，如果內容先前已從URL匯入，預覽無法更新的問題。
* YouTube圖示已新增至 **社交** 內容元件。
* 此 **清單** 已針對「電子郵件設計工具」浮動視窗中顯示的內容元件和片段新增檢視。

**其他改善項目**

* Adobe Campaign現在完全符合SDK V4和AEP SDK應用程式的FCM。
* Adobe Campaign支援Android的Wear OS推播通知以及Apple的watchOS。
* 在介面中導覽時可能顯示的警告和錯誤訊息已變得更清晰、更易於理解。
* 您現在可以將與選擇加入和選擇退出相關的欄新增到設定檔清單中（「不再聯絡……」欄位）。
* 設定檔建立畫面中的「時區」下拉式清單已從「地址」區段移至介面的上半部分。
* 您現在可以在設定自訂資源畫面時新增分隔符號，好讓您將欄位組織成類別。

  如需詳細資訊，請參閱[詳細文件](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)以瞭解詳情。

**其他變更**

* 從2019年春季和Campaign Standard 19.2版開始，Adobe Campaign和Adobe Experience Cloud將停止支援Microsoft Internet Explorer 11。 請切換至 Microsoft Edge 或其他支援的瀏覽器。另請參閱 [過時和移除的功能](../../rn/using/deprecated-features.md) 頁面。
* 此 **國家/地區代碼** 設定檔資源的欄位已重新命名為 **國家/地區代碼**.

**修補程式**

* 修正在電子郵件交易式訊息中新增測試設定檔時，無法傳送訊息的問題。 (CAMP-29854)
* 修正在同時觸發從所有頻道傳送訊息時，如果一個頻道傳送低，從其他頻道傳送訊息的速度變慢的問題。
* 修正在尚未建立外部帳戶連線時，造成MTA開始傳送SMS訊息的問題。
* 修正排程器活動執行頻率和開始時間發生的問題。 (CAMP-30745)
* 修正使用擴充設定檔資源時產生PKEY時可能發生的問題。 (CAMP-30285)
* 修正了行事曆日期型疲勞規則可能發生的問題。 (CAMP-30136)
* 修正嘗試存取名稱結尾為「Base」的自訂資源時可能發生的問題。 (CAMP-30109)
* 修正無法使用PATCH呼叫來訂閱服務的設定檔問題。 (CAMP-29728)
* 修正透過「載入檔案」活動匯入XML檔案時，可能會損毀工作流程的問題。 (CAMP-29208和CAMP-28205)
* 修正連結自訂資源時，無法產生反向基數連結的問題。 (CAMP-30476)
* 修正僅使用區段代碼時無法擴充傳送記錄的問題。
* 修正在工作流程中使用檔案傳輸活動時，可能會重複列的問題。
* 修正無法在選定時間傳送排程報告的問題。
* 修正工作流程中應用程式內傳送的「待傳送」與「已傳送」KPI不一致的問題。
* 修正使用自訂HTML編寫的應用程式內訊息無法進行追蹤的問題。
* 修正使用工作流程時，無法儲存應用程式內傳送內容的問題。
* 修正管理員無法顯示行動應用程式的問題。
* 修正導致傳遞能力更新技術工作流程失敗的問題。 (CAMP-26387)
* 修正建立應用程式內傳送時，目標設定檔與傳送控制面板中顯示的設定檔不一致的問題。 (CAMP-28722)
* 修正Campaign與Assets核心服務整合的問題，此問題可能會阻止您選取電子郵件中的共用資產。

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
   <td> 電子郵件設計工具一般可用性<br /> </td> 
   <td> <p>全新的直覺式電子郵件設計工具（先前稱為Creative Designer）已移至GA。 它現在支援舊版內容編輯器的所有功能，包括：</p> 
    <ul> 
     <li> 使用 <a href="../../integrating/using/adding-target-dynamic-content.md">Adobe Target的動態影像</a> </li> 
     <li> 能夠 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">準備時從URL自動擷取內容</a> </li> 
     <li> 完全相容 <a href="../../designing/using/using-reusable-content.md#content-templates">現成可用的內容範本</a>. </li> 
    </ul> 
    <p>如需詳細資訊，請參閱<a href="../../designing/using/designing-content-in-adobe-campaign.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">作法影片</a>。以下列出改善與修正。</p><p>因此，舊版的電子郵件內容編輯器現已棄用。 如需詳細資訊，請參閱此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hant#release-notes">頁面</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 異動電子郵件中的產品清單<br /> </td> 
   <td> <p>您現在可以在交易式電子郵件訊息中參考一或多個產品集合。 例如，您可以自動傳送放棄購物車電子郵件，列出使用者購物車中的所有產品，並附帶每個產品的影像、價格及連結。</p><p>如需詳細資訊，請參閱<a href="../../designing/using/using-product-listings.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">作法影片</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件設計工具中的行動裝置檢視<br /> </td> 
   <td> <p>您現在可以在編輯電子郵件內容時，切換至專用的行動裝置檢視。 此功能可讓您分別編輯行動顯示的所有樣式選項（例如調整邊界、縮小字型大小、使用不同的背景顏色等），微調電子郵件的回應式設計。</p><p> 如需詳細資訊，請參閱<a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內訊息測試版改良<br /> </td> 
   <td> <p>應用程式內傳訊功能Beta版已經過強化，現可提供下列新功能：</p> 
    <ul> 
     <li> 應用程式內測試版管道符合GDPR規定 </li> 
     <li> 與Analytics API整合，以填入「觸發器」下拉選單 </li> 
     <li> 傳遞範本的直覺式外觀和說明 </li> 
     <li> 針對易用性增強製作介面的功能 </li> 
    </ul> <p>如需詳細資訊，請參閱<a href="../../channels/using/about-in-app-messaging.md">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* 「載入資料」活動中的新選項現在可讓您將後處理階段套用至包含已拒絕記錄的檔案(例如： 壓縮郵遞區號格式)。(CAMP-24521)
* 更新資料活動中的新選項現在可讓您設定要上傳之資料的最大批次大小。 (CAMP-28400)
* 改善設定檔的位址狀態選擇。 選取國家/地區時，「州」下拉式清單現在會自動更新相關的州值。 (CAMP-28874)
* 現在，如果入站轉變為空，「擷取檔案」活動中的新選項將防止產生檔案。 如此可避免在SFTP伺服器上建立和上傳空白檔案。
* 已改善傳遞摘要報告。
* 定義設定檔地址時可用的國家/地區清單已擴充。 (CAMP-26707)
* 嘗試匯入內建工作流程時，現在會顯示錯誤訊息。

**電子郵件設計工具**

* 修正了在電子郵件範本或使用Email Designer建立的內容片段上啟用地理單位功能的問題，即使此功能在Adobe Campaign中已停用，導致範本或片段在嘗試再次存取時無法使用。 (CAMP-28174)
* 修正使用電子郵件設計工具編輯內容時，無法儲存動態內容條件的問題。 (CAMP-27905)
* 修正在電子郵件設計工具中編輯純文字版本的訊息並中斷HTML同步後，從電子郵件內容移除HTML版本的問題。 (CAMP-28507)
* 修正使用Internet Explorer 11時無法開啟電子郵件設計工具介面的問題。 (CAMP-28273)
* 修正套用至「電子郵件設計工具」按鈕之樣式設定的Microsoft Outlook轉譯扭曲的問題。
* 修正電子郵件設計工具中，使電子郵件中所用內容片段的URL可編輯的問題，此問題在預設鎖定片段時不應發生。
* 修正電子郵件設計工具分隔線元件無法在Microsoft Office中顯示的問題。
* 修正某些網際網路瀏覽器在使用舊版電子郵件內容編輯器檢視從AEM同步的內容時，造成頁面凍結的問題。 (CAMP-29068)
* 修正使用舊版電子郵件內容編輯器時，按一下電子郵件中的任何影像時發生的錯誤。 (CAMP-30424)
* 修正使用電子郵件設計工具編輯電子郵件時，無法顯示新建立片段的問題。 (CAMP-29928)
* 修正使用電子郵件設計工具建立並使用Outlook網頁郵件使用者端接收之電子郵件時，無法正確顯示按鈕文字的問題。
* 現在可以使用電子郵件設計工具建立設定檔交易式訊息。 (CAMP-28900)
* 修正電子郵件設計工具中的錯誤，此錯誤會讓內容在準備期間從URL自動擷取內容時變成可編輯，但此時應鎖定內容。

**修補程式**

* 修正動態報告中顯示錯誤傳送記錄的問題。 (CAMP-23446)
* 修正了可能影響退回摘要報告之數字的問題(CAMP-28703)
* 修正Campaign與Assets核心服務整合的問題，此問題可能導致在選取時無法顯示資產 **[!UICONTROL Image shared from Adobe Experience Cloud]** (CAMP-28732)。
* 修正即使已在SMPP外部帳戶中授權音譯，仍無法傳送包含「oe」字元之SMS訊息的問題。 (CAMP-29041)
* 修正在工作流程中使用區段活動時，可能顯示重複記錄的問題。 (CAMP-28743)
* 修正無法刪除工作流程活動中欄位其中一個值對應的問題。 (CAMP-28708)
* 修正檔案傳輸活動中使用萬用字元搭配「測試以檢視檔案是否存在」選項的問題。 (CAMP-28977)
* 修正檔案傳輸活動中更新外部帳戶設定時可能發生的問題。 (CAMP-28894)
* 修正使用「電子郵件非空白」條件時，查詢編輯器中的自訂篩選器問題。 (CAMP-28741)
* 修正匯出包含超過100,000筆記錄的自訂資源表格時可能發生的問題。 (CAMP-28150)
* 修正無法刪除連結至觸發器的異動訊息的問題。 (CAMP-28385)
* 移除了某些SMS記錄檔中顯示的不安全密碼。
* 修正了由於Adobe Campaign傳送的空白密碼而導致與SMPP模擬器的連線失敗的問題。
* 修正了在SMS連線不穩定時無法傳送行銷活動的問題。
* 修正動態報告中顯示已刪除傳遞的問題。
* 修正在工作流程中使用擴充活動時，可能無法從傳遞記錄、追蹤記錄和排除記錄表格擷取其他資料的問題。
* 修正使用「N基數集合連結」連結型別及「刪除目標籤錄表示透過連結刪除記錄參考」選項時，GDPR刪除請求可能發生的問題。
* 修正報告共用問題。
* 修正傳送推播通知時，可能導致輸送量問題的問題。
* 修正直接郵件輸出檔案缺少欄位的問題。
* 修正允許使用者修改內建工作流程的問題。
* 修正根據行銷活動範本建立行銷活動時，包含具有已設定擷取活動的工作流程的問題。 (CAMP-29198)
* 修正檔案擷取活動無法將相同運算式用於數個元素的問題。 (CAMP-29182)
* 修正查詢編輯器中，rtEvent的broadlog和追蹤記錄之間連線條件的問題。 (CAMP-28780)
* 修正無法儲存「特定動作」登陸頁面選項修改的問題。 (CAMP-29422)
* 修正無法在工作流程中匯出事件裝載的問題。 (CAMP-29029)
* 修正封鎖清單上的SMS號碼無法在SMS訊息中排除的問題。 (CAMP-28898)
* 修正在處理傳入訊息時，在出現錯誤的情況下，無法通知SMPP提供者的問題。 (CAMP-29804)
* 修正允許刪除具有關聯傳遞的外部帳戶的問題。 (CAMP-29738)
* SMS訊息的傳送輸送量已改善並穩定。
* 修正的問題：無法在SMS訊息中使用「~」字元。 (CAMP-29172)
* 修正傳送時間最佳化選項的問題。 (CAMP-29231)
