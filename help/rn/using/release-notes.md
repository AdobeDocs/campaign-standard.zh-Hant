---
title: 發行說明
seo-title: 發行說明
description: 發行說明
seo-description: 此頁面列出所有最新版本的Adobe Campaign Standard。
page-status-flag: 從未啓動
uuid: cf2e40c-beca-43db-8261-a1820 ee86 ad3
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release
discoiquuid: 5c7bfb74-4002-3ffe-87e8-bddb41 d34 b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 830292bd6f5bbd143ad0c674aaac67b67abc5665

---


# Release Notes{#release-notes}

尋找特定版本的Adobe Campaign Standard嗎？

每個版本都隨附新功能和修補程式。按一下版本可檢視其內容。Consult the [Release Planning](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) to find out when the next release will happen.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a previous release, consult these pages: [2018 Release Notes](../../rn/using/release-notes-2018.md), [2017 Release Notes](../../rn/using/release-notes-2017.md), [2015-2016 Release Notes](../../rn/using/release-notes-2015-2016.md). Also consult the list of [Deprecated and Removed Features](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

## Release 19.2.7 - July 2019 {#release-19-2-7---july-2019}

### Improvements {#improvements-2}

* GDPR刪除查詢已改進，以提高效能。
* 修正19.2升級後網路當機的問題。(CAMP-34862)
* 修正無法讓非管理員使用者儲存或排程報告的問題。(CAMP-31133)
* 修正使用時|」作為載入檔案工作流程活動中的日期分隔符號。(CAMP-34706)

## Release 19.2.4 - June 2019 {#release-19-2-4---june-2019}

### Email Designer {#email-designer-2}

* 修正HTML中使用空白樣式標記時，使用者無法編輯片段的問題。這是AMP-33778在19.2.3中的後續修正。

## Release 19.2.3 - June 2019 {#release-19-2-3---june-2019}

### Email Designer {#email-designer-1}

推出一系列改良和修正，以最佳化19.2版本中的片段。新建立的片段可順暢運作。先前建立的片段已過時，必須移轉至新格式。若要這麼做，請按一下每個片段並驗證其移轉至新格式。建議您先測試幾個片段，然後再轉換所有片段。

* 修正使用者解除鎖定片段後無法編輯片段的問題。更新至19.2時會影響現有片段。(CAMP-33778)
* 修正使用動態內容的問題。HTML中新增了額外空間。

### Other improvements {#other-improvements-2}

* 修正SMS連接器中斷連線後，無法繼續傳送SMS傳送的問題。
* 已修正啓用TLS時，可能關閉SMPP連線的問題。
* 已修正啓用TLS時，可能關閉SMPP連線的問題。
* Campaign中已新增「Launch_ URL_ Campaign」選項，以管理使用Adobe Experience Platform Mobile SDK建立的行動應用程式屬性。
* 修正在上傳新建立行動屬性的憑證並退出行動應用程式屬性頁面後，導致沙箱環境選項未勾選的錯誤。
* 修正您無法利用「服務」資源中的資訊豐富交易訊息內容的問題。(CAMP-33707)
* 修正在嘗試取消訂閱服務中的描述檔時，列入黑名單的著陸頁面問題。

## Release 19.2 - May 2019 {#release-19-2---may-2019}

### What's new? {#what-s-new-}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Control Panel<br /> </td> 
   <td> <p>為協助您以管理員使用者的身分提高工作效率，您可以輕鬆監控執行個體的容量並管理執行個體的設定(從SFTP伺服器管理開始)。</p><p>For more information, refer to the <a href="https://helpx.adobe.com/campaign/kb/control-panel.html">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-control-panel-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Local notifications<br /> </td> 
   <td> <p>本機通知訊息可讓您在行動應用程式中提供新資料時通知使用者，即使沒有網際網路或在前景上執行的行動應用程式亦然。本機通知會在特定時間和根據事件觸發行動應用程式。</p><p>For more information, refer to the <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">detailed documentation</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Workflow enhancement - Add a payload to external signal activity<br /> </td> 
   <td> <p>從其他工作流程成功符合定義條件，或REST API呼叫與外部系統整合，以啓動工作流程。This also includes a new <strong>test</strong> activity where you can run tests on this functionality.</p><p>For more information, refer to the <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-external-signal-activity-feature-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Landing Pages enhancement - Google reCAPTCHA<br /> </td> 
   <td> <p>利用Google ReCAPTCHA防止垃圾郵件在您的登陸頁面上出現，而不需要客戶採取任何動作。</p><p>For more information, refer to the <a href="../../channels/using/designing-a-landing-page.md#setting-google-recaptcha">detailed documentation</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements}

