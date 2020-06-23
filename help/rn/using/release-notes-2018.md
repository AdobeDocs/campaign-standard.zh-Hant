---
title: 發行說明 2018 年
description: 本頁列出2018年版本的所有Adobe Campaign Standard。
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
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '5401'
ht-degree: 1%

---


# 發行說明 2018 年{#release-notes}

想要尋找2018年版Adobe Campaign Standard嗎？

每個版本都提供新功能和修補程式。 按一下某個版本以檢視其內容。

檢視Adobe Campaign Standard的 [最新檔案](../../rn/using/documentation-updates.md) 更新。 如果您要尋找較新的版本，請參閱本 [頁](../../rn/using/release-notes.md)。

## 發行版本18.9 - 2018年9月 {#release-18-9---september-2018}

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
   <td> 應用程式內訊息（測試版）<br /> </td> 
   <td> 應用程式內訊息可讓您提供情境式互動，並讓您觸及可能已選擇退出推播通知的使用者，以更有效率地吸引行動應用程式使用者。 搭配推播通知使用應用程式內訊息，以建立高度個人化且相關的體驗。 這可提升應用程式使用者的轉化率和維繫率。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/about-in-app-messaging.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 適用於行動應用程式的Adobe Launch整合（測試版）<br /> </td> 
   <td> Adobe Launch與Adobe Campaign的整合現在使用Mobile SDK V5簡化並自動化Campaign中「行動應用程式屬性」啟動的程式。<br /> 如需詳細資訊，請參閱詳 <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改進**

* Adobe Campaign Standard現在支援Amazon S3 API第4版。

**其他變更**

