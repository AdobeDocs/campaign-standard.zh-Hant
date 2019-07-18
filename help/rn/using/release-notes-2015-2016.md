---
title: 發行說明2015-2016
seo-title: 發行說明2015-2016
description: 發行說明2015-2016
seo-description: 此頁面列出2015和2016年Adobe Campaign Standard版本。
page-status-flag: 從未啓動
uuid: d5a0f6cc -fed-46cf-8dff-1717fb624f8f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release
discoiquuid: a3ce6b80-1858-49d1-8880-35341812127f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2015-2016{#release-notes}

正在尋找2016年版Adobe Campaign Standard的特定版本嗎？

每個版本都隨附新功能和修補程式。按一下版本可檢視其內容。

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 16.11 - November 2016 {#release-16-11---november-2016}

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
   <td> Deliverability exclusion rules<br /> </td> 
   <td> 加密的全域抑制清單現在會在傳送能力例項中管理，以避免因為惡意活動(尤其是使用Spamtrap)而列入黑名單。<br /> 對於每個電子郵件傳送，預設的typolology規則會比較收件者電子郵件地址，以及此清單中包含的隱含位址或網域名稱。如果有相符項目，則該收件者會被排除在目標人口之外。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> General optimization<br /> </td> 
   <td> 此更新包含許多變更和修補程式，可修正客戶遇到的問題。The global platform performances have also been optimized. <br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### General {#general}

* 已修正數個安全性問題。
* 修正REST API中空白欄位或重復欄位的數個問題。
* 您現在可以直接從應用程式的首頁建立SMS訊息和推播通知。

#### Emails and SMS messages {#emails-and-sms-messages}

* 修正使用者無法在內容編輯器中上傳郵遞區號的問題。
* 修正傳送後無法開啓校樣的問題。
* Fixed an issue that led to an error message displaying when accessing the **[!UICONTROL Hot Clicks]** report on an A/B test email.
* Fixed an issue that prevented modifications made using the **[!UICONTROL Show source]** mode from being applied.
* 修正無法匯入預測主旨行xml模型檔案的問題。
* A new screen dedicated to importing data for the subject line trained model is now available in **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]** .
* 修正非管理員使用者在電子郵件配置畫面中編輯授權遮色片的問題。

#### Push notifications {#push-notifications}

* Fixed an issue that prevented sending logs and event logs from being displayed for the recipients after sending a push notification using the **[!UICONTROL Send push on profiles]** template.
* 修正無法建立新行動應用程式的問題。

#### Workflows {#workflows}

* Fixed a performance issue that occured when using the **[!UICONTROL Subscription]** activity.
* 修正當工作流程包含空間時，無法運作的問題。

#### Integrations {#integrations}

* Fixed an issue that could lead to an error being displayed when using the **Image shared from Adobe Marketing Cloud** option in an email.

#### Custom resources {#custom-resources}

* 增強API欄位兩出版物之間的API記錄檔預覽。
* 修正自訂資源發佈前無法刪除的問題。
* 修正無法擴充描述檔及識別索引鍵與動態欄位的問題。
* 修正在自訂資源中新增連結時可能發生的問題。

## Release 16.10 - October 2016 {#release-16-10---october-2016}

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
   <td> Email predictive subject line<br /> </td> 
   <td> 編輯電子郵件時，新選項可讓您試用不同的主旨行，並在傳送之前先獲得其開啓率的估計值。透過根據您過去的傳送資料或使用符合您產業的預先定義模型，培訓您自己的模型。此功能適用於電子郵件訊息，以及僅包含英文內容的資料庫。<br /> 如需啓用和使用的詳細資訊，請參閱 <a href="../../designing/using/personalizing-the-subject-line-of-an-email.md#predictive-subject-line">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> SMS transactional messaging<br /> </td> 
   <td> SMS頻道已新增至Adobe Campaign的交易訊息功能。交易訊息現在支援兩個頻道：電子郵件和簡訊。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Follow-up message for transactional messaging<br /> </td> 
   <td> 現在可以建立定位事件的工作流程。這表示您可以傳送後續訊息給先前收到交易訊息的客戶。您可以依事件類型、事件記錄和追蹤記錄來篩選目標。在後續訊息中，您將能夠運用事件的內容(裝載)。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/follow-up-messages.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Extended Profile &amp; Services API<br /> </td> 
   <td> 您現在可以在「設定檔與服務API」中公開延伸欄位。出版機制可讓API對應描述檔或服務自訂資源的延伸欄位。For this to work, the <strong>Datamodel</strong> role has been added. 此新角色可讓使用者設定可存取資料模型的管理員集。<br /> 如需詳細資訊，請參閱 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### General {#general-1}

* 已修正數個安全性問題。

#### Emails and SMS messages {#emails-and-sms-messages-1}

* The SMS external account configuration screen ( **[!UICONTROL Administration > Channels > SMS > SMS accounts]** ) has been improved. **[!UICONTROL SMSC specifics]** 區段中已新增數個參數，以支援「文字」欄位中的錯誤碼。

#### Push notifications {#push-notifications-1}

* Fixed an issue that prevented the predefined filters from being displayed when editing the audience of a push notification based on the **[!UICONTROL Send via push notification]** (mobileApp) template.
* The mobile application configuration screen ( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]** ) now displays a message to indicate that the iOS or Android platform has been successfully created.

#### Landing pages {#landing-pages}

* 修正當提交著陸頁面表單時，無法傳送確認電子郵件的問題。

#### Audiences and queries {#audiences-and-queries}

* 修正在查詢編輯器中選取描述檔時所發生的幾個問題。

#### Transactional messages {#transactional-messages}

* 修正交易範本無法解除發佈的錯誤。
* 修正事件清單中顯示觸發事件的問題。

#### Integrations {#integrations-1}

* 修正更新對象後，無法在傳送中使用共用觀眾的問題。
* Fixed an issue that prevented a shared asset ( **[!UICONTROL Image shared from Adobe Marketing Cloud]** option) from being used in a landing page.
* 修正編輯從Adobe Audience Manager匯入的共用觀眾時所發生的問題。

