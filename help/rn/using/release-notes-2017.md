---
title: 發行說明 2017 年
description: 本頁列出 2017 年的所有 Adobe Campaign Standard 版本。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '4613'
ht-degree: 5%

---

# 發行說明 2017 年{#release-notes}

是否希望在2017年發行Adobe Campaign Standard?

每個版本都提供新功能和修補程式。 按一下某個版本以查看其內容。

查看最新 [文檔更新](../../rn/using/documentation-updates.md) Adobe Campaign Standard。 如果您要尋找較新的版本，請咨詢 [頁](../../rn/using/release-notes.md)。

## 發行版本 17.10 – 2017 年 10 月 {#release-17-10---october-2017}

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
   <td> 疲勞管理<br /> </td> 
   <td> 疲勞管理允許您建立疲勞規則以管理與輪廓的過度通信。 已多次聯繫的規則很容易構建，但具有非常靈活的功能，例如，在多個渠道（包括事務性消息）中計數消息、僅計數特定交貨或將規則應用於特定配置檔案。<br /> 有關詳細資訊，請參閱 <a href="../../sending/using/fatigue-rules.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 內容建立：從URL導入<br /> </td> 
   <td> 通過從URL導入，您可以快速從網站檢索創意內容，以生成任何傳遞的電子郵件。 此外，您還可以通過讓第三方直接通過URL共用內容來簡化創意流程。 導入的內容可以靈活地用作單個交付的一部分，或在模板級別使用，以確保所有相關活動的品牌一致性，包括A/B或多元測試。 從URL導入會自動轉換和跟蹤所有連結，以通過動態報告監視電子郵件效能。<br /> 有關詳細資訊，請參閱 <a href="../../designing/using/using-existing-content.md">詳細文檔</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 已修復可能阻止正確解壓大檔案的問題。
* 品牌管理的安全性得到提高。 現在，為Adobe技術管理員保留修改品牌名稱和發件人地址。
* 為了提高安全性，用戶生成的內容（影像、鏡像頁、登錄頁等） 不能再由adobe.com域服務。 現在，您必須通過使用品牌來使用您自己的域來處理這些資源。
* 解決了顯示和篩選市場營銷活動時的介面問題。
* 已修復一個問題，該問題阻止使用POST剩餘API調用更新訂閱日期欄位。

_電子郵件、簡訊和直郵_

* 已修復可能無法針對郵件中清單類型受眾的問題，導致準備失敗。
* 多語言電子郵件傳遞功能中添加的語言缺失。
* 現在，當用戶修改內容並保存時，顯示在傳送儀表板上的內容縮略圖將自動更新。
* 已修復阻止開啟交貨的時區相關問題。

_推播通知_

* 配置推送通知通道時，iOS的推送提供程式平台應 **蘋果** 對於Android **gc**。
* 已修復阻止在iOS介面中添加Adobe Campaign移動應用的錯誤。
* 現在，GCM和啟用FCM的Android移動應用程式都支援推送通知。
* 修復了在複製推送通知模板時阻止保存內容的錯誤。
* 現在，通過協調移動應用程式用戶的資料，可以從Adobe Campaign資料庫建立或更新配置檔案。
* Adobe Campaign現在將處理事務推送通知優先於處理標準推送通知。

_報告_

* 修復了阻止熱點按一下百分比顯示在電子郵件內容中的問題。
* 已修復denylist度量的問題，該度量被計算為硬彈跳而不是彈跳。
* 已修復導致匯總資料中顯示負計數的問題。
* 已修復計算錯誤年齡段中配置檔案的問題。
* 軟彈跳和硬彈跳計算公式已經改變。

_工作流程_

* 已修復 **[!UICONTROL Load file]** 在手動添加和刪除活動中的列後可能導致錯誤的活動。
* 的 **[!UICONTROL deliverabilityUpdate]** 技術工作流現在計畫在伺服器時間凌晨2點運行。
* 已修復允許在沒有導出角色的情況下執行清單導出的安全問題。
* 已修復 **[!UICONTROL Reconciliation]** 的子菜單。
* 在中使用通配符解決了問題 **[!UICONTROL File Transfer]** 的子菜單。

_設定檔與對象_

* 修復了一個問題，該問題可能會防止在某些特定情況下正確考慮查詢條件，從而導致結果錯誤。
* 修復了一個問題，如果配置檔案是已準備但從未發送和過期的消息中的目標，則它可能會阻止訪問它們。