* 在廣播中，現在可以區分每小時最大連接數和最大消息數。 當達到限制時，便可知道為什麼吞吐量受到限制。 以前，這兩種情況都會套用相同的訊息（「符合配額」）。
* 在Campaign中設定行動應用程式時，使用者現在可以知道iOS憑證和Android伺服器金鑰是否已成功上傳，以及其到期日。

   如需詳細資訊，請參閱有關如何使用 [SDK V4和](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) SDK V5設定行動應用程式的詳細檔案 [](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

* 在定義促銷活動屬性時選取行動應用程式，以定位特定行動應用程式上的使用者。 這項功能適用於推播和應用程式內訊息通道。

   如需詳細資訊，請參閱[詳細文件](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)。

* 使用Creative Designer介面選取內容區塊時，現在會載入並顯示清單中的所有內容區塊。 (CAMP-27311)

   For more on this, refer to the [detailed documentation](../../designing/using/personalization.md#adding-a-content-block).

**修補程式**

* 修正電子郵件儀表板與交易電子郵件的電子郵件摘要報告之間記錄計數不一致的問題。 (CAMP-28237)
* 修正工作流程中，透過檔案傳輸活動匯入檔案時可能顯示錯誤訊息的問題。 (CAMP-27435)
* 已修正包含超過25個服務的著陸頁面，導致在表單中隨機取消選取服務的問題。 (CAMP-26572)
* 修正工作流程中，使用檔案傳輸活動時無法使用SFTP URL設定外部帳戶的問題。 (CAMP-26475)
* 修正無法更新服務摘要報告的問題。 (CAMP-26301)
* 修正使用「擴充」活動時，自訂欄位無法顯示正確日期的工作流程問題。 (CAMP-26242)
* 修正透過檔案匯入匯入時，無法更新服務訂閱日期的問題。
* 修正載入檔案活動導致工作流程無法匯入檔案的錯誤(CAMP-27068)。
* 修正「服務」摘要報告中顯示錯誤訂閱數的問題(CAMP-25587)。
* 修正Adobe Analytics和Adobe Campaign報表之間資料不一致的問題。 (CAMP-25393)
* 已修正無法讓有限存取使用者登入的問題。 (CAMP-27381)
* 修正使用Creative Designer編輯電子郵件時，Adobe Experience Manager內容清單無法顯示的問題。 (CAMP-27181)
* 修正可能無法開啟Creative Designer，造成錯誤的問題。 (CAMP-27304)
* 修正使用Internet Explorer 11時，拖放在Creative Designer中無法正確運作的問題。
* 修正從相機上傳並以縱向模式拍攝的像片，在不想要的旋轉位置顯示的問題。
* 修正在Creative Designer中使用查詢編輯器介面時，選取資訊不清楚的問題。
* 修正使用Creative Designer中的查詢編輯器介面時，無法正確複製元素的問題。
* 修正即使已透過自動回覆取消訂閱SMS訊息，仍持續傳送SMS訊息給區塊清單上的收件者的問題。 (CAMP-27128)
* 修正無法顯示導致「資料庫清除」工作流程 **失敗的錯誤** 。 (CAMP-26876)
* 修正推播通知定義中無法刪除自訂欄位的問題。 (CAMP-25588)

## 發行版本18.7 - 2018年7月 {#release-18-7---july-2018}

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
   <td> Android推播通知的高優先順序標幟<br /> </td> 
   <td> Android的高優先順序標幟——為Android應用程式啟用高優先順序的推播通知，讓休眠裝置喚醒並執行一些有限的處理。 請注意，預設優先順序為「正常」，這可能會延遲消息發送以節省電池。 <br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式訂閱者的排版篩選<br /> </td> 
   <td> 支援排版篩選中的訂閱——當指定排版規則的篩選條件時，應用程式訂閱可以選為篩選和定位維度，提供篩選有無描述檔使用者屬性的能力。 <br /> 如需詳細資訊，請參閱詳 <a href="../../sending/using/about-typology-rules.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 在準備訊息期間，從URL自動匯入內容<br /> </td> 
   <td> 現在可在準備階段從URL匯入電子郵件內容。 對於定期傳送的電子郵件，每次準備訊息時都會擷取最新的HTML內容，確保內容在傳送電子郵件時永遠保持最新。 此功能也可讓您建立含URL內容的排程傳送，即使內容尚未準備好。<br /> 如需詳細資訊，請參閱詳 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 促銷活動發行通知訊息<br /> </td> 
   <td> 現在，當使用者在例項升級至新版本後登入時，會出現快顯訊息。 此訊息會指出版本號碼，並包含發行說明的連結。 您可以選擇隱藏訊息，直到下次發行為止。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 使用者管理<br /> </td> 
   <td> 現在，新的「促銷活動標準」例項以及未建立地理單位的現有例項（從18.7版開始）無法使用地理單位功能。<br /> 如需詳細資訊，請參閱本 <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">頁</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改進**

* Adobe Campaign和Adobe Target整合現在可讓您運用Target的「權 [限](https://docs.adobe.com/content/help/en/target/using/administer/manage-users/enterprise/properties-overview.html) 」功能。 在電子郵件中包含Adobe Target的動態影像時，您現在可以指定Target屬性（at_property代碼）。
* GDPR隱私權存取／刪除要求現在會考量到具有描述檔資源之下載連結的自訂資源。 對於1個基數簡單連結和N個基數收集連結，您需要在自定義資源中選擇「刪除／複製目標籤錄意味著刪除／複製連結引用的記錄」。 對於0或1個基數簡單連結，選擇「刪除／複製記錄意味著刪除／複製連結引用的目標籤錄」。

**其他變更**

* 報表共用逾時時間已從1分鐘增加到4分鐘，以避免任何逾時錯誤。
* 編輯電子郵件內容時，全新的Creative Designer會依預設開啟。 如果您願意，在儲存變更後，您仍可隨時返回預設的內容編輯器。 For more on this, refer to the [detailed documentation](../../designing/using/designing-content-in-adobe-campaign.md).
* 在Creative Designer中，現在可以將新的內容元件新增至電子郵件： 轉盤。 For more on this, refer to the [detailed documentation](../../designing/using/designing-from-scratch.md#about-content-components).
* 在事務性消息熱點按一下報告中，當您按一下「 **Change profile** （更改配置檔案）」按鈕時，現在只會列出連結到您為事務性消息定義的事件的測試配置檔案。

**修補程式**

* 修正byEmail查詢篩選器無法傳回任何結果的問題。 (CAMP-23420)
* 修正標準使用者可存取限於管理員的特定功能或畫面（/rest/head/*端點、交易式訊息畫面、設定檔和觀眾匯入畫面）的問題。
* 修正GDPR隱私權刪除要求無法處理自訂資源（如果自訂資源的名稱是以數字開頭）的問題。
* 修正「儲存對象」活動無法在Adobe Experience Cloud中共用應用程式訂閱者的錯誤。
* 修正當檔案名稱包含空白字元時，可能發生的「檔案傳輸」活動問題。 (CAMP-25936)
* 修正作業過期後使用重新連線按鈕時可能發生的問題。 (CAMP-25560)
* 修正傳送傳送與疲勞性規則相關之時區最佳化時，可能導致排除的問題。 (CAMP-25425)
* 修正使用API GDPR功能時，無法刪除具有0-1類型連結的資料的問題。
* 已修正取消疲勞排版規則版本時可能會產生錯誤訊息的問題。
* 修正在編輯傳送內容後預覽傳送內容時可能發生的問題。
* 修正使用「解壓縮」選項處理CSV Zip檔案時可能發生的問題。
* 修正Creative Designer在將內建樣式的部分文字變更為連結或編輯該連結時，產生不想要的色彩字型和格式的問題。 (CAMP-26001)
* 修正導致熱點按報表無法顯示包含動態內容之傳送中每個條件的百分比的問題。 以前只會顯示對預設變體的點按次數。

## 發行版本18.6 - 2018年6月 {#release-18-6---june-2018}

**改進**

* API **[!UICONTROL History]** 已新增至Adobe.IO。 它可讓您存取與描述檔的行銷歷史記錄相關的資訊： 觸點數、已傳送傳送、鏡像頁面URL等。 如需詳細資訊，請參閱專 [用使用案例](../../api/using/interacting-with-marketing-history.md) 。
* 為了 **[!UICONTROL Database cleanup]** 確保資料庫備份的更佳效能，已優化了技術工作流程。
* 適用於電子郵件的Creative Designer現在也提供法文和德文版。

**其他變更**

* 已 **[!UICONTROL Compute stats]** 在傳送的傳送視窗 **[!UICONTROL Deployment]** 中新增按鈕。 它可讓您擷取最新的KPI，例如，如果傳送的結果需要太長時間才能更新，或未考慮到這些結果。 For more on this, refer to this [section](../../sending/using/confirming-the-send.md).
* 在「更 **新」中** ，功能管理員現在可以在「更新規則 **** Javascript」活動中定義要忽略的連續錯誤數目。 依預設，欄位值會設為0，這表示將忽略所有錯誤。
* 管理單元訪問限制條件時生成的SQL已優化。
* 現 **[!UICONTROL Update]** 在，此活動可讓您新增、更新或刪除與訂閱相關的資料（nms:appSubscriptionRcp表格）。
* 為 **[!UICONTROL Update delivery execution]** 了優化效能，將技術工作流分為兩個工作流： - **[!UICONTROL Update delivery execution]**: 更新傳送的追蹤。 預設每10分鐘啟動一次。 **[!UICONTROL Update delivery indicators]**: 更新傳送的KPI，預設每小時啟動一次。 For more on technical workflows, refer to this [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* 傳送訊息時，區段中的狀態現 **[!UICONTROL Deployment]** 在可以有兩個值： **[!UICONTROL Sending]**: 正在發送消息。 **[!UICONTROL Sending (retry)]**: 重試通過正在進行中。
* 具有角色 **[!UICONTROL Delivery preparation]** 的使用者現在可以傳送校樣。 (CAMP-24313)
* 「 **Enable TLS over SMPP** over SMPP **」(啟用TLS over SMPP** )選項已經通過SMPP外部帳戶添加到SMS路由中。 For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**修補程式**

* 修正當包含來自Adobe Target的動態影像時，無法傳送電子郵件的問題(CAMP-24848)。
* 修正技術工作 **[!UICONTROL Privacy Access/Delete Request]** 流程的問題，當有任何請求失敗時，此問題無法完成。
* 修正「隱私權核心」服務無法從「促銷活動」接收請求狀態更新的問題。
* Fixed an issue which could prevent the **[!UICONTROL Import shared audience]** technical workflow from working properly (CAMP-25465).
* 修正促銷活動隱私權要求無法在核心隱私權服務中標示為已完成的問題。
* 修正當Adobe ID過長時，某些使用者無法透過IMS驗證登入Campaign Standard的問題。 (CAMP-24095)
* 修正Creative Designer中移除內容模組時可能發生的問題。 (CAMP-25242)
* 修正在資料庫中沒有設定檔的訂閱者使用推播通知疲勞規則時的問題。 (CAMP-25344)
* 修正存取傳送排除記錄時可能顯示錯誤訊息的問題。 (CAMP-24724)
* 修正在具有延伸傳送記錄的例項中無法準備校樣的問題。
* 已修正在啟動擴充功能時發佈自訂資源時可能 **[!UICONTROL Sending log]** 發生的兩個問題。
* 修正交貨持續期未計入週期性交貨時可能發生的問題。
* 修正在功能表中排序資料時，對於超過100K **[!UICONTROL Client data]** 記錄的自訂資源時可能發生的問題。 (CAMP-24308)
* 修正自訂描述檔維度在使用動態報表中的搜尋功能時，未考慮的問題。
* 修正「動態」報表中「帳戶」層級的國際資料顯示問題。
* 現在，您可以建立不含訂閱或取消訂閱確認訊息的服務。

## 發行版本18.5 - 2018年5月 {#release-18-5---may-2018}

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
   <td> GDPR: 核心服務整合<br /> </td> 
   <td> 「隱私權核心服務整合」可讓您透過單一JSON API呼叫，在多解決方案內容中自動化您的GDPR要求。 <br /> 從隱私權核心服務推送至所有Experience Cloud解決方案的GDPR要求現在由Campaign自動處理。 <br /> 如需詳細資訊，請參閱詳 <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播改進——詳細的傳送意見回應<br /> </td> 
   <td> Adobe Campaign現在提供透過MCPNS從提供者(APNS/GCM)接收推播訊息的詳細意見回應（傳送記錄和排除記錄）的能力。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送記錄擴充功能<br /> </td> 
   <td> 傳送記錄擴充功能可讓您使用來自工作流程的描述檔資料和區段代碼來擴充傳送記錄檔。 此資訊隨後可用於動態報表，並可讓您在傳送時保留某些資訊的快照。<br /> 還有2種使用案例：<br /> 
    <ul> 
     <li> 使用「凍結」資料匯出延伸廣播： 身為行銷人員，我想匯出區段代碼等於「A」（來自工作流程引擎）的所有設定檔。 </li> 
     <li> 「凍結」資料的分段： 身為行銷人員，我想重新定 <strong>位</strong> ，自上次傳送以來已贏得1000個忠誠度點的所有個人檔案，或區段代碼等於「A」的個人檔案。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用自訂描述檔資料進行動態報告<br /> </td> 
   <td> 此功能可讓您根據在描述檔資源擴充期間建立的自訂描述檔資料來建立和管理報告。 您可以依據描述檔屬性（例如忠誠度方案、偏好渠道等）劃分報表。<br /> 如需詳細資訊，請參閱詳 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改進**

* 應用程式的整體記憶體和CPU使用量已增強

**其他變更**

* 「讀取對象」工作流程活動現在可以讀取Experience Cloud對象。 以前，此活動只能讀取「查詢」和「清單」對象。 請參閱詳細 [檔案](../../automating/using/read-audience.md)。 (CAMP-23623)
* 預設「共用」資料來源的識別碼現在為唯讀模式，無法再變更。 變更此識別碼可能會在與Experience Cloud共用觀眾時產生一些問題。
* 從Audience Manager匯入觀眾現在可處理分割檔案。 以前，只有區段的最後一個檔案是由importSharedAudience技術工作流程匯入的。
* AWS S3外部帳戶現在支援地區和版本4身份驗證機制。 請參閱詳細 [檔案](../../administration/using/external-accounts.md)。
* 現在，「資產選擇」視窗應可加快載入速度，並允許選取資產，然後退出視窗而無任何問題。
* 具有管理權限且屬於「所有」組織和地理單位的用戶現在可以修改技術工作流程的屬性和結構。
* 建立新區段時，已在區段活動介面中進行增強： 現在，在新增限制後，「限制」標籤會直接顯示。 新區段的名稱現在會增加（「區段1」、「區段2」等）。
* 「nextProcessingDate」欄位會新增至「工作流程」資源。 此欄位只會透過REST API呼叫顯示，可讓您視覺化下一個處理日期的工作流程。
* 「sourceId」欄位現在會公開在追蹤記錄檔資源(nms:trackingLog)中。
* 「開啟總次數」和「點按總次數」值現在可透過工作流程匯出為平面檔案。 (CAMP-24186)
* 「英文- Danmark」現在可在設定檔的「慣用語言」清單中取用。 (CAMP-23728)
* 將「區段」活動與「其他資料」(targetData)連結搭配使用時，現在會有訊息通知您該資料在工作流程之外無法使用。 按一下「區段」活動中的「計數」或「預覽」按鈕時，會顯示此訊息。 (CAMP-23651)
* 已增強功能，以最佳化工作流程所使用的磁碟空間： (CAMP-21979): 「載入檔案」活動處理的檔案現在預設會刪除。 您可以透過選項，依特定需求保留這些檔案。 刪除工作流時，其專用資料夾會自動從伺服器目錄中隱藏。

**修補程式**

* 修正某些原始報表事件由於eventDate欄位未正確填入而沒有關聯追蹤事件的問題。
* 修正推播通知傳送的預覽視窗無法顯示個人化欄位的問題。
* 修正在預覽視窗中，文字無法在推播通知的訊息內文上包覆文字的問題。
* 修正當主目標為空時，從工作流程傳送重新固化傳送的問題。
* 修正當目標映射連結至未存在的架構時，無法存取該映射的問題。
* 修正透過檔案載入活動匯入zip檔案時可能發生的問題。 (CAMP-24309)
* 修正傳送循環傳送時導致PostgreSQL錯誤的問題。 (CAMP-23613)
* 修正傳送具有空JSON屬性的REST API請求時，顯示錯誤訊息的問題。 (CAMP-23506)
* 修正設定檔中，設為&quot;ß&quot;字元後大寫的問題。 (CAMP-23136)
* 修正當使用連結描述檔結構中的屬性傳送與個人化或動態內容區塊的資格條件搭配使用的傳送時，發生的問題。 (CAMP-22751)
* 修正無法刪除服務的問題。 (CAMP-22050)
* 修正無法變更測試設定檔中的國家／地區或州值的問題。 (CAMP-20426)
* 已修正無法載入Creative Designer的問題。 (CAMP-24573)
* 修正移除電子郵件主題中個人化欄位後新增的字元的問題。 (CAMP-24113)

## 發行版本18.4 - 2018年4月 {#release-18-4---april-2018}

**修補程式**

_平台_

* 修正無法正確處理GDPR存取或刪除請求的錯誤。 在某些罕見的情況下，提取的資料包含以下字元之一，這種行為已被觀察到： &amp; &lt; > &quot; &#39;。

_電子郵件、簡訊訊息和直效郵件_

* 修正如果廣播同步花費了一小時以上，可能導致KPI被錯誤值覆寫的問題。

_工作流程_

* 改善記憶體管理並最佳化工作流程效能。

_報告_

* KPI共用工作流程現在會擷取過去2個月而非過去6個月的傳送值。 修正KPI共用外部帳戶顯示截斷日期的問題。
* 修正「已傳送」、「已傳送」和「彈回數」中可能未考 **慮特定**&#x200B;訊息 **的******&#x200B;問題。
* 修正「傳送摘要報表」中選取的時 **間範圍過長時** ，發生的錯誤。

_自訂資源_

* 修正自訂資源準備失敗的錯誤。

## 發行版本18.3 - 2018年3月 {#release-18-3---march-2018}

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
   <td> 歐盟通用資料保護規則(GDPR)<br /> </td> 
   <td> GDPR是歐盟(EU)的新隱私權法，協調並現代化將於2018年5月25日生效的資料保護要求。 GDPR 適用於所持有資料的主體居住於歐盟的 Adobe Campaign 客戶。<br /> 除了Adobe Campaign中已提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）外，我們也將利用這個機會，以資料處理者的身分，加入其他功能，以協助您做好準備，做為特定GDPR要求的資料掌控者：<br /> 
    <ul> 
     <li> 存取權： 允許資料主體接收資料掌控者所擷取的個人資料副本，可能包括儲存在Adobe Campaign中的資料。 </li> 
     <li> 刪除權： 資料主體有權清除資料掌控者擷取的個人資料，可能包括Adobe Campaign中儲存的資料。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 適用於電子郵件的Creative Designer（測試版）<br /> </td> 
   <td> Adobe Campaign的全新創意設計人員在Campaign中提供完全整合的創作體驗，讓您快速輕鬆地以視覺化方式建立引人入勝的個人化電子郵件，毋需編寫程式碼。 Creative Designer透過其強大的拖放介面，協助您擴大電子郵件的建立範圍，不論使用者是從空白的位置開始，或是運用現有的內容片段或範本。 <br /> 主要功能包括：<br /> 
    <ul> 
     <li> 透過拖放介面，以視覺化方式設計並建立完全個人化、回應速度快的電子郵件，再加上Creative Cloud的原生整合 </li> 
     <li> 建立和儲存電子郵件內容範本並運用儲存的範本，以協助縮放電子郵件建立 </li> 
     <li> 建立並儲存內容片段（例如頁首、頁尾、文章等） 簡化內容製作並確保品牌一致性 </li> 
     <li> 在拖放介面中建立內容，以及按一下按鈕直接編輯電子郵件的HTML之間順暢切換 </li> 
    </ul> 適用於電子郵件的Creative Designer僅提供英文版。<br /> 如需詳細資訊，請參閱詳 <a href="../../designing/using/designing-content-in-adobe-campaign.md">細檔案</a> ，並觀看 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">影片</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 多語言推播傳送<br /> </td> 
   <td> 推播通道中已新增了電子郵件和簡訊通道上相同的簡單多語言介面，協助您不論客戶偏好使用何種語言，都能吸引客戶。<br /> 此功能為管理跨多個地區且想要以偏好語言鎖定使用者的推播促銷活動的客戶，提供可擴充且自動化的解決方案。 它可讓您透過範本化試算表，按一下滑鼠，將所有語言變體上傳至單一推送傳送。 然後，Adobe Campaign會根據使用者的語言偏好來執行自動分段，借以簡化工作流程和報告，協助降低重複率。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/creating-a-multilingual-push-notification.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事務性消息傳遞中自定義資源的使用<br /> </td> 
   <td> 除了現成可用的欄位外，交易式訊息現在可讓您使用自訂資源豐富訊息的內容。<br /> 例如：<br /> 
    <ul> 
     <li> 利用自訂欄位做為協調標準，將交易訊息與描述檔相符 </li> 
     <li> 利用完整的個人檔案、服務和連結資料，進一步個人化交易訊息 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../administration/using/configuring-transactional-messaging.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 修正無法從清單匯出超過5000個記錄的問題。
* 修正將資料匯出至以個人化欄位命名的檔案時的問題。

_電子郵件、簡訊訊息和直效郵件_

* 修正多部分SMS因為部分大小是以字元而非位元組計算而遭到截斷的問題。
* 新增選項，可讓您 **[!UICONTROL Delivered]** 在傳送 **[!UICONTROL Bounces + Errors]** 傳送後即時更新或KPI。 它們直接從從提供者收到的SR（狀態報告）重新計算。
* 修正傳送排程器中日曆Widget的問題。
* 修正在已傳送傳送中第二次開啟目標時的顯示問題。
* 修正建立電子郵件範本時，傳送日期延遲時，導致錯誤訊息要求開始日期的問題。
* 修正編輯傳送內容時，可能導致影像轉譯問題的問題。
* 修正複製促銷活動時的校樣問題。
* 修正在將傳送新增至工作流程後，透過導覽列存取促銷活動範本時，會導致錯誤訊息的問題。
* 修正無法自動選取A/B測試電子郵件成功者，導致電子郵件無法傳送的問題。 如果傳送處於狀態，就可能會發生此 **[!UICONTROL retryInProgress]** 行為。
* 修正重新開啟A/B測試電子郵件參數時，可能會顯示錯誤訊息的問題。

_觀眾與查詢_

* 修正無法存取資料並設定從Adobe Campaign Classic複製至Standard之收件者查詢的問題。
* 修正使用「計數」或「預覽」按鈕後，在查詢編輯器中使用篩選類型欄位 **時** ，發 **生的問題** 。

_工作流程_

* 帳單 **工作流程已經最佳化** ，以改善傳送準備延遲。
* 修正使用循環傳送活動時，人口資料無法顯示在對外轉移中的問題。
* 修正「更新」資料活動後，無法在轉場中顯示拒絕記錄 **的問題** 。
* 修正可能導致可傳送性更 **新技術工作流程** 失敗的問題。

_整合_

* 修正無法正確傳送國際字元至Adobe Analytics的問題。
* 現在，嘗試從訊息中插入Experience Cloud資產庫的影像時，資產載入速度應該會更快。
* 修正資產選擇視窗在某些情況下無法關閉的問題。
* 您現在可以從資料來源的詳細資料直接存取其相關工作流程，以檢查工作流程的狀態。
* 現在，您可以在定義或編輯觸發器事件時直接更新觸發器結構。 有了這項變更，您不再需要解除發佈觸發器並建立另一個觸發器。

_交易式訊息_

* 修正延伸傳送資源時，交易訊息範本的錯誤。
* 現在可以刪除事務性消息。

## 發行版本18.2 - 2018年2月 {#release-18-2---february-2018}

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
   <td> 訂閱——訂閱或取消訂閱多項服務的設定檔清單<br /> </td> 
   <td> 「訂 <strong>閱服務</strong> 」工作流程活動現在可讓您訂閱或取消訂閱多項服務的描述檔清單。 在工作流中，導入包含配置檔案的檔案，以及每個配置檔案的操作類型和服務。 「訂 <strong>閱服務</strong> 」活動將能夠使用這項資訊，並一次動態處理您所有的設定檔訂閱和取消訂閱。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/subscription-services.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 擴充活動——根據先前的轉場來擴充資料<br /> </td> 
   <td> 新的 <span class="uicontrol">Enrichment</span> workflow活動可讓您運用傳入的轉場效果，並使用其他資料完成輸出轉場。 如果您定位配置檔案，則擴充活動允許您使用未儲存在資料庫中的其他資料（例如，來自導入的檔案）來豐富配置檔案資訊。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/enrichment.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* Adobe Campaign介面的頂端列已使用新的Experience Cloud功能表更新。
* 修正無法在解決方案下拉式清 **[!UICONTROL Offers]** 單中顯示連結的問題。

_電子郵件、簡訊訊息和直效郵件_

* 遞送準備階段已經增強以改進效能。
* 已修正若干問題，這些問題可能會在某些小眾情況下造成追蹤記錄檔損毀。
* 修正當傳送準備與確認之間的聯絡日期變更時，發生的連絡人日期更新問題。 現在，當您在準備後變更連絡人日期時，您必須先重新準備傳送，才能確認傳送。 請參閱詳 [細檔案](../../sending/using/preparing-the-send.md)。

_推播通知_

* 修正某些個人化欄位無法在iOS推播通知中運作的錯誤。
* 修正推播通知控制面板中，點按和開啟率顯示為0%的錯誤。

_報表_

* 修正某些瀏覽器中報表清單顯示為空白的錯誤。
* 修正技術工作流程中，在 **[!UICONTROL Report sharing]** 到達其過期限制之前發生的錯誤。

_工作流程_

* 修正拖放活動後無法存取的問題。
* 修正在某些情況下，活動的輸出轉場順 **[!UICONTROL Segmentation]** 序可能會變更的問題。
* 修正讀取包含列舉類型欄位且先前已從工作流程儲存的對象時發生的錯誤
* 修正在定義在工 **[!UICONTROL Request confirmation before sending messages]** 作流程中建立之傳送的排程屬性時，即使取消核取選項後，仍會保留核取選項的問題。
* 現在，可以通過頁籤中的新選項，在活動中禁 **[!UICONTROL Query]** 用自動刪除重複行(DISTINCT子 **[!UICONTROL Additional data]** 句)。 基於效能原因，在定義許多（超過100個）其他元素時，建議停用此選項。

_整合_

* 已對設定畫面進行 **[!UICONTROL Data sources]** 一些改進。

_已知問題_

我們建議您不要使用Internet Explorer 11版，因為可能的顯示問題。

使用「促銷活動」介面的內容相關說明連結時，可能會發生一些問題。 將在18.3版中修正。

## 發行版本18.1 - 2018年1月 {#release-18-1---january-2018}

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
   <td> 「疲乏管理報表」是專屬的可設定報表，顯示傳送前指定日期範圍內，電子郵件、推播、簡訊和直效郵件通道的傳送對影響疲勞規則。 由於新增了能夠在單一檢視中快速查看所有衝突促銷活動的見解，行銷人員可以更有效率地根據疲勞規則來規劃行銷活動，並排定通訊的優先順序。<br /> 如需詳細資訊，請參閱詳 <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 報告共用<br /> </td> 
   <td> 「報表共用」可讓您以電子郵件附件的形式與Adobe Campaign使用者共用報表，包括自動循環使用。 收到定期報告的使用者可以透過每封電子郵件的專屬連結取消訂閱這些通訊內容。<br /> 如需詳細資訊，請參閱詳 <a href="../../reporting/using/reporting-interface.md#share-tab">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播新功能<br /> </td> 
   <td> 推播訊息預覽——從推播通知內容編輯器中預覽iOS和Android裝置上的推播通知，以在測試或執行傳送之前，確切瞭解收件者會看到的內容。<br />如需詳細資訊，請參閱<a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">詳細文件</a>。<br /> 可用內容——當應用程式在較長時間內未開啟時，其資料可能會變得過時。 如此，當使用者最終開啟應用程式時，就必須更新或取代資料，這可能會造成應用程式的使用延遲。 透過新增的「可用內容」支援，Adobe Campaign使用者可以在傳送推播通知時喚醒其應用程式，以在背景重新整理資料，讓使用者的應用程式內體驗更具一致性和控制力。<br /> 可變內容——有了可變內容的新增支援，Adobe Campaign使用者現在可以運用其行動應用程式擴充功能，進一步修改從Adobe Campaign傳送的推播通知的內容或呈現方式。 例如，使用者可以利用「可變內容」: <br /> 
    <ul> 
     <li> 解密以加密格式傳送的資料 </li> 
     <li> 下載影像或其他媒體檔案，並將它們新增為通知的附件 </li> 
     <li> 變更通知的正文或標題文字 </li> 
     <li> 向通知添加線程標識符 </li> 
    </ul> 有關「可用內容」和「可變內容」的詳細資訊，請參閱詳 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">細檔案</a>。<br /> <strong>警告：</strong> 這些推播通知的更新需要客戶升級其行動應用程式。 Refer to <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> 時區最佳化傳送<br /> </td> 
   <td> 排程定期傳送的電子郵件、簡訊和推播通知，以便在每個收件者的時區中，於特定日／時間傳送，確保訊息在適當的時間傳送，而不需設定多個傳送。 <br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/scheduler.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> API Signal活動觸發<br /> </td> 
   <td> 現在可以直接從Adobe Campaign Standard API觸發工作流程的訊號活動。<br /> 如需詳細資訊，請參閱詳細 <a href="/help/api/using/triggering-a-signal-activity.md">檔案</a> 。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 已最佳化描述檔搜尋，以改善效能。
* 預設安全性群組的內部識別碼現在為標準使用者的唯讀模式。

_電子郵件、簡訊訊息和直效郵件_

* 修正將emoji插入傳送內容時發生的顯示問題。
* 修正當傳送仍在版本中時，使用者可存取傳送記錄檔的問題。
* 活動 **[!UICONTROL Scheduler]** 現在可讓您根據收件者的時區，傳送您的傳送內容。
* 簡訊： 資料庫 **[!UICONTROL Store incoming MO]** 中的選項已新增至外部帳戶。 勾選後，所有傳入的SMS都會儲存在 **inSMS表** 中。
* 簡訊： 服務現在會附加至事件，而非交易範本。
* 簡訊： 預設的SMTP連接超時已減少到30秒。

_推播通知_

* 修正推播通知傳送無法停止的錯誤。
* 在推播通知中新增了進階選項，可使用推播通知來喚醒應用程式。
* 新增推播通知預覽影片的暫停按鈕。
* 推播通知預覽現在適用於不同的裝置，例如iPhone、Android、平板電腦。

_報表_

* 修正顯示超過100%的比率的錯誤。
* 修正使用者無法以CSV格式下載報表的問題。
* 在首頁中 **[!UICONTROL Report]** 新增項目。

_工作流程_

* 修正在查詢中使用其他資料並新增包含空格之別名時，會導致錯誤訊息的問題。 非英數字元現在會以&quot;_&quot;取代。
* 修正計算KPI的技術工作流程在某些情況下預設會停止的問題。

_設定檔與閱聽眾_

* 修正在對象查詢中新增多個篩選器時發生的錯誤。
* 修正變更描述檔圖片時發生的顯示問題。
* 新增工具提示，顯示計算查詢填入量後的確切結果編號。
* 修正使用者無法選取對象或關閉對象選擇器視窗的問題。
* 運算式編輯器中可用函式的清單已更新。 FormatCurrency **** 和 **ConvertCurrency** 函式已移除。