## Release 16.9 - September 2016 {#release-16-9---september-2016}

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
   <td> Remarketing Triggers<br /> </td> 
   <td> Integration between the core service <span class="uicontrol">Triggers</span> and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).<br /> 在Adobe Marketing Cloud中，您定義了不同的觸發因素，也就是說，您要監視的客戶行為，例如所有放棄購物車或表單的客戶，或是從購物車移除的客戶，甚至是作業過期的客戶。建立觸發器時，您會定義觸發的條件和將在事件(plad)中傳送的資料(pload)。<br /> 在Adobe Campaign中，您會選取先前建立的觸發器，您會利用資料資料資料豐富事件資料，並定義連結到該觸發器的交易訊息範本。例如，當用戶端放棄購物車時，會傳送事件給Adobe Campaign，該事件接著會透過在15分鐘內傳送給用戶端的重新行銷電子郵件利用此事件。<br /> 如需詳細資訊，請參閱 <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages: Pause / Unpublish<br /> </td> 
   <td> 您現在可以在更新其內容時暫停交易範本的發佈。對應的訊息不會再傳送，但會儲存在資料庫中。在繼續時，佇列訊息會進行處理，如果未過期，則會傳送這些訊息。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication">詳細文件</a>。<br /> 您現在也可以解除發佈事件和交易範本。對應的訊息不會再傳送，也不會儲存在資料庫中。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Multibranding<br /> </td> 
   <td> 有多個品牌的客戶現在可以在同一個例項中管理它們。品牌是由Adobe Campaign實例管理員管理的功能，可讓您集中設定Adobe Campaign內品牌的所有相關參數。這包括標誌等其他技術參數，例如追蹤URL、Web Analytics、伺服器URL、網域名稱等。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/branding.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Responsive email design preview<br /> </td> 
   <td> 此功能可讓您測試電子郵件在不同類型裝置上的回應速度。In the email preview, a grid has been added to test your email on various screen sizes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications<br /> </td> 
   <td> 已新增新頻道，允許行銷人員在iOS和Android行動裝置上傳送個人化和分段推播通知。訊息可透過單次傳送或使用工作流程活動來傳送。未來版本將提供與交易訊息的相容性。This channel leverages the Mobile core service’s SDK (available <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">here</a>).<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/about-push-notifications.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general-2}

* 此版本提供介面清單中新的篩選和搜尋功能。此新功能可供使用，例如記錄檔(傳送、追蹤)、服務(訂閱、訂閱記錄)、觀眾和工作流程轉場。
* 已修正客戶個人檔案中接觸點數的數個顯示問題。
* 修正數個打字問題。

#### Emails and SMS messages {#emails-and-sms-messages-2}

* 修正允許編輯錯誤校樣的錯誤。它們現在是唯讀的。
* 修正當SMS太長或編碼問題時，會導致收件者列入黑名單的問題。

#### Custom resources {#custom-resources-1}

* 修正使用自訂資源的進階篩選器時，無法顯示所有結果的錯誤。

#### Transactional messages {#transactional-messages-1}

* 前置詞現在會自動新增至新事件定義的識別碼。
* 代表介面中交易訊息的圖示已變更。

#### Integrations {#integrations-2}

* Fixed a display error that would occur when a high resolution image was inserted via the **Dynamic image from Adobe Target** option.
* 修正即使未在AMC資料來源中設定目標ID，仍可儲存共用觀眾的錯誤。

## Release 16.7 - July 2016 {#release-16-7---july-2016}

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
   <td> Enriched transactional messages<br /> </td> 
   <td> 您現在可以連結交易範本與Adobe Campaign資料庫，以恢復資訊，讓您豐富交易訊息的內容。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic URLs for images<br /> </td> 
   <td> 這項新功能可讓您插入內容區塊和動態文字，以進行追蹤和個人化，讓您個人化影像來源。<br /> 此外，還可以在影像URL中輸入參數，從AEM Asset(S7)動態媒體的功能中獲利。例如，您可以傳送電子郵件，內含個人化的影像「問候Alexandre，取得有關巴黎即將舉辦活動的最新消息！」或「問候Frank，取得紐約即將舉辦的活動的最新消息！」。<br /> 如需詳細資訊，請參閱 <a href="../../designing/using/personalizing-urls.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with People Core Service<br /> </td> 
   <td> The Adobe Marketing Cloud <strong>Declared IDs</strong> are now covered by the integration between Adobe Campaign and People Core Service (Profiles &amp; Audiences).<br /> 這表示您可以匯入區段並匯出由 <strong>訪客ID</strong>或 <strong>宣告ID組成的對象</strong>。<br /> 如需詳細資訊，請參閱 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs<br /> </td> 
   <td> The MTA logs (delivery server) now display the complete history of each message, particularly all of the delivery attempts as well as the associated error statuses, and this has no impact on the application's performance.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### General {#general-3}

* 修正可能會顯示不相關欄位而非需要填寫欄位的錯誤。這會發生在比較運算子多次修改查詢中的條件之後。
* Fixed the behavior of the option **[!UICONTROL The last X days/months/quarters/years]** when defining a relative filtering condition for a date field. 計算期間現在是相對於伺服器的日期和時間的滑動期間，而非基於日曆的時段。

#### Workflows {#workflows-1}

* Fixed an error that would return an incorrect list of values in the screen for selecting the targeting dimension in the properties of a **[!UICONTROL Query]** activity.
* Fixed an error that would force the **Exists** operator to be selected when adding an average or count aggregate on a collection element in a **[!UICONTROL Query]** activity.

#### Content editing {#content-editing}

* 修正匯入HTML內容時可能導致顯示問題(回應式設計)的錯誤：在匯入後第一次開啓內容時，不會再重新編寫樣式屬性。
* 修正動態內容變體上新增條件時造成的非封鎖錯誤。
* 修正在登陸頁面內容中新增核取方塊所造成的錯誤。核取方塊無法使用。
* 修正在區塊的開頭處放置游標時，刪除區塊中的文字時可能發生的錯誤。

#### Transactional messages {#transactional-messages-2}

* 整合網站時，您現在可以定義任何指定事件的到期日。在傳遞此日期後，就無法再傳送對應該事件的訊息。

## Release 16.6 - June 2016 {#release-16-6---june-2016}

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
   <td> Profiles and Services API<br /> </td> 
   <td> The Adobe Campaign <span class="uicontrol">Profiles and Services</span> API is available in the <a href="https://www.adobe.io/products/campaign">adobe.io</a> portal. 這可讓Adobe Campaign設定檔更新、新增及刪除，以及供他們透過REST呼叫訂閱或取消訂閱。<br /> 如需詳細資訊，請參閱API <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">的詳細說明</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### General {#general-4}

* 現在行動裝置已停用工具提示，以確保螢幕上顯示的資訊易於閱讀。
* 修正使用者無法捲動iPad畫面上特定區域內容的錯誤。
* 已修正在Internet Explorer11中編輯內容時所發生的數個相容性錯誤。
* 修正當資料匯入第一次失敗時，無法存取詳細記錄的錯誤。
* 修正無法儲存範圍篩選的錯誤。
* 修正設定清單的方式時，無法顯示資源元素的錯誤。
* 修正查詢編輯器Explorer中的錯誤。搜尋欄位傳回的結果保留在搜尋歷史記錄中，並繼續顯示在每次新搜尋上。

#### Emails and SMS messages {#emails-and-sms-messages-3}

* 修正無法在傳送記錄檔中復原連結至彈回數的資訊的錯誤。
* 修正無法存取交易訊息動態內容區塊中上下文的錯誤。
* 修正導致URL連結無法在電子郵件內容中定義動態文字的錯誤。
* 修正遞送建立精靈頂端列的顯示。
* 傳送的主要索引鍵無法再用作個人化欄位。

#### Workflows {#workflows-2}

* 工作流程兩個活動之間的切換現在會顯示計算元素的計數，並從一個活動轉移到另一個活動。
* **[!UICONTROL Query]** 當活動中新增其他資料時，不相容欄位現在會隱藏。
* 新增額外資料時顯示的匯總定義視窗，只會改進為僅提供與使用中資料相容的選項(例如：計算平均值只能用於數值資料)。
* 啓動或重新啓動立即可用的技術工作流程，現在只能由具有管理權限的使用者進行。

#### Landing pages {#landing-pages-1}

* 修正著陸頁面屬性中可能會截斷32位元AES編碼索引鍵的錯誤。
* 修正當定義可見度條件或新增動態內容至登陸頁面時，查詢編輯器無法正確顯示的錯誤。

#### Custom resources {#custom-resources-2}

* The **[!UICONTROL Switch to parameters]** option is now hidden when defining a filter related to a profile's subscriptions to a service.
* 修正從自訂資源設定0-1類型連結時可能發生的錯誤。
* Fixed an error that, where relevant, could prevent the defined **Constant default value** from being edited when adding a **Date and time** type field in a custom resource.

## Release 16.5 - May 2016 {#release-16-5---may-2016}

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
   <td> Predefined filters<br /> </td> 
   <td> 管理員現在可以使用預先設定的規則，建立顯示在查詢編輯器中的進階篩選器。例如，選取這些篩選器可讓使用者在定義觀眾時，更輕鬆地在簡化的介面中開發複雜的設定。<br /> 如需詳細資訊，請參閱 <a href="../../developing/using/configuring-filter-definition.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Subscription Services<br /> </td> 
   <td> A new <span class="uicontrol">Subscription Services</span> activity offers the possibility of subscribing several profiles to a service or unsubscribing them from a service with in a single action.<br /> 您可以在執行定位或匯入已識別資料的檔案後使用此活動。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/subscription-services.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: data enrichment<br /> </td> 
   <td> The <span class="uicontrol">Additional data</span> tab is now available in <span class="uicontrol">Query</span> type activities. 此功能可讓您豐富查詢所定位的資料，並將此資料傳輸至下列工作流程活動，以便利用此資料。<br /> 新增其他資料後，您可以根據定義的其他資料建立條件，將其他篩選層級套用至初始目標資料。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/query.md#enriching-data">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Contextual help<br /> </td> 
   <td> 上下文說明功能現在可在不同的Adobe Campaign畫面上使用。這表示只要按一下滑鼠，您就可以直接存取目前使用的功能文件。若要顯示上下文說明，請按一下「？」icon in the upper-right corner of the screen, as shown in the example below.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-5}