* 已修正報告工作區中潛在的點按安全性問題。

### Email Designer enhancements {#email-designer-enhancements}

* 修正重復片段並嘗試在電子郵件設計工具中使用它們時所發生的問題。(CAMP-33193)
* 修正在電子郵件設計人員介面中使用內嵌元素時，建立不想要空間的問題。(CAMP-32163)
* 修正在電子郵件設計人員中儲存電子郵件內容後，刪除使用者新增之其他HTML標籤屬性的問題。(CAMP-32162)
* 修正即使在將Microsoft Office標記移除後，仍會顯示Microsoft Office標記的問題。(CAMP-32141)
* 如果您使用舊版電子郵件設計程式建立電子郵件，開啓此電子郵件內容時，快顯視窗現在會提示使用者更新至最新版本。(CAMP-31529)
* 修正當傳送給某些傳訊用戶端時，使用電子郵件設計工具建立的電子郵件會造成影像扭曲的問題。(CAMP-31407)
* 修正當以HTML模式建立清單或按鈕等元素時，無法以純文字模式正確顯示的問題。(CAMP-32582，SAMP-32542)
* 修正無法在內容範本或片段屬性中顯示超過50個組織單位的問題。(CAMP-32932)
* 修正在Outlook上接收電子郵件設計人員建立的電子郵件時，檢視區背景顏色的問題。(CAMP-31402)
* 修正在Outlook中開啓時，以電子郵件設計人員建立的電子郵件內容無法回應的問題。(CAMP-31400)
* 修正動態內容在電子郵件主體中使用時無法正常運作的問題。(CAMP-32837)
* 已修正未正確逸出的電子郵件主旨相關問題。
* 修正「電子郵件設計師」左側浮動視窗無法載入片段的問題。
* 修正在重新整理片段清單時，電子郵件內容版本期間建立的片段無法顯示在「電子郵件設計師」左側浮動視窗中的問題。
* 已修正在電子郵件中使用動態內容時發生的數個問題。
* 修正在嘗試使用RGB值定義顏色時，檢色器發生的問題。
* 修正在行動裝置上接收電子郵件時，鏡像頁面無法回應的問題。

### Transactional Messaging enhancements {#transactional-messaging-enhancements}

Transactional Messaging頻道已增加數項改進，以最佳化運作與效能。