_整合_

* 已修復可能阻止為觸發器建立的某些資料源正確顯示和被選擇的問題。

_自訂資源_

* 修復了清單螢幕中出現的問題，在清單螢幕中，可以在沒有任何資料的情況下顯示自定義資源行。
* 修復了阻止在自定義資源中顯示值為「False」的布爾類型欄位的問題。

## 發行版本 17.9 – 2017 年 9 月 {#release-17-9---september-2017}

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
   <td> 電子郵件模板庫<br /> </td> 
   <td> 介紹18個全新、反應靈敏的模板，以兩個美麗的主題 — Astro和Feather設計。 這些可定製模板不受行業限制，可立即使用。 模板包括各種使用案例的內容，以使您的電子郵件營銷活動比以往更快、更高效、更美觀地設計和交付。<br /> 有關詳細資訊，請參閱 <a href="../../designing/using/using-reusable-content.md#content-templates">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用配置檔案資料動態報告<br /> </td> 
   <td> 動態報告提供完全可定製和即時的業務報告。 通過此版本，對動態報告功能的強大增強增加了對配置檔案資料的訪問，使用戶能夠按配置檔案維度（如性別、城市、郵遞區號和年齡）以及功能性電子郵件活動資料（如開啟和按一下）進行人口分析。 使用同樣易於使用的拖放介面，確定您針對您最重要的客戶群體執行電子郵件活動的方式比以往任何時候都更加容易。<br /> 有關詳細資訊，請參閱 <a href="../../reporting/using/about-dynamic-reports.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 具有原始和日期的成批訂閱<br /> </td> 
   <td> 通過此批量訂閱增強功能，您現在可以通過工作流中的訂閱服務活動將訂閱資訊（來源和日期）直接儲存在Adobe Campaign Standard資料庫中。<br /> 有關詳細資訊，請參閱 <a href="../../automating/using/subscription-services.md">詳細文檔</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 有些客戶需要能夠利用來自Adobe Campaign Standard的ID，因為他們沒有管理唯一的密鑰來識別自己的記錄。 此ID(**ACS ID**)可在更新資料時導出並用作協調密鑰。 如需詳細資訊，請參閱[詳細文件](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)以瞭解詳情。
* FTP協定已棄用。 現在應改用SFTP。 為了不阻止現有實施，FTP上的現有配置仍將像以前一樣工作，但新活動不會顯示該選項。

_電子郵件、簡訊和直郵_

* 現在，可以建立新的警報標準，以便在傳遞警報通知中使用它們。 如需詳細資訊，請參閱[詳細文件](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)以瞭解詳情。
* 交付警報通知具有新設計，而且交付警報儀表板用戶體驗得到改進。
* 現在，當路由外部帳戶被禁用時，受影響的遞送（電子郵件、SMS和推送）和 **預覽** 按鈕。
* 修復了在主題行中啟用動態文本時在電子郵件內容上的A/Btest預覽中導致錯誤的問題。

_異動訊息_

* 現在，您可以定義要發送後續消息的時間，例如，事務性消息發送3天後。 如需詳細資訊，請參閱[詳細文件](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)以瞭解詳情。
* 現在，可以定義應發送連結到事件的事務性消息的日期。
* 修復了在刪除連結到已接收和已處理事件的配置檔案後執行包含後續消息的工作流時導致SQL錯誤的問題。
* 修復了阻止刪除連結到事件的配置檔案的錯誤。
* 已修復可能阻止跟蹤連結重定向工作的問題。
* 已修復一個問題，該問題阻止您對電子郵件或SMS消息中的某些連結禁用跟蹤。

_報告_

* 的 **熱點擊** 報告已經改進。 此外，現在可以根據在傳遞中定義的每個條件內容顯示熱點按一下，並可針對重複傳遞或事務性消息的每次執行顯示熱點按一下。 如需詳細資訊，請參閱[詳細文件](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)以瞭解詳情。
* 已修復導致隔離度量無法檢索正確資料的問題。
* 已將新的預設時間框架添加到日曆小部件。
* 的 [動態報告度量](../../reporting/using/indicator-calculation.md) 和 [市場活動的KPI](../../sending/using/confirming-the-send.md) （顯示在已發送消息的儀表板上）已對齊，以便更加一致。
* 已修復可能導致debian 7上流水線崩潰的問題。

_工作流程_

* 已修復可能阻止導入檔案保留的問題。

