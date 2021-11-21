---
title: 發行說明 2019 年
description: 本頁列出 2019 年的所有 Adobe Campaign Standard 版本。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: 6a53e6f5-9b69-4068-ab7d-10e22e266277
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '7588'
ht-degree: 8%

---

# 發行說明 2019 年{#release-notes-2019}

[發行計畫](https://helpx.adobe.com/tw/campaign/kb/acs-release-planning.html) | [「控制面板」發行版本](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hant) | [檔案更新](../../rn/using/documentation-updates.md) | [最新發行說明](../../rn/using/release-notes.md) | [過時的功能](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hant#release-notes)

## 發行版本19.4 - 2019年12月 {#release-19-4---october-2019}

**有哪些新增功能？**

<table> 
 <thead> 
  <tr> 
   <th> <strong>加州消費者隱私法(CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA是加州新推出的隱私權法，調和了2020年1月1日起生效的資料保護要求，並將其現代化。 CCPA適用於為居住在加州的資料主體保管資料的Adobe Campaign客戶。</p>
   <p>除了Adobe Campaign中已提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）之外，我們也趁此次機會加入其他功能，以協助您為CCPA做好準備：</p>
   <ul>
    <li>存取權與刪除權：我們善用針對GDPR新增的功能。 <a href="https://helpx.adobe.com/content/help/tw/campaign/kb/acs-privacy.html#righttoaccess">了解更多</a> </li>
    <li><p>建立隱私權要求時，隱私權核心服務已新增規範類型（GDPR或CCPA）。 此方法是您應該用於所有存取和刪除請求的方法。不建議使用促銷活動 API 和介面來存取和刪除請求。請參閱「<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">已過時和已移除的功能</a>」文章。</p></li>
    <li>A <strong>CCPA選擇退出</strong> 「設定檔」資源已新增欄位，讓Adobe Campaign使用者追蹤消費者是否選擇退出個人資訊銷售。 <a href="https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ccpa">深入瞭解</a>。</li>
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
    <p>Adobe Campaign Standard與Microsoft Dynamics 365之間的整合現已推出。 You’ll be able to transfer your contact and custom entity records from Dynamics 365 to Campaign, and get email event data back from Campaign to Dynamics 365 for better sales/marketing alignment.</p>
    <p>請參閱 <a href="../../integrating/using/d365-acs-get-started.md">詳細檔案</a> 來設定此整合。</p>
  </td>
  </tr> 
 </tbody> 
</table>

**功能改善**

* 已更新動態報告的同意快顯視窗，加入Adobe Campaign Standard和Microsoft Dynamics 365整合。 若接受條款，則使用Adobe Campaign Standard/Microsoft Dynamics 365整合和動態報告時，將會包含設定檔資料。 [了解詳情](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* 修正了在收到傳送警報時，顯示錯誤聯絡日期的問題。
* 當使用未知的內容參數提交交易式訊息事件時，Campaign現在會傳回「400」錯誤訊息，而非「500」。 (CAMP-28632)
* 新 **排除校樣** 區段已新增至動態報表中。 This segment is now selected by default to filter your reports. [閱讀全文](../../reporting/using/list-of-components-.md#segments)
* The **Message expiration** option has been added to push notification. 它可讓您指定訊息不再由Apple(APNS)或Android(FCM)傳送的到期日。 [閱讀全文](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* 已對 **載入檔案** 活動：工作流程記錄檔已更清楚且更詳細地說明檔案無法載入時發生的錯誤。 啟動 **將拒絕項保留在檔案中** 選項已重新命名 **拒絕**. [閱讀全文](../../automating/using/load-file.md)
* Multilingual related logs have been added to the sending logs to better understand sending failures due to missing languages in the uploaded CSV files.

**安全性改善功能**

* 修正透過隱私權請求刪除量化設定檔資訊時，除隔離清單中的電子郵件地址外，會移除所有資料的問題。
* 已增強安全性，以防止插入電子郵件標題。
* 已增強安全性，以抵御可使用xtk運算式(電子郵件HTML、文字內容和主旨、SMS及推播通知內容)的SSRF攻擊。

**電子郵件設計工具增強功能**

* 修正無法在插入電子郵件時追蹤取消訂閱、訂閱和登錄頁面連結的問題。 (CAMP-37809)
* 修正建立新電子郵件和選取範本時，可能導致錯誤的問題。 (CAMP-38000)
* 使用電子郵件設計工具編輯連結時，您現在可以使用 **底線連結** 選項。 此外， **目標** 屬性已新增，預設值設為 **無**. [閱讀全文](../../designing/using/styles.md#about-styling-links)
* 修正電子郵件內文文字元件中連結的顏色問題。 (CAMP-37330)
* 修正刪除影像時無法移除相關連結的問題。 (CAMP-37234)
* 修正無法在 **順序** 條件中動態內容的設定。 (CAMP-36883)
* 修正搜尋登錄頁面時的問題。 搜索已從最初建立的50個擴展到所有資料庫。 (CAMP-36839)
* 修正將修改儲存在 **開始日期：名稱** 欄位。 (CAMP-36606)
* 轉盤元件相容性警告已修改，以反映支援的電子郵件用戶端。
* 修正行動裝置的顯示問題。 高度屬性現在一律設為「height:自動」。 (CAMP-35497)
* 修正從結構元件刪除片段時，HTML中保留樣式和中繼標籤的問題。 (CAMP-35390)
* 修正更新可重複使用內容時的片段問題。 (CAMP-35186)
* 修正在電子郵件中僅顯示行動裝置條件式內容的問題。 (CAMP-35155)
* 修正隨機顯示零寬度不斷空格的問題。 (CAMP-35116)
* 修正 **另存為片段** 對話框。
* 修正在影像標題和替代文字中新增HTML標籤時的預覽問題。
* 修正在電子郵件設計工具中，使用舊版編輯器編輯電子郵件中建立的連結時的問題。
* Fixed an issue which left duplicated style tags in the content.
* 修正在電子郵件中插入個人化欄位時，日期格式的問題。
* 修正從HTML模式切換為純文字時的儲存問題。
* 修正按一下「鎖定和解除鎖定」選項時，在內嵌樣式屬性面板中新增邊界值的問題。
* 修正行動裝置預覽大小的問題，以改善轉譯效果。
* 修正範本和片段中按鈕大小的問題。
* 修正插入按鈕元件時影像大小的問題。

**其他變更**

* 已對齊資料在傳送KPI頁面和動態報告頁面上顯示的預設時間範圍，以防止報告結果不一致。 (CAMP-35148)
* 應用程式憑證過期時，記錄檔中已新增錯誤訊息。
* 裝載計算預覽現在包含自訂欄位大小，以防止推播通知失敗。 (CAMP-35303)
* The name of the **Rejects file** in the **Load file** activity can now be personalized in the same was as in the **File export** activity.
* 所有未連結至任何現成可用實體的自訂實體，現在都可透過API存取。
* 改善大型資源的資料庫效能。
* The descriptions of some errors occurring when sending SMS messages have been made clearer. (CAMP-36558)
* An error message now displays when executing a workflow&#39;s **Scheduler** activity that is connected to itself, either directly or through several activities, as this could lead to the instance&#39;s workflow server being stuck.
* 已改善以協助疑難排解交易式訊息：「資料」連結在事件設定畫面中已重新命名為「上次交易事件」，現在會以遞減順序列出接收的事件。 此外，已建立新的交易式事件狀態：&quot;targetingFailed&quot;。 當交易式傳訊模組無法擴充用於訊息定位的連結時，交易式事件現在會處於這個新狀態（而非「routingFailed」狀態）。
* 已改善將登錄頁面存取限制在特定地理或組織單位時的介面。 其目的是警告登錄頁面可能受到可見性條件的影響：現在，建立登錄頁面時必須選取地理和組織單位。 現在當選取裝置後，會顯示包含相關資訊的橫幅。 測試登錄頁面時顯示的錯誤訊息已更清楚。
* 在Campaign StandardAPI中，如果鍵值與來源鍵不同，或您使用自己的業務鍵值作為URI，而非Adobe提供的業務鍵，則無法使用PATCH操作來修改自訂鍵值。
* The &quot;Albanian - Macedonia&quot; language has been added to the preferred language drop-down list. (CAMP-35396)

**修補程式**

* 修正排程報表無法排序或搜尋的問題。
* 修正觸發器規則造成混合AND和OR規則的問題。
* Fixed an issue that displayed the Mobile property as Deleted in Launch. (CAMP-35382)
* 修正Adobe Campaign中無法同步AdobeLaunch行動屬性的問題。 (CAMP-35411、CAMP-35089、CAMP-35014、CAMP-35487)
* 修正當事件富含設定檔資料時，交易式推送訊息失敗的問題。 (CAMP-34385)
* 修正行動屬性未在多個環境上同步的問題。 (CAMP-37060)
* 修正在推播通知中使用聯絡人日期公式選取範本時的問題。 (CAMP-35300)
* 修正可能導致訊息傳送服務當機的問題。 (CAMP-35287)
* 修正循環直接郵件的問題，這些郵件全部以第一個事件日期定義。 (CAMP-35139)
* 修正新擴充的問題 **設定檔** 無法用於查詢的自訂資源。 (CAMP-35119)
* 修正 **修復資料庫結構** 已啟用共用配置的實例的模式。 (CAMP-35118)
* 修正在broadlogs上新增匯總資料時，導致SQL記錄錯誤的問題。 (CAMP-35034)
* 修正建立 **區段** 活動。 (CAMP-35033)
* 修正 **查詢** 阻止 **encryption_aescbcDecrypt** 函式 **encryption_aescbcEncrypt** 函式。 (CAMP-34952)
* 修正了 **追蹤記錄** 顯示在傳送中。 (CAMP-34855)
* 修正使用 **傳送時間最佳化** 自訂日期公式，可防止因工作流程其他資料發生錯誤而傳送推播通知。 (CAMP-30336)
* 修正無法發佈自訂資源的問題。 (CAMP-37425)
* 修正管理員使用者無法修改匯入套件的問題。  (CAMP-37176)
* 修正了工作流程中，如果傳送活動已連線至空白，則無法傳送校樣的問題 **讀取閱聽眾** 活動。 (CAMP-37164)
* 修正無法將自訂資源匯入新環境的問題。 (CAMP-36506)
* 修正點按報告中，造成影像隱藏百分比的問題(CAMP-36407)
* 修正嘗試匯出傳送說明欄位時發生的問題。 (CAMP-35467)
* 修正儘管傳送已完成，傳送狀態仍可能為「開始擱置中」的問題。 (CAMP-35355)
* Fixed an issue that prevented workflow logs from being displayed after enabling, then disabling SQL logs.

## 發行版本 19.3 – 2019 年 7 月 {#release-19-3---july-2019}

**有哪些新增功能？**

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
   <td> <p>為了更深入個人化，外部API活動可讓您透過REST API呼叫，將外部系統的資料匯入工作流程。 REST端點可以是客戶管理系統、Adobe I/O Runtime或Adobe Experience Cloud REST端點（例如Data Platform、Target、Analytics、Campaign）。</p><p>此功能目前正在公開測試。</p><p>如需詳細資訊，請參閱<a href="../../automating/using/external-api.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">作法影片</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流程區段報告<br /> </td> 
   <td> <p>此功能可讓行銷人員依區段代碼來劃分其傳送效能。 當您建立工作流程並使用分段活動來指派區段至傳送母體時，這些區段現在可以進入相同的傳送。 這可讓您根據單一傳送內的多個區段來顯示開啟/點按統計資料。</p><p>如需詳細資訊，請參閱<a href="../../reporting/using/creating-a-report-workflow-segment.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">作法影片</a>。</p></td>
  </tr> 
 </tbody> 
</table>

**安全性改善功能**

* 修正了安全性問題，以防止拒絕服務(DoS)攻擊無效請求以取得影像。 (CAMP-33454)

**電子郵件設計工具增強功能**

* 修正每次新增元件時，在HTML範本中新增其他HTML樣式標籤的問題，這可能會大幅增加範本大小。 (CAMP-34694)
* 修正無法使用某些右上角工具列選單選項的問題。 (CAMP-34577)
* 修正將鏡像頁面URL內容區塊插入電子郵件內容時發生的問題。 (CAMP-34779)
* 修正在電子郵件中使用JSPP程式碼時，導致難以編輯內容的問題。 (CAMP-34574)
* 修正當新增超連結至超連結時，導致頂端影像截斷的問題。 (CAMP-34382)
* 修正搭配Firefox使用電子郵件設計工具時的顯示問題。 (CAMP-34364)
* 修正在電子郵件中定義動態內容時，「進階」模式發生的數個問題。 (CAMP-34351、CAMP-34333、CAMP-34331)
* 修正動態內容規則編輯器(CAMP-34304、CAMP-34303)發生的數個問題。
* 修正「電子郵件設計工具設定」窗格無法顯示「連結」欄位的問題(CAMP-33749)。
* 修正已傳送電子郵件中YouTube圖示過大的問題。 (CAMP-33726)
* 修正了讓鏡像頁面內容可編輯的安全性問題。 (CAMP-33691)
* 修正在動態內容中使用大於符號時中斷HTML輸出的問題。 (CAMP-33688)
* 修正在「電子郵件設計工具」中編輯文字時，使用「還原」選項時發生的問題。 (CAMP-32565)
* 修正在還原樣式（而非移除樣式）時建立額外標籤的問題。 (CAMP-32359)
* 您現在可以定義電子郵件中使用的每個元件是否只會顯示在桌上型裝置上，或是只會顯示在行動裝置上。
* 您現在可以設定Social內容元件的寬度和高度。
* 修正刪除動態內容後，無法移除動態內容舊原始碼的問題。
* 修正修改電子郵件主旨後無法更新的問題。
* 修正將n:n欄結構放入工作區後無法選取的問題。
* 修正電子郵件控制面板中訊息縮圖模糊的問題。
* 修正Outlook中收到的電子郵件無法正確顯示背景的問題。
* 修正電子郵件設計工具首頁的一些排序問題。
* 修正使用動態內容複製變體時發生的問題。
* 「電子郵件設計工具設定」窗格中移除了一些不需要的欄位。

**其他改善項目**

* 透過與Adobe Experience Platform Location Services的整合，Adobe Campaign現在可相容，透過Experience PlatformSDK將位置型行銷訊息傳送給行動應用程式的訂閱者。 如需詳細資訊，請參閱[詳細文件](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)以瞭解詳情。
* 已改善報表功能，以提供更佳體驗。 若要使用此功能，您必須接受動態報告使用協定。 有關詳細資訊，請參閱 [詳細檔案](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* 在工作流程中，已新增新選項，以預覽工作流程接下來的十個執行。 有關詳細資訊，請參閱 [詳細檔案](../../automating/using/scheduler.md).
* 在排程器活動中，新選項可讓您為每月傳送選取特定星期的特定一天。 有關詳細資訊，請參閱 [詳細檔案](../../automating/using/scheduler.md).
* 建立沒有匯總期間的循環傳送時，傳送控制面板現在可讓您在傳送傳送前要求確認。 有關詳細資訊，請參閱 [詳細檔案](../../sending/using/confirming-the-send.md).
* 您現在可以使用已在工作流程外部訊號活動中宣告的事件變數，個人化傳送的標籤。 For more on this, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md).
* 已改善GDPR刪除查詢以提升效能。 (CAMP-33504)
* 「ftp」選項已從外部帳戶設定介面中移除。 (CAMP-34472)
* You can now enable and disable the SMTP test mode option for each email message. 有關詳細資訊，請參閱 [詳細檔案](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**其他變更**

* 傳送屬性介面中新增警告。 它會指定傳送是根據其匯總期間準備，並解凍以每天呼叫工作流程多次，您應確定沒有任何期間。 (CAMP-34393)
* 自訂資源設定畫面中已新增警告。 我們建議對自訂資源 ID 使用最多 30 個字元。這也適用於自訂資源欄位、索引和連結。
* 嘗試刪除登錄頁面用作確認訊息的交易式訊息時，現在會顯示訊息。
* 活動執行超過6小時時，現在工作流程記錄中會顯示警告。 這不適用於推播通知、傳送、訊號、開始、結束、分叉、AND-joint、排程和等待活動。
* 當您達到同時執行的工作流程數量上限時，現在工作流程記錄中會顯示警告。
* 已暫停或失敗狀態超過7天的工作流程現在會停止，以耗用較少的磁碟空間。 清除任務顯示在工作流程記錄檔中。
* 使用「傳輸檔案」活動時，如果檔案大小超過可用磁碟空間，現在會記錄錯誤。
* 無法再為應用程式內訊息中的次要按鈕選取重新導向至目的地URL動作。

**修補程式**

* 修正可能導致GDPR存取請求失敗的問題。
* 修正當針對唯一設定檔收到多個觸發器時，可能導致觸發器遭捨棄的問題。
* 修正登入後可能導致自訂資源發佈錯誤訊息的問題。
* 修正建立或擴充自訂資源時顯示空白頁面的問題。
* 已修正將appSubscriptionrcp作為目標維度的對象無法在行動傳送中用於目標定位的問題。
* 修正無法將硬退信電子郵件地址放入隔離區的錯誤。 (CAMP-24587)
* 修正新增類型規則，然後在儲存類型之前刪除該規則時發生的問題。 (CAMP-32789)
* 修正了在停用動態內容時，無法顯示登錄頁面內容的問題。 (CAMP-32924)
* 修正對主要傳送的屬性使用個人化時發生的循環傳送問題。 (CAMP-32983)
* 修正工作流程中，從包含傳入SMS訊息資料的轉變中無法讀取結果的問題。 (CAMP-33134)
* 修正結合復本和排除活動以建立對象時，在工作流程中發生的問題。 (CAMP-33401)
* 修正了無法顯示鏡像頁面內容，以及無法針對循環傳送傳送傳送校樣訊息的問題。 (CAMP-33413)
* 修正在設定檔與對象之間使用聯合活動時導致錯誤的問題。 此問題是由於輸入轉變中的識別鍵不相容所致。 (CAMP-33713)
* 修正在「測試」活動中，連按兩下「recCount」運算式時無法使用正確語法的問題。 (CAMP-33756)
* 修正開啟「帳單」技術工作流程記錄檔時，可能導致錯誤訊息的問題。 (CAMP-34313)
* 修正登錄頁面中，使用訂閱設定核取方塊欄位時可能發生的問題。 (CAMP-34369)
* 修正設定清單並新增「圖示」欄位時發生的問題。 (CAMP-34585)
* 修正無法在「載入檔案」工作流程活動中使用「|」和「%」符號做為日期或時間分隔符號的問題。 (CAMP-34706)
* 修正在登錄頁面中使用具有核取方塊的可見性條件時發生的問題。 (CAMP-34802)
* 修正「擴充」活動中，如果篩選維度設為追蹤記錄，而目標維度設為設定檔，則欄位無法顯示在「其他資料」標籤中的問題。
* 修正匯出「workflowTemplate」資源時導致錯誤訊息的問題。
* 修正建立新設定檔時，如果從對話方塊中選取「國家/地區代碼」欄位，則無法儲存該欄位的問題。
* 修正了使用直接郵件匯入範本(updateQuaninesDeliveryLogsDirectMail)時發生的數個問題。
* 修正與隨選資產整合相關的問題。
* 修正了在時間軸檢視上放大時發生的問題。 (CAMP-33628)
* 修正無法針對排程日期和時間的電子郵件訊息立即傳送校樣的問題。 (CAMP-33723)
* 修正與交易式訊息相關的問題，此問題會在使用者登出時產生錯誤記錄。 (CAMP-31698)
* 修正排程電子郵件訊息時，可能在特定環境上發生的錯誤。
* 修正導致更新傳送執行工作流程失敗的問題。
* 修正當主旨包含多行時，會中斷電子郵件內容的安全性問題。


## 發行版本 19.2.7 – 2019 年 7 月 {#release-19-2-7---july-2019}

**功能改善**

* 已改善GDPR刪除查詢以提升效能。
* Fixed an issue which could cause web crashes after the 19.2 upgrade. (CAMP-34862)
* 修正非管理員使用者無法儲存或排程報表的問題。 (CAMP-31133)
* 修正在「載入檔案」工作流程活動中使用「|」作為日期分隔符號的問題。 (CAMP-34706)

## 發行版本 19.2.4 – 2019 年 6 月 {#release-19-2-4---june-2019}

**電子郵件設計工具**

* 修正當HTML中使用空白樣式標籤時，使用者無法編輯片段的問題。 這是CAMP-33778 19.2.3的後續修正。

## 發行版本 19.2.3 – 2019 年 6 月 {#release-19-2-3---june-2019}

**電子郵件設計工具**

在19.2版本中導入了一系列改善和修正，以最佳化片段。 新建立的片段可順暢運作。 先前建置的片段會呈現灰色，且需要移轉至新格式。 若要這麼做，請按一下每個片段，並驗證其移轉至新格式。 建議您先測試幾個片段，再移轉所有片段。

* 修正解除鎖定片段後，使用者無法編輯片段的問題。 這在更新至19.2時會影響現有片段。 (CAMP-33778)
* 修正使用動態內容時的問題。 HTML中已新增額外空格。

**其他改善項目**

* 修正了SMS連接器斷線後，SMS傳送無法恢復的問題。
* 修正了啟用TLS時，可能會關閉SMPP連線的問題。
* 修正了啟用TLS時，可能會關閉SMPP連線的問題。
* 已在Campaign中新增「Launch_URL_Campaign」選項，以管理使用Adobe Experience Platform Mobile SDK建立之行動應用程式的屬性。
* 修正在上傳新建立行動屬性的憑證並退出行動應用程式屬性頁面後，取消勾選沙箱環境選項的錯誤。
* 修正無法透過服務資源的資訊擴充交易式訊息內容的問題。 (CAMP-33707)
* 修正了封鎖清單登錄頁面中嘗試從服務取消訂閱設定檔時發生的問題。

## 發行版本 19.2 – 2019 年 5 月 {#release-19-2---may-2019}

**有哪些新增功能？**

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
   <td> <p>若要協助您提高身為管理員使用者的工作效率，您可以輕鬆監控執行個體的容量並管理其設定（從SFTP伺服器管理開始）。</p><p>如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=zh-Hant">作法影片</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 本機通知<br /> </td> 
   <td> <p>本機通知訊息可讓您在行動應用程式內有新資料可用時通知使用者，即使無法存取網際網路或行動應用程式在前景執行亦然。 行動應用程式會在特定時間並根據事件來觸發本機通知。</p><p>如需詳細資訊，請參閱<a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">詳細文件</a>以瞭解詳情。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流程增強功能 — 將裝載新增至外部訊號活動<br /> </td> 
   <td> <p>從其他工作流程或REST API呼叫成功符合已定義的條件時，即可啟動具有裝載的工作流程，以便與外部系統整合。 這也包含新的 <strong>測試</strong> 活動，您可以對此功能執行測試。</p><p>如需詳細資訊，請參閱<a href="../../automating/using/calling-a-workflow-with-external-parameters.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">作法影片</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 登錄頁面增強功能 — Google reCAPTCHA<br /> </td> 
   <td> <p>運用Google reCAPTCHA來防止登陸頁面上出現垃圾訊息，而無須客戶採取任何動作。</p><p>如需詳細資訊，請參閱<a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">詳細文件</a>以瞭解詳情。</p></td> 
  </tr> 
 </tbody> 
</table>

**安全性改善功能**

* 修正報告工作區中潛在的點按頂升安全性問題。

**電子郵件設計工具增強功能**

* 修正重複片段並嘗試在電子郵件設計工具中使用片段時發生的問題。 (CAMP-33193)
* 修正在「電子郵件設計工具」介面中使用內嵌元素時，建立不想要空格的問題。 (CAMP-32163)
* 修正在「電子郵件設計工具」中儲存電子郵件內容後，刪除了使用者新增的其他HTML標籤屬性的問題。 (CAMP-32162)
* 修正即使移除Microsoft Office標籤後，仍會以「電子郵件設計工具」HTML模式顯示該標籤的問題。 (CAMP-32141)
* 如果您使用舊版電子郵件設計工具建立電子郵件，開啟此電子郵件內容時，現在會出現快顯視窗提示使用者更新為最新版本。 (CAMP-31529)
* 修正當傳送至某些傳訊用戶端時，使用電子郵件設計工具建立的電子郵件可能會扭曲影像的問題。 (CAMP-31407)
* 修正在HTML模式中建立清單或按鈕等元素時，無法以純文字模式正確顯示的問題。 (CAMP-32582, CAMP-32542)
* 修正無法在內容範本或片段屬性中顯示超過50個組織單位的問題。 (CAMP-32932)
* 修正了在Outlook中收到使用「電子郵件設計工具」建立的電子郵件時，檢視區背景顏色的問題。 (CAMP-31402)
* 修正在Outlook中開啟使用「電子郵件設計工具」建立的電子郵件內容時，無法回應的問題。 (CAMP-31400)
* 修正在電子郵件主旨中使用動態內容時無法正常運作的問題。 (CAMP-32837)
* 修正未正確逸出之電子郵件主題的相關問題。
* 修正電子郵件設計工具左側浮動視窗無法載入片段的問題。
* 修正重新整理片段清單時，電子郵件內容版本期間建立的片段無法顯示在「電子郵件設計工具」左側浮動視窗中的問題。
* 修正在電子郵件中使用動態內容時發生的數個問題。
* 修正嘗試使用RGB值定義顏色時，檢色器發生的問題。
* 修正在行動裝置上收到電子郵件時，鏡像頁面無法回應的問題。

**交易式訊息增強功能**

交易式訊息通道已新增數項改善，以最佳化操作與效能。

* 交易式訊息持續時間已延長，以確保所有訊息在過期前都傳送，尤其是在執行重試時。
* 在不同的傳送執行緒上分配負載，以提高交易式訊息效能。
* 交易式訊息傳送程式已最佳化，以能夠同時啟動同一訊息的多重分析。
* 修正交易推播通知的吞吐量和延遲可能不一致的問題。
* 修正交易式訊息執行傳送顯示錯誤目標對象的問題。
* 修正匯入包含事件設定和相關交易式訊息的套件時發生的問題。 有關詳細資訊，請參閱 [詳細檔案](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* 修正從針對包含產品清單的交易式訊息建立的測試設定檔中刪除收集資料的問題。

**其他變更**

* SMS外部帳戶已新增選項。 它可以限制傳送SMS的MTA程式數量上限，以便更妥善地控制平行連線的數量。 如需詳細資訊，請參閱 [SMS連接器通訊協定與設定](https://helpx.adobe.com/tw/campaign/kb/sms-connector-protocol-and-settings.html) 技術檔案。
* 使用API擴充功能發佈資源時，如果API已發佈，現在每次重新發佈時都會自動更新。 此動作過去為手動操作，且無法更新API，可能會中斷此API的設定檔或服務資源。 有關詳細資訊，請參閱 [詳細檔案](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* 郵遞區號維度已從動態報告中移除。 建議您改用「城市」、「國家/地區」、「州」維度。
* 應用程式內訊息的「首次啟動」生命週期事件觸發器已移除。
* 匯出包含安全組時，它現在包含指派給每個群組的角色。 (CAMP-32960)
* 在「載入檔案」活動中，新選項可讓您檢查要上傳的檔案的欄是否符合欄定義。 如需詳細資訊，請參閱[詳細文件](../../automating/using/load-file.md)以瞭解詳情。(CAMP-32229)
* 現在可以使用裝載來啟動工作流程，讓您在工作流程中的活動之間使用和共用外部參數。 如需詳細資訊，請參閱[詳細文件](../../automating/using/calling-a-workflow-with-external-parameters.md)以瞭解詳情。(CAMP-29412和CAMP-29413)
* Campaign StandardAPI現在可讓您使用裝載來更新設定檔的地理和組織單位。 如需詳細資訊，請參閱[詳細文件](../../api/using/get-started-apis.md)以瞭解詳情。
* 無法存取資料庫中的物件時，錯誤訊息已更清楚明瞭，以便了解。
* 在擷取檔案活動中，定義要匯出的檔案名稱時，已更新Javascript功能。 現在只有formatDate函式可在「輸出」欄位中使用。 如需詳細資訊，請參閱[詳細文件](../../automating/using/extract-file.md)以瞭解詳情。
* 改善自訂資源的自動序列ID產生。 新自訂資源的主要金鑰現在預設為64位元。
* 改善自訂資源發佈測試模式。 如果上次自訂資源發佈失敗且未修正，系統現在會向使用者顯示警告訊息。 在自訂資源發佈失敗後，您可以回復至上次使用的版本。 如需詳細資訊，請參閱[詳細文件](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)以瞭解詳情。
* 已在傳輸檔案活動中新增選項。 它可讓您在使用檔案下載動作時，以SFTP模式排序檔案。 如需詳細資訊，請參閱[詳細文件](../../automating/using/transfer-file.md)以瞭解詳情。(CAMP-33109)

**修補程式**

* 修正了重新載入SMS設定時，可能導致MTA記憶體洩漏的問題。
* 修正了無法在修復模式下發佈資料庫更新的問題。
* 修正造成「Adobe Analytics報表」與「Adobe Campaign動態報表」之間不一致的問題。 (CAMP-25393)
* 修正造成「報表」共用工作流程失敗的錯誤。
* 修正使用者無法只使用媒體URL傳送應用程式內訊息的錯誤。
* 修正即使未將行動應用程式的憑證上傳至執行個體，仍顯示該應用程式的問題。
* 修正使用 **鎖定行動應用程式的所有使用者** 範本。
* 已布建新的Campaign Standard執行個體。 (CAMP-32635和CAMP-32344)
* 修正無法在工作流程中自訂日期公式的錯誤。 (CAMP-30336)
* 修正定義自訂日期公式時，下拉式清單中無法提供「其他資料」和「區段代碼」欄位的問題。 (CAMP-32383)
* 修正「傳輸檔案」和「擷取檔案」活動在加密時無法找到檔案遭拒的問題。 (CAMP-32377)
* 修正API中，lineCount篩選器無法轉譯確切總計的問題。 (CAMP-31424)
* 修正登錄頁面中，修改輸入值後，輸入欄位無法顯示更新值的問題。 (CAMP-31401)
* 修正可能導致訊號活動意外啟動的問題。
* 修正對象空白時無法顯示電子郵件預覽的問題。
* 修正「擷取檔案」活動中，啟用「入站轉變為空時，請勿產生檔案」選項時，可能會產生檔案的問題。
* 修正傳遞工作流程未成功完成時，導致關閉的問題。
* 修正使用者無法儲存或排程報表的問題。 (CAMP-31133)

## 發行版本 19.1.3 – 2019 年 3 月 {#release-19-1-3---march-2019}

**電子郵件設計工具增強功能**

* 修正儲存範本後無法修改範本的問題。
* 修正在電子郵件中使用先前建立的範本時的各種問題。
* 修正無法在匯入的範本中隱藏元件的問題。

**其他改善項目**

* 修正檢視類型規則時的錯誤。 (CAMP-32059和CAMP-31849)
* 修正無法編輯類型規則的問題。 (CAMP-31750)
* 修正inMail程式可能意外停止的問題。 (CAMP-31238)

## 發行版本 19.1 – 2019 年 2 月 {#release-19-1---february-2019}

**有哪些新增功能？**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 推播通道報告改善<br /> </td> 
   <td> <p>推播通道報表已新增數項增強功能，可讓您更直覺地測量使用者參與度。 在此版本中，「推播」管道量度清單已擴增至三種量度：曝光數、點按次數、開啟次數（應用程式開啟次數）可協助您更有效測量和分析使用者與推播通知的互動。 除此之外，我們也標準化這些量度的定義與實作。 推播通知內建報表也已改良為常用的視覺效果和量度。</p><p> 如需詳細資訊，請參閱<a href="../../reporting/using/push-notification-report.md">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式的Launch整合<br /> </td> 
   <td> <p>此版本包含Adobe Campaign與Adobe Experience Platform Launch和行動SDK中適用於Adobe Campaign Standard的GA版Android和iOS擴充功能的整合。 這些擴充功能支援推送訊息、應用程式內訊息和行動應用程式設定檔更新。</p><p> 如需詳細資訊，請參閱<a href="https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式內傳訊<br /> </td> 
   <td> <p>此版本包含Campaign中的GA版應用程式內管道。 從功能角度來看，Beta版中最值得注意的新增項目為應用程式內管道動態報表，以及Mobile SDK與MCIAS之間的安全交握(為SDK提供應用程式內規則的Marketing Cloud應用程式內傳訊服務)。 安全交握可確保使用者的PII資料不會落入惡意人手，並可讓您在使用者每次登出時清除訊息快取，以維護共用裝置上的使用者隱私。</p><p>如需詳細資訊，請參閱 <a href="../../channels/using/about-in-app-messaging.md">詳細檔案</a> 和 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">應用程式內教學課程</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 工作流程增強功能<br /> </td> 
   <td> <p>已新增下列工作流程功能：</p> 
    <ul> 
     <li> 您現在可以從相同的Campaign例項複製貼上工作流程或其他工作流程中的活動。 這樣，您就可以輕鬆複製整個工作流程或特定活動，並保留最初定義的設定。 如需詳細資訊，請參閱<a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">詳細文件</a>以瞭解詳情。(CAMP-20014) </li> 
     <li> 使用 <strong>載入檔案</strong> 活動中，您現在可以將時間戳記新增至包含已拒絕記錄之檔案的名稱。 如需詳細資訊，請參閱<a href="../../automating/using/load-file.md#configuration">詳細文件</a>以瞭解詳情。 </li> 
     <li> <strong>查詢</strong> 和 <strong>區段</strong> 活動現在可讓您在活動未擷取任何資料時啟用出站轉變。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**安全性改善功能**

* 已更新產生的登錄頁面HTML代碼，以防止搜尋引擎索引。

**電子郵件設計工具增強功能**

* 由Behance藝術家設計的四組同級最佳回應式電子郵件範本現已推出。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/using-reusable-content.md#content-templates)以瞭解詳情。

* 我們的全新入門體驗可協助您更快開始建立電子郵件，並讓您更輕鬆地存取檔案和教學課程。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)以瞭解詳情。

* 您現在可以根據需求，靈活設定欄數和寬度。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)以瞭解詳情。

* 在行動檢視中編輯時，您可以僅在行動顯示中隱藏特定元件，以有效利用空間。

   如需詳細資訊，請參閱[詳細文件](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)以瞭解詳情。

* 您現在可以在現有的社交管道之上，將自訂的社交管道新增至您的電子郵件範本。
* 修正使用超過18個結構時，無法向下捲動結構功能表的問題。 (CAMP-31173)
* 修正轉送包含隨Adobe Campaign傳送之預先標題的電子郵件時，內容頂端會顯示預先標題的問題。 (CAMP-30736)
* 修正在按一下 **重新整理AEM內容** 選項(在Adobe Experience Manager中修改主題後)。 (CAMP-29984)
* 修正無法從Adobe Target使用動態影像的數個問題。
* 修正了先前從URL匯入內容時，在準備時擷取內容時無法更新預覽的問題。
* YouTube圖示已新增至 **社交** 內容元件。
* 此 **清單** 已針對「電子郵件設計工具」浮動視窗中顯示的內容元件和片段新增檢視。

**其他改善項目**

* Adobe Campaign現在已完全符合SDK V4和AEP SDK應用程式的FCM規範。
* Adobe Campaign支援Android版Wear OS的推播通知，以及Apple版的watchOS。
* 在介面中導覽時可能顯示的警告和錯誤訊息已更清楚且更容易了解。
* 您現在可以新增至與選擇加入和選擇退出（「不再聯絡……」欄位）相關的設定檔清單欄。
* 「設定檔」建立畫面中的「時區」下拉式清單已從「位址」區段移至介面的上方區段。
* 您現在可以在設定自訂資源畫面時新增分隔符號，讓您將欄位組織為類別。

   如需詳細資訊，請參閱[詳細文件](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)以瞭解詳情。

**其他變更**

* Adobe Campaign和Adobe Experience Cloud將於2019年春季起停止支援Microsoft Internet Explorer 11和Campaign Standard19.2版本。 請切換至 Microsoft Edge 或其他支援的瀏覽器。請參閱 [過時和移除的功能](../../rn/using/deprecated-features.md) 頁面。
* 此 **國家/地區代碼** 「設定檔」資源的欄位已重新命名為 **國家/地區代碼**.

**修補程式**

* 修正將測試設定檔新增至電子郵件交易式訊息時，無法傳送訊息的問題。 (CAMP-29854)
* 修正了當同時觸發從所有通道傳送的訊息時，一個通道的傳送率較低時，會拖慢從其他通道傳送訊息的問題。
* 修正當外部帳戶連線尚未建立時，MTA開始傳送SMS訊息的問題。
* 修正排程器活動執行頻率和開始時間的問題。 (CAMP-30745)
* 修正使用擴充設定檔資源時產生PKEY時可能發生的問題。 (CAMP-30285)
* 修正日曆日型疲勞規則可能發生的問題。 (CAMP-30136)
* 修正嘗試存取名稱以「Base」結尾的自訂資源時可能發生的問題。 (CAMP-30109)
* 修正無法使用PATCH呼叫將設定檔訂閱至服務的問題。 (CAMP-29728)
* 修正了透過「載入檔案」活動匯入XML檔案時，可能會損毀工作流程的問題。 (CAMP-29208和CAMP-28205)
* 修正連結自訂資源時，無法產生反向基數連結的問題。 (CAMP-30476)
* 修正僅使用區段代碼時無法擴充傳送記錄的問題。
* 修正在工作流程中使用檔案傳輸活動時，可能會複製列的問題。
* 修正無法在選擇的時間傳送排程報表的問題。
* 修正工作流程中應用程式內傳送的「傳送」和「已傳送」KPI之間不一致的問題。
* 修正使用自訂HTML製作的應用程式內訊息無法使用追蹤的問題。
* 修正在工作流程中使用應用程式內傳遞內容時無法儲存的問題。
* 修正無法為管理員顯示行動應用程式的問題。
* 修正「傳遞能力更新」技術工作流程失敗的問題。 (CAMP-26387)
* 修正建立應用程式內傳送時，目標設定檔與傳送控制面板中顯示的設定檔之間不一致的問題。 (CAMP-28722)
* 修正了「促銷活動」與「資產」核心服務整合，無法在電子郵件中選取共用資產的問題。

## 發行版本 19.0 – 2019 年 1 月 {#release-19-0---january-2019}

**有哪些新增功能？**

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
   <td> <p>新的直覺式電子郵件設計工具（舊稱Creative Designer）已移至GA。 現在支援舊版內容編輯器的所有功能，包括：</p> 
    <ul> 
     <li> 使用 <a href="../../integrating/using/adding-target-dynamic-content.md">動態影像來自Adobe Target</a> </li> 
     <li> 能夠 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">在準備時自動從URL擷取內容</a> </li> 
     <li> 完全相容 <a href="../../designing/using/using-reusable-content.md#content-templates">內容範本</a>. </li> 
    </ul> 
    <p>如需詳細資訊，請參閱<a href="../../designing/using/designing-content-in-adobe-campaign.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">作法影片</a>。以下列出改善項目和修正項目。</p><p>因此，舊版電子郵件內容編輯器現已過時。 如需詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">頁面</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 交易式電子郵件中的產品清單<br /> </td> 
   <td> <p>您現在可以在交易式電子郵件訊息中參考一或多個產品集合。 例如，您可以自動傳送放棄購物車電子郵件，列出使用者購物車中的所有產品，以及每個產品的影像、價格和連結。</p><p>如需詳細資訊，請參閱<a href="../../designing/using/using-product-listings.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">作法影片</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件設計工具中的行動裝置檢視<br /> </td> 
   <td> <p>您現在可以在編輯電子郵件內容時切換至專用的行動檢視。 這可讓您分別編輯行動顯示的所有樣式選項，例如調整邊界、縮小字型大小、改變背景顏色等，以微調電子郵件的回應式設計。</p><p> 如需詳細資訊，請參閱<a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內訊息測試版改善<br /> </td> 
   <td> <p>應用程式內訊息測試版功能已經過增強，現提供下列功能：</p> 
    <ul> 
     <li> 應用程式內Beta版管道符合GDPR規範 </li> 
     <li> 與Analytics API整合，以填入「觸發器」下拉式清單 </li> 
     <li> 傳遞範本的直覺式外觀和說明 </li> 
     <li> 從可用性角度對製作介面進行增強 </li> 
    </ul> <p>如需詳細資訊，請參閱<a href="../../channels/using/about-in-app-messaging.md">詳細文件</a>以瞭解詳情。</p> </td> 
  </tr> 
 </tbody> 
</table>

**功能改善**

* 「載入資料」活動中的新選項現在可讓您將後處理階段套用至包含已拒絕記錄的檔案(例如， 壓縮郵遞區號格式)。(CAMP-24521)
* 「更新資料」活動中的新選項現在可讓您設定要上傳之資料的最大批次大小。 (CAMP-28400)
* 改善設定檔的位址狀態選取。 選取國家時，「狀態」下拉式清單現在會自動更新為相關狀態值。 (CAMP-28874)
* A new option in the Extract file activity now prevents from generating a file if the inbound transition is empty. 這可避免在SFTP伺服器上建立和上傳空白檔案。
* 改善「傳送摘要」報表。
* 定義設定檔位址時可用的國家/地區清單已擴充。 (CAMP-26707)
* 現在嘗試匯入內建工作流程時，會顯示錯誤訊息。

**電子郵件設計工具**

* 修正即使在Adobe Campaign中停用了電子郵件範本或使用電子郵件設計工具建立的內容片段上啟用地理單位功能的問題，此問題導致在嘗試再次存取時無法使用範本或片段。 (CAMP-28174)
* 修正使用電子郵件設計工具編輯內容時無法儲存動態內容條件的問題。 (CAMP-27905)
* Fixed an issue that removed the HTML version from the email content after editing the plain text version of a message and breaking HTML synchronization in the Email Designer. (CAMP-28507)
* Fixed an issue that prevented the Email Designer interface to open when using Internet Explorer 11. (CAMP-28273)
* 修正了使用電子郵件設計工具將樣式設定套用至按鈕時，導致Microsoft Outlook轉譯失真的問題。
* Fixed an issue in the Email Designer that made editable a URL from a content fragment used in an email, which was not expected as the fragment is locked by default.
* 修正無法在Microsoft Office中顯示電子郵件設計工具分隔元件的問題。
* 修正使用舊版電子郵件內容編輯器檢視從AEM同步的內容時，造成某些網際網路瀏覽器頁面凍結的問題。 (CAMP-29068)
* 修正使用舊版電子郵件內容編輯器時，按一下電子郵件中的任何影像時發生的錯誤。 (CAMP-30424)
* 修正使用電子郵件設計工具編輯電子郵件時，無法顯示新建立片段的問題。 (CAMP-29928)
* 修正在使用「電子郵件設計工具」建立並使用Outlook網頁郵件用戶端接收的電子郵件中，無法正確顯示按鈕文字的問題。
* It is now possible to create profile transactional messages using the Email Designer. (CAMP-28900)
* 修正「電子郵件設計工具」中，在準備時從URL自動擷取內容時，讓內容可編輯的錯誤，但此錯誤應已鎖定。

**修補程式**

* 修正動態報告中顯示錯誤傳送記錄的問題。 (CAMP-23446)
* 修正可能影響「退回摘要」報表上數字的問題(CAMP-28703)
* 修正促銷活動與資產核心服務整合的問題，若選取 **[!UICONTROL Image shared from Adobe Experience Cloud]** (CAMP-28732)。
* 修正即使音譯已在SMPP外部帳戶中授權，仍無法傳送包含&#39;oe&#39;字元的SMS訊息的問題。 (CAMP-29041)
* 修正在工作流程中使用分段活動時，可能顯示重複記錄的問題。 (CAMP-28743)
* 修正無法刪除工作流程活動中欄上其中一個值對應的問題。 (CAMP-28708)
* 修正了在檔案傳輸活動中使用萬用字元搭配「測試以查看檔案是否存在」選項的問題。 (CAMP-28977)
* 修正更新外部帳戶設定時，可能發生的檔案傳輸活動問題。 (CAMP-28894)
* 修正使用「電子郵件非空白」條件時，查詢編輯器中自訂篩選器的問題。 (CAMP-28741)
* 修正了匯出自訂資源表格（包含超過100,000筆記錄）時可能發生的問題。 (CAMP-28150)
* 修正無法刪除連結至觸發器的交易式訊息的問題。 (CAMP-28385)
* 移除某些SMS記錄檔中無法安全顯示的密碼。
* 修正由於Adobe Campaign傳送的空密碼，導致與SMPP模擬器的連線失敗的問題。
* 修正當SMS連線不穩定時，無法傳送促銷活動的問題。
* 修正在動態報告中顯示已刪除傳送的問題。
* 修正在工作流程中使用擴充活動時，無法從傳送記錄檔、追蹤記錄檔及排除記錄檔表格擷取其他資料的問題。
* 修正了GDPR刪除請求的問題，此問題在使用「N基數收集連結」連結類型和「刪除目標籤錄即表示連結刪除記錄參考」選項時可能發生。
* 修正報告共用的問題。
* Fixed an issue which could lead to throughput issues when sending a push notification.
* 修正直接郵件輸出檔案缺少欄位的問題。
* 修正允許使用者修改內建工作流程的問題。
* 修正根據促銷活動範本建立促銷活動時，包含已設定擷取活動之工作流程的問題。 (CAMP-29198)
* 修正檔案擷取活動無法對數個元素使用相同運算式的問題。 (CAMP-29182)
* 修正了在查詢編輯器中，broadlog和rtEvent追蹤記錄之間出現連接條件的問題。 (CAMP-28780)
* 修正無法儲存對「特定動作」登陸頁面選項修改的問題。 (CAMP-29422)
* 修正無法在工作流程中匯出事件裝載的問題。 (CAMP-29029)
* 修正封鎖清單上的SMS號碼無法在SMS訊息中排除的問題。 (CAMP-28898)
* 修正了處理傳入訊息時發生錯誤時，無法通知SMPP提供者的問題。 (CAMP-29804)
* 修正允許刪除與相關聯傳送之外部帳戶的問題。 (CAMP-29738)
* 已改善並穩定SMS訊息的傳送輸送量。
* 修正SMS訊息中無法使用「~」字元的問題。 (CAMP-29172)
* 修正了傳送時間最佳化選項的傳送問題。 (CAMP-29231)