* 交易訊息持續時間已延長，以確保所有訊息在過期之前都傳送，尤其是執行重試時。
* 透過發送不同傳送緒上的負載，來提高交易傳訊效能。
* 交易傳訊程序已最佳化，可同時進行同一訊息的多個分析。
* 修正交易推播通知的總處理能力和延遲不一致的問題。
* 修正交易訊息執行傳送顯示不正確目標對象的問題。
* 修正在匯入套件及相關聯的交易訊息時，匯入套件的問題。For more on this, refer to the [detailed documentation](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* 已修正針對包含產品清單之交易訊息建立的測試設定檔中，刪除系列資料的問題。

### Other changes {#other-changes}

* SMS外部帳戶已新增新選項。它可限制傳送SMS的MTA程序數目上限，以更好地控制並行連線數目。For more information, refer to the [SMS connector protocol and settings](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) technote.
* 使用API擴充功能發佈資源時，如果API已發佈，現在會在每次發佈時自動更新。之前此動作是手動的，而且無法更新API可能會破壞此API的描述檔或服務資源。For more on this, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* 已從動態報表中移除郵遞區號維度。建議您改用城市、國家、州維度。
* 已移除應用程式內訊息的「首次啓動」生命週期事件觸發器。
* 將套件匯出為安全群組時，現在會包含指派給每個群組的角色。(CAMP-32960)
* 在載入檔案活動中，新選項可讓您檢查上傳的檔案欄是否符合欄定義。For more information, refer to the [detailed documentation](../../automating/using/load-file.md). (CAMP-3229)
* 工作流程現在可以開始使用裝載，讓您在工作流程中使用和共用活動之間的外部參數。For more information, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412與Camp-29413)
* Campaign Standard API現在可讓您使用裝載來更新設定檔的地理和組織單位。For more information, refer to the [detailed documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).
* 無法存取資料庫中物件的錯誤訊息已獲得深入瞭解。
* 在提取檔案活動中，Javascript功能在定義要匯出的檔案名稱時已更新。現在僅能在「輸出」欄位中使用FormatDate函數。For more information, refer to the [detailed documentation](../../automating/using/extract-file.md).
* 自訂資源的自動序列ID產生已改善。新自訂資源的主要索引鍵現在預設為64位元。
* 自訂資源出版測試模式已改善。如果上次自訂資源出版物失敗且未修正，現在會向使用者顯示警告訊息。自訂資源出版失敗後，您可以返回最後一個工作版本。For more information, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* 「轉移」檔案活動中新增了一個新選項。它可讓您在SFTP模式中使用檔案下載動作時，對檔案進行排序。For more information, refer to the [detailed documentation](../../automating/using/transfer-file.md). (CAMP-33109)

### Patches {#patches}

* 修正當重新載入SMS設定時，可能會導致記憶體洩漏的問題。
* 修正無法在修復模式中更新資料庫更新的問題。
* 修正造成Adobe Analytics報表與Adobe Campaign動態報表之間不一致的問題。(CAMP-25393)
* 修正造成報表共用工作流程失敗的錯誤。
* 修正使用者無法只使用Media URL傳送應用程式內訊息的錯誤。
* 修正即使其憑證未上傳至例項，仍會顯示行動應用程式的問題。
* Fixed an error that prevented personalization fields from working when using the **Target all users of a Mobile app** template.
* 已布建新促銷活動標準例項。(CAMP-32635與Camp-32344)
* 修正工作流程中無法自訂日期公式的錯誤。(CAMP-30336)
* 修正在定義自訂日期公式時，無法在下拉式清單中使用「其他資料」和「區段代碼」欄位的問題。(CAMP-32383)
* 修正「轉移檔案」和「擷取檔案」活動無法在檔案加密時尋找檔案的問題。(CAMP-32377)
* 修正API中無法顯示完全計數的API問題。(CAMP-31424)
* 修正著陸頁面中的問題，此問題可防止輸入欄位在修改後的值顯示。(CAMP-31401)
* 修正可能導致訊號活動意外啓動的問題。
* 修正當觀眾為空白時，無法顯示電子郵件預覽的問題。
* 已修正「擷取檔案」活動中，「如果傳入的轉場是空」選項，「不產生檔案」時可能產生檔案的問題。
* 修正「傳送能力」工作流程無法成功完成時關閉的問題。
* 修正使用者無法儲存或排程報告的問題。(CAMP-31133)

## Release 19.1.3 - March 2019 {#release-19-1-3---march-2019}

### Email Designer enhancements {#email-designer-enhancements-1}

* 修正範本儲存後無法修改範本的問題。
* 修正在電子郵件中使用先前建立範本時的各種問題。
* 修正元件無法隱藏在匯入範本中的問題。

### Other improvements {#other-improvements}