_整合_

* 現在，分析和市場活動整合支援Vars和事件。
* 在發送包含已放棄購物車內容的電子郵件時，從購物車中刪除的元素的有效負載參數現在是可選的。

_設定檔與對象_

* Adobe Campaign現在提供顯示活動配置檔案數的報告。 此報告僅提供資訊，對計費沒有直接影響。 如需詳細資訊，請參閱[詳細文件](../../audiences/using/active-profiles.md)以瞭解詳情。
* 修復了在使用配置式和服務API時阻止配置式訂閱服務的問題。

## 發行版本 17.7 – 2017 年 7 月 {#release-17-7---july-2017}

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
   <td> 多語言電子郵件和簡訊交付<br /> </td> 
   <td> 根據您自動分段的客戶首選語言，通過單次交付定義並執行多語言電子郵件和簡訊交付。 報告每次傳送的效能，包括語言和個別層級。<br /> 隨著內容在國內外的發展，越來越多的公司面臨著以多種語言提供內容的挑戰。 因此，簡化本地化消息傳遞是跨國公司有效客戶溝通戰略的關鍵部分；多語言國家的公司；以及希望在語言級別進一步個性化其內容的公司，無論客戶位於何處。 如需詳細資訊，請參閱<a href="../../channels/using/creating-a-multilingual-email.md">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign通知<br /> </td> 
   <td> 直接在Adobe Campaign Standard接收有關重要系統活動的通知。 例如，您將收到有關當前交貨進度或工作流出錯的通知。<br /> 即時通知可隨時通知相關利益相關方，並為用戶提供立即和直接對應用程式內的活動通知採取行動的能力。 團隊的結果是提高靈活性、效率和更順利地執行活動。 如需詳細資訊，請參閱<a href="../../administration/using/sending-internal-notifications.md">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付警報<br /> </td> 
   <td> 除了直接在Adobe Campaign Standard查看通知外，Adobe Campaign公司現在還提供電子郵件警報系統，以向用戶或外部利益相關方發送有關重要系統活動的電子郵件警報。 建立、管理和接收可自定義的警報和儀表板，以跟蹤交付成功或失敗的情況。<br /> Adobe Campaign交付警報通過電子郵件和控制板讓公司內所有參與的Adobe Campaign用戶自動瞭解交付執行狀態，從而提高效率。 如需詳細資訊，請參閱<a href="../../sending/using/receiving-alerts-when-failures-happen.md">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 資料源中已加密聲明的ID<br /> </td> 
   <td> 使用加密的聯繫資訊（電子郵件地址或電話號碼）作為聲明的ID，發送電子郵件和SMS觸發器，而不需要市場活動中的現有配置檔案。 由於加密聲明的ID可以由Adobe Campaign Standard解碼，因此當從包含以前未知聯繫人的其他Experience Cloud解決方案接收觀眾時，Campig現在可以建立新的可銷售配置檔案。<br /> 通過電子郵件和簡訊即時瞄準客戶和未知潛在客戶，以分別提高現有客戶群的忠誠度和獲得新客戶。 一旦潛在客戶在Adobe Campaign驗證並利用這些洞見，就充分利用您的第一方cookie資料(來自Adobe Audience Manager*)。 <br /> *需要Adobe Audience Manager。 如需詳細資訊，請參閱<a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 從市場活動到分析的KPI共用<br /> </td> 
   <td> 與Adobe Analytics共用市場活動資料，以通過轉換、統一點擊前和點擊後行為來衡量來自市場活動的電子郵件營銷指標以及其他營銷和廣告工作。<br /> 直接跟蹤總體效能，並發現與分析中的外部計畫的協同效應。 將您從此整合視圖中學到的知識應用到您的活動中；最終改善開放、點擊和轉換率，提高收入和整體營銷表現。 <br /> Adobe Analytics是必填項。 如需詳細資訊，請參閱<a href="../../integrating/using/about-campaign-analytics-integration.md">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 直郵渠道 — 返回發件人<br /> </td> 
   <td> 現在支援與包含「返回發件人」資訊的Direct Mail提供商進行平面檔案交換。 這種對直郵通道的增強允許將相應的郵政地址排除在未來通信之外。<br /> 這使營銷人員能夠獲知錯誤的地址並通過其他渠道與客戶接觸或鼓勵他們更新其郵政地址。 這還減少了營銷人員在將郵件發送到不正確地址時浪費的營銷資金。 <br /> Direct Mail可作為附加渠道使用。 如需詳細資訊，請參閱<a href="../../channels/using/return-to-sender.md">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_常規_

