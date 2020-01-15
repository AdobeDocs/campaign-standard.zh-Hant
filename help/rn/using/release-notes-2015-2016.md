---
title: 發行說明 2015-2016 年
description: 本頁列出2015年和2016年版本的Adobe Campaign Standard。
page-status-flag: never-activated
uuid: d5a0f6cc-0bed-46cf-8dff-1717fb624f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: a3ce6b80-1858-49d1-8880-3543181127f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d1ec5dddcf4c1aa3fe6338d35b381986ba32a28d

---


# 發行說明 2015-2016 年{#release-notes}

想要2015-2016年版Adobe Campaign Standard嗎？

每個版本都提供新功能和修補程式。 按一下某個版本以檢視其內容。

檢視Adobe Campaign standard的 [最新檔案](../../rn/using/documentation-updates.md) 更新。 如果您要尋找較新的版本，請參閱本 [頁](../../rn/using/release-notes.md)。

## 發行版本16.11 - 2016年11月 {#release-16-11---november-2016}

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
   <td> 可傳遞性排除規則<br /> </td> 
   <td> 加密的全域抑制清單現在會在傳送能力例項中管理，以避免因惡意活動而列入黑名單，尤其是使用Spamtrap。<br /> 對於每封電子郵件傳送，兩個預設的排版規則會比較收件者電子郵件地址與此清單中包含的禁止地址或網域名稱。 如果有相符項目，該收件者會從目標人口中排除。<br /> 如需詳細資訊，請參閱詳 <a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 一般最佳化<br /> </td> 
   <td> 此更新包含許多修改和修補程式，可修正客戶遇到的問題。 並對全球平台效能進行了優化。 <br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 已修正數個安全性問題。
* 修正REST API中空欄位或重複欄位的數個問題。
* 您現在可以直接從應用程式的首頁建立SMS訊息和推播通知。

_電子郵件和簡訊_

* 修正使用者無法在內容編輯器中上傳zip檔案的問題。
* 修正無法在傳送證明後開啟證明的問題。
* 修正當存取A/B測試電子郵件的報表時， **[!UICONTROL Hot Clicks]**會顯示錯誤訊息的問題。
* 修正無法套用使用模式所 **[!UICONTROL Show source]**做的修改的問題。
* 修正可能無法匯入預測性主旨行xml模型檔案的問題。
* 專為受訓練的主題模型匯入資料的新畫面，現在可在 **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]**。
* 修正非管理員使用者可在電子郵件設定畫面中編輯授權遮色片的問題。

_推播通知_

* 修正使用範本傳送推播通知後，無法為收件者顯示傳送記錄檔和事件記錄檔的 **[!UICONTROL Send push on profiles]**問題。
* 修正可能無法建立新行動應用程式的問題。

_工作流程_

* 修正使用活動時發生的效能 **[!UICONTROL Subscription]**問題。
* 修正當工作流程的內部名稱包含空格時，工作流程無法運作的問題。

_整合_

* 修正在電子郵件中使用「從Adobe Marketing cloud共用的 **** 影像」選項時，可能會顯示錯誤的問題。

_自訂資源_

* 增強的API記錄檔預覽（在兩個擴充的API欄位出版物之間）。
* 修正自訂資源無法在發佈前刪除的問題。
* 修正無法擴充描述檔，且無法使用動態欄位設定識別碼鍵的問題。
* 修正在自訂資源中新增連結時可能發生的問題。

## 發行版本16.10 - 2016年10月 {#release-16-10---october-2016}

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
   <td> 電子郵件預測性主旨行<br /> </td> 
   <td> 編輯電子郵件時，新選項可讓您嘗試不同的主旨行，並在傳送電子郵件前先估計其開放率。 您可以根據過去的傳送資料來訓練自己的模型，或使用您產業專屬的預先定義模型，就能達成此目標。 此功能適用於電子郵件訊息和僅包含英文內容的資料庫。 <br /> 有關啟用和使用它的詳細資訊，請參閱詳 <a href="../../designing/using/subject-line.md#predictive-subject-line">細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> SMS交易訊息<br /> </td> 
   <td> SMS頻道已新增至Adobe Campaign的交易訊息功能。 交易式訊息現在支援兩個通道：電子郵件和簡訊<br /> 如需詳細資訊，請參閱詳 <a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事務性消息傳遞的後續消息<br /> </td> 
   <td> 現在可以建立以事件為目標的工作流程。 這表示您可以傳送後續訊息給先前收到交易訊息的客戶。 您可以依事件類型、事件廣播和追蹤記錄來篩選目標。 在後續訊息中，您將可運用事件的內容（裝載）。 <br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/follow-up-messages.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 擴充的設定檔與服務API<br /> </td> 
   <td> 您現在可以在Profile and Services API中公開延伸欄位。 出版機制可讓API對應描述檔或服務自訂資源的延伸欄位。 為了使此功能正常運作， <strong>已添加Datamodel</strong> 角色。 此新角色可讓使用者設定一組具有資料模型存取權的管理員。<br /> 如需詳細資訊，請參閱詳 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 已修正數個安全性問題。

_電子郵件和簡訊_

* SMS外部帳戶設定畫面( **[!UICONTROL Administration > Channels > SMS > SMS accounts]**)已改良。 已在區段中新增數個參**[!UICONTROL SMSC specifics]** 數，以支援「文字」欄位中的錯誤碼。

_推播通知_

* 修正根據(mobileApp)範本編輯推播通知的對象時，無法顯示預先定義篩選 **[!UICONTROL Send via push notification]**器的問題。
* 行動應用程式設定畫面( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]**)現在會顯示訊息，指出iOS或Android平台已成功建立。

_登錄頁面_

* 修正提交著陸頁面表單時無法傳送確認電子郵件的問題。

_對象與查詢_

* 修正在查詢編輯器中選取描述檔時發生的數個問題。

_交易式訊息_

* 修正無法取消發佈交易範本的錯誤。
* 修正導致觸發事件顯示在事件清單中的問題。

_整合_

* 修正在更新對象後，無法在傳送中使用共用對象的問題。
* 修正著陸頁面無法使 **[!UICONTROL Image shared from Adobe Marketing Cloud]**用共用資產（選項）的問題。
* 已修正編輯從Adobe Audience manager匯入的共用觀眾時發生的問題。