* 各種介面新功能遵循Marketing Cloud標準。
* 標準化不同下拉式清單類型。

#### Emails and SMS messages {#emails-and-sms-messages-4}

* 修正指定錯誤地址遮色片時，無法傳送電子郵件的錯誤。
* 現在，電子郵件傳送支援TLS通訊協定。MX管理中的新欄可讓您定義每個網域所要的TLS行為。
* SMS介面已改善。

#### Workflows {#workflows-3}

* 各種工作流程介面新功能。
* 修正顯示快速動作時發生的錯誤。
* Fixed an error that could cause a workflow to fail when using a **[!UICONTROL Segmentation]** type activity containing a 1-N link.
* 已修正混合裝置無法開啓工作流程轉場的錯誤。
* 修正第一次啓動工作流程時，暫停按鈕無法顯示的錯誤。

#### Content editor {#content-editor}

* 內容編輯器現在可讓您個人化電子郵件或登陸頁面中包含的任何URL。Refer to the [detailed documentation](../../designing/using/personalizing-urls.md).
* 修正當影像新增至傳送建立精靈及其內容之後，可能會導致影像遺失的錯誤。

#### Custom resources {#custom-resources-3}

* 修正在自訂資源的組態畫面中新增個人化1-N類型連結時所發生的錯誤。
* 改進準備和發佈自訂資源時進度列的顯示。
* 修正顯示自訂資源清單時發生的錯誤。

#### Transactional messages {#transactional-messages-3}

* 使用者介面的使用者親和力以及交易訊息引擎的效能與強穩性已獲得最佳化。
* 現在可以暫時暫停交易訊息範本的發佈。For more on this, refer to the [detailed documentation](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication).
* 修正可能會將不相容定位維度新增至交易訊息範本中的內容區塊錯誤。
* 修正API預覽無法顯示在事件設定畫面中的錯誤。

#### Audiences and queries {#audiences-and-queries-1}

* 關於在查詢編輯器中使用日期的各種修補程式。Refer to the [detailed documentation](../../automating/using/editing-queries.md#creating-queries).

#### Administration {#administration}

* 已修正「Standard使用者」安全性群組的名稱無法登入的錯誤。

## Release 16.3 - March 2016 {#release-16-3---march-2016}

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
   <td> Interface and navigation<br /> </td> 
   <td> Adobe Campaign介面經過改良，讓導覽和操作變得簡單直覺。<br /> 您現在會從應用程式的頂端列導覽。The advanced menus are accessible by selecting the <strong>Adobe Campaign</strong> logo.<br /> 如需詳細資訊，請參閱 <a href="../../start/using/interface-description.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Save audience<br /> </td> 
   <td> A new option, <span class="uicontrol">Create then update an audience</span> , is now available in the <span class="uicontrol">Save audience</span> activity. 此選項可讓您手動輸入對象標籤。如果輸入的標籤對應至現有對象，則會更新此標籤。如果對象不存在，則會建立此對象。<br /> 此外，每次執行工作流程時都會更新觀眾。<br /> 您隨時可以選擇對象更新模式：為觀眾提供新資料，或在每次執行時取代整個觀眾資料。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/save-audience.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Segmentation<br /> </td> 
   <td> <span class="uicontrol">「區段</span> 」活動現在可讓使用者分段暫存資源的資料。例如：匯入檔案的資料。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/segmentation.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-6}