* 已修復允許任何用戶導出清單的問題。 現在僅具有 **[!UICONTROL Export]** 允許角色。

_電子郵件、簡訊和直郵_

* 已修復 **更新DeliveryExecInfo** 設定 **交付** 指示符為0表示SMS交付。
* 在 **高級參數** 的屬性， **路由** 下拉清單現在只顯示與模板消息類型對應的外部帳戶。 例如，電子郵件傳遞模板只顯示電子郵件外部帳戶。
* 已修復 **[!UICONTROL Text]** 為test配置檔案定義的首選電子郵件格式。
* 修復了在交貨的計畫定義螢幕中選擇預設時區時導致Javascript錯誤的問題。
* 已修復阻止發送日誌中出現陷阱的問題。
* 在傳遞建立嚮導的模板選擇螢幕中，後續操作和A/Btest模板現在預設為隱藏。 有關詳細資訊，請參閱 [詳細文檔](../../channels/using/creating-an-email.md)。
* 已修復允許任何用戶發送交貨的問題。 現在僅具有 **[!UICONTROL Start deliveries]** 允許角色。 有關詳細資訊，請參閱 [詳細文檔](../../sending/using/confirming-the-send.md)。

_推播通知_

* 已修復 **市場活動跟蹤終結點** 阻止報告的URL。
* 已修復導致Android設備上無法顯示推送通知標題的問題。
* 修復了在推送通知僅包含標題（消息正文中沒有任何內容）時阻止推送通知顯示在iOS設備上的問題。
* 修復了強制跟蹤傳送中的媒體附件URL的問題，從而防止視頻和圖片嵌入傳送中。 現在，預設情況下，對推送通知的URL類型mediaAttachmentURL的跟蹤已停用。

_報告_

* 更正了圖表和表之間值不同的問題。
* 更正了將推送通知值顯示為電子郵件值的問題。
* 修復了在市場活動之外建立交貨時將值顯示為未知的問題。
* 更正了將SMS報告資料顯示為移動應用程式資料的問題。

_工作流程_

* 您現在可以篩選工作流日誌（時段和文本搜索）。 有關詳細資訊，請參閱 [詳細文檔](../../automating/using/monitoring-workflow-execution.md)。
* 工作流交付中現在提供了一個選項，可在發送前停用確認。
* 已修復導致無法在循環傳遞的建立嚮導中設定出站轉移的問題。
* 已修復使用基於自定義資源欄位的工作流查詢活動時發生的問題，該欄位包含具有許多值的枚舉

## 發行版本 17.5 – 2017 年 5 月 {#release-17-5---may-2017}

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
   <td> 直接郵件<br /> </td> 
   <td> 突破數字障礙，通過Adobe Campaign Standard的第一個離線頻道Direct Mail連接到實體世界。 此功能允許您將直接郵件提供商所需的檔案個性化並生成，作為跨渠道活動的一部分。 利用Direct Mail重新吸引客戶或增強客戶體驗，通過觸感觸點吸引客戶訪問您的應用、網站或商店。<br /> 有關詳細資訊，請參閱 <a href="../../channels/using/about-direct-mail.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件密件抄送<br /> </td> 
   <td> 電子郵件密件抄送功能可保存發送給單個收件人的唯一電子郵件，從而允許品牌存檔這些郵件。 通過向所有電子郵件添加密件抄送電子郵件地址，Adobe Campaign Standard客戶可以使用此功能保留每個電子郵件的準確副本。 這是金融服務行業的共同法律要求，有助於幫助客戶服務中心即時解決衝突。<br /> 有關詳細資訊，請參閱 <a href="../../sending/using/archiving.md">詳細文檔</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_介面更新_

* 在頂欄， **[!UICONTROL Timeline]** 連結已被刪除，並替換為指向 **[!UICONTROL Programs & Campaigns]** 。

_電子郵件和簡訊_

* 已修復顯示錯誤顏色的問題 **[!UICONTROL Retry in progress]** 交貨狀態。 顏色是灰色而不是藍色。

_工作流程_

* 已修復將操作更改為在 **[!UICONTROL Transfer file]** 的子菜單。

_報告_

* 的 **[!UICONTROL Spam]** 和 **[!UICONTROL Spam rate]** 指標計算已更改。
* 的 **[!UICONTROL Bounce]** 為了獲得更準確的結果，對度量進行了改進。

