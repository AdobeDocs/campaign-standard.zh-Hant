---
title: 發行說明2018
seo-title: 發行說明2018
description: 發行說明2018
seo-description: 此頁面列出所有2018版Adobe Campaign Standard。
page-status-flag: 從未啓動
uuid: 99f92a544b3d-48b9-b08 d-e98 b24 e75 f62
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release
discoiquuid: e54f8305-1e32-4193-8e5a-b5 d87 b03038 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Release Notes 2018{#release-notes}

正在尋找Adobe Campaign Standard的特定2018版本嗎？

每個版本都隨附新功能和修補程式。按一下版本可檢視其內容。

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 18.9 - September 2018 {#release-18-9---september-2018}

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
   <td> In-App messaging (beta)<br /> </td> 
   <td> 應用程式內訊息可讓您提供內容相關互動，並讓您觸及可能選擇退出推播通知的使用者，以更有效地吸引行動應用程式使用者。使用應用程式內訊息與推播通知，建立高度個人化且相關的體驗。如此可讓應用程式使用者更好地轉換和保留。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/about-in-app-messaging.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Launch integration for mobile apps (beta)<br /> </td> 
   <td> Adobe Launch與Adobe Campaign的整合現在可簡化並自動化使用Mobile SDK V在Campaign中啓用行動應用程式屬性啓動的程序。<br /> 如需詳細資訊，請參閱 <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* Adobe Campaign Standard現在支援Amazon S API的第版。

### Other changes {#other-changes}

* 在多個項目中，現在會區分每小時最大連線次數與最大訊息數之間的區別。達到限制後，就可以瞭解為何總處理能力有限。以前，這兩種情況都套用相同的訊息('contribution')。
* 在Campaign中設定行動應用程式時，使用者現在可以得知iOS憑證和Android伺服器金鑰是否已成功上傳及其到期日。

   For more on this, refer to the detailed documentation on how to configure a mobile application using [SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [SDK V5](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

* 在定義促銷活動屬性時選取行動應用程式，以定位特定行動應用程式的使用者。此功能適用於推送和應用程式內訊息頻道。

   For more information, refer to the [detailed documentation](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* 使用Creative Designer介面選取內容區塊時，現在會載入並顯示清單中所有的內容區塊。(CAMP-27311)

   For more on this, refer to the [detailed documentation](../../designing/using/adding-a-content-block.md).

### Patches {#patches}

* 修正電子郵件控制面板和電子郵件交易電子郵件的電子郵件摘要報表中，記錄不一致的問題。(CAMP-28237
* 修正工作流程中，透過檔案傳輸活動匯入檔案時，可能會顯示錯誤訊息的問題。(CAMP-27435)
* 修正包含25項服務之著陸頁面的問題，此問題會在表單中隨機取消選取服務。(CAMP-26572)
* 修正工作流程中，使用檔案傳輸活動時無法使用SFTP URL設定外部帳戶的問題。(CAMP-26475)
* 修正無法更新服務摘要報表的問題。(CAMP-26301)
* 修正使用「Rich」(擴充)活動時工作流程中的問題，此問題導致自訂欄位無法顯示正確日期。(CAMP-26242)
* 修正透過檔案匯入匯入時，服務訂閱日期無法更新的問題。
* 修正載入檔案活動時無法匯入檔案的錯誤(Campaign-27068)。
* 修正服務摘要報表(Camp-25587)中顯示訂閱次數錯誤的問題。
* 修正Adobe Analytics和Adobe Campaign報表之間資料不一致的問題。(CAMP-25393)
* 修正無法讓有限存取使用者登入的問題。(CAMP-27381)
* 修正使用Creative Designer編輯電子郵件時，無法顯示Adobe Experience Manager內容清單的問題。(CAMP-27181)
* 修正可能導致Creative Designer無法開啓，造成錯誤的問題。(CAMP-27304)
* 修正使用Internet Explorer11時，無法在Creative Designer中正確運作的問題。
* 修正從相機上傳圖片並以縱向模式拍攝，以顯示在不需要旋轉位置的問題。
* 修正使用Creative Designer中的查詢編輯器介面時，顯示不清楚選取資訊的問題。
* 修正使用Creative Designer中的查詢編輯器介面時，無法正確複製元素的問題。
* 已修正即使已透過自動回覆取消訂閱，仍會持續傳送SMS訊息給黑名單收件者的問題。(CAMP-27128)
* Fixed an issue that prevented displaying the errors that caused the **Database Cleanup** workflow to fail. (CAMP-26876)
* 修正無法刪除推播通知定義中自訂欄位的問題。(CAMP-25588)

## Release 18.7 - July 2018 {#release-18-7---july-2018}

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
   <td> High priority flag for Android push notifications<br /> </td> 
   <td> Android的高優先順序標幟-針對Android應用程式提供高優先順序的推播通知，讓睡眠裝置喚醒並執行部分有限處理。請注意，預設優先順序是正常的，可能會延遲訊息傳送以儲存電池。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Typology filter for mobile app subscribers<br /> </td> 
   <td> 支援打字篩選中的訂閱-當指定打字規則的篩選標準時，可以選取應用程式訂閱作為篩選和定位維度，提供篩選屬性給使用者或不含描述檔的屬性。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/about-typology-rules.md#typology-rules">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Automated content import from a URL during message preparation<br /> </td> 
   <td> 現在可以在準備階段中從URL匯入電子郵件內容。對於週期性的電子郵件傳送，每當訊息準備好確保內容在傳送時始終保持最新狀態，就會擷取最新的HTML內容。此功能還可讓您使用URL中的內容建立排程傳送，即使內容尚未準備好。<br /> 如需詳細資訊，請參閱 <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign release notification message<br /> </td> 
   <td> 當使用者在執行個體升級至新版本後，現在會顯示快顯訊息。訊息會指出版本號碼，並包含版本注意事項的連結。You can choose to hide the message until the next release. <br /> </td> 
  </tr> 
  <tr> 
   <td> User management<br /> </td> 
   <td> 新的Campaign Standard例項以及未建立的現有執行個體(開始18.7版)，地理單位功能現在無法使用。<br /> 如需詳細資訊，請參閱本 <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">頁</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-1}

* The Adobe Campaign and Adobe Target integration now allows you to leverage Target’s [Permissions](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html) feature. 在電子郵件中加入來自Adobe Target的動態影像時，您現在可以指定目標屬性(at_ property code)。
* GDPR隱私權存取/刪除要求現在會考量具有描述檔資源之副本連結的自訂資源。對於日曆簡單連結和N基數系列系列，您必須選取「刪除/複製目標記錄」，才能在自訂資源中刪除/複製連結參照的記錄。對於或個基數簡單連結，選取「刪除/複製記錄表示刪除/複製連結參照的目標記錄」。

### Other changes {#other-changes-1}

* 報表共用逾時已從一到四分鐘增加，以避免發生逾時錯誤。
* 編輯電子郵件內容時，預設會開啓新的Creative Designer。您可以在儲存變更後隨時返回預設內容編輯器。For more on this, refer to the [detailed documentation](../../designing/using/about-email-content-design.md).
* 在Creative Designer中，現在可以將新的內容元件加入電子郵件中：轉盤。For more on this, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#about-content-components).
* In a transactional message hot click report, when you click the **Change profile** button, now only the test profiles linked to the event that you defined for your transactional message are listed.

### Patches {#patches-1}

* 修正ByEmail查詢篩選器無法傳回任何結果的問題。(CAMP-23420)
* 已修正允許標準使用者存取特定功能或螢幕的問題(/rest/head/*端點、交易傳訊畫面、描述檔和觀眾匯入畫面)。
* 修正GDPR隱私權刪除請求無法處理自訂資源(如果其名稱由數字開始)的問題。
* 修正「儲存對象」活動無法在Adobe Experience Cloud中共用應用程式訂閱者的錯誤。
* 修正檔案名稱包含空白空格時，可能發生的檔案傳輸活動問題。(CAMP-25936)
* 修正在作業過期後使用重新連線按鈕時可能發生的問題。(CAMP-25560)
* 修正在傳送與傳真規則關聯的時區最佳化時，可能導致排除的問題。(CAMP-25425)
* 修正使用API GDPR功能時，無法以0-1類型連結刪除資料的問題。
* 修正當取消疲勞特徵規則的版本時可能導致錯誤訊息的問題。
* 修正在編輯傳送內容後，可能會發生的問題。
* 修正在使用解壓縮選項處理CSV壓縮檔案時可能發生的問題。
* 已修正Creative Designer中的問題：將內建的樣式變更為連結或編輯連結時，造成不想要的色彩字型和格式設定。(CAMP-26001)
* 修正了導致熱按報表無法顯示包含動態內容之傳送中每個條件的百分比的問題。以前只會顯示預設變體上的點按。

## Release 18.6 - June 2018 {#release-18-6---june-2018}

### Improvements {#improvements-2}

* **[!UICONTROL History]** API已新增至Adobe. IO。它可讓您存取與描述檔行銷歷史記錄相關的資訊：接觸點、傳送的傳送、鏡像頁面URL等。For more on this, refer to the [dedicated use case](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#how-to-retrieve-the-mirror-page-for-a-delivery-sent-to-a-profile) .
* **[!UICONTROL Database cleanup]** 技術工作流程已最佳化，以確保資料庫備份的效能。
* Creative Designer for Email現在也提供法文版和德文版。

### Other changes {#other-changes-2}

* **[!UICONTROL Compute stats]** 已傳送傳送 **[!UICONTROL Deployment]** 視窗中的按鈕。它可讓您擷取最新KPI，例如傳送時間太長的結果，或是尚未考量的結果。For more on this, refer to this [section](../../sending/using/confirming-the-send.md).
* **在「更新」提供** 可用技術工作流程的更新中，功能管理員現在可以定義 **在「更新規則** javascript」活動中忽略的連續錯誤數目。依預設，欄位值會設為0，這表示所有錯誤都將被忽略。
* 管理單元存取限制條件時產生的SQL已最佳化。
* The **[!UICONTROL Update]** activity now allows you to add, update or delete data related to subscriptions (nms:appSubscriptionRcp table).
* **[!UICONTROL Update delivery execution]** 技術工作流程已分為兩個工作流程，以最佳化效能：- **[!UICONTROL Update delivery execution]**：更新傳送的追蹤。預設每10分鐘就會啓動一次。**[!UICONTROL Update delivery indicators]**：更新傳送的KPI，預設每小時會啓動。For more on technical workflows, refer to this [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* When a delivery is sending messages, the status in the **[!UICONTROL Deployment]** section can now have two values: **[!UICONTROL Sending]**: the messages are being sent. **[!UICONTROL Sending (retry)]**：正在進行重試傳遞。
* **[!UICONTROL Delivery preparation]** 具有角色的使用者現在可以傳送校樣。(CAMP-24313)
* **「啓用TLS over SMPP** 」選項已新增至 **透過SMPP** 外部帳戶的SMS路由。For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

### Patches {#patches-2}

* 修正當包含來自Adobe Target的動態影像(Camp-24848)時，無法傳送電子郵件的問題。
* Fixed an issue with the **[!UICONTROL Privacy Access/Delete Request]** technical workflows, which did not complete if any of the requests failed.
* 修正隱私權核心服務無法從Campaign接收請求狀態更新的問題。
* Fixed an issue which could prevent the **[!UICONTROL Import shared audience]** technical workflow from working properly (CAMP-25465).
* 修正「核心隱私權服務」中無法標示促銷活動隱私權請求的問題。
* 修正當Adobe ID太長時，某些使用者無法透過IMS驗證登入Campaign Standard的問題。(CAMP-24095)
* 已修正Creative Designer中移除內容模組時可能發生的問題。(CAMP-25242)
* 修正使用推播通知疲勞規則給資料庫中沒有描述檔的用戶的問題。(CAMP-25344)
* 修正存取傳送排除記錄時可能顯示錯誤訊息的問題。(CAMP-24724)
* 修正無法在延伸傳送記錄檔的例項中準備校樣的問題。
* Fixed two issues that could occur when publishing custom resources with the **[!UICONTROL Sending log]** extension activated.
* 已修正循環傳送中未考量傳送期間的問題。
* Fixed an issue that could occur when sorting data in the **[!UICONTROL Client data]** menu, for custom resources with more than 100K records. (CAMP-24308)
* 修正使用動態報表中的搜尋功能時，未考量自訂描述檔維度的問題。
* 修正動態報表中「帳戶」層級的國際資料顯示問題。
* 現在可以建立不含訂閱或取消訂閱確認訊息的服務。

## Release 18.5 - May 2018 {#release-18-5---may-2018}

### What's new? {#what-s-new--2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR: Core Service Integration<br /> </td> 
   <td> 隱私權核心服務整合可讓您透過單一JSON API呼叫，將GDPR請求自動化至多解決方案內容。<br /> 從隱私權核心服務推送至所有Experience Cloud解決方案的GDPR請求現在會自動由Campaign處理。<br /> 如需詳細資訊，請參閱 <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Push improvements - detailed delivery feedback<br /> </td> 
   <td> Adobe Campaign現在可透過MCNS接收供應商(APNS/GCM)推播訊息上的詳細意見回應(傳送記錄檔排除記錄)。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs extension<br /> </td> 
   <td> 傳送記錄功能擴充功能可讓您使用描述檔資料和來自工作流程的區段代碼來擴充傳送記錄檔。然後可在動態報表中使用此資訊，並讓您在傳送時保留一些資訊的快照。<br /> 有個使用案例：<br /> 
    <ul> 
     <li> 匯出含「凍結」資料的擴充範圍：身為行銷人員，我想要匯出區段代碼等於「A」(來自工作流程引擎)的所有描述檔。 </li> 
     <li> Segmentation on "frozen" data: As a marketer, I would like to <strong>retarget</strong> all profiles who have won 1000 loyalty points since the last sending or where segment code was equal to "A". </li> 
    </ul> For more information, refer to the <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic reporting with Custom profile data<br /> </td> 
   <td> 此功能可讓您根據設定檔資源擴充功能期間建立的自訂描述檔資料來建立和管理報表。您可以依描述檔屬性(例如忠誠度計劃、偏好渠道等)劃分報表。<br /> 如需詳細資訊，請參閱 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-3}

* 應用程式的整體記憶體和CPU使用量已增強

### Other changes {#other-changes-3}

* 「閱讀對象」工作流程活動現在可以讀取Experience Cloud觀眾。以前，此活動只能讀取查詢和清單對象。Refer to the [detailed documentation](../../automating/using/read-audience.md). (CAMP-23623)
* 預設共用資料來源的識別碼現在僅處於唯讀模式，無法再變更。變更此識別碼可能會導致與Experience Cloud共用觀眾時發生一些問題。
* 從Audience Manager匯入觀眾現在可處理分割檔案。以前，ImportSharedAudience技術工作流程只匯入區段的最後一個檔案。
* AWS S外部帳戶現在支援地區和第版驗證機制。Refer to the [detailed documentation](../../administration/using/external-accounts.md).
* 「資產選取」視窗現在應該更快載入，並允許選取資產，然後退出視窗而不發生任何問題。
* 技術工作流程的屬性和結構現在可以由擁有管理權限的使用者修改，並屬於「所有」組織和地理單位。
* 建立新區段時，區段活動介面中已進行增強：「限制」標籤現在會在新增限制後直接顯示。新區段的名稱現在已增量(「區段1」、「區段2」等)。
* 「nextprocessingDate」欄位會新增至工作流程資源。此欄位僅可透過REST API呼叫顯示，可讓您視覺化後續處理日期的工作流程。
* 現在在追蹤記錄檔資源中公開「sourceId」欄位(nms：trackingLog)。
* 「總開啓次數」和「點按總次數」值現在可透過工作流程匯出至平面檔案。(CAMP-24186)
* 「英文-丹麥文」現在可在個人檔案中使用偏好語言清單。(CAMP-23728)
* 使用「區段」活動搭配其他資料(TargetData)連結時，訊息現在通知您資料無法在工作流程外部提供。按一下區段活動中的「計數」或「預覽」按鈕時，會顯示此訊息。(CAMP-23651)
* 已改善工作流程使用的磁碟空間：(CAMP-219779)：預設會刪除「載入檔案」活動處理的檔案。選項可讓您保留特定需求。刪除工作流程時，會自動從伺服器目錄抑制專屬資料夾。

### Patches {#patches-3}

* 修正有些原始報告事件沒有相關聯追蹤事件，因為eventDate欄位未正確填入的問題。
* 修正推送通知傳遞的預覽視窗中無法顯示個人化欄位的問題。
* 已修正此問題：無法在預覽視窗中將推播通知的訊息內文加上字詞。
* 修正當主要目標為空白時，傳送從工作流程傳送重新導向傳送的問題。
* 修正如果連結至未現有的結構，無法存取目標對應的問題。
* 修正透過檔案載入活動匯入zip檔案時可能發生的問題。(CAMP-24309)
* 修正傳送週期性傳送時造成PostGregL錯誤的問題。(CAMP-23613)
* 修正傳送具有空白JSON屬性之REST API請求時，會顯示錯誤訊息的問題。(CAMP-23506)
* 修正設定檔中設定為大寫字元後方字元的問題。(CAMP-23136)
* 已修正傳送用於個人化或動態內容區塊資格條件的傳送時，同時使用描述檔連結結構屬性的問題。(CAMP-22751)
* 修正無法刪除服務的問題。(Camp-22050)
* 修正無法變更Test Profile中「國家/地區」值的問題。(CAMP-20426)
* 修正可能導致Creative Designer無法載入的問題。(CAMP-24573)
* 修正電子郵件主旨中個人化欄位之後新增字元的問題。(CAMP-24113)

## Release 18.4 - April 2018 {#release-18-4---april-2018}

### Patches {#patches-4}

#### Platform {#platform}

* 修正無法正確處理GDPR存取或刪除請求的錯誤。在某些罕見的情況下，已擷取的資料包含下列其中一個字元：&amp;&lt;&gt;」。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* 修正當Broadlog同步花了一小時以上時，造成KPI被錯誤值覆寫的問題。

#### Workflows {#workflows}

* 改善記憶體管理和工作流程中最佳化效能。

#### Reporting {#reporting}

* KPI共用工作流程現在會擷取過去個月的傳送值，而非過去個月。已修正KPI共用外部帳戶顯示截斷日期的問題。
* Fixed an issue which could lead to certain messages not being taken into account in **Sent**, **Delivered** and **Bounce** metrics.
* Fixed an error which occurred when the chosen time range in the **Delivery Summary Report** was too long.

#### Custom resources {#custom-resources}

* 修正自訂資源準備失敗的問題。

## Release 18.3 - March 2018 {#release-18-3---march-2018}

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
   <td> EU General Data Protection Regulation (GDPR)<br /> </td> 
   <td> GDPR是歐盟最新的隱私權法律，旨在協調並現代規範資料保護要求在2018年月25日生效的情況。GDPR適用於持有位於歐盟之資料主體之資料的Adobe Campaign客戶。<br /> 除了Adobe Campaign中已提供的隱私權功能(包括同意管理、資料保留設定及使用者角色)，我們將此機會納入資料處理方以納入額外功能，以協助您為特定GDPR要求的資料掌控者做好準備：<br /> 
    <ul> 
     <li> 存取權：允許資料主體接收資料控制器擷取的個人資料副本，可能包括儲存在Adobe Campaign中的資料。 </li> 
     <li> 刪除權利：賦予資料主體資料主體擷取的個人資料，包括儲存在Adobe Campaign中的資料。 </li> 
    </ul> For more information, refer to the <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email (Beta)<br /> </td> 
   <td> Adobe Campaign全新的Creative Designer在Campaign中提供完全整合的建立體驗，讓您快速且輕鬆地建立吸引人的個人化電子郵件，毋需編寫程式碼。Creative Designer透過強大的拖放介面，幫助您擴展電子郵件建立的規模，不論使用者是從空白的切割片段開始，還是運用現有的內容片段或範本。<br /> 主要功能包括：<br /> 
    <ul> 
     <li> 透過拖放介面，以視覺化方式設計並建立完全個人化的回應式電子郵件，並由原生Creative Cloud整合增強 </li> 
     <li> 建立並儲存電子郵件內容範本並運用儲存的範本來協助縮放電子郵件 </li> 
     <li> 建立並儲存內容片段(例如頁首、頁尾、文章等)簡化內容建立並確保品牌一致性 </li> 
     <li> 在按下按鈕時，在拖放介面中流暢地切換，並直接編輯電子郵件的HTML </li> 
    </ul> Creative Designer for Email僅提供英文版。<br /> 如需詳細資訊，請參閱 <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">詳細文件</a> 並觀看此 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">影片</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Multilingual Push Deliveries<br /> </td> 
   <td> 電子郵件和簡訊通道中已存在同樣簡單的多語言介面，並新增至推播管道，協助您不論偏好的語言，都能吸引客戶。<br /> 此功能可為管理多個地區的推送促銷活動的客戶提供可擴充和自動解決方案，並希望以他們偏好的語言鎖定使用者。它可讓您只需按一下，即可將所有的文字變體透過範本試算表上傳至單一推播傳送。Adobe Campaign接著會根據使用者的語言偏好設定執行自動細分，借以簡化工作流程和報告，協助減少冗余。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/creating-a-multilingual-push-notification.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Use of Custom Resources in Transactional Messaging<br /> </td> 
   <td> 除了立即可用的欄位外，交易式訊息現在可讓您使用自訂資源豐富訊息內容。<br /> 例如：<br /> 
    <ul> 
     <li> 利用自訂欄位做為協調准則，將交易訊息與描述檔相符 </li> 
     <li> 運用完整的個人檔案、服務和連結資料，進一步個人化交易訊息 </li> 
    </ul> For more information, refer to the <a href="../../administration/using/configuring-transactional-messaging.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### Platform {#platform-1}

* 修正從清單匯出超過5000筆記錄的問題。
* 修正將資料匯出至以個人化欄位命名的檔案時的問題。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* 修正造成多零件SMS截斷的問題，因為部分的部分是以字元而非位元組計算。
* Added an option which allows the **[!UICONTROL Delivered]** or **[!UICONTROL Bounces + Errors]** KPIs to be updated in real time after sending your delivery. 它們會從提供者收到的SR(狀態報表)直接重新計算。
* 修正傳送排程器中的日曆介面工具集問題。
* 修正在傳送傳送中第二次開啓目標時的顯示問題。
* 修正在建立具有延遲傳送日期的電子郵件範本時，會導致請求開始日期的錯誤訊息。
* 修正編輯傳送內容時可能導致影像轉譯問題的問題。
* 修正複製促銷活動時校樣的問題。
* 修正在新增傳送至工作流程後透過導覽列存取促銷活動範本時導致錯誤訊息的問題。
* 修正無法自動選取A/B測試電子郵件成功者的問題，導致未傳送電子郵件。This behavior could occur if the delivery was in **[!UICONTROL retryInProgress]** state.
* 修正重新開啓A/B測試電子郵件參數時出現錯誤訊息的問題。

#### Audiences &amp; queries {#audiences-e-queries}

* 修正從Adobe Campaign Classic複製到Standard的收件者無法存取資料並設定查詢的問題。
* Fixed an issue that occurred when using a filter type field in the query editor, after using the **Count** or **Preview** buttons.

#### Workflows {#workflows-1}

* **計費** 工作流程已進行最佳化，以改善傳送準備延遲。
* 修正使用循環傳送活動時，人口統計資料無法顯示在傳出轉換中的問題。
* Fixed an issue that prevented reject records from being displayed in a transition after an **Update data** activity.
* Fixed an issue which could cause the **deliverabilityUpdate** technical workflow to fail.

#### Integrations {#integrations}

* 修正國際字元無法正確傳送至Adobe Analytics的問題。
* 在嘗試將Experience Cloud資產庫中的影像插入訊息時，資產現在應該會更快速載入。
* 修正某些情況下無法關閉資產選取視窗的問題。
* 從資料來源詳細資料，您現在可以直接存取其相關工作流程，以檢查工作流程狀態。
* 您現在可以在定義或編輯觸發事件時，直接更新觸發器結構。有了這項變更，您不再需要解除發佈觸發器並建立另一個觸發器。

#### Transactional messages {#transactional-messages}

* 修正傳送資源時，交易訊息範本的錯誤。
* 現在可以刪除交易訊息。

## Release 18.2 - February 2018 {#release-18-2---february-2018}

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
   <td> Subscription - subscribe or unsubscribe a list of profiles to multiple services<br /> </td> 
   <td> <strong>「訂閱服務</strong> 」工作流程活動現在可讓您訂閱或取消訂閱多個服務的個人檔案清單。在您的工作流程中，匯入包含描述檔的檔案，以及每個描述檔、作業類型和服務。<strong>訂閱服務</strong> 活動可使用此資訊，同時動態處理您所有的個人檔案訂閱和取消訂閱。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/subscription-services.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Enrichment activity - enrich data based on previous transitions<br /> </td> 
   <td> <span class="uicontrol">全新的Rich</span> Workflow活動可讓您運用傳入的轉場效果，並透過額外資料完成輸出轉變。如果您設定個人檔案，則擴充活動可讓您利用未儲存在資料庫中的額外資料(例如匯入的檔案)豐富個人檔案資訊。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/enrichment.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### Platform {#platform-2}

* Adobe Campaign介面頂端列已更新為新的Experience Cloud功能表。
* Fixed an issue which prevented the link to **[!UICONTROL Offers]** from being displayed in the solution dropdown list.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* 已增強傳送準備階段，以改善效能。
* 修正了一些可能導致追蹤記錄在某些不同情況下損毀的問題。
* 修正在傳送準備和確認之間的連絡人日期變更時，發生連絡人日期更新問題。現在，當您變更準備後的連絡人日期時，必須先準備傳送，才能確認傳送。See the [detailed documentation](../../sending/using/preparing-the-send.md).

#### Push notifications {#push-notifications}

* 已修正某些個人化欄位無法在iOS推播通知中運作的問題。
* 修正推播通知控制面板中，點按和開啓率會顯示為0%的錯誤。

#### Reports {#reports}

* 修正某些瀏覽器中，報表清單顯示為空白的錯誤。
* Fixed an error that occurred in the **[!UICONTROL Report sharing]** technical workflow just before its expiration limit was reached.

#### Workflows {#workflows-2}

* 修正拖放活動後無法存取的問題。
* Fixed an issue that could cause the order of output transitions of a **[!UICONTROL Segmentation]** activity to change in some situations.
* 修正在讀取包含列舉類型欄位且先前已從工作流程儲存的對象時發生的錯誤
* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain checked even after unchecking it when defining the scheduling properties of a delivery created in a workflow.
* Automatic removal of duplicate rows (DISTINCT clause) can now be disabled in **[!UICONTROL Query]** activities, via a new option located in the **[!UICONTROL Additional data]** tab. 基於效能原因定義許多(超過100個)元素時，建議停用此選項。

#### Integrations {#integrations-1}

* Some improvements were made to the **[!UICONTROL Data sources]** configuration screen.

### Known issues {#known-issues}

我們建議您不要因為顯示問題而使用Internet Explorer11。

在「促銷活動」介面使用上下文說明連結時，可能會發生一些問題。它們將於18.3中固定。

## Release 18.1 - January 2018 {#release-18-1---january-2018}

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
   <td> Reporting for Fatigue Management<br /> </td> 
   <td> 「疲勞管理報告」是專用、可設定的報告，顯示在傳送前，在電子郵件、推播、簡訊和直接郵件管道之間傳送的影響疲勞規則。透過在單一視圖中快速查看所有衝突的宣傳活動的新增洞見，行銷人員可以規劃行銷活動，更有效地制定疲勞規則，並優先安排通訊。<br /> 如需詳細資訊，請參閱 <a href="../../administration/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Report sharing<br /> </td> 
   <td> 「報表共用」可讓您將您的報表與Adobe Campaign使用者共用為電子郵件附件，包括自動循環。接收循環報表的使用者可以透過每封電子郵件中的專用連結，取消訂閱這些通訊。<br /> 如需詳細資訊，請參閱 <a href="../../reporting/using/reporting-interface.md#share-tab">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Push New capabilities<br /> </td> 
   <td> 推播訊息預覽-在推播通知內容編輯器中預覽iOS和Android裝置上的推播通知，以查看收件者在測試或執行傳送前所看到的確切內容。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">詳細文件</a>。<br /> 可用內容-當應用程式未在較長期間內開啓時，其資料可能會過時。如此會在使用者終於開啓應用程式時更新或取代資料，因而導致使用應用程式延遲。借由新增的內容支援，Adobe Campaign使用者可以在傳送推播通知時喚醒其應用程式，以便在提供推播通知的同時，更能一致性和控制使用者的應用程式內體驗。<br /> 可靜音內容-透過新增的可靜音內容支援，Adobe Campaign使用者現在可以利用其行動應用程式擴充功能進一步修改從Adobe Campaign傳送之推播通知的內容或簡報。For example, users can leverage Mutable Content to: <br /> 
    <ul> 
     <li> 解密以加密格式傳送的資料 </li> 
     <li> 下載影像或其他媒體檔案，並將它們新增為通知的附件 </li> 
     <li> 變更通知的內文或標題文字 </li> 
     <li> 新增執行緒識別碼至通知 </li> 
    </ul> For more information on Content Available and Mutable Content, refer to the <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">detailed documentation</a>.<br /><strong>警告：</strong> 這些推播通知更新需要客戶升級其行動應用程式。Refer to <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> Time-zone optimized deliveries<br /> </td> 
   <td> 在每個收件者的時區中排程週期性的電子郵件、簡訊和推播通知，以確保您的訊息在正確的時間傳送，而無需設定多個傳送。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/scheduler.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> API Signal activity triggering<br /> </td> 
   <td> 現在可以直接從Adobe Campaign Standard API觸發工作流程的訊號活動。<br /> 如需詳細資訊，請參閱 <a class="anchorLink" href="https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity" target="_blank">詳細文件</a> 。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### Platform {#platform-3}

* 設定檔搜尋已最佳化，以改善效能。
* 預設安全群組的內部識別碼現在為標準使用者的唯讀模式。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-3}

* 已修正插入表情符號放入傳送內容中時所發生的顯示問題。
* 修正當傳送仍處於版本時，使用者可存取傳送記錄檔的問題。
* **[!UICONTROL Scheduler]** 活動現在可讓您根據收件者的時區傳送傳送。
* SMS: The option **[!UICONTROL Store incoming MO]** in the database has been added to external accounts. When checked, all incoming SMS will be stored into the **inSMS** table.
* SMS：服務現在會附加至事件，而非交易範本。
* SMS：預設的SMTP連線逾時已縮短為30秒。

#### Push notifications {#push-notifications-1}

* 修正無法停止推播通知傳送的錯誤。
* 在推播通知進階選項中新增選項，以喚醒使用推播通知的應用程式。
* 新增推播通知預覽影片的暫停按鈕。
* 推播通知預覽現在適用於不同裝置，例如iPhone、Android、平板電腦。

   所有頻道

#### Reports {#reports-1}

* 修正顯示率高於100%的錯誤。
* 修正使用者無法下載CSV報表的問題。
* Added a new **[!UICONTROL Report]** item in the homepage.

#### Workflows {#workflows-3}

* 修正在查詢中使用其他資料並新增包含空格的別名時，導致錯誤訊息的問題。非英數字元現在會由「_」取代。
* 修正在某些情況下，可能會停止計算KPI技術工作流程的問題。

#### Profiles and audiences {#profiles-and-audiences}

* 已修正在觀眾查詢中新增多個篩選器時所發生的錯誤。
* 修正變更描述檔圖片時發生的顯示問題。
* 新增工具提示，在計算查詢人口後顯示確切結果編號。
* 修正使用者無法選取對象或關閉觀眾選擇器視窗的問題。
* 運算式編輯器中可用函數清單已更新。**Formatcurrency** 和 **ConvertCurrency** 函數已移除。