## 發行版本16.9 - 2016年9月 {#release-16-9---september-2016}

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
   <td> 重新行銷觸發器<br /> </td> 
   <td> 核心服務觸發程式與Adobe Campaign的整合可讓您傳送個人化電子郵件給客戶，以回應Adobe Analytics在您網站上追蹤的特定行為（15分鐘內）。 <span class="uicontrol"></span><br /> 在Adobe Marketing cloud中，您定義不同的觸發器，即您要監控的客戶行為，例如所有放棄購物車或表單的客戶、從購物車移除產品的客戶，或甚至作業過期的客戶。 建立觸發器時，您會定義觸發器的條件，以及在事件（上傳）中傳送至Adobe Campaign的資料。 <br /> 在Adobe Campaign中，您選取先前建立的觸發器，您會以資料圖資料豐富事件資料，並定義連結至該觸發器的交易訊息範本。 例如，當客戶放棄購物車時，會將事件傳送至Adobe Campaign，然後Adobe Campaign會透過15分鐘內傳送給客戶的再行銷電子郵件來運用此事件。<br /> 如需詳細資訊，請參閱詳 <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事務性消息：暫停／取消發佈<br /> </td> 
   <td> 您現在可以在更新交易範本內容時暫停其發佈。 不再發送相應的消息，但它們儲存在資料庫中。 繼續時，將處理已排隊的消息，並在消息未過期時發送這些消息。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication">細檔案</a>。<br /> 您現在也可以解除發佈事件和交易範本。 對應的消息不再發送，也不儲存在資料庫中。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 多品牌<br /> </td> 
   <td> 擁有多個品牌的客戶現在可以在同一個實例中管理它們。 品牌是由您Adobe Campaign實例的管理員管理的功能，可讓您在Adobe Campaign中集中設定與品牌相關的所有參數。 這包括標誌等更多技術參數，例如追蹤URL、Web Analytics、伺服器URL、網域名稱等。<br /> 如需詳細資訊，請參閱詳 <a href="../../administration/using/branding.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 互動式電子郵件設計預覽<br /> </td> 
   <td> 這項功能可讓您測試不同裝置類型的電子郵件回應速度。 在電子郵件預覽中，已新增格線，以在各種螢幕大小上測試您的電子郵件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播通知<br /> </td> 
   <td> 已新增新通道，可讓行銷人員在iOS和Android行動裝置上傳送個人化和分段的推播通知。 訊息可透過單一傳送或使用工作流程活動來傳送。 未來版本將提供與交易式訊息的相容性。 此通道運用Mobile核心服務的SDK(可在 <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">這裡</a>)。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/about-push-notifications.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 此版本在介面清單中提供新的篩選和搜尋功能。 這項新功能可用於記錄檔（傳送、追蹤）、服務（訂閱、訂閱歷史記錄）、觀眾和工作流程轉場。
* 修正客戶個人檔案中觸點數目的數個顯示問題。
* 已修正數個類型學問題。

_電子郵件和簡訊_

* 修正允許編輯錯誤校樣的錯誤。 它們現在是唯讀的。
* 修正當SMS過長或有編碼問題時，會將收件者列入黑名單的問題。

_自訂資源_

* 修正使用自訂資源的進階篩選時，無法顯示所有結果的錯誤。

_交易式訊息_

* 現在會自動將前置詞新增至新事件定義的識別碼。
* 表示介面中事務性消息的表徵圖已更改。

_整合_

* 修正透過「來自Adobe Target的動態影像」選項插入高解析度影像時 **所發生的顯示錯誤** 。
* 修正即使未在AMC資料來源中設定目標ID，仍能儲存共用對象的錯誤。

## 發行版本16.7 - 2016年7月 {#release-16-7---july-2016}

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
   <td> 豐富的交易訊息<br /> </td> 
   <td> 您現在可以將交易範本與Adobe Campaign資料庫連結，以復原可讓您豐富交易訊息內容的資訊。<br /> 如需詳細資訊，請參閱詳 <a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 影像的動態URL<br /> </td> 
   <td> 這項新功能可讓您插入內容區塊和動態文字，以便追蹤和個人化，以個人化影像來源。<br /> 然後，除其他外，透過在影像URL中輸入參數，就可以從AEM Asset(S7)動態媒體的功能獲利。 例如，您可以傳送包含個人化影像的電子郵件，指出「您好，亞歷山大，取得有關巴黎即將舉辦之活動的最新消息！」 或「您好，Frank，取得有關紐約近期活動的最新消息！」<br /> 如需詳細資訊，請參閱詳 <a href="../../designing/using/personalization.md#personalizing-urls">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 與People Core service整合<br /> </td> 
   <td> Adobe Campaign與People Core Service <strong></strong> (Profiles &amp; Audiences)的整合現在涵蓋Adobe Marketing cloud宣告的ID。<br /><strong> 這表示您可以匯入區段並匯出由訪客ID或 </strong>Declared<strong>ID組成 </strong>的<br />觀眾。如需詳細資訊，請參閱詳 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送記錄檔<br /> </td> 
   <td> MTA記錄檔（傳送伺服器）現在會顯示每則訊息的完整記錄，尤其是所有傳送嘗試以及相關的錯誤狀態，這對應用程式的效能沒有影響。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 修正可能導致顯示不相關欄位，而非需要填寫欄位的錯誤。 在編輯查詢中的條件時，比較運算子被多次修改後，就會發生這種情況。
* 修正為日期欄位定 **[!UICONTROL The last X days/months/quarters/years]**義相對篩選條件時選項的行為。 計算的時段現在是相對於伺服器日期和時間的滑動時段，而非以日曆為基礎。

_工作流程_

* 修正在畫面中傳回錯誤值清單，以在活動屬性中選取定位維度的錯誤 **[!UICONTROL Query]**。
* 修正在活動中新增平均或計數 **匯總至收集元素時，會強制選取「存在」運算子的****[!UICONTROL Query]**錯誤。

_內容編輯_

* 已修正匯入HTML內容時可能導致顯示問題（自適應設計）的錯誤：當內容在匯入後第一次開啟時，不會再重寫樣式屬性。
* 修正在動態內容變體上新增條件時，造成的非封鎖錯誤。
* 修正在著陸頁面內容中新增核取方塊所造成的錯誤。 複選框不可用。
* 修正當刪除區塊中的文字時，如果游標放在相關區塊的開頭，可能會發生的錯誤。

_交易式訊息_

* 整合網站時，您現在可以為任何指定事件定義到期日。 傳送此日期後，便無法再傳送與事件對應的訊息。

## 發行版本16.6 - 2016年6月 {#release-16-6---june-2016}

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
   <td> 設定檔與服務API<br /> </td> 
   <td> Adobe Campaign <span class="uicontrol">Profiles and Services</span> API可在 <a href="https://www.adobe.io/products/campaign">adobe.io Portal中取得</a> 。 這可讓Adobe Campaign設定檔更新、新增和刪除，並透過REST呼叫訂閱或取消訂閱服務。<br /> 如需詳細資訊，請參 <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">閱API的詳細說明</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 現在行動裝置上已停用工具提示，以確保螢幕上顯示的資訊易於閱讀。
* 修正使用者無法捲動iPad畫面上特定區域內容的錯誤。
* 修正在Internet Explorer 11中編輯內容時發生的數個相容性錯誤。
* 修正當資料匯入首次失敗時，無法存取詳細記錄檔的錯誤。
* 修正可能無法儲存範圍篩選器的錯誤。
* 修正設定清單顯示方式時，資源元素無法顯示的錯誤。
* 修正查詢編輯器檔案總管中的錯誤。 搜尋欄位傳回的結果會保留在搜尋歷史記錄中，並持續顯示在每次新搜尋時。

_電子郵件和簡訊_

* 修正無法在傳送記錄中復原連結至彈回的資訊的錯誤。
* 修正無法存取交易訊息動態內容區塊中內容的錯誤。
* 修正無法在電子郵件內容的動態文字上定義URL連結的錯誤。
* 修正傳送建立精靈頂端列的顯示。
* 傳送的主要金鑰無法再當做個人化欄位使用。

_工作流程_

* 工作流程中兩個活動之間的轉換現在會顯示從一個活動計算並傳送至另一個活動的元素計數。
* 現在，當活動中新增其他資料時，不相容的欄位會隱 **[!UICONTROL Query]**藏。
* 新增其他資料時顯示的匯整定義視窗已改進為僅提供與使用中資料相容的選件選項(例如：計算平均值只能用於數值資料)。
* 現在，只有具有管理權限的使用者才能執行立即可用的技術工作流程。

_登錄頁面_

* 修正著陸頁面屬性中可能截斷32位元AES編碼索引鍵的錯誤。
* 修正在定義可見性條件或新增動態內容至著陸頁面時，查詢編輯器無法正確顯示的錯誤。

_自訂資源_

* 現 **[!UICONTROL Switch to parameters]**在在定義與描述檔服務訂閱相關的篩選時，會隱藏該選項。
* 修正從自訂資源設定0-1類型連結時可能發生的錯誤。
* 修正在自訂資源中新增「日期與時間類型」欄位時，可能無法編輯已定義「常數 **」預設值的****** 錯誤（若相關）。

## 發行版本16.5 - 2016年5月 {#release-16-5---may-2016}

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
   <td> 預先定義的篩選<br /> </td> 
   <td> 管理員現在可以建立進階篩選器，以預先設定的規則形式顯示在查詢編輯器中。 例如，選取這些篩選器可讓使用者在定義觀眾時，更輕鬆地在簡化的介面中開發複雜的設定。<br /> 如需詳細資訊，請參閱詳 <a href="../../developing/using/configuring-filter-definition.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：訂閱服務<br /> </td> 
   <td> 新的「 <span class="uicontrol">訂閱服務</span> 」活動可讓您透過單一動作，將數個描述檔訂閱至服務或取消訂閱服務。<br /> 執行定位或匯入含識別資料的檔案後，即可使用此活動。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/subscription-services.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：資料濃縮<br /> </td> 
   <td> 「 <span class="uicontrol">Additional data</span> 」(其他資料 <span class="uicontrol">)標籤現在可用於</span> 「查詢類型」活動。 此功能可讓您豐富查詢所定位的資料，並將此資料傳輸至下列工作流程活動，以供其利用。<br /> 新增其他資料後，您可以根據已定義的其他資料建立條件，將額外的篩選層級套用至初始目標資料。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/query.md#enriching-data">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 情境式說明<br /> </td> 
   <td> 現在，不同Adobe Campaign螢幕上都可使用內容相關的說明功能。 這表示，只要按一下，您就可以直接存取您目前使用之功能的相關檔案。 若要顯示內容相關說明，請按一下「?」 表徵圖，如下例所示。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 各種介面符合Marketing cloud標準的新功能。
* 不同下拉式清單類型的標準化。

_電子郵件和簡訊_

* 修正在指定錯誤位址遮色片時，無法傳送電子郵件的錯誤。
* 現在支援TLS通訊協定來傳送電子郵件。 MX管理中的新欄可讓您定義每個網域所需的TLS行為。
* SMS介面已改善。

_工作流程_

* 各種工作流程介面新功能。
* 修正顯示「快速」動作時發生的錯誤。
* 修正使用包含1-N連結的類型活動時，可 **[!UICONTROL Segmentation]**能導致工作流程失敗的錯誤。
* 修正無法在混合裝置上開啟工作流程轉場的錯誤。
* 修正首次啟動工作流程時無法顯示暫停按鈕的錯誤。

_內容編輯器_

* 內容編輯器現在可讓您個人化電子郵件或登陸頁面中包含的任何URL。 請參閱詳細 [檔案](../../designing/using/personalization.md#personalizing-urls)。
* 修正當影像新增至傳送的建立精靈中，且其內容在之後修改時，可能會遺失的錯誤。

_自訂資源_

* 修正在自訂資源的設定畫面中新增個人化1-N類型連結時發生的錯誤。
* 已改善準備和發佈自訂資源時的進度列顯示。
* 修正顯示自訂資源連結清單時發生的錯誤。

_交易式訊息_

* 優化了介面友好性以及事務消息引擎的效能和魯棒性。
* 現在可以暫時暫停事務性消息模板的發佈。 如需詳細資訊，請參閱詳細 [檔案](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication)。
* 修正可能導致具有不相容定位維度的內容區塊新增至交易訊息範本的錯誤。
* 修正API預覽無法顯示在事件設定畫面中的錯誤。

_對象與查詢_

* 有關在查詢編輯器中使用日期的各種修補程式。 請參閱詳細 [檔案](../../automating/using/editing-queries.md#creating-queries)。

_管理_

* 修正「標準使用者」安全性群組名稱的錯誤，此錯誤會讓使用者無法登入。

## 發行版本16.3 - 2016年3月 {#release-16-3---march-2016}

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
   <td> 介面與導覽<br /> </td> 
   <td> Adobe Campaign介面已經過改良，讓導覽和作業變得簡單且直覺。<br /> 您現在可從應用程式的頂端列導覽。 您可選擇 <strong>Adobe Campaign標誌來存取進階功能表</strong> 。<br /> 如需詳細資訊，請參閱詳 <a href="../../start/using/interface-description.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：儲存觀眾<br /> </td> 
   <td> 「儲存觀眾 <span class="uicontrol">」活動現在提供新選</span> 項「建立然後更新觀眾 <span class="uicontrol"></span> 」。 此選項可讓您手動輸入對象標籤。 如果輸入的標籤對應現有對象，則會更新它。 如果對象不存在，則會建立它。<br /> 此外，每次執行工作流程時（再次），觀眾都會更新。<br /> 您隨時都可以選取對象更新模式：在每次執行時，以新資料填寫觀眾，或取代整個觀眾資料。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/save-audience.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：區段<br /> </td> 
   <td> 「 <span class="uicontrol">分段</span> 」活動現在可讓使用者分段暫存資源的資料。 例如：匯入檔案的資料。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/segmentation.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 修正排序清單時發生的顯示錯誤：只能針對某些類型的資料反轉指示列排序順序的箭頭。
* 修正在查詢中新增規則時，限制下拉式選單中顯示元素數的錯誤。

_電子郵件和簡訊_

* 修正可能無法存取電子郵件轉譯報表的錯誤。
* 如果未提供傳送者位址，訊息的準備傳送階段現在會傳回錯誤。

_工作流程_

* 某些檔案格式選項是可見的，但在擷取CSV格式檔案時並未考慮。 這些選項現在不再顯示。
* 修正選取文字檔 **[!UICONTROL Delete the source files after transfer]**案傳輸選項時所**[!UICONTROL SFTP]** 造成的錯誤。
* 修正重新整理頁面後，無法顯示計數 **[!UICONTROL Query]**器和資料預覽的錯誤。
* 修正在工作流程中開啟某些轉場時，尤其是傳送活動或定位和篩選維度不同之查詢後，造成的錯誤。
* 修正當新增工作流程後未儲存工作流程時，個人化欄位無法插入至工作流程傳送活動的錯誤。
* 修正無法顯示電子郵件傳送活動之傳出轉場定位維度的錯誤。

_登錄頁面_

* 修正個人化欄位無法在著陸頁面的可本地化內容區塊中正常運作的錯誤。

_自訂資源_

* 修正如果已檢查資源畫面定義的選項，以及在中選取了數個欄位，則無法對自訂資源執行搜尋的錯誤 **[!UICONTROL Add search fields]****[!UICONTROL Filter zone composition]** 。

## 發行版本16.2 - 2016年2月 {#release-16-2---february-2016}

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
   <td> 電子郵件的A/B測試<br /> </td> 
   <td> 您現在可以對電子郵件的內容、主旨或寄件者名稱進行A/B測試。 這項新功能最多可測試元素的3種變體。<br /> 從A/B測試的其中一個新範本建立電子郵件時，建立精靈中的新步驟可讓您定義測試的參數。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/designing-an-a-b-test-email.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 品牌管理<br /> </td> 
   <td> 您現在可以定義一或多個品牌，以集中輸入影響品牌識別的參數。 Adobe Campaign可讓您建立這些品牌，並將其連結至傳送或著陸頁面範本。<br /> 如需詳細資訊，請參閱詳 <a href="../../administration/using/branding.md#assigning-a-brand-to-an-email">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：增量查詢<br /> </td> 
   <td> 新的工作流活動 <span class="uicontrol">Incremental query</span> ，允許您執行一個查詢，每次執行時，該查詢只針對新結果。 先前執行的結果會自動排除。 連結到 <span class="uicontrol">Scheduler</span> 活動，可以定義增量查詢的執 <span class="uicontrol">行頻率</span> 。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/incremental-query.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易式訊息<br /> </td> 
   <td> 事務消息介面的用戶友好性得到了改善。 所有連結至交易訊息的業務流程管理目前都集中在「行銷計畫 <span class="uicontrol">&gt;交易</span> 訊息」功能表中 <span class="uicontrol"></span> 。 事件設定也已改善。 事件現在可獨立於自訂資源進行管理。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/about-transactional-messaging.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 修正報表、清單和查詢中的數個顯示錯誤。
* 已修正行動裝置上的數個相容性和顯示錯誤。

_電子郵件和簡訊_

* 修正建立訊息（電子郵件或SMS）時，用來插入個人化欄位的按鈕無法顯示的錯誤。
* 已修正可能無法正確傳送透過Mblox傳送的SMS訊息的錯誤。

_對象與查詢_

* 修正在修改篩選維度後，在查詢中新增其他條件時可能造成的計數錯誤。
* 修正預覽查詢結果時，可能導致不正確分頁的錯誤。

_內容編輯_

* 修正使用個人化枚舉時，可能無法正確考慮動態內容設定的錯誤。

_工作流程_

* 修正當活動標籤中有空行時，工作流程中的任何動作都無法執行的 **[!UICONTROL Fields to update]**錯誤**[!UICONTROL Update data]** 。
* 修正無法匯入包含地理／組織單位資訊的資料的錯誤。
* 修正新增規則類型 **[!UICONTROL Change axis]**所造成的**[!UICONTROL Exclusion]** 錯誤。
* 修正當控制活動的對外轉換時，可能會建立不想要的額外區段的錯 **[!UICONTROL Segmentation]**誤。
* 修正在工作流程範本中載入檔案所造成的錯誤。
* 修正可能無法將空格用作活動中欄分隔符的 **[!UICONTROL Load file]**錯誤。

_自訂資源_

* 修正匯入套件後，如果匯出時已發佈自訂資源，自訂資源狀態無法重新草稿的錯誤。

_套件_

* 修正無法匯出包含工作流程的套件的錯誤。
* 修正可能無法選取相同資源之數個元素的錯誤。

## 發行版本16.1 - 2016年1月 {#release-16-1---january-2016}

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
   <td> 報表<br /> </td> 
   <td> 已新增下列電子郵件特定報表：投 <span class="uicontrol">訴</span> 、開 <span class="uicontrol">啟</span> 、取消 <span class="uicontrol">訂閱</span> 。<br /> 已改善下列報表：傳送 <span class="uicontrol">摘要、</span> 彈回數摘要 <span class="uicontrol">、</span> 傳送吞吐量 <span class="uicontrol">、追蹤指</span> 標 <span class="uicontrol"></span> 。<br /> 如需詳細資訊，請參閱詳 <a href="../../reporting/using/defining-the-report-period.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 查詢編輯<br /> </td> 
   <td> 查詢編輯器已經過改進，現在可讓您掃描 <strong>1-N類型的連結</strong> 。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/editing-queries.md#creating-queries">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 內容個人化<br /> </td> 
   <td> 至於電子郵件或著陸頁面編輯，內容區塊顯示條件的輸入介面已改善。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：導入時的列定義<br /> </td> 
   <td> 現 <span class="uicontrol">在，「載入檔案</span> 」活動可讓您詳細設定匯入檔案的欄：預期的資料類型、日期和時間格式、在空值或錯誤時套用的處理，以及值重新對應。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/load-file.md#column-format">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> SMS編碼的對應<br /> </td> 
   <td> 現在，可以為未使用標準編碼的提供者定義個人化SMS訊息編碼的映射。 管理員可以進行個性化映射的配置，並定義應考慮這些映射的順序。<br /> 如需詳細資訊，請參閱詳 <a href="../../administration/using/configuring-sms-channel.md#smsc-specifics">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 已改善混合／觸控螢幕裝置上與Internet explorer和Chrome的相容性。
* 修正當所指示的電子郵件位址包含語法錯誤時，可能導致新使用者／描述檔／測試描述檔所輸入的所有資料遺失的錯誤。

_電子郵件和簡訊_

* 已修正無法在電子郵件預覽畫面中產生內容縮圖的錯誤。
* 修正無法在訊息預覽畫面中顯示訊息（電子郵件或SMS）原始內容的錯誤。

_對象與查詢_

* 修正無法在「服務」資 **源中建立** 「查詢」類型對象的 **錯誤** 。
* 修正在進階模式中編輯查詢條件時，功能清單無法正確顯示的錯誤。
* 修正如果查詢類型對象包含 **以系列為基礎的准則** ，則無法建立該對象的錯誤。
* 修正無法建立包含傳送KPI篩選器的查詢的錯誤。
* 修正可能無法預覽從工作流程建立之對象內容的錯誤。

_自訂資源_

* 修正當自訂資源包含動態預設值的欄位時，可能導致伺服器當機的錯誤。
* 修正在定義自訂資源畫面時，移動區段中的元素， **[!UICONTROL Detail screen configuration]**然後刪除區段中的元素所造成的錯誤。
* 修正當為未包含0的整數清單定義 **預設值** ，且其可能值範圍中未包 **含** 0時發生的錯誤。
* 修正重新初始化後，自訂資源的詳細資料畫面設定無法新增元素的錯誤。

_工作流程_

* 修正可能導致顯示工作流程中所有活動的記錄，而非只顯示所選活動記錄的錯誤。
* 修正活動中的錯 **[!UICONTROL Scheduler]**誤。 未**[!UICONTROL Day of the month]** 正確考慮此選項，並由取代 **[!UICONTROL Week day]**。
* 修正當過期模式設 **[!UICONTROL Scheduler]**為時，活動無法正常運作的錯誤**[!UICONTROL After a certain number of iterations]** 。
* 修正使用活動匯出資料時發生的 **[!UICONTROL Extract file]**錯誤。 導出檔案中顯示的行數低於導出元素數。
* 修正可能無法選取活動中 **[!UICONTROL Load file]**檔案的錯誤。
* 修正無法刪除活動中要更新的欄 **[!UICONTROL Update data]**位的錯誤。
* 修正在開啟工作流程執行記錄後，無法儲存對工作流程所做的修改的錯誤。
* 修正如果將活動設 **[!UICONTROL Load file]**定為從其傳入轉換使用檔案，且此檔案已使用活動載入，則會執行兩次的錯**[!UICONTROL Transfer file]** 誤。
* 修正「排除」活動無法正確處理某些臨時實體的 **錯誤** 。
* 修正當定位維度和在活 **[!UICONTROL Query]**動中設定的篩選維度不同時，可能無法正確執行活動的錯誤。
* 修正新增至活動的傳出轉場自動命名錯誤，此 **[!UICONTROL Fork]**錯誤可能會阻止儲存工作流程。

_內容編輯_

* 修正編輯內容時，可能導致圖示或搜尋列顯示不理想的錯誤。

_登錄頁面_

* 修正無法使用套件匯入來匯入著陸頁面的錯誤。

_交易式訊息_

* 現在，可以在「消息中心推播代理」運算子的安全參數中指定可信IP地址。
* 修正可能無法建立新類型事件的錯誤。

## 發行版本15.11 - 2015年11月 {#release-15-11---november-2015}

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
   <td> 簡訊頻道<br /> </td> 
   <td> 您現在可以使用Adobe Campaign傳送SMS訊息。<br /> 就像電子郵件一樣，您也可以從促銷活動和行銷活動清單建立新的SMS傳送。 您也可以從工作流程建立單一傳送和循環的SMS訊息。<br /> 這些SMS傳送是以範本為基礎，您可從傳送範本清單中設定範本。 預設範本可供使用。<br /> 這些SMS傳送使用SMPP 3.4通訊協定，大部分的SMS路由器都使用此通訊協定。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/about-sms-messages.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索轉變<br /> </td> 
   <td> 您現在可以在工作流程的最後一次轉換中探索資料及其結構。 這可讓您檢查每個活動所套用的程式是否符合您的需求。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程中的檔案前後處理<br /> </td> 
   <td> 現在，當透過「載入檔案」和「擷取檔案」活動匯入或匯出資料檔案時，您可以對 <span class="uicontrol">資料檔案</span><span class="uicontrol">執行其他處理</span> 。<br /> 依預設，您可以在這些活動中解壓縮GZIP格式檔案。<br /> 如需詳細資訊，請參閱有關「載入檔案」和「擷 <a href="../../automating/using/load-file.md">取檔案</a> 」活 <a href="../../automating/using/extract-file.md">動的檔案</a> 。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞能力報告<br /> </td> 
   <td> 現在提供電子郵件轉譯報告。 此報告允許您根據用於讀取消息的支援和消息服務來查看消息的不同渲染。<br /> 報告摘要還顯示接收的消息、垃圾郵件、未接收的消息和等待接收的消息的數量。<br /> 如需詳細資訊，請參閱詳 <a href="../../sending/using/email-rendering.md#email-rendering-report-description">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 套件管理<br /> </td> 
   <td> 現在可以匯入和匯出封裝中的影像。<br /> </td> 
  </tr> 
  <tr> 
   <td> 快速動作<br /> </td> 
   <td> 將滑鼠暫留在清單或工作流程中選取元素或之後，會顯示某些動作。 現在，為方便存取，有些動作會顯示為相關元素的圖示。 這些快速動作可用來複製元素、刪除元素、顯示詳細資料等。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 修正可能無法從管理員帳戶存取執行個體一般參數的錯誤。
* **現在** ，自訂資源中已正確考慮浮動資料。
* 修正已執行簡化匯入清單中的顯示錯誤，此錯誤是在修改對應範本的狀態時造成的。

_登錄頁面_

* 已修正著陸頁面範本的某些元素，這些元素在英文例項上可能會以法文錯誤顯示。

_觀眾_

* 修正從Adobe Marketing cloud匯入的觀眾無法顯示在觀眾清單中的錯誤。
* 修正定義查詢時，可能會強制區分大小寫的錯誤。
* 修正在定義查詢時無法篩選對象的錯誤。
* 已修正可能無法在對象中取消動作的錯誤。

_工作流程_

* 修正無法手動設定活動中要更新的欄 **[!UICONTROL Update data]**位的錯誤。
* 修正如果在圖中放置活 **[!UICONTROL Query]**動後未儲存工作流程，在開啟時可能導致活動無限載入的錯誤。
* 修正在計算或預覽從工作流程中選取的對象時，伺服器會停止的 **[!UICONTROL Query]**錯誤。
* 修正開啟工作流程中的活動時可能出現的非嚴重錯誤。
* 修正無法將活動設 **[!UICONTROL Scheduler]**定為每天執行數次工作流程的錯誤。
* 修正無法執行查詢的欄位在某些工作流程活動中出現的錯誤。
* 修正可能導致使用者無法在出站轉移的傳送上，找 **[!UICONTROL Query]**到新增的KPI的錯誤。
* 修正將檔案匯入工作流程後，無法建立檔案對象的錯誤。
* 修正當使用資源的 **location/address3** field時，設定檔無法更新資料的錯誤。
* 修正導致異構活動集合無法在工作流程中複製的錯誤。
* 修正無法顯示SQL的錯誤，從而允許在工作流程中針對重複傳送診斷錯誤。

_內容編輯器_

* 已修正導致無法在著陸頁面或電子郵件的原始碼中搜尋的錯誤。

_套件_

* 已修正可能無法將某些類型的元素匯出至封裝（尤其是著陸頁面、工作流程）的各種錯誤。
* 修正如果標籤已修改，則會顯示前一個套件匯入標籤的錯誤。
* 修正可能導致可匯出資源清單中顯示不相容資源的錯誤。

## 發行版本15.10 - 2015年10月 {#release-15-10---october-2015-}

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
   <td> 工作流程：重複資料消除活動<br /> </td> 
   <td> 工作流程中現在提供專門用於消除重複資料的新活動。 此活動可讓您根據您選擇的准則，篩選目標中的任何復本。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/deduplication.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：改良的圖表<br /> </td> 
   <td> 從工作流程工作區，您現在可以使用數個鍵盤快速鍵來選取、開啟和刪除活動。<br /> 活動對齊方式也已改善，讓工作流程以視覺化方式更有條理。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/workflow-interface.md#workspace">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：擷取檔案活動<br /> </td> 
   <td> 現在，使用「擷取檔案」活動匯出的檔案標籤會自動新增匯出的日期 <span class="uicontrol">和時間</span> 。 如此產生的檔案就是唯一的。<br /> </td> 
  </tr> 
  <tr> 
   <td> 簡化資料匯入<br /> </td> 
   <td> 從中執行簡化導入的模板的名稱現在預設顯示在導入清單和每個導入的詳細資訊中。<br /> </td> 
  </tr> 
  <tr> 
   <td> 自訂資源<br /> </td> 
   <td> 改善並擴展管理和定義自訂資源連結的可能性。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_電子郵件_

* 修正無法從鏡像頁面正確運作服務取消訂閱連結的錯誤。
* 修正電子郵件傳送標籤無法正確顯示在電子郵件編輯頁面上的錯誤。
* 修正無法在複製的傳送范 **[!UICONTROL Routing]**本中選取外部帳戶的錯誤。

_觀眾_

* 修正當查詢中使用1-N連結時，造成對象計數期間發生的錯誤。
* 修正無法在電子郵件傳送的目標對象中選取描述檔的錯誤。

_工作流程_

* 修正在工作流程中設定電子郵件傳送時，可能導致顯示問題的錯誤。
* 修正可能導致活動無法正 **[!UICONTROL Load file]**常運作的錯誤。 然後會出現空白錯誤訊息。
* 修正可能導致活動無法正 **[!UICONTROL Transfer file]**常運作的錯誤。 存取權未一律正確納入考量。
* 修正如果工作流程包含 **[!UICONTROL Recurring email]**。
* 修正在工作流程中無法建立電子郵件傳送，或無法將主旨和定義內容納入考量的錯誤。
* 修正在設定簡化匯入範本的工作流程時，可能無法在活 **[!UICONTROL Update data]**動中選取協調金鑰的錯誤。
* 修正刪除活動後無法儲存工作流程的錯誤。

_平台_

* 修正當自訂資源包含元素資源類型的連結時，無法建立新元素的錯誤。
* 修正某些記錄寫入時，可能導致15分鐘延遲的錯誤。
* 修正當依或欄排序時，無法顯示行銷活動清單的 **[!UICONTROL Date]**錯**[!UICONTROL Indicators]** 誤。

_登錄頁面_

* 修正選取測試描述檔以預覽著陸頁面時發生的錯誤。

_交易式訊息_

* 修正刪除測試設定檔上的事件後，可能導致應用程式當機的錯誤。

_報表_

* 修正可能導致報表和傳送錯誤資料的 **[!UICONTROL deliveryThroughputReport]**錯誤**[!UICONTROL deliveryTrackingReport]** 。

_內容編輯器_

* 修正處理動態內容區塊時發生的HTML標籤管理錯誤。

## 發行版本15.8 - 2015年8月 {#release-15-8---august-2015}

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
   <td> 簡化資料匯入<br /> </td> 
   <td> 您現在可以以簡化的方式匯入資料。<br /> 使用者只需選取管理員預先定義的範本，然後上傳包含要匯入之資料的檔案。 對於用戶，模板中定義的工作流將透明地執行，用戶可以訪問導入結果的詳細資訊以及任何錯誤的日誌。<br /> 這些檔案的資料可以插入資料庫或做為直接建立觀眾的方式。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/about-data-import-and-export.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 建立方案和促銷活動<br /> </td> 
   <td> 現在，已設定促銷活動和程式，以便自動將其建立的日期當做開始日期。<br /> 結束日期是根據開始日期設定，例如：<br /> 
    <ul> 
     <li> 適用於方案的D+186 </li> 
     <li> D+61促銷活動 </li> 
    </ul> 如需詳細資訊，請參閱詳 <a href="../../start/using/programs-and-campaigns.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件<br /> </td> 
   <td> 追蹤的URL清單現在為唯讀。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易式訊息<br /> </td> 
   <td> 您現在可以管理個人化交易訊息，以處理建立帳戶後發生的事件，例如密碼變更或確認。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/about-transactional-messaging.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 自訂資源<br /> </td> 
   <td> 新增多項功能，例如：擴充測試設定檔、狀態管理和刪除資源。<br /> 如需詳細資訊，請參閱詳 <a href="../../developing/using/resource-statuses.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_顯示_

* 修正Safari中查詢編輯器中並列兩個欄位的錯誤。

_內容編輯器_

* 修正無法在電子郵件主旨中使用字元「&lt;」、「&amp;」和「>」的錯誤。

_電子郵件_

* 修正使用者無法在動態文字後新增文字的錯誤。

_清單_

* 修正工作流程執行記錄檔 **中的** 「訊息」欄無法正確匯出的錯誤。

_設定檔與閱聽眾_

* 修正導致重複確認元素複製或刪除時間的錯誤。 **僅限使用Internet Explorer 11的混合裝置**。

_工作流程_

* 修正可能無法從工作流程傳送電子郵件的錯誤。
* 修正當未在活動中指定拒絕檔案名稱時，工作流無法執行的錯誤 **[!UICONTROL Load file]**問題。
* 修正當活動設為時，工作流程無 **[!UICONTROL Execution frequency]**法執行**[!UICONTROL Schedule]** 的錯誤 **[!UICONTROL Daily]**。

_平台_

* 修正無法在負載平衡環境中產生縮圖的錯誤。

## 發行版本15.7 - 2015年7月 {#release-15-7---july-2015}

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
   <td> 匯出清單<br /> </td> 
   <td> 您現在可以將清單中的內容匯出為CSV格式的檔案。 此函式適用於所有具有清單模式 <strong>的畫面</strong> (例如：設定檔清單)。<br /> 導出的資料是導出時顯示的列中的資料。 因此，您可以編輯清單，以選取要匯出的資料。<br /> 有關使用此功能的詳細資訊，請參閱詳 <a href="../../automating/using/exporting-lists.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 與Adobe Profiles &amp; Audiences整合<br /> </td> 
   <td> 您現在可以在Adobe Campaign和其他Adobe Marketing cloud解決方案之間共用受眾：<br /> 
    <ul> 
     <li> 匯出：當您在工作流程中儲存由描述檔組成的觀眾時，新的「在Adobe Marketing Cloud <span class="uicontrol"></span> 」（在Adobe Marketing Cloud中共用）選項可讓您將描述檔新增至現有觀眾或建立新觀眾。 </li> 
     <li> 匯入：透過從觀眾管 <strong>理畫面建立</strong> 「清單」類型的觀眾，新的選項可讓您將其識別為 <span class="uicontrol">Adobe Marketing Cloud Audience</span> 。 然後，您可以選取現有的共用對象，將其匯入Adobe Campaign。 </li> 
    </ul> 有關配置和使用此功能的詳細資訊，請參閱詳 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 數位內容編輯器——動態內容<br /> </td> 
   <td> 動態內容介面已改善。 箭頭現在可讓您直接在電子郵件內文中，導覽不同的動態內容。<br /> 有關使用此功能的詳細資訊，請參閱詳 <a href="../../designing/using/personalization.md#defining-dynamic-content-in-an-email">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 數位內容編輯器——動態文字<br /> </td> 
   <td> 從電子郵件的內容編輯器，您現在可以定義動態文字：<br /> 
    <ul> 
     <li> 在電子郵件主題中， </li> 
     <li> 在HTML模式中， </li> 
     <li> 或在文字模式中。 </li> 
    </ul> 有關使用此功能的詳細資訊，請參閱詳 <a href="../../channels/using/defining-dynamic-text.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 方案與促銷活動——報表<br /> </td> 
   <td> 報表的介面和圖形已改善。<br /> 有關使用此功能的詳細資訊，請參閱詳 <a href="../../reporting/using/defining-the-report-period.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_安裝_

* Adobe Campaign例項名稱現在限制為32個字元。

_工作流程_

* 修正在工作流程中編輯查詢時，無法定位「傳送」資源的錯誤。
* 修正編輯工作流程中的查詢時，無法處理某些連結資源的錯誤。
* 修正當工作流程已執行時， **Recurring delivery** activity無法修改的錯誤。

_電子郵件_

* 修正當透過運算式編輯器新增動態內容時，在傳送電子郵件之前無法檢查JavaScript語法錯誤的錯誤。

_登錄頁面_

* 修正無法從平板電腦編輯著陸頁面的錯誤。

_資產核心服務_

* 從正在編輯的電子郵件或登陸頁面選擇共用資源時，現在會篩選Adobe Campaign的可用資源清單。

## 發行版本15.6 - 2015年6月 {#release-15-6---june-2015}

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
   <td> 工作流程：協調活動<br /> </td> 
   <td> 新的「 <strong>協調</strong> 」活動會將未識別的資料（例如，匯入檔案後）與工作流程中的現有資源連結在一起。<br /> 此活動主要用於資料管理。 它回應兩種不同的使用案例：<br /> 
    <ul> 
     <li> <strong>添加關係</strong>:「關 <strong>系</strong> 」索引標籤可讓您在傳入資料和Adobe Campaign資料庫的數個其他維度之間新增連結。 </li> 
     <li> <strong>資料識別</strong>:「識 <strong>別</strong> 」標籤可讓您將傳入資料與Adobe Campaign資料庫中現有維度的欄建立關聯。 當資料離開活動時，會識別為屬於指定維度。 </li> 
    </ul> 請參閱詳細 <a href="../../automating/using/reconciliation.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：擷取檔案活動<br /> </td> 
   <td> 新的 <strong>Extract file</strong> （擷取檔案）活動可讓您從工作流程中以外部檔案的形式匯出Adobe Campaign資料庫的資料。 <br /> 限制：目前無法將動態名稱用於輸出檔案。<br /> 請參閱詳細 <a href="../../automating/using/extract-file.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：排程器活動<br /> </td> 
   <td> 改進的Widget，可讓您在工作流程中選取「排程器 <strong></strong> 」活動的執行時間。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：傳輸檔案活動<br /> </td> 
   <td> 現在支援SFTP。<br /> </td> 
  </tr> 
  <tr> 
   <td> 自訂資源<br /> </td> 
   <td> 「開 <span class="uicontrol">發</span> 」功能表現在可讓擁有管理員權限的使用者透過建立自己的自訂資源（例如購買或產品表格）來豐富資料範本。 <br /> 您也可以擴充現成可用的資源，以新增欄位至這些資源。<br /> 此外，還可設定新或擴充自訂資源對應之畫面中的導覽。<br /> 請參閱詳細 <a href="../../developing/using/data-model-concepts.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 測試設定檔<br /> </td> 
   <td> 現在 <strong>設定測</strong><strong></strong> 試設定檔清單時，可以選取測試設定檔的中間名稱和標題。<br /> </td> 
  </tr> 
  <tr> 
   <td> 內容編輯器：動態內容<br /> </td> 
   <td> 您可以定義不同的內容，這些內容將根據透過運算式編輯器定義的條件動態顯示給使用者。<br /> 請參閱詳細 <a href="../../designing/using/personalization.md#defining-dynamic-content-in-an-email">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件<br /> </td> 
   <td> 「測 <strong>試設定檔</strong> 」欄現在可在電子郵件的傳送記錄檔中使用。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_清單_

* 從清單中刪除元素現在會自動重新整理清單。
* 修正無法從僅包含一欄的清單中選取元素的錯誤。
* 修正重新整理頁面後，造成對清單顯示所套用的變更遺失的錯誤。
* 現在，測試設定檔的中間名稱和標題都可以顯示在測試設定檔清單中。
* 修正在Mozilla Firefox清單中選取核取方塊時發生的錯誤。

_觀眾_

* 修正無法在觀眾介 **[!UICONTROL Add]**面中使用按鈕的錯誤。

_電子郵件_

* 修正編輯電子郵件時，預覽按鈕無法連續使用兩次的JavaScript錯誤。
* 修正使用Internet Explorer 11 **[!UICONTROL Edit properties]**的Microsoft Surface Pro3**[!UICONTROL Show proofs]** 平板電腦無法使用和按鈕的錯誤。
* 修正可能無法顯示電子郵件傳送記錄檔的錯誤。

_登錄頁面_

* 修正在登陸頁面中編 **** 輯內容時，無法使用品牌標誌內容區塊的錯誤。
* 修正如果為著陸頁面指定有效日期，則無法在行銷活動清單中顯示著陸頁面的錯誤。

_工作流程_

* 修正在設定「區段」活動時，群組模式中的區段無法正常運作的 **錯誤** 。
* 修正在設定「區段」活動後無法選取轉場的 **錯誤** 。
* 修正在設定「區段」活動後，無法刪除轉場 **的錯** 誤。
* 修正「區段」活動中無法計算和預覽人口族群的 **錯誤** 。
* 修正無法有效刪除循環電子郵件的錯誤。
* 修正刪除的「傳輸」檔案活動 **中的資料** ，顯示在新「傳輸」檔案活 **動中的錯誤** 。
* 修正「排除」活動無法正確考慮排除規則的 **錯誤** 。
* 修正在工作流程中刪除電子郵件傳送活動時發生的錯誤。 對應的傳送現在也會從行銷活動清單中移除。

_導覽_

* 您現在可以使用Tab鍵，在同一頁的欄位之間正確導覽。

## 發行版本15.4 - 2015年4月 {#release-15-4---april-2015}

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
   <td> 包導出／包導入<br /> </td> 
   <td> 「部 <strong>署</strong> 」功能表現在可讓擁有管理員權限的使用者，透過匯出和匯入套件，在不同的Adobe Campaign執行個體之間交換資源。<br /> 請參閱詳細 <a href="../../automating/using/managing-packages.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 報表<br /> </td> 
   <td> 現在，所有報表(「熱點 <strong>點按」報表</strong> )都可從程式存取。 這些報告包括：<br /> 
    <ul> 
     <li> 程式傳送吞吐量 </li> 
     <li> 方案跟蹤指標 </li> 
     <li> 依網域劃分的方案 </li> 
     <li> 方案非交付項和彈回數 </li> 
     <li> 程式URL和點按串流 </li> 
    </ul> 這些報表可在指定期間（例如3個月、6個月等）進行篩選。 您也可以篩選促銷活動報表。<br /> 請參閱詳細 <a href="../../reporting/using/about-dynamic-reports.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：電子 <strong>郵件傳送</strong> 活動<br /> </td> 
   <td> 工作 <strong>流程中的</strong> 「電子郵件傳送」活動已改善。 您現在可以從應用程式行銷活動清單中找到電子郵件、循環電子郵件，以及有關循環執行電子郵件的詳細資訊。<br /> 請參閱詳細 <a href="../../automating/using/email-delivery.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：區 <strong>段活動</strong><br /> </td> 
   <td> 「 <strong>區段</strong> 」活動現在可在工作流程中使用。 此活動可讓您建立一或多個區段，並將區段代碼從同一工作流程中上游活動計算的人口中連結到這些區段。 從此活動，區段可在單一轉場或不同多重轉場中處理。 現在有可篩選人口並限制每個區段大小的選項，以最佳化個人化。 例如，您可以隨機選取與特定准則對應的描述檔。<br /> 請參閱詳細 <a href="../../automating/using/segmentation.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 整合：資 <strong>產核心服務</strong><br /> </td> 
   <td> 您現在可以透過電子郵件和登陸頁 <strong>面內容中的Assets Core Service</strong> ，使用共用資源。 您可以直接從Adobe Marketing cloud管理共用資源。<br /> 請參閱詳細 <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 整合： <strong>Adobe Target</strong><br /> </td> 
   <td> 您現在可以將 <strong>Adobe Target動態計算的影像插入</strong> Adobe Campaign電子郵件。 這可讓您根據Adobe Target區段中定義的准則個人化內容，提供數種版本的相同電子郵件。<br /> 請參閱詳細 <a href="../../integrating/using/about-campaign-target-integration.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 數位內容編輯器：塊 <strong>選擇器</strong><br /> </td> 
   <td> 當在HTML內容編輯器中選取區塊時，編輯區域底部會顯示階層連結。 這可讓您輕鬆導覽並選取不同的元素。<br /> 請參閱詳細 <a href="../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style">檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 發行版本15.3 - 2015年3月 {#release-15-3---march-2015}

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
   <td> 報表<br /> </td> 
   <td> 現在，您可以直接從方案或促銷活動存取報表。 「 <strong>傳送摘要</strong> 」報表已新增至方案層級。<br /> 請參閱詳細 <a href="../../reporting/using/delivery-summary.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 更新資料<br /> </td> 
   <td> 在工作流程中，可用的 <strong>Update data</strong> activity有一個新選項，它允許您自動將入站資料欄位與應用程式架構的欄位連結起來。 這有助於更新欄位的選擇程式。<br /> 請參閱詳細 <a href="../../automating/using/update-data.md">檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件傳送<br /> </td> 
   <td> 在工作流程中，現在可以透過 <strong>動作列中的特定按鈕存取「電子郵件傳送</strong> 」活動的進階選項。 只有在選取「電子郵件傳送」活 <strong>動時</strong> ，此按鈕才可用。 主要優點是，它可讓您新增活動的對外轉場，並編輯活動在工作流程中顯示的名稱。<br /> 請參閱詳細 <a href="../../automating/using/email-delivery.md">檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 修正建立傳送時無法顯示收件者的錯誤。
* 修正無法使用基於「已開啟的收件者」條件的對象的錯誤。
* 修正無法刪除空白描述檔的錯誤。
* 修正預覽傳送時發生的錯誤。
* 修正無法複製行銷活動的錯誤。
* 修正刪除促銷活動時發生的錯誤。