* 修正排序清單時發生的顯示錯誤：箭頭表示只能針對特定類型的資料反轉欄順序。
* 修正當查詢中新增規則時，會限制下拉式選單中顯示元素數目的錯誤。

#### Emails and SMS messages {#emails-and-sms-messages-5}

* 修正無法存取電子郵件轉換報表的錯誤。
* 如果未提供傳送者地址，則準備訊息的準備階段現在會傳回錯誤。

#### Workflows {#workflows-4}

* 擷取CSV格式檔案時，會顯示某些檔案格式選項，但不會考量到。現在已不再顯示這些選項。
* Fixed an error caused when the **[!UICONTROL Delete the source files after transfer]** option was checked for a **[!UICONTROL SFTP]** type file transfer.
* Fixed an error that could prevent the counter and preview of **[!UICONTROL Query]** data from being displayed after refreshing the page.
* 修正在工作流程中開啓某些轉場的錯誤，尤其是傳送活動後，或定位和篩選維度不同的查詢。
* 修正在新增活動後未儲存工作流程時，個人化欄位無法插入工作流程傳送活動的錯誤。
* 修正無法顯示電子郵件傳送活動的對外轉換目標維度的錯誤。

#### Landing pages {#landing-pages-2}

* 修正個人化欄位無法在著陸頁面的可本地化內容區塊中正確運作的錯誤。

#### Custom resources {#custom-resources-4}

* Fixed an error that prevented a search on a custom resource from being carried out if the **[!UICONTROL Add search fields]** option of the resource screen definition was checked and if several fields were selected in the **[!UICONTROL Filter zone composition]** .

## Release 16.2 - February 2016 {#release-16-2---february-2016}

### New capabilities {#new-capabilities-7}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> A/B test for emails<br /> </td> 
   <td> 您現在可以對電子郵件的內容、主旨或傳送者名稱進行A/B測試。此新功能最多可測試元素的三個變體。<br /> 從A/B測試專用的新範本建立電子郵件時，建立精靈中的新步驟可讓您定義測試的參數。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/designing-an-a-b-test-email.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Brand management<br /> </td> 
   <td> 您現在可以定義一或數個品牌，以集中輸入影響品牌身分的參數。Adobe Campaign可讓您建立這些品牌，並將其連結至交付或著陸頁面範本。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/branding.md#assigning-a-brand-to-an-email">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Incremental query<br /> </td> 
   <td> A new workflow activity, <span class="uicontrol">Incremental query</span> , allows you to carry out a query which, on every execution, targets only the new results. 先前執行的結果會自動排除。Linked to a <span class="uicontrol">Scheduler</span> activity, you can define the execution frequency of the <span class="uicontrol">Incremental query</span> .<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/incremental-query.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> 交易訊息介面的使用者友善已改善。All business process management linked to transactional messages is currently centralized in the <span class="uicontrol">Marketing plans</span> &gt; <span class="uicontrol">Transactional messages</span> menu. 事件設定也已改善。事件現在可獨立於自訂資源管理。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/about-transactional-messaging.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### General {#general-7}

* 修正報表、清單和查詢中的數個顯示錯誤。
* 已修正行動裝置上的數個相容性和顯示錯誤。

#### Emails and SMS messages {#emails-and-sms-messages-6}

* 修正在建立訊息(電子郵件或簡訊)時，無法將個人化欄位用來插入個人化欄位的錯誤。
* 修正無法正確傳送透過Mblox傳送SMS訊息的錯誤。

#### Audiences and queries {#audiences-and-queries-2}

* 修正在修改篩選維度後，在查詢中新增額外條件時可能造成的計數錯誤。
* 修正預覽查詢結果時可能導致錯誤分頁的錯誤。

#### Content editing {#content-editing-1}

* 修正使用個人化列舉時，動態內容設定無法正確考量的錯誤。

#### Workflows {#workflows-5}

* Fixed an error that could prevent any action in a workflow from being carried out if there was an empty line in the **[!UICONTROL Fields to update]** tab of an **[!UICONTROL Update data]** activity.
* 修正無法匯入包含地理/組織單位資訊的資料的錯誤。
* Fixed an error caused by adding a **[!UICONTROL Change axis]** type of **[!UICONTROL Exclusion]** rule.
* Fixed an error that could lead to an unwanted additional segment being created when manipulating an outbound transition of a **[!UICONTROL Segmentation]** activity.
* 修正載入工作流程範本中檔案所造成的錯誤。
* Fixed an error that could prevent spaces from being used as column separators in a **[!UICONTROL Load file]** activity.

#### Custom resources {#custom-resources-5}

* 修正匯出封裝時，如果資源已發佈時，自訂資源狀態無法重新起草的錯誤。

#### Packages {#packages}

* 已修正無法匯出包含工作流程之封裝的錯誤。
* 修正無法選取相同資源的數個元素的錯誤。

## Release 16.1 - January 2016 {#release-16-1---january-2016}

### New capabilities {#new-capabilities-8}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> The following email specific reports have been added: <span class="uicontrol">Complaints</span> , <span class="uicontrol">Opens</span> , and <span class="uicontrol">Unsubscriptions</span> .<br /> 已改善下列報表： <span class="uicontrol">傳送摘要</span> 、 <span class="uicontrol">反彈摘要</span> 、 <span class="uicontrol">傳送總處理能力</span> 和 <span class="uicontrol">追蹤指標</span> 。<br /> 如需詳細資訊，請參閱 <a href="../../reporting/using/defining-the-report-period.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Query editing<br /> </td> 
   <td> The query editor has been improved and now allows you to scan the <strong>1-N</strong> type links.<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/editing-queries.md#creating-queries">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Content personalization<br /> </td> 
   <td> As for email or landing page editing, the input interface for content block display conditions has been improved.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: column definition when importing<br /> </td> 
   <td> <span class="uicontrol">「載入檔案</span> 」活動現在可讓您詳細設定匯入檔案的欄：預期的資料類型、日期和時間格式、處理以套用至空白值或錯誤，以及值重新對應。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/load-file.md#column-format">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Mapping of SMS encodings<br /> </td> 
   <td> 現在可以針對未使用標準編碼的提供者定義個人化SMS訊息的編碼映射。管理員可以執行個人化對應的設定，並定義應考量的順序。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/configuring-sms-channel.md#smsc-specifics">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-8}