_推播通知_

* 已修復阻止您在配置檔案的市場營銷歷史記錄中按一下推送事件的問題。
* 工作流中推送通知的使用已得到改進。

## 發行版本 17.4 – 2017 年 4 月 {#release-17-4---april-2017}

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
   <td> Creative SDK增強的映像編輯功能<br /> </td> 
   <td> 現在，您可以訪問由Creative SDK支援的一整套功能，以便在編輯電子郵件或登錄頁時直接在內容編輯器中增強您的影像。<br /> 此功能不需要購買其他Creative Cloud解決方案。<br /> 有關詳細資訊，請參閱 <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 異動推送通知<br /> </td> 
   <td> Mobile應用程式渠道已經添加到Adobe Campaign的事務性消息傳送功能中。 事務性消息現在支援三個通道：電子郵件、簡訊和推送通知。<br /> 有關詳細資訊，請參閱 <a href="../../channels/using/transactional-push-notifications.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 定期推送通知<br /> </td> 
   <td> 您現在可以在工作流中配置定期推送通知。 在客戶希望定期更新（如每週提醒）以簽出新內容或促銷時，您可以使用定期推送通知。<br /> 有關詳細資訊，請參閱 <a href="../../automating/using/push-notification-delivery.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon簡單儲存服務(S3)連接器<br /> </td> 
   <td> Amazon簡單儲存服務(S3)連接器現在可用於將資料導入或導出到Adobe Campaign。 可以在工作流活動中設定。 配置在外部帳戶中完成。<br /> 有關詳細資訊，請參閱 <a href="../../administration/using/external-accounts.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver整合<br /> </td> 
   <td> Adobe Campaign和Dreamweaver的融合現在已經開始。 它現在與官方上一版Dreamweaver(17.0.2)合作。<br /> 這需要安裝Adobe Campaign整合擴展。 有關詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hant">視頻</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 已修復記憶體消耗問題。

_電子郵件和簡訊_

* 修復了在預覽消息時內容無法與最新更改正確同步的問題。
* 已修復阻止建立或刪除MX或域電子郵件處理規則的問題。
* 已修復一個問題，該問題可能會阻止您發送具有多個別名的電子郵件。
* 已修復阻止陷阱傳遞日誌出現在傳遞的發送日誌中的問題。
* 已修復顯示內容中沒有URL的傳遞的跟蹤URL時導致錯誤的問題。
* 已修復阻止在已發送消息中正確應用影像大小屬性的問題。

_異動訊息_

* rtEventHistoId欄位不再作為事務性消息模板中的個性化欄位公開。

_登陸頁面_

* 我們優化了 **[!UICONTROL by email]** 登錄頁中使用的篩選器，用於協調新訂戶與資料庫配置檔案。
* 在表單配置中使用布爾欄位時，已修復顯示自由文本輸入而非複選框的問題。
* 已修復阻止生成登錄頁縮略圖的問題。

_工作流程_

* 修復編輯時的顯示錯誤 **[!UICONTROL End]** 或 **[!UICONTROL External Signal]** 活動（僅在Safari上）。
* 改進編輯時顯示的錯誤消息 **[!UICONTROL Read Audience]** 包含錯誤受眾的活動。
* 已修復在執行訂閱活動時可能導致SQL錯誤的問題。

_整合_

* 興趣點資料：修復了計數位置訂閱伺服器時發生的錯誤。

_受眾和查詢_

* 已修復一個問題，該問題阻止在查詢編輯器中的集合上使用總和和平均聚合。
* 已修復在更改篩選器資源後可能無法重新載入查詢編輯器的問題。

_報告_

* 修復了在選擇表中的多行時無法正確計算開放速率度量的問題。
* 已修復僅將度量顯示為整數值的錯誤。 現在可以使用小數顯示度量。

_推播通知_

* 修復了在建立連結到在MCPNS上建立失敗的移動應用的Android應用程式時未顯示錯誤消息的問題。
* 已修復允許用戶向靜默通知添加聲音的問題。