* 修正檢視類文規則時的錯誤。(CAMP-32059與Camp-31849)
* 修正無法編輯打字規則的問題。(CAMP-31750)
* 已修正無法預期停止的Inmail程序問題。(CAMP-31238)

## Release 19.1 - February 2019 {#release-19-1---february-2019}

### What's new? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Push channel Reporting improvements<br /> </td> 
   <td> <p>推播管道報告新增了幾項增強功能，讓您能夠更直覺地測量使用者互動。在這個版本中，我們將推送管道量度清單擴充至三個不同的量度：印象、點按、開啓(應用程式開啓)，以協助您更有效地測量和分析使用者與推播通知的互動。此外，我們也標準化這些度量的定義和實施。此外，推播通知內建報告也已使用常用的視覺化和度量改進。</p><p> For more information, refer to the <a href="../../reporting/using/push-notification-report.md">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Launch integration for Mobile App<br /> </td> 
   <td> <p>此版本包含Adobe Campaign與GA版本的Android和iOS延伸功能(Adobe Experience Platform Launch和Mobile SDK中的Adobe Campaign Standard)的整合。這些擴充功能支援推送訊息、應用程式內傳訊和行動應用程式設定檔更新。</p><p> For more information, refer to the <a href="../../administration/using/about-typology-rules.md#typology-rules">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile In-App Messaging<br /> </td> 
   <td> <p>此版本包含Campaign中的GA應用程式內頻道GA版本。從功能觀點來看，Beta版最明顯的新增功能是應用程式內頻道，以及在Mobile SDK和MCIAS之間的安全交握(Marketing Cloud應用程式內訊息服務，提供應用程式內規則至SDK的Marketing Cloud應用程式內訊息服務)。安全交握可確保使用者的PII資料不會落入惡意手中，也可讓您在每次使用者登出時清除訊息快取，以維持使用者在共用裝置上的隱私權。</p><p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a> and the dedicated <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-in-app-message-tutorial.html">In-App tutorial</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Workflow enhancements<br /> </td> 
   <td> <p>已新增下列工作流程功能：</p> 
    <ul> 
     <li> 您現在可以從工作流程中複製活動，或從相同的促銷活動例項中複製其他工作流程。如此，您就可以輕鬆複製整個工作流程或特定活動，並保留最初定義的設定。For more information, refer to the <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">detailed documentation</a>. (Camp-2014) </li> 
     <li> When using the <strong>Load file</strong> activity, you can now add a timestamp to the name of the file containing the rejected records. For more information, refer to the <a href="../../automating/using/load-file.md#configuration">detailed documentation</a>. </li> 
     <li> <strong>現在，如果活動沒有擷取任何資料，則查詢</strong> 和 <strong>劃分</strong> 活動可讓您啓用傳出轉場。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements-1}

* 產生的著陸頁面HTML程式碼已更新，以防止搜尋引擎索引。

### Email Designer enhancements {#email-designer-enhancements-2}