#### General {#general-8}

* 已改善混合/觸控螢幕裝置的Internet Explorer和Chrome相容性。
* 修正當指定的電子郵件地址包含語法錯誤時，可能導致新使用者/個人資料/測試描述檔輸入的所有資料遺失的錯誤。

#### Emails and SMS messages {#emails-and-sms-messages-7}

* 修正電子郵件預覽畫面無法產生內容縮圖的錯誤。
* 修正訊息預覽畫面中無法顯示訊息(電子郵件或簡訊)原始內容的錯誤。

#### Audiences and queries {#audiences-and-queries-3}

* Fixed an error that could prevent a **Query** type audience from being created in the **Service** resource.
* 修正在進階模式中編輯查詢條件時，無法正確顯示函數清單的錯誤。
* Fixed an error that could prevent a **Query** type audience from being created if it contained criteria based on collections.
* 修正無法建立包含傳送KPI之篩選器之查詢的錯誤。
* 已修正無法預覽從工作流程建立之觀眾內容的錯誤。

#### Custom resources {#custom-resources-6}

* 修正當自訂資源包含動態預設值時，可能導致伺服器當機的錯誤。
* Fixed an error caused by moving, then deleting an element in the **[!UICONTROL Detail screen configuration]** section while defining screens of a custom resource.
* Fixed an error that occurred when a default value had been defined for an **integer** list that did not include **0** in its range of possible values.
* 修正重新初始化後，自訂資源的詳細畫面配置中無法新增元素的錯誤。

#### Workflows {#workflows-6}

* 修正可能導致顯示工作流程中所有活動記錄的錯誤，而不只是顯示選取的活動。
* Fixed an error in the **[!UICONTROL Scheduler]** activity. **[!UICONTROL Day of the month]** 未正確將選項納入考量並取代 **[!UICONTROL Week day]** 。
* Fixed an error that could prevent a **[!UICONTROL Scheduler]** activity from working correctly with the expiration mode set to **[!UICONTROL After a certain number of iterations]** .
* Fixed an error that occurred when exporting data using an **[!UICONTROL Extract file]** activity. 匯出檔案中顯示的行數低於匯出的元素數目。
* Fixed an error that could prevent a file in a **[!UICONTROL Load file]** activity from being selected.
* Fixed an error that prevented fields that were to be updated in an **[!UICONTROL Update data]** activity from being deleted.
* 已修正開啓工作流程執行記錄檔後，無法儲存工作流程修改的錯誤。
* Fixed an error that caused a **[!UICONTROL Load file]** activity to be executed twice if it was configured to use the file from its inbound transition and this file had been loaded using a **[!UICONTROL Transfer file]** activity.
* Fixed an error that could prevent certain temporary entities from being correctly processed by an **Exclusion** activity.
* Fixed an error that could prevent a **[!UICONTROL Query]** activity from being executed correctly if the targeting dimension and the filtering dimension configured in the activity were different.
* Fixed an error concerning the automatic naming of outbound transitions added to a **[!UICONTROL Fork]** activity that could prevent the workflow from being saved.

#### Content editing {#content-editing-2}

* 修正在編輯內容時導致圖示或搜尋列無法彈性顯示的錯誤。

#### Landing pages {#landing-pages-3}

* 修正無法使用套件匯入匯入著陸頁面的錯誤。

#### Transactional messages {#transactional-messages-4}

* 現在可以在訊息中心推送代理業者的安全性參數中指定受信任的IP位址。
* 修正無法建立新類型事件的錯誤。

## Release 15.11 - November 2015 {#release-15-11---november-2015}

### New capabilities {#new-capabilities-9}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> SMS Channel<br /> </td> 
   <td> 您現在可以使用Adobe Campaign傳送SMS訊息。<br /> 就電子郵件而言，您可以從促銷活動和行銷活動清單建立新的SMS傳送。您也可以從工作流程建立單一傳送和週期性SMS訊息。<br /> 這些SMS傳送是根據您可從傳送範本清單中設定的範本。可使用預設範本。<br /> 這些SMS傳送使用SMPP3.4通訊協定，大多數SMS路由器都使用此通訊協定。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/about-sms-messages.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring transitions<br /> </td> 
   <td> 您現在可以在工作流程的最後轉換中探索資料及其結構。This allows you to check that the processes applied by each activity correspond to your needs.<br /> </td> 
  </tr> 
  <tr> 
   <td> File pre- and post-processing in workflows<br /> </td> 
   <td> You can now carry out additional processing on a data file when importing or exporting it via the <span class="uicontrol">Load file</span> and <span class="uicontrol">Extract file</span> activities.<br /> 根據預設，您可以在這些活動中解壓縮ZZIP格式檔案。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/load-file.md">「載入檔案</a> 」和 <a href="../../automating/using/extract-file.md">「擷取檔案</a> 活動」的文件。<br /> </td> 
  </tr> 
  <tr> 
   <td> Deliverability reports<br /> </td> 
   <td> 電子郵件轉換報表現在可供使用。此報告可讓您根據支援的支援和訊息服務，檢視訊息的不同轉譯。<br /> 報表摘要也會顯示接收的訊息、垃圾訊息訊息、未接收訊息和等待接收的訊息。<br /> 如需詳細資訊，請參閱 <a href="../../sending/using/email-rendering.md#email-rendering-report-description">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Package Management<br /> </td> 
   <td> It is now possible to import and export images in packages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quick actions<br /> </td> 
   <td> 在選擇清單或工作流程中的元素上方或之後會顯示某些動作。其中有些動作現在會顯示為相關元素周圍的圖示，以方便存取。These quick actions can be used to duplicate an element, delete it, show the detail, etc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-9}

#### General {#general-9}

* 修正無法從管理員帳戶存取例項一般參數的錯誤。
* **現在在自訂資源中已正確將浮動** 資料納入考量。
* 修正在已修改的簡化匯入清單中，當對應範本狀態修改時所產生的顯示錯誤。