## 發行版本 17.2 – 2017 年 3 月 {#release-17-2---march-2017}

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
   <td> 動態報告<br /> </td> 
   <td> 動態報告提供了新一代完全可定製的即時業務報告。 基於可視的動態透視表和圖形，此功能允許您拖放變數和維度，以分析市場營銷活動的效率和有效性。 動態報告還使您能夠從頭開始建立自己的業務報告，並保存這些報告供以後使用。<br /> 有關詳細資訊，請參閱 <a href="../../reporting/using/about-dynamic-reports.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver整合（實驗室）<br /> </td> 
   <td> 隨著Adobe Campaign和Dreamweaver的整合，您現在有了一個整合流程，用Adobe解決方案建立電子郵件活動。<br /> 您可以編輯Dreamweaver的Adobe Campaign電子郵件，並使內容在兩個解決方案之間無縫同步。<br /> 對於初始版本，該整合作為「實驗室」功能提供，僅與Dreamweaver預發行測試版一起使用。 如果要激活它，請聯繫AC-DW-integration@adobe.com。<br /> 有關詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">視頻</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 手動發送時間優化<br /> </td> 
   <td> 現在，您可以手動定義每個收件人的自定義發送時間 — 在交貨級別或使用工作流。 <br /> 有兩個新選項可用： <br /> 
    <ul> 
     <li> 所有收件人都收到郵件，其時區也已考慮在內。 </li> 
     <li> 每個接收者在公式定義的計算日期和時間接收消息。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../sending/using/optimizing-the-sending-time.md">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送通知新功能<br /> </td> 
   <td> 推送通知通道已通過以下幾項新功能得到增強：<br /> 
    <ul> 
     <li> 新的創作介面 </li> 
     <li> 無提示通知 </li> 
     <li> 互動式推送 </li> 
     <li> 豐富的內容支援 </li> 
     <li> 負載大小計算器 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../channels/using/about-push-notifications.md">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：新信號活動<br /> </td> 
   <td> 使用新工作流從另一個工作流觸發工作流 <span class="uicontrol">信號</span> 的子菜單。<br /> 通過能夠從另一個工作流啟動一個工作流，您現在可以支援更複雜的客戶行程。 您可以更好地監控客戶的行程，並在出現問題時做出反應。<br /> 已更新若干工作流活動：<br /> 
    <ul> 
     <li> <span class="uicontrol">結束</span> 活動：使用新頁籤，您可以指定在執行此活動後觸發的工作流。 </li> 
     <li> <span class="uicontrol">更新資料</span> 活動：使用新的空出站轉換添加 <strong>結束</strong> 觸發另一個工作流的活動。 空出站過渡不會攜帶任何資料，也不會佔用系統上不必要的空間 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../automating/using/external-signal.md">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：新閱讀受眾活動<br /> </td> 
   <td> 從現有受眾開始目標流程，您可以在一個活動中輕鬆選擇和細化目標受眾。<br /> 有關詳細資訊，請參閱 <a href="../../automating/using/read-audience.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 興趣點資料<br /> </td> 
   <td> 興趣點資料整合了Adobe Campaign和Adobe Analytics的Mobile。 品牌可以從用戶的移動位置收集資料 <strong>興趣點</strong>  — 用戶開啟品牌應用時。 這使品牌能夠利用Adobe Campaign的工作流，以便根據用戶的位置發送個性化的消息。 此渠道利用Mobile核心服務的SDK。<br /> 請注意，使用此功能需要Mobile分析，這是付費解決方案。<br /> 有關詳細資訊，請參閱 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API<br /> </td> 
   <td> 任何級別連結到配置檔案或服務資源的資源現在都可在API中使用。<br /> 有關詳細資訊，請參閱 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">詳細文檔</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_常規_

* 現在，在導出傳遞日誌時可以添加配置檔案資料。

_電子郵件和簡訊_

* 已修復導致 **[!UICONTROL Request confirmation before sending messages]** 選項，即使在取消選中並保存交貨後仍保持選中狀態。
* 已修復可能阻止取消發佈事務性電子郵件的問題。
* 修復了在預覽傳遞之前內容無法與最新更改正確同步的問題。

_登陸頁面_

* 修復了在按一下登錄頁的內容時阻止用戶編輯的錯誤。

_工作流程_

* 已修復可能無法讀取的拒絕轉換內容的問題 **[!UICONTROL Load file]** 的子菜單。
* 修復了在配置 **[!UICONTROL Load file]** 的子菜單。

