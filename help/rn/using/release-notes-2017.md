---
title: 2017年發行說明
seo-title: 2017年發行說明
description: 2017年發行說明
seo-description: 此頁面列出2017年版Adobe Campaign Standard。
page-status-flag: 從未啓動
uuid: d73f8186-e309-441b-969d-71d0 c33 cf4
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release
discoiquuid: 1metrics9b3b-9b3e-45587-9c46-b6 fb02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2017{#release-notes}

尋找2017年特定版本的Adobe Campaign Standard嗎？

每個版本都隨附新功能和修補程式。按一下版本可檢視其內容。

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 17.10 - October 2017 {#release-17-10---october-2017}

### New capabilities {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Fatigue Management<br /> </td> 
   <td> 疲勞管理可讓您建立疲勞規則，以管理與個人檔案之間的過度通訊。疲勞規則易於建立，但具有極為靈活的功能，例如計算多個通道(包括交易訊息)的訊息、只計算特定遞送，或套用規則至特定個人檔案。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/fatigue-rules.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Content creation: Import from a URL<br /> </td> 
   <td> 從URL匯入可讓您從網站快速擷取您的創意內容，以建立適用於任何傳送的電子郵件。此外，第三方可以透過URL直接分享內容，簡化您的創意流程。匯入的內容可以靈活地用作單次傳送或範本層級的一部分，確保所有相關促銷活動的品牌一致性，不論是工作流程或交易訊息，以及包含A/B或多變數測試。從URL匯入可自動轉換並追蹤所有連結，透過動態報告監控電子郵件效能。<br /> 如需詳細資訊，請參閱 <a href="../../designing/using/importing-content-from-a-url.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### Platform {#platform}

* 修正無法正確壓縮大型壓縮檔案的問題。
* 品牌管理的安全性已獲得改善。修改品牌名稱和傳送者地址現在會保留給Adobe技術管理員。
* 為了改善安全性、使用者產生的內容(影像、鏡像頁面、登陸頁面等)不再由adobe.com網域提供。您現在必須使用自己的網域，透過使用品牌來處理這些資源。
* 修正顯示和篩選行銷活動時的介面問題。
* 修正無法使用POST REST API呼叫更新訂閱日期欄位的問題。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* 修正無法將清單類型對象定位在訊息中，造成準備失敗的問題。
* 多語言電子郵件傳送功能中新增了語言。
* 顯示在傳送控制面板上的內容縮圖現在會在使用者修改內容和儲存時自動更新。
* 修正無法開啓傳送的時區相關問題。

#### Push notifications {#push-notifications}

* When configuring the push notification channel, the push provider platform for iOS should be **apns** and for Android **gcm**.
* 修正無法在Adobe Campaign介面中新增iOS行動應用程式的錯誤。
* 現在，支援GCM和FCM的Android行動應用程式都支援推播通知。
* 修正重復推播通知範本時，無法儲存內容的錯誤。
* 現在可以協調行動應用程式使用者資料，從Adobe Campaign資料庫建立或更新描述檔。
* Adobe Campaign現在會排定處理交易推播通知高於標準推播通知的優先順序。

#### Reports {#reports}

* 修正電子郵件內容中無法顯示作用點按百分比的問題。
* 已修正黑名單量度被計為硬碟(而非彈回數)的問題。
* 修正摘要資料中顯示負面計數的問題。
* 修正錯誤年齡區段中的設定檔問題。
* 軟和硬反彈計算公式已變更。

#### Workflows {#workflows}

* Fixed an issue in the **[!UICONTROL Load file]** activity that could lead to errors after manually adding and removing columns in the activity.
* **[!UICONTROL deliverabilityUpdate]** 技術工作流程現在已排定在上午2：00執行。
* 已修正允許執行清單匯出而未使用匯出角色的安全性問題。
* Fixed an issue with the **[!UICONTROL Reconciliation]** activity.
* Fixed an issue with the use of wildcard characters in the **[!UICONTROL File Transfer]** activity.

#### Profiles and audiences {#profiles-and-audiences}

* 修正可能導致查詢條件在某些特定情況下無法正確考量，造成錯誤結果的問題。
* 修正無法存取設定檔的問題，如果將設定檔定位在已準備好但從未傳送且過期的訊息中。

#### Integrations {#integrations}

* 修正造成有些「資料來源」無法正確顯示和選擇的「資料來源」問題。

#### Custom resources {#custom-resources}

* 修正清單畫面中的問題，此問題會在不含任何資料的情況下顯示自訂資源列。
* 修正「False」值無法顯示在自訂資源中的布林類型欄位問題。

## Release 17.9 - September 2017 {#release-17-9---september-2017}

### New capabilities {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Library of Email templates<br /> </td> 
   <td> 推出18種全新的多方互動範本，以兩個優美的主題設計- Astro和Publisher。這些可自訂的範本是業界不受限制，可立即使用。範本包含多種使用案例的內容，讓您以更快速、有效率且更具美感的方式，設計和發佈電子郵件行銷宣傳。<br /> 如需詳細資訊，請參閱 <a href="../../start/using/about-templates.md#content-templates">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic Reporting with Profile Data<br /> </td> 
   <td> 動態報告提供可完全自訂和即時的商業報表。在這個版本中，強大的動態報表增強功能可新增個人資料資料存取權，讓人口統計分析依據描述檔維度(如性別、城市、郵遞區號和年齡)以及功能電子郵件促銷活動資料(例如開啓和點擊)進行分析。使用易於使用的拖放介面，決定您的電子郵件促銷活動對最重要客戶細分的執行方式，比以往更輕鬆。<br /> 如需詳細資訊，請參閱 <a href="../../reporting/using/about-dynamic-reports.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Mass Subscription with Origin &amp; Date<br /> </td> 
   <td> 透過此大量訂閱增強功能，您現在可以透過工作流程中的訂閱服務活動，直接在Adobe Campaign Standard資料庫中儲存訂閱資訊(原始和日期)。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/subscription-services.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### Platform {#platform-1}

* 有些客戶需要能夠利用來自Adobe Campaign Standard的ID，因為他們不會管理唯一金鑰來識別自己的記錄。This ID (**ACS ID**) can be exported as well as used as a reconciliation key while updating the data. For more information, refer to the [detailed documentation](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* FTP通訊協定已過時。您現在應該改用SFTP。為了不封鎖現有的實施，FTP上現有的設定仍可照常運作，但新活動將無法顯示。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* 現在可以建立新的警報標準，在傳送警報通知中使用這些標準。For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* 傳送警示通知具有新設計，提供的傳送提醒控制面板使用者體驗已改善。
* Now when a routing external account is disabled, a warning is displayed in the impacted deliveries (email, SMS and push) and the **Preview** button is hidden in these deliveries.
* 修正在主旨行中啓用動態文字時，A/B測試預覽預覽的錯誤。

#### Transactional messages {#transactional-messages}

* 現在可以在傳送追蹤訊息後的天內，定義您要傳送後續訊息的時間。For more information, refer to the [detailed documentation](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* 現在可以從連結到事件的交易訊息中定義日期。
* 修正在刪除連結至接收和處理事件之設定檔之後，執行包含後續訊息之後續訊息時，造成SQL錯誤的問題。
* 修正無法刪除連結至事件之設定檔的錯誤。
* 修正追蹤連結重新導向無法運作的問題。
* 修正無法停用電子郵件或簡訊訊息中特定連結追蹤的問題。

#### Reports {#reports-1}

* **Hot Click** 報表已改善。此外，現在可以根據傳送中定義的每個條件內容顯示熱門點按，並針對每次執行循環傳送或交易訊息顯示熱門點按。For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* 修正隔離度量無法擷取正確資料的問題。
* 新的預設時間範圍已新增至日曆Widget。
* [動態報表量度](../../reporting/using/indicator-calculation.md) 和 [促銷活動的KPI](../../sending/using/confirming-the-send.md) (顯示於傳送訊息的控制面板上)已對齊，以提高一致性。
* 修正debian可能導致路徑損毀的問題。

#### Workflows {#workflows-1}

* 修正可能導致匯入檔案無法運作的問題。

#### Integrations {#integrations-1}

* 現在，Analytics與Campaign整合支援eVar和事件。
* 傳送內含放棄購物車內容的電子郵件時，從購物車移除的元素的裝載參數現在是選用項目。

#### Profiles and audiences {#profiles-and-audiences-1}

* Adobe Campaign現在提供顯示作用中設定檔數目的報表。此報告僅提供資訊，不會影響計費。For more information, refer to the [detailed documentation](../../audiences/using/active-profiles.md).
* 修正使用Profiles and Services API時，描述檔無法訂閱服務的問題。

## Release 17.7 - July 2017 {#release-17-7---july-2017}

### New capabilities {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Multilingual email and SMS deliveries<br /> </td> 
   <td> 透過自動分段客戶慣用的語言，透過單次傳送定義並執行多語言電子郵件與簡訊傳送。報告每個傳送至語言和個別層級的效能。<br /> 越來越多的公司面臨著在國內及國外提供多種語言內容的挑戰。因此，簡化本地化訊息傳遞是跨國公司有效的客戶通訊策略的關鍵部分；多語言國家/地區的公司；和公司，無論客戶身在何處，都希望在語言層級進一步個人化內容。For more information, refer to the <a href="../../channels/using/creating-a-multilingual-email.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign Notifications<br /> </td> 
   <td> 直接在Adobe Campaign Standard中接收有關重要系統活動的通知。您將會收到通知，例如您持續傳送的進度，或是工作流程發生錯誤的通知。<br /> 即時通知可讓相關利益相關者得知資訊，並讓使用者能夠立即直接對應用程式中的活動通知採取行動。為團隊帶來更高的敏捷性、效率和更順暢的促銷活動執行。For more information, refer to the <a href="../../administration/using/sending-internal-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery Alerting<br /> </td> 
   <td> 除了直接在Adobe Campaign Standard中檢視通知以外，Adobe Campaign現在還提供電子郵件警報系統，以觸發重要系統活動的電子郵件警報給使用者或外部利益相關者。建立、管理和接收可自訂的警報和儀表板，以追蹤遞送成敗。<br /> Adobe Campaign遞送快訊透過電子郵件和儀表板，自動通知公司內所有參與的Adobe Campaign使用者，自動得知遞送執行狀態，進而提高效率。For more information, refer to the <a href="../../sending/using/receiving-alerts-when-failures-happen.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Encrypted Declared ID in Datasources<br /> </td> 
   <td> 使用加密的聯絡資訊(電子郵件地址或電話號碼)作為宣告ID，傳送電子郵件和簡訊觸發程式，無需在Campaign中現有的設定檔。由於加密的宣告ID可由Adobe Campaign Standard解碼，因此Campaign現在可以在接收其他Experience Cloud解決方案的受眾時建立新的行銷描述檔，其中包含先前未知的聯絡人。<br /> 透過電子郵件和簡訊即時鎖定客戶和未知潛在客戶，以提高現有客戶群的忠誠度並分別獲取新客戶。潛在客戶在Adobe Campaign中驗證並運用這些見解後，就能充分利用您的第一方Cookie資料(來自Adobe Audience Manager*)。<br /> *需要Adobe Audience Manager。For more information, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> KPI sharing from Campaign to Analytics<br /> </td> 
   <td> 與Adobe Analytics共用宣傳資料，以測量Campaign的電子郵件行銷指標，以及其他行銷和廣告活動，透過轉化率、統一點擊前後行為。<br /> 直接追蹤整體效能，並在Analytics中與外部程式發現同步。將您的學習從整合式檢視套用到宣傳活動中；最終改善開放、點進和轉化率，進而提高收益和整體宣傳績效。<br /> 需要Adobe Analytics。For more information, refer to the <a href="../../integrating/using/about-campaign-analytics-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Direct Mail Channel - Return To Sender<br /> </td> 
   <td> 現在支援與包含傳送者資訊的Direct Mail提供者進行簡單的檔案交換。此「直接郵件」頻道的增強功能可讓對應的郵寄地址排除在未來的通訊之外。<br /> 這可讓行銷人員收到不正確位址的通知，並透過其他管道與客戶互動，或鼓勵他更新郵寄地址。這也減少了浪費的行銷資金，因為行銷人員避免將郵件傳送至不正確的地址。<br /> 直接郵件可作為附加頻道使用。For more information, refer to the <a href="../../channels/using/return-to-sender.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general}

* 修正任何使用者匯出清單的問題。Now only users with the **[!UICONTROL Export]** role are allowed to.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* Fixed an issue with the **updateDeliveryExecInfo** workflow that set the **To deliver** indicator to 0 for SMS deliveries.
* In the **Advanced parameters** of the delivery template’s properties, the **Routing** drop-down list now only displays external accounts corresponding to the template message type. 例如，電子郵件傳送範本只會顯示電子郵件外部帳戶。
* Fixed an issue with the **[!UICONTROL Text]** preferred email format defined for test profiles.
* 修正在傳送的排程定義畫面中選擇預設時區時，導致Javascript錯誤的問題。
* 修正無法顯示在傳送記錄檔中的問題。
* 在遞送建立精靈的範本選取畫面中，預設會隱藏「後續」和「A/B測試範本」。For more information, refer to the [detailed documention](../../channels/using/creating-an-email.md).
* 修正任何使用者傳送傳送的問題。Now only users with the **[!UICONTROL Start deliveries]** role are allowed to. For more information, refer to the [detailed documention](../../sending/using/confirming-the-send.md).

#### Push notifications {#push-notifications-1}

* Fixed an issue with the **Campaign Tracking Endpoint** URL that prevented reporting.
* 修正無法在Android裝置上顯示推播通知標題的問題。
* 修正推播通知只包含標題(而且訊息內文中沒有任何內容)時，無法顯示推播通知的問題。
* 修正傳送的媒體附件URL被追蹤的問題，無法將視訊和圖片內嵌於傳送中。現在，推播通知預設會停用type MediaatchentURL的URL追蹤。

#### Reports {#reports-2}

* 修正圖表和表格之間值顯示不同的問題。
* 修正顯示推播通知值作為電子郵件值的問題。
* 修正在促銷活動外部建立傳送時，顯示值未知的問題。
* 修正顯示SMS報告資料作為行動應用程式資料的問題。

#### Workflows {#workflows-2}

* 您現在可以篩選工作流程記錄檔(時間長度和文字搜尋)。For more information, refer to the [detailed documention](../../automating/using/executing-a-workflow.md#monitoring).
* 工作流程傳送中現在提供一個選項，可在傳送前停用確認。
* 修正無法在週期性傳送的建立精靈中設定傳出轉換的問題。
* 修正在使用以自訂資源欄位為基礎的自訂資源欄位(具有許多值)時，使用工作流程查詢活動的問題

## Release 17.5 - May 2017 {#release-17-5---may-2017}

### New capabilities {#new-capabilities-3}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Direct mail<br /> </td> 
   <td> 透過Adobe Campaign Standard的第一個離線通道直接郵件，突破數位障礙並連接實體世界。這項功能可讓您個人化並產生直效郵件提供者所需的檔案，做為跨通道宣傳的一部分。運用Direct Mail，透過吸引人的觸點吸引客戶到您的應用程式、網站或商店，以重新吸引客戶或強化客戶體驗。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/about-direct-mail.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Email BCC<br /> </td> 
   <td> 電子郵件密件副本可儲存傳送給個別收件者的唯一電子郵件訊息，因此允許品牌封存這些訊息。透過將BCC電子郵件地址新增至所有電子郵件，Adobe Campaign Standard客戶可透過此功能保存每封電子郵件的確切副本。這是金融服務業的常見法律要求，有助於協助客服中心即時解決衝突。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/configuring-email-channel.md#archiving-emails">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### Interface updates {#interface-updates}

* In the top bar, the **[!UICONTROL Timeline]** link has been removed and replaced with a link to **[!UICONTROL Programs & Campaigns]** .

#### Emails and SMS messages {#emails-and-sms-messages}

* Fixed an issue which displayed the wrong color for the **[!UICONTROL Retry in progress]** delivery status. 顏色是灰色而非藍色。

#### Workflows {#workflows-3}

* Fixed an issue that occurred when changing the action to perform in a **[!UICONTROL Transfer file]** activity.

#### Reports {#reports-3}

* **[!UICONTROL Spam]****[!UICONTROL Spam rate]** 和指標計算已變更。
* **[!UICONTROL Bounce]** 量度已改進，以獲得更準確的結果。

#### Push notifications {#push-notifications-2}

* 修正無法按一下描述檔行銷歷史記錄中推送事件的問題。
* 在工作流程中使用推播通知的功能已改善。

## Release 17.4 - April 2017 {#release-17-4---april-2017}

### New capabilities {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Enhanced Image edition capabilities with the Creative SDK<br /> </td> 
   <td> 您現在可以存取Creative SDK支援的完整功能集，在編輯電子郵件或登陸頁面時直接在內容編輯器中增強影像。<br /> 此功能不需要購買其他Creative Cloud解決方案。<br /> 如需詳細資訊，請參閱 <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional push notifications<br /> </td> 
   <td> Mobile應用程式頻道已新增至Adobe Campaign的交易訊息功能。交易訊息現在支援三個頻道：電子郵件、簡訊和推播通知。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/transactional-push-notifications.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Recurring push notifications<br /> </td> 
   <td> 您現在可以在工作流程中設定循環推播通知。在客戶期望定期更新(如每周提醒)以查看新內容或促銷活動時，您可以使用循環推播通知。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/push-notification-delivery.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service (S3) connector<br /> </td> 
   <td> Amazon Simple Storage Service(S3)連接器現在可用來匯入或匯出資料至Adobe Campaign。它可在工作流程活動中設定。設定是在外部帳戶中完成。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/external-accounts.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration live<br /> </td> 
   <td> Adobe Campaign和Dreamweaver之間的整合現已推出。它現在可與正式的Dreamweaver版本(17.0.2)搭配使用。<br /> 這需要從此處安裝Adobe Campaign整合擴充功能： <a href="http://adobe.ly/acdw_addon">http://adobe.ly/acdw_addon</a><br /> 如需詳細資訊，請參閱此 <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">影片</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### Platform {#platform-2}

* 已修正記憶體耗用問題。

#### Emails and SMS messages {#emails-and-sms-messages-1}

* 修正預覽訊息時，內容無法與最新變更適當同步的問題。
* 修正無法建立或刪除MX或網域電子郵件處理規則的問題。
* 修正可能導致您無法傳送多個別名的電子郵件問題。
* 修正傳送記錄檔無法顯示在傳送記錄檔中的問題。
* 修正顯示追蹤的URL之傳送URL時，其內容中沒有URL的問題。
* 修正影像大小屬性無法正確套用至傳送訊息的問題。

#### Transactional messages {#transactional-messages-1}

* RetEventIstois欄位不再作為交易訊息範本中的個人化欄位公開。

#### Landing pages {#landing-pages}

* We have optimized the **[!UICONTROL by email]** filter used in landing pages to reconcile new subscribers with database profiles.
* 修正在表格設定中使用布林欄位時，顯示免費文字輸入而非核取方塊的問題。
* 修正無法產生著陸頁面縮圖的問題。

#### Workflows {#workflows-4}

* Fixed a display error when editing an **[!UICONTROL End]** or **[!UICONTROL External Signal]** activity (on Safari only).
* Improved the error message displayed when editing a **[!UICONTROL Read Audience]** activity containing an erroneous audience.
* 修正執行訂閱活動時可能導致SQL錯誤的問題。

#### Integrations {#integrations-2}

* 興趣點資料：修正計算位置訂閱者時發生的錯誤。

#### Audiences and queries {#audiences-and-queries}

* 修正查詢編輯器中的系列無法使用總和和平均組合的問題。
* 修正變更篩選器資源後，查詢編輯器無法重新載入的問題。

#### Reports {#reports-4}

* 修正在表格中選取多個列時，開啓比率量度無法正確計算的問題。
* 修正僅將度量顯示為整數值的錯誤。現在可使用小數顯示量度。

#### Push notifications {#push-notifications-3}

* 修正在建立連結至行動應用程式(在MPCNS上建立的行動應用程式)時，不會顯示錯誤訊息的問題。
* 修正使用者在無聲通知中新增音效的問題。

## Release 17.2 - March 2017 {#release-17-2---march-2017}

### New capabilities {#new-capabilities-5}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Dynamic reporting<br /> </td> 
   <td> 動態報告提供新一代可完全自訂和即時商業報表。此功能以視覺動態樞紐表和圖形為基礎，可讓您拖放變數和維度，以分析行銷活動的效率和有效性。動態報告也可讓您從頭開始建立自己的業務報表，並儲存以供日後使用。<br /> 如需詳細資訊，請參閱 <a href="../../reporting/using/about-dynamic-reports.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration (Labs)<br /> </td> 
   <td> 透過Adobe Campaign和Dreamweaver整合，您現在可以使用Adobe解決方案建立電子郵件宣傳的整合程序。<br /> 您可以在Dreamweaver中編輯Adobe Campaign電子郵件，並在兩個解決方案之間順暢地同步化內容。<br /> 在初始版本中，整合提供「Labs」功能，而且只能搭配Dreamweaver測試版測試版使用。如果您想要啓動，請聯絡AC-DW-integration@adobe.com。<br /> 如需詳細資訊，請參閱此 <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">影片</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Manual send time optimization<br /> </td> 
   <td> 您現在可以手動定義每個收件者的自訂傳送時間-在傳送層級或使用工作流程。<br /> 有兩個新選項可供使用： <br /> 
    <ul> 
     <li> 所有收件者都會收到考量其時區的訊息。 </li> 
     <li> 每位收件者在計算的日期和時間都會收到公式所定義的訊息。 </li> 
    </ul> For more information, refer to the <a href="../../sending/using/optimizing-the-sending-time.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications New capabilities<br /> </td> 
   <td> The push notification channel has been enhanced with several new capabilities:<br /> 
    <ul> 
     <li> 新製作介面 </li> 
     <li> 無聲通知 </li> 
     <li> 互動式推播 </li> 
     <li> 多樣化內容支援 </li> 
     <li> 裝載大小計算機 </li> 
    </ul> For more information, refer to the <a href="../../channels/using/about-push-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Signal activity<br /> </td> 
   <td> Trigger a workflow from another workflow using the new <span class="uicontrol">Signal</span> activity.<br /> 透過從另一個工作流程開始的工作流程，您現在可以支援更複雜的客戶歷程。您可以更好地監控客戶歷程，並因應發生問題。<br /> 已更新數個工作流程活動：<br /> 
    <ul> 
     <li> <span class="uicontrol">結束</span> 活動：新標籤可讓您指定在執行此活動後觸發的工作流程。 </li> 
     <li> <span class="uicontrol">更新資料</span> 活動：使用新的空轉場轉場，新增觸發其他工作流程的 <strong>End</strong> 活動。空的對外轉場效果不會保留任何資料，也不會消耗系統上不必要的空間 </li> 
    </ul> For more information, refer to the <a href="../../automating/using/external-signal.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Read audience activity<br /> </td> 
   <td> 透過現有受眾開始進行定位程序，您可以輕鬆地在單一活動中選擇並調整。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/read-audience.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest data<br /> </td> 
   <td> 興趣點資料整合Adobe Campaign與Adobe Analytics for Mobile。A brand can collect data from users' mobile locations - called <strong>Points of Interest</strong> - when users open the brand's app. 這可讓品牌利用Adobe Campaign工作流程，根據使用者的位置傳送個人化訊息。此渠道運用Mobile核心服務的SDK。<br /> 請注意，使用此功能需要Analytics for Mobile，這是付費解決方案。<br /> 如需詳細資訊，請參閱 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> REST APIs<br /> </td> 
   <td> API現在可提供任何層級連結到描述檔或服務資源的資源。<br /> 如需詳細資訊，請參閱 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-1}

* 匯出傳送記錄檔時，現在可以新增描述檔資料。

#### Emails and SMS messages {#emails-and-sms-messages-2}

* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain selected even after unchecking it and saving the delivery.
* 修正無法解除發佈交易電子郵件的問題。
* 修正在預覽傳送前，內容無法與最新變更適當同步的問題。

#### Landing pages {#landing-pages-1}

* 修正使用者在登陸頁面內容時無法編輯的錯誤。

#### Workflows {#workflows-5}

* Fixed an issue that could prevent from reading the content of the reject transition of a **[!UICONTROL Load file]** activity.
* Fixed an issue that prevented swapped columns to be properly taken into account when configuring a **[!UICONTROL Load file]** activity.

## Release 17.1 - January 2017 {#release-17-1---january-2017}

### New capabilities {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Log export for external reporting<br /> </td> 
   <td> 匯出記錄檔，例如傳送和追蹤記錄檔，以便在您偏好的報告或BI工具中處理。您可以使用簡單的工作流程搭配漸進式查詢，自動匯出新記錄檔。<br /> 除了資源選擇器的記錄資源可用性外，還對 <a href="../../automating/using/incremental-query.md">「增量查詢</a> 」和 <a href="../../automating/using/extract-file.md">「擷取檔案</a> 活動」進行了增強：<br /> 
    <ul> 
     <li> <span class="uicontrol">遞增查詢</span> 現在可讓您使用日期欄位擷取新的或更新的資料。以前，先前執行的所有結果都會自動排除，即使自上次執行後更新。 </li> 
     <li> <span class="uicontrol">擷取檔案</span> 現在可以匯出標籤的標籤值，而非ID。 </li> 
    </ul> 這些活動可供管理員存取所有地理位置和組織單位。<br /> 如需匯出記錄檔的詳細資訊，請參閱 <a href="../../automating/using/exporting-logs.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Marketing capabilities for transactional messages<br /> </td> 
   <td> 行銷人員現在可以根據客戶行銷個人檔案傳送交易訊息。This allows them to:<br /> 
    <ul> 
     <li> Apply marketing typology rules such as <span class="uicontrol">Blacklisted address</span> . </li> 
     <li> 在訊息中加入取消訂閱連結。 </li> 
     <li> 將交易訊息新增至全域傳送報告。 </li> 
     <li> 運用客戶歷程中的交易訊息。 </li> 
    </ul> For more information, refer to the <a href="../../channels/using/profile-transactional-messages.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional Messaging API<br /> </td> 
   <td> The Transactional Messaging API is now available through <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, making it easier to use and to monitor:<br /> 
    <ul> 
     <li> 您可以從adobe. io平台報告與監控功能中獲益。 </li> 
     <li> 驗證現在是使用基於adobe. io的驗證而非IP白名單來進行，使得安全性程序變得更簡單。 </li> 
     <li> 所有API現在都已整合在單一平台上，如果您已支援設定檔與服務API，則可比以往更輕鬆地將交易傳訊功能新增至您的整合。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-2}

* **[!UICONTROL Access authorization]** 選項已傳回著陸頁面屬性。
* 修正可能導致舊影像轉換而非正確影像的問題。如果來源影像已在傳送或登陸頁面的內容定義中更新，則會發生此情況。
* 修正使用者無法編輯現有SFTP外部帳戶中某些欄位的問題。
* 已修正數個UI問題。例如，使用者現在可以編輯描述檔屬性並儲存修改，而不會遇到UI問題。

#### Emails and SMS messages {#emails-and-sms-messages-3}

* 修正傳送範本與包含

#### Push notifications {#push-notifications-4}

* 修正無法從應用程式回傳至Adobe Campaign伺服器的問題。
* Fixed an issue that may have prevented **[!UICONTROL Play a sound]** and **[!UICONTROL Custom fields]** to be taken into account for Android.
* 修正可能會新增額外逸出字元至Emojis使用的Unicode字元的問題。
* 當訂戶的註冊Token列入黑名單時，現在會在應用程式的Adobe Campaign訂閱者清單中立即更新對應狀態。

#### Workflows {#workflows-6}

* 修正可能無法預覽事件資源上的查詢(例如RetEvent)的問題。
* **[!UICONTROL Load file]** 活動產生的拒絕檔案現在可以在其傳出轉場中擷取，並在下一個活動中處理。For example, upload the reject file via an SFTP server using **[!UICONTROL Transfer file]** .
* Fixed an issue that may have prevented a user from limiting the population of a segment if **[!UICONTROL Temporary resource]** was selected in the **[!UICONTROL General]** tab of **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** 活動不能再設定為每10分鐘觸發一次工作流程。
* Fixed an issue that may have prevented **[!UICONTROL Use common columns]** from working properly in an **[!UICONTROL Union]** activity.

#### Integrations {#integrations-3}

* 修正在Adobe Campaign中部署事件觸發器時可能發生錯誤的問題。這個錯誤發生在Adobe Marketing Cloud中的「30天後退貨可能性」中繼資料新增至「放棄」觸發器時。
* 修正從「人員」核心服務匯入對象時，技術工作流程清除「目標維度」欄位的問題。後續查詢無法擷取匯入的對象。
* Fixed an issue that may have caused the **[!UICONTROL Save audience]** activity of a workflow to fail when the option **[!UICONTROL Share in Adobe Marketing Cloud]** was checked.