#### Landing pages {#landing-pages-4}

* 修正某些著陸頁面範本的某些元素，這些元素在英文上會在法文上錯誤顯示。

#### Audiences {#audiences}

* 修正可能導致從Adobe Marketing Cloud匯入的對象無法顯示在觀眾清單中的錯誤。
* 修正定義查詢時可能會強制區分大小寫的錯誤。
* 修正定義查詢時無法篩選對象的錯誤。
* 修正對象無法取消動作的錯誤。

#### Workflows {#workflows-7}

* Fixed an error that could prevent the fields that were to be updated in an **[!UICONTROL Update data]** activity from manually being configured.
* Fixed an error that could cause the **[!UICONTROL Query]** activity to load infinitely when opened if the workflow had not been saved after having placed the activity in the diagram.
* Fixed an error that could cause the server to stop while counting or previewing an audience selected from a **[!UICONTROL Query]** in a workflow.
* 已修正開啓工作流程中的活動時可能出現的非重大錯誤。
* Fixed an error that prevented a **[!UICONTROL Scheduler]** activity from being configured to execute a workflow several times a day.
* 修正導致您無法執行查詢的欄位出現在某些工作流程活動中的錯誤。
* Fixed an error that could prevent the user from locating the KPIs added from a **[!UICONTROL Query]** on deliveries in the outbound transition.
* 修正將檔案匯入工作流程後，無法建立檔案對象的錯誤。
* Fixed an error that could prevent data from being updated on profiles if the **location/address3** field of the resource was used.
* 修正無法在工作流程中重復複製活動的不同系列的錯誤。
* 修正無法顯示SQL的錯誤，因此允許診斷錯誤，以便在工作流程中循環傳送。

#### Content editor {#content-editor-1}

* 修正了導致搜尋無法在著陸頁面的原始碼中或電子郵件中進行搜尋的問題。

#### Packages {#packages-1}

* 修正無法將某些類型的元素匯出至套件(尤其是登陸頁面、工作流程)的各種錯誤。
* 修正當標籤已修改時，會導致舊套件匯入標籤顯示的錯誤。
* 修正可能導致不相容資源顯示在可導出資源清單中的錯誤。

## Release 15.10 - October 2015 {#release-15-10---october-2015-}

### New capabilities {#new-capabilities-10}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Deduplication activity<br /> </td> 
   <td> 工作流程現在提供用於去重復資料的新活動。此活動可讓您依據您選擇的准則篩選目標中的任何重復項目。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/deduplication.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Improved diagram<br /> </td> 
   <td> 從工作流程工作區，您現在可以使用數個鍵盤快速鍵來選取、開啓和刪除活動。<br /> 活動對齊也已改進，讓工作流程更有條理地進行組織。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/workflow-interface.md#workspace">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> The date and time of the export is now automatically added to the labels of the files exported using an <span class="uicontrol">Extract file</span> activity. This way the files generated are unique.<br /> </td> 
  </tr> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> The name of the template from which a simplified import was carried out is now visible by default in the import list and in the detail of each import.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> Improvement and extended possibilities for managing and defining links for custom resources.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-10}

#### Email {#email}

* 修正服務取消訂閱連結無法從鏡像頁面正確運作的錯誤。
* 修正電子郵件傳送標籤上無法正確顯示電子郵件傳送標籤的錯誤。
* Fixed an error that could prevent an external **[!UICONTROL Routing]** account from being selected in a duplicated delivery template.

#### Audiences {#audiences-1}

* 修正觀眾計數在查詢中使用1-N連結時所造成的錯誤。
* 修正無法在電子郵件傳送目標對象中選取描述檔的錯誤。

#### Workflows {#workflows-8}

* 修正在工作流程中設定電子郵件傳送時可能導致顯示問題的錯誤。
* Fixed an error that could prevent the **[!UICONTROL Load file]** activity from working correctly. 隨即出現空白錯誤訊息。
* Fixed an error that could prevent the **[!UICONTROL Transfer file]** activity from working correctly. 無法正確將存取權限納入考量。
* Fixed an error that could prevent a file from being exported if the workflow contained a **[!UICONTROL Recurring email]** .
* 修正無法在工作流程中建立電子郵件傳送，或防止主旨和定義的內容被納入考量的錯誤。
* Fixed an error that could prevent a reconciliation key from being selected in an **[!UICONTROL Update data]** activity when configuring the workflow of a simplified import template.
* 已修正刪除活動後，無法儲存工作流程的錯誤。

#### Platform {#platform}

* 修正當自訂資源包含該元素資源類型的連結時，無法建立新元素的錯誤。
* 修正某些記錄檔寫入時可能延遲15分鐘的錯誤。
* Fixed an error that could prevent the marketing activity list from being displayed when sorted by the **[!UICONTROL Date]** or **[!UICONTROL Indicators]** columns.

#### Landing pages {#landing-pages-5}

* 修正在選取測試設定檔以預覽著陸頁面時發生的錯誤。

#### Transactional messages {#transactional-messages-5}

* 修正在測試描述檔上刪除事件後，導致應用程式當機的錯誤。

#### Reports {#reports}

* Fixed an error that could cause incorrect data to be sent for the reports **[!UICONTROL deliveryThroughputReport]** and **[!UICONTROL deliveryTrackingReport]** .

#### Content editor {#content-editor-2}

* 修正處理動態內容區塊時發生的HTML標籤管理錯誤。

## Release 15.8 - August 2015 {#release-15-8---august-2015}

### New capabilities {#new-capabilities-11}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> 您現在可以簡化的方式匯入資料。<br /> 使用者只需選取由管理員預先定義的範本，並上傳包含要匯入資料的檔案。範本中定義的工作流程會透明地執行，使用者可以存取匯入結果的詳細資訊以及記錄任何錯誤。<br /> 這些檔案的資料可以插入資料庫中，或做為直接建立觀眾的方式。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/about-data-import-and-export.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Creating programs and campaigns<br /> </td> 
   <td> 現在，已設定促銷活動和計劃，讓建立的日期自動用作開始日期。<br /> 結束日期會根據開始日期設定，例如：<br /> 
    <ul> 
     <li> 適用於程式的D+186 </li> 
     <li> 適用於促銷活動的D+61 </li> 
    </ul> For more information, refer to the <a href="../../start/using/programs-and-campaigns.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> The list of tracked URLs is now read only.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> 您現在可以針對建立的帳戶，管理事件的個人化交易訊息，例如密碼變更或確認。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/about-transactional-messaging.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> 新增多種功能，例如：擴充測試設定檔、狀態管理及刪除資源。<br /> 如需詳細資訊，請參閱 <a href="../../developing/using/resource-statuses.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-11}