## 發行版本 17.1 – 2017 年 1 月 {#release-17-1---january-2017}

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
   <td> 外部報告的日誌導出<br /> </td> 
   <td> 導出日誌（如交付日誌和跟蹤日誌），以在首選報告或BI工具中處理這些日誌。 您可以使用帶有增量查詢的簡單工作流來自動定期導出新日誌。<br /> 除了資源選取器提供的日誌資源可用性外，還對 <a href="../../automating/using/incremental-query.md">增量查詢</a> 和 <a href="../../automating/using/extract-file.md">提取檔案</a> 活動：<br /> 
    <ul> 
     <li> <span class="uicontrol">增量查詢</span> 現在允許您使用日期欄位來檢索新資料或更新資料。 以前，即使上次執行後更新了先前執行的所有結果，也會自動排除這些結果。 </li> 
     <li> <span class="uicontrol">提取檔案</span> 現在可以導出枚舉值的標籤，而不是ID。 </li> 
    </ul> 這些活動可供具有所有地理和組織單位訪問權限的管理員使用。<br /> 有關導出日誌的詳細資訊，請參閱 <a href="../../automating/using/exporting-logs.md">詳細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事務性消息的營銷能力<br /> </td> 
   <td> 營銷人員現在可以根據客戶市場營銷配置檔案發送事務性消息。 這允許他們：<br /> 
    <ul> 
     <li> 應用市場營銷類型規則，如 <span class="uicontrol">登錄地址</span> 。 </li> 
     <li> 在訊息中包含取消訂閱連結。 </li> 
     <li> 將交易式訊息新增至全域傳送報告。 </li> 
     <li> 在客戶歷程中善用交易式訊息。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事務性消息傳遞API<br /> </td> 
   <td> 事務消息傳遞API現在可通過 <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>，使使用和監控更方便：<br /> 
    <ul> 
     <li> 您可以從adobe.io平台報告和監視功能中獲益。 </li> 
     <li> 現在使用基於adobe.io令牌的身份驗證而不是IP允許清單來執行身份驗證，使安全過程更簡單。 </li> 
     <li> 現在，所有API都整合在一個平台上，這樣，在您已經支援配置檔案和服務API的情況下，將事務性消息傳遞功能添加到整合中變得比以往任何時候都更簡單。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_常規_

* 的 **[!UICONTROL Access authorization]** 選項已返回到登錄頁屬性。
* 修復了可能導致舊影像被渲染而不是正確影像的問題。 如果源映像已在傳遞或登錄頁的內容定義中更新，則會發生此情況。
* 修復了阻止用戶編輯現有SFTP外部帳戶中某些欄位的問題。
* 已修復多個UI問題。 例如，用戶現在可以編輯配置檔案屬性並保存修改，而不會遇到UI問題。

_電子郵件和簡訊_

* 已修復與包含HTML內容的傳遞模板相關的問題

_推播通知_

* 已修復可能阻止從應用程式回傳到Adobe Campaign伺服器的問題。
* 已修復可能阻止 **[!UICONTROL Play a sound]** 和 **[!UICONTROL Custom fields]** 要考慮Android。
* 已修復可能導致額外轉義字元添加到用於Emoji的Unicode字元的問題。
* 當訂戶的註冊令牌被添加到denylist時，相應的狀態現在立即在Adobe Campaign的訂戶的應用程式清單中更新。

_工作流程_

* 已修復可能阻止了事件資源查詢預覽的問題（例如rtEvent）。
* 由 **[!UICONTROL Load file]** 活動現在可以在其出站轉換中檢索，並在下一個活動中進行處理。 例如，通過SFTP伺服器使用 **[!UICONTROL Transfer file]** 。
* 修復了一個問題，如果 **[!UICONTROL Temporary resource]** 在 **[!UICONTROL General]** 頁籤 **[!UICONTROL Segmentation]** 。
* **[!UICONTROL Scheduler]** 活動不能再設定為每10分鐘觸發一次工作流。
* 已修復可能阻止 **[!UICONTROL Use common columns]** 不能在 **[!UICONTROL Union]** 的子菜單。

_整合_

* 已修復在Adobe Campaign部署事件觸發器時可能導致錯誤的問題。 當將「30天後返回的可能性」元資料添加到Adobe Marketing Cloud的「放棄」觸發器時，出現此錯誤。
* 修復了在從人員核心服務導入受眾時可能導致技術工作流清除目標Dimension欄位的問題。 後續查詢無法檢索導入的訪問群體。
* 已修復可能導致 **[!UICONTROL Save audience]** 選項時工作流的活動失敗 **[!UICONTROL Share in Adobe Marketing Cloud]** 已選中。