* Behance藝術家現在已提供四種同級最佳的回應式電子郵件範本。

   For more information, refer to the [detailed documentation](../../start/using/about-templates.md#content-templates).

* 我們新的入門體驗將幫助您加快電子郵件建立速度，並讓您更輕鬆地存取文件和教學課程。

   For more information, refer to the [detailed documentation](../../designing/using/about-email-content-design.md#email-designer-home-page).

* 您現在可以靈活地根據需求設定欄數和寬度。

   For more information, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

* 在行動檢視中編輯時，您可以隱藏行動顯示中的某些元件，以有效使用空間。

   For more information, refer to the [detailed documentation](../../designing/using/about-email-content-design.md#switching-to-mobile-view).

* 您現在可以在已提供的電子郵件範本之上新增自訂社交頻道。
* 修正使用超過18個結構時，無法向下捲動結構選單的問題。(CAMP-31173)
* 修正在轉寄包含隨Adobe Campaign傳送之首標題的電子郵件時，內容頂端顯示前置標題的問題。(CAMP-30736)
* Fixed an issue that prevented the subject line from being updated when clicking the **Refresh AEM content** option after modifying the subject in Adobe Experience Manager. (CAMP-29984)
* 修正無法從Adobe Target使用動態影像的數個問題。
* 修正當先前從URL匯入內容時，在準備時擷取內容時無法更新預覽的問題。
* The YouTube icon has been added to the **Social** content component.
* The **List** view has been added for content components and fragments displayed in the Email Designer palette.

### Other improvements {#other-improvements-1}

* 對於SDK V和AEP SDK應用程式，Adobe Campaign現在完全符合FCM標準。
* Adobe Campaign支援Android的推播通知以及Apple的WatchOS推播通知。
* 在介面中導覽時可能顯示的警告和錯誤訊息已獲得清晰易懂的資訊。
* 您現在可以新增至與選擇加入和選擇退出相關的描述檔清單欄(「不再連絡…」欄位)。
* 描述檔建立畫面中的時區下拉式清單已從「位址」區段移至介面的上半部。
* 您現在可以在設定自訂資源畫面時新增分隔符號，讓您將欄位組織成類別。

   For more information, refer to the [detailed documentation](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

### Other changes {#other-changes-1}

* Adobe Campaign和Adobe Experience Cloud將對開始於2011年春季及Campaign Standard19.2版的Microsoft Internet Explorer11提供支援。請切換至Microsoft Edge或其他支援的瀏覽器。See [Deprecated and removed features](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) page.
* The **Country code** field from the Profile resource has been renamed to **Country/Region code**.

### Patches {#patches-1}

* 修正新增測試描述檔至電子郵件交易訊息時，無法傳送訊息的問題。(CAMP-29854)
* 修正當從所有頻道傳送訊息時，一個頻道傳送的訊息較低時，會減緩從其他頻道傳送訊息的問題。
* 修正尚未建立外部帳戶連線時，MTA開始傳送SMS訊息的問題。
* 修正Scheduler活動執行頻率和開始時間的問題。(CAMP-30745)
* 修正使用延伸描述檔資源時，產生PKE的問題。(CAMP-30285)
* 修正日曆日期疲勞規則可能發生的問題。(CAMP-30136)
* 修正嘗試存取自訂資源時，名稱結尾為「基本」的問題。(CAMP-30109)
* 修正無法使用修補呼叫來訂閱服務的問題。(CAMP-29728)
* 修正透過載入檔案活動匯入XML檔案時，可能會破壞工作流程的問題。(Camp-29208和Camp-28205)
* 修正連結自訂資源時，可能導致反向連結連結產生的問題。(CAMP-30476)
* 修正僅在使用區段代碼時無法擴充傳送記錄檔的問題。
* 修正使用工作流程中檔案傳輸活動時，可能重復列的問題。
* 修正計劃報表無法在選定時間傳送的問題。
* 修正在工作流程中「若要傳送」和「傳送的」KPI在工作流程中造成不一致的問題。
* 修正無法追蹤使用自訂HTML編寫之應用程式內訊息的問題。
* 修正在工作流程中，無法儲存應用程式內傳送內容的問題。
* 修正無法為管理員顯示行動應用程式的問題。
* 修正「傳送能力更新」技術工作流程失敗的問題。(CAMP-26387)
* 修正造成在建立應用程式內傳送和顯示在傳送控制面板中的報表中，設定目標之間不一致的問題。(CAMP-28722)
* 修正促銷活動與資產核心服務整合無法在電子郵件中選取共用資產的問題。

## Release 19.0 - January 2019 {#release-19-0---january-2019}

### What's new? {#what-s-new--2}

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Email Designer General Availability<br /> </td> 
   <td> <p>全新的直覺式電子郵件設計人員(舊稱為Creative Designer)已移轉至GA。它現在支援舊版內容編輯器中的所有功能，包括：</p> 
    <ul> 
     <li> The use of <a href="../../integrating/using/adding-target-dynamic-content.md">dynamic images from Adobe Target</a> </li> 
     <li> The ability to <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">retrieve content from a URL automatically at preparation time</a> </li> 
     <li> Fully compliant <a href="../../start/using/about-templates.md#content-templates">out-of-the box content templates</a>. </li> 
    </ul> 
    <p>For more information, refer to the <a href="../../designing/using/about-email-content-design.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html">how-to video</a>. 以下列出改進和修正。</p><p>因此，舊版電子郵件內容編輯器現已過時。For more information, refer to this <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Product Listings in Transactional Emails<br /> </td> 
   <td> <p>您現在可以在交易式電子郵件訊息中參照一或多個產品系列。例如，您可以自動傳送購物車放棄電子郵件，列出使用者購物車中包含影像、價格和連結的所有產品。</p><p>For more information, refer to the <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html">how-to video</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile View in the Email Designer<br /> </td> 
   <td> <p>編輯電子郵件內容時，您現在可以切換至專用的行動裝置檢視。這可讓您透過個別編輯行動顯示的所有樣式選項，來微調電子郵件的多方互動設計，例如調整邊界、較小的字體大小、不同背景色彩等等。</p><p> For more information, refer to the <a href="../../designing/using/about-email-content-design.md#switching-to-mobile-view">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> In-App Messaging Beta Improvements<br /> </td> 
   <td> <p>「應用程式內訊息測試」功能已增強，具備下列功能：</p> 
    <ul> 
     <li> 應用程式內測試版與GDPR相容 </li> 
     <li> 與Analytics API整合以填入觸發器 </li> 
     <li> 傳送範本的直覺式外觀和說明 </li> 
     <li> 製作介面的增強功能從可用性標準 </li> 
    </ul> <p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* 載入資料活動中的新選項現在可讓您將處理後階段套用至包含已拒絕記錄的檔案(例如。壓縮格式壓縮)。(CAMP-24521)
* 「更新」資料活動中的新選項現在可讓您設定要上載資料的最大批次大小。(CAMP-28400)
* 已改善設定檔的位址狀態選擇。選取國家時，「州」下拉式清單現在會自動更新為相關狀態值。(CAMP-28874)
* 「摘取」檔案活動中的新選項現在可防止傳入的轉場變成空白。如此可避免在SFTP伺服器上建立和上傳空白檔案。
* 傳送摘要報表已改善。
* 定義描述檔位址時可用國家/地區清單已過豐富。(CAMP-26707)
* 嘗試匯入內建工作流程時，現在會顯示錯誤訊息。

### Email Designer {#email-designer}

* 修正即使在Adobe Campaign中停用此功能，卻在電子郵件範本或使用電子郵件設計工具建立的內容片段上啓用地理單位功能的問題，這使得範本或片段在嘗試再次存取時無法使用。(CAMP-28174)
* 修正使用電子郵件設計工具編輯內容時，無法儲存動態內容條件的問題。(CAMP-27905)
* 修正在電子郵件設計人員中編輯純文字版本的訊息並中斷HTML同步後，從電子郵件內容移除HTML版本的問題。(CAMP-28507)
* 修正使用Internet Explorer11時無法開啓電子郵件設計人員介面的問題。(CAMP-28273)
* 修正使用電子郵件設計工具將樣式設定套用至按鈕時，Microsoft Outlook會顯示樣式設定的問題。
* 修正電子郵件設計工具中，從電子郵件使用的內容片段編輯URL時，無法預期的問題，因為預設片段已鎖定。
* 修正無法在Microsoft Office中顯示電子郵件設計人員分隔元件的問題。
* 修正在使用舊版電子郵件內容編輯器檢視從AEM同步的內容時，導致某些網際網路瀏覽器凍結頁面的問題。(CAMP-29068)
* 修正在使用舊版電子郵件內容編輯器時，按下電子郵件中任何影像時所發生的錯誤。(CAMP-30424)
* 修正使用電子郵件設計工具編輯電子郵件時，新建立的片段無法顯示的問題。(CAMP-29928)
* 修正在使用電子郵件設計工具建立並使用Outlook網路郵件用戶端收到的電子郵件中，無法正確顯示按鈕文字的問題。
* 現在可以使用電子郵件設計工具建立設定檔交易訊息。(CAMP-28900)
* 修正電子郵件設計工具中，在準備時間自動從URL擷取內容時，造成內容無法編輯的錯誤，但應加以鎖定。

### Patches {#patches-2}

* 修正動態報告中顯示錯誤傳送記錄的問題。(CAMP-23446)
* 修正反彈摘要報表上可能會影響數字的問題(Camp-28703)
* Fixed an issue with the Campaign and Assets Core Service integration which could prevent assets from being displayed when selecting **[!UICONTROL Image shared from Adobe Experience Cloud]** in an email (CAMP-28732).
* 修正即使在SMPP外部帳戶中授權翻譯，仍無法傳送包含「œ」字元之SMS訊息的問題。(CAMP-29041)
* 修正在工作流程中使用區段活動時，可能顯示重復記錄的問題。(CAMP-28743)
* 修正工作流程活動中，無法刪除欄上一個值對應的問題。(CAMP-28708)
* 修正檔案傳輸活動中使用萬用字元與「測試是否存在(是否存在)」選項時的問題。(CAMP-28977)
* 修正了在更新外部帳戶設定時可能發生的檔案傳輸活動問題。(CAMP-28894)
* 修正使用「電子郵件非空白」條件時，查詢編輯器中自訂篩選器的問題。(CAMP-28741)
* 修正匯出超過100k記錄的自訂資源表格時可能發生的問題。(CAMP-28150)
* 修正無法刪除連結至觸發器的交易訊息的問題。(CAMP-28385)
* 移除部分SMS記錄檔中不安全顯示的密碼。
* 修正因Adobe Campaign傳送的空密碼而導致連接至SMPP模擬器失敗的問題。
* 修正SMS連線不穩定時無法傳送促銷活動的問題。
* 修正動態報告中顯示已刪除傳送的問題。
* 修正在工作流程中使用「豐富」活動時，無法從傳送記錄檔擷取其他資料、追蹤記錄檔和排除記錄表格的問題。
* 修正當使用「N基數系列」連結類型和「刪除目標記錄」時，可能會發生GDPR刪除請求的問題，「刪除目標記錄表示刪除連結參照」選項。
* 修正報表共用的問題。
* 修正傳送推播通知時導致生產力問題的問題。
* 已修正直接郵件輸出檔案遺失欄位的問題。
* 修正使用者修改內建工作流程的問題。
* 修正在促銷活動範本根據促銷活動範本(包括已設定的擷取活動)建立促銷活動時的問題。(CAMP-29198)
* 修正檔案擷取活動無法對數個元素使用相同運算式的問題。(CAMP-29182)
* 修正查詢編輯器中的問題，以及RetEvent的Broadlog和追蹤記錄之間的連結條件。(CAMP-28780)
* 修正無法儲存「特定動作」著陸頁面選項的問題。(CAMP-29422)
* 修正無法在工作流程中匯出事件裝載的問題。(CAMP-29029)
* 已修正導致黑名單SMS編號無法排除在SMS訊息中的問題。(CAMP-28898)
* 修正當處理傳入訊息時，無法通知SMPP供應商發生錯誤的問題。(CAMP-29804)
* 已修正允許刪除關聯傳送的外部帳戶的問題。(CAMP-29738)
* SMS訊息的傳送總處理能力已改善並穩定。
* 修正SMS訊息無法使用「~」字元的問題。(CAMP-29172)
* 修正傳送時傳送時間最佳化選項的問題。(CAMP-29231)