#### Display {#display}

* 修正Safari中查詢編輯器中可能導致兩個欄位的問題。

#### Content editor {#content-editor-3}

* 修正電子郵件主旨中無法使用字元'&lt;'、'&amp;'和'&gt;'的錯誤。

#### Email {#email-1}

* 修正使用者無法在動態文字後面新增文字的錯誤。

#### Lists {#lists}

* Fixed an error that prevented the **Message** column in workflow execution logs from being exported correctly.

#### Profiles and audiences {#profiles-and-audiences}

* 修正複製或刪除元素時，造成雙重確認的錯誤。**僅使用Internet Explorer11的混合裝置**。

#### Workflows {#workflows-9}

* 修正無法從工作流程傳送電子郵件的錯誤。
* Fixed an error that could prevent a workflow from executing when the name of the rejection file was not specified in a **[!UICONTROL Load file]** activity.
* Fixed an error that could prevent a workflow from executing when the **[!UICONTROL Execution frequency]** of a **[!UICONTROL Schedule]** activity was set to **[!UICONTROL Daily]** .

#### Platform {#platform-1}

* 修正造成縮圖在負載平衡環境中無法產生的錯誤。

## Release 15.7 - July 2015 {#release-15-7---july-2015}

### New capabilities {#new-capabilities-12}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exporting lists<br /> </td> 
   <td> 您現在可以將清單中的內容匯出成CSV格式的檔案。This function is available in all screens with a <strong>List</strong> mode (for example: profile list).<br /> 匯出的資料是匯出時顯示的欄中的資料。編輯清單後，您可以選取想要匯出的資料。<br /> 如需使用此功能的詳細資訊，請參閱 <a href="../../automating/using/exporting-lists.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with Adobe Profiles &amp; Audiences<br /> </td> 
   <td> You can now share audiences between Adobe Campaign and your other Adobe Marketing Cloud solutions:<br /> 
    <ul> 
     <li> Export: when you save an audience composed of profiles in a workflow, a new <span class="uicontrol">Share in Adobe Marketing Cloud</span> option allows you to add profiles to an existing audience or to create a new audience. </li> 
     <li> Import: by creating a <strong>List</strong> type audience from the audience management screen, a new option allows you to identify it as an <span class="uicontrol">Adobe Marketing Cloud Audience</span> . 然後您可以選取現有的共用對象，將其匯入Adobe Campaign。 </li> 
    </ul> For more information on configuring and using this functionality, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic content<br /> </td> 
   <td> 動態內容介面已改善。現在，Arrows會讓您直接在電子郵件內文中導覽不同的動態內容。<br /> 如需使用此功能的詳細資訊，請參閱 <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic text<br /> </td> 
   <td> From the content editor of an email, you can now define dynamic text:<br /> 
    <ul> 
     <li> 在電子郵件主旨中， </li> 
     <li> 在HTML模式中， </li> 
     <li> 或文字模式。 </li> 
    </ul> For more information on using this functionality, refer to the <a href="../../designing/using/defining-dynamic-text.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Programs and campaigns - Reports<br /> </td> 
   <td> 報表的介面和圖形已改善。<br /> 如需使用此功能的詳細資訊，請參閱 <a href="../../reporting/using/defining-the-report-period.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-12}

#### Installation {#installation}

* Adobe Campaign例項名稱現在限制為32個字元。

#### Workflows {#workflows-10}

* 修正在工作流程中編輯查詢時，無法定位「傳送」資源的錯誤。
* 修正在工作流程中編輯查詢時，無法處理某些連結資源的錯誤。
* Fixed an error that could prevent a **Recurring delivery** activity from being modified if the workflow had already been executed.

#### Emails {#emails}

* 修正透過運算式編輯器新增動態內容時，無法檢查JavaScript語法錯誤的錯誤。

#### Landing pages {#landing-pages-6}

* 修正無法從平板電腦編輯著陸頁面的錯誤。

#### Assets Core Service {#assets-core-service}

* 從正在編輯的電子郵件或登陸頁面選取共用資源時，現在會篩選可用資源的清單。

## Release 15.6 - June 2015 {#release-15-6---june-2015}

### New capabilities {#new-capabilities-13}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Reconciliation activity<br /> </td> 
   <td> A new <strong>Reconciliation</strong> activity links unidentified data (for example, after importing a file) with existing resources within a workflow.<br /> 此活動基本上用於資料管理用途。It responds to two different use cases:<br /> 
    <ul> 
     <li> <strong>新增關係</strong>： <strong>「關係</strong> 」標籤可讓您在傳入的資料和Adobe Campaign資料庫的其他數個維度之間新增連結。 </li> 
     <li> <strong>資料識別</strong>： <strong>「識別</strong> 」標籤可讓您直接將傳入的資料與Adobe Campaign資料庫中現有維度中的欄關聯。離開活動時，資料會被識別為屬於指定維度。 </li> 
    </ul> Refer to the <a href="../../automating/using/reconciliation.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> <strong>新的擷取檔案</strong> 活動可讓您從工作流程以外部檔案形式匯出Adobe Campaign資料庫中的資料。<br /> 限制：目前無法使用輸出檔案的動態名稱。<br /> 請參閱 <a href="../../automating/using/extract-file.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Scheduler activity<br /> </td> 
   <td> Improved widget that allows you to select the execution time of the <strong>Scheduler</strong> activity in a workflow.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Transfer file activity<br /> </td> 
   <td> SFTP is now supported.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> <span class="uicontrol">「開發</span> 」功能表現在允許擁有管理員權限的使用者建立自己的自訂資源，例如購買或產品表格，以豐富提供的資料範本。<br /> 您也可以擴充可用的資源，以便新增欄位給他們。<br /> 此外，也可以設定對應至新或延伸自訂資源之畫面中的導覽。<br /> 請參閱 <a href="../../developing/using/data-model-concepts.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Test profiles<br /> </td> 
   <td> The <strong>Middle name</strong> and <strong>Title</strong> of the test profiles can now be selected when configuring the list of test profiles.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content editor: Dynamic content<br /> </td> 
   <td> 您可以定義不同的內容，根據透過運算式編輯器定義的條件動態顯示給使用者。<br /> 請參閱 <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> A <strong>Test profiles</strong> column is now available in an email's sending logs.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-13}

#### Lists {#lists-1}

* 刪除清單中的元素現在會自動重新整理清單。
* 修正無法從僅包含一欄的清單中選取元素的錯誤。
* 修正在重新整理頁面後，套用至清單顯示的變更會遺失的錯誤。
* 中間名稱和測試描述檔標題現在都可以顯示在測試描述檔清單中。
* 修正在使用Mozilla Firefox選取清單中的核取方塊時所發生的錯誤。

#### Audiences {#audiences-2}

* Fixed an error that prevented the **[!UICONTROL Add]** button from being used in the audience interface.

#### Emails {#emails-1}

* 修正了編輯電子郵件時，無法連續使用預覽按鈕兩次的JavaScript錯誤。
* Fixed an error that prevented the **[!UICONTROL Edit properties]** and **[!UICONTROL Show proofs]** buttons from being used on Microsoft Surface Pro3 tablets using Internet Explorer 11.
* 修正無法顯示電子郵件傳送記錄檔的錯誤。

#### Landing pages {#landing-pages-7}

* Fixed an error that prevented the **Brand logo** content block from being used when editing content in a landing page.
* 修正如果著陸頁面指定有效日期時，著陸頁面無法顯示在行銷活動清單中的錯誤。

#### Workflows {#workflows-11}

* Fixed an error that prevented limiting a segment in group mode from working correctly when configuring a **Segmentation** activity.
* Fixed an error that prevented a transition from being selected after having configured a **Segmentation** activity.
* Fixed an error that prevented a transition from being deleted after having configured a **Segmentation** activity.
* Fixed an error that prevented populations from being counted and previewed within a **Segmentation** activity.
* 已修正重復的電子郵件無法有效刪除的錯誤。
* Fixed an error that caused data from a deleted **Transfer file** activity to appear in a new **Transfer file** activity.
* Fixed an error that prevented an exclusion rule from being correctly taken into account within an **Exclusion** activity.
* 修正刪除工作流程中的電子郵件傳送活動時發生的錯誤。現在，也會從行銷活動清單移除對應的傳送。

#### Navigation {#navigation}

* 您現在可以使用定位鍵，在相同頁面上的欄位之間正確導覽。

## Release 15.4 - April 2015 {#release-15-4---april-2015}

### New capabilities {#new-capabilities-14}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Package exports / Package imports<br /> </td> 
   <td> <strong>「部署</strong> 」功能表現在可讓使用者透過匯出和匯入套件，擁有在不同Adobe Campaign例項之間交換資源的管理員權限。<br /> 請參閱 <a href="../../automating/using/managing-packages.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> All reports (except the <strong>Hot clicks</strong> report) can now be accessed from a program. These reports are:<br /> 
    <ul> 
     <li> 方案遞送總處理能力 </li> 
     <li> 程式追蹤指標 </li> 
     <li> 依網域劃分計劃 </li> 
     <li> 計劃未交付和彈回數 </li> 
     <li> 方案URL和點按流 </li> 
    </ul> 這些報告可在指定期間內篩選(例如三個月、六個月等)。也可以篩選促銷活動報表。<br /> 請參閱 <a href="../../reporting/using/about-dynamic-reports.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Email delivery</strong> activity<br /> </td> 
   <td> The <strong>Email delivery</strong> activity in the workflows has been improved. 您現在可以從應用程式行銷活動清單找到電子郵件、週期性電子郵件和有關週期性電子郵件執行的詳細資訊。<br /> 請參閱 <a href="../../automating/using/email-delivery.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Segmentation</strong> activity<br /> </td> 
   <td> <strong>「區段</strong> 」活動現在可用於工作流程中。此活動可讓您建立一或數個區段，並從位於同一工作流程中上游的活動計算的人口族群中連結區段代碼。在此活動中，區段可以在單一轉場或不同的多轉場中處理。現在有一些選項可以篩選人口族群並限制每個群體的大小，以最佳化個人化。例如，您可以隨機選取對應於特定標準的設定檔。<br /> 請參閱 <a href="../../automating/using/segmentation.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Assets Core Service</strong><br /> </td> 
   <td> You can now use shared resources via <strong>Assets Core Service</strong> in your email and landing page contents. 您可以直接從Adobe Marketing Cloud管理共用資源。<br /> 請參閱 <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Adobe Target</strong><br /> </td> 
   <td> You can now insert images that are dynamically computed by <strong>Adobe Target</strong> into your Adobe Campaign emails. 這可讓您根據Adobe Target區段中定義的標準個人化內容，提供相同電子郵件的數個版本。<br /> 請參閱 <a href="../../integrating/using/about-campaign-target-integration.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor: <strong>Block selector</strong><br /> </td> 
   <td> 在HTML內容編輯器中選取區塊時，導覽路徑標示會顯示在編輯區域底部。這可讓您輕鬆導覽並選取不同的元素。<br /> 請參閱 <a href="../../designing/using/managing-landing-page-structure-and-style.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Release 15.3 - March 2015 {#release-15-3---march-2015}

### New capabilities {#new-capabilities-15}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> 現在可直接從程式或促銷活動存取報表。<strong>傳送摘要</strong> 報表已新增至程式層級。<br /> 請參閱 <a href="../../reporting/using/delivery-summary.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Update data<br /> </td> 
   <td> In the workflows, the available <strong>Update data</strong> activity has a new option, which allows you to automatically link inbound data fields with the fields of an application schema. 這有助於更新欄位的選取程序。<br /> 請參閱 <a href="../../automating/using/update-data.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Email delivery<br /> </td> 
   <td> In workflows, the advanced options of the <strong>Email delivery</strong> activity can now be accessed via a specific button in the action bar. This button is only available if an <strong>Email delivery</strong> activity is selected. 主要優點是它可讓您在活動中加入對外轉場，並編輯工作流程中顯示的活動名稱。<br /> 請參閱 <a href="../../automating/using/email-delivery.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-14}

#### General {#general-10}

* 修正在建立傳送時無法顯示收件者的錯誤。
* 已修正根據「已開啓開啓」條件的「收件者」無法使用對象的錯誤。
* 已修正禁止刪除空白描述檔的錯誤。
* 修正預覽傳送時發生的錯誤。
* 修正行銷活動無法重復複製的錯誤。
* 修正刪除促銷活動時發生的錯誤。

