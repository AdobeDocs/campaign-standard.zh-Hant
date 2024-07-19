---
title: 發行說明 2017 年
description: 本頁列出 2017 年的所有 Adobe Campaign Standard 版本。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '4572'
ht-degree: 3%

---

# 發行說明 2017 年{#release-notes}

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
   <td> 疲勞管理可讓您建立疲勞規則，以管理與設定檔的過度通訊。 疲勞規則可輕鬆建置，但其功能極為靈活，例如跨多個管道計算訊息（包括交易式訊息）、僅計算特定傳送或將規則套用至特定設定檔。<br />如需詳細資訊，請參閱<a href="../../sending/using/fatigue-rules.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 內容建立：從URL<br />匯入 </td> 
   <td> 從URL匯入可讓您快速從網站擷取創意內容，以建立任何傳遞的電子郵件。 此外，您可以讓第三方直接透過URL分享內容，藉此簡化您的創意程式。 匯入的內容可以靈活地用於單一傳遞或範本層級，確保所有相關行銷活動的品牌一致性（不論是工作流程型或異動訊息），並包含A/B或多變數測試。 從URL匯入會自動轉換並追蹤所有連結，以透過動態報告監控電子郵件效能。<br />如需詳細資訊，請參閱<a href="../../designing/using/using-existing-content.md">詳細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 修正了無法正確解壓縮大型壓縮檔案的問題。
* 已改善品牌管理中的安全性。 現在會為Adobe技術管理員保留修改品牌名稱和寄件者地址的許可權。
* 為了改善安全性，使用者產生的內容（影像、映象頁面、登入頁面等） 無法再由adobe.com網域提供服務。 現在，您必須使用自己的網域，透過使用品牌來處理這些資源。
* 修正顯示和篩選行銷活動時的介面問題。
* 修正無法使用POSTRest API呼叫更新訂閱日期欄位的問題。

_電子郵件、簡訊和直接郵件_

* 修正可能導致無法在訊息中鎖定清單型別對象，導致準備失敗的問題。
* 多語言電子郵件傳送功能中新增了缺少的語言。
* 現在當使用者修改內容並儲存時，傳送控制面板上顯示的內容縮圖會自動更新。
* 修正無法開啟傳遞的時區相關問題。

_推播通知_

* 設定推播通知通道時，iOS的推播提供者平台應為&#x200B;**apns**，Android的推播提供者平台應為&#x200B;**gcm**。
* 修正無法將iOS行動應用程式新增到Adobe Campaign介面的錯誤。
* GCM和啟用FCM的Android行動應用程式現在均支援推播通知。
* 修正複製推播通知範本時無法儲存內容的錯誤。
* 現在，可以透過協調行動應用程式使用者的資料，從Adobe Campaign資料庫建立或更新設定檔。
* Adobe Campaign現在會優先處理交易式推播通知，而非標準推播通知。

_報告_

* 修正無法在電子郵件內容中顯示熱門點選百分比的問題。
* 修正封鎖清單量度計入硬退信而非退信的問題。
* 修正導致摘要資料中顯示負數的問題。
* 修正了在錯誤年齡區段中計算設定檔的問題。
* 軟跳出和硬跳出的計算公式已變更。

_工作流程_

* 修正&#x200B;**[!UICONTROL Load file]**&#x200B;活動中手動新增及移除活動中的欄後，可能導致錯誤的問題。
* **[!UICONTROL deliverabilityUpdate]**&#x200B;技術工作流程現在已排程在伺服器時間凌晨2點執行。
* 修正了在沒有匯出角色的情況下允許執行清單匯出的安全性問題。
* 已修正&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動的問題。
* 已修正&#x200B;**[!UICONTROL File Transfer]**&#x200B;活動中使用萬用字元的問題。

_設定檔與對象_

* 修正某些特定情況下無法正確考慮查詢條件，導致錯誤結果的問題。
* 修正了無法存取設定檔的問題，若設定檔在已準備但從未傳送及過期的訊息中定位。

_整合_

* 修正了無法正確顯示和選取為觸發器建立之部分資料來源的問題。

_自訂資源_

* 修正在清單畫面中發生的問題，該問題導致自訂資源列沒有任何資料顯示。
* 修正具有「False」值的布林值型別欄位無法顯示在自訂資源中的問題。

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
   <td> 電子郵件範本庫<br /> </td> 
   <td> 向您介紹18種全新的回應式範本，採用兩種精美的主題設計 — Astro和Feather。 這些可自訂範本不受業界限制，可立即使用。 範本包含各種使用案例的內容，讓您的電子郵件行銷活動的設計及傳送比以往更快、更有效率且更精美。<br />如需詳細資訊，請參閱<a href="../../designing/using/using-reusable-content.md#content-templates">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用設定檔資料建立動態報告<br /> </td> 
   <td> 動態報告提供完全可自訂的即時業務報告。 在此版本中，動態報告的強大增強功能新增了設定檔資料的存取權，除了功能性電子郵件促銷活動資料（如開啟和點按）外，還支援依設定檔維度（例如，性別、城市、郵遞區號和年齡）進行人口統計分析。 透過相同的輕鬆拖放介面，比以往更容易判斷電子郵件促銷活動對最重要客戶細分的執行方式。<br />如需詳細資訊，請參閱<a href="../../reporting/using/about-dynamic-reports.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 具有來源與日期<br />的大量訂閱 </td> 
   <td> 透過此「大量訂閱」增強功能，您現在可以透過工作流程中的「訂閱服務」活動，將訂閱資訊（來源和日期）直接儲存在Adobe Campaign Standard資料庫中。<br />如需詳細資訊，請參閱<a href="../../automating/using/subscription-services.md">詳細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 有些客戶必須能夠運用來自Adobe Campaign Standard的ID，因為他們不會管理唯一索引鍵來識別自己的記錄。 此ID (**ACS ID**)可以匯出，並在更新資料時作為調解金鑰。 如需詳細資訊，請參閱[詳細文件](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)以瞭解詳情。
* FTP通訊協定已淘汰。 您現在應該改用SFTP。 為了不封鎖現有的實作，FTP上的現有設定仍會像之前一樣運作，但不會為新活動顯示選項。

_電子郵件、簡訊和直接郵件_

* 您現在可以建立新的警報條件，以便用於傳送警報通知。 如需詳細資訊，請參閱[詳細文件](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)以瞭解詳情。
* 傳送警報通知具有新設計，而且傳送警報控制面板使用者體驗已改善。
* 現在，當路由外部帳戶停用時，受影響的傳送（電子郵件、簡訊和推播）中會顯示警告，並且&#x200B;**預覽**&#x200B;按鈕會隱藏在這些傳送中。
* 修正在主旨行中啟用動態文字時，造成電子郵件內容A/B測試預覽發生錯誤的問題。

_異動訊息_

* 現在可以定義您何時要傳送後續訊息，例如在傳送交易式訊息後3天。 如需詳細資訊，請參閱[詳細文件](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)以瞭解詳情。
* 現在可以定義連結至事件的交易式訊息的開始傳送日期。
* 修正在刪除連結至已接收和已處理事件的設定檔後，執行包含後續訊息的工作流程時導致SQL錯誤的問題。
* 修正無法刪除連結至事件之設定檔的錯誤。
* 修正了無法重新導向追蹤連結的問題。
* 修正無法停用電子郵件或簡訊訊息中特定連結追蹤的問題。

_報告_

* 已改善&#x200B;**熱點點按**&#x200B;報告。 此外，現在可以根據傳送中定義的每個條件式內容顯示熱點點按，並顯示定期傳送或異動訊息每個執行的熱點點按。 如需詳細資訊，請參閱[詳細文件](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)以瞭解詳情。
* 修正隔離量度無法擷取正確資料的問題。
* 行事曆Widget已新增預設時間範圍。
* 已調整[動態報告量度](../../reporting/using/indicator-calculation.md)與[行銷活動KPI](../../sending/using/confirming-the-send.md) （顯示在已傳送訊息的控制面板上），以更協調一致。
* 修正可能導致管線在debian 7上當機的問題。

_工作流程_

* 修正匯入的檔案保留功能無法運作的問題。

_整合_

* Analytics與Campaign整合現在支援eVar和事件。
* 傳送包含捨棄的購物車內容的電子郵件時，從購物車移除的元素的裝載引數現在是選用專案。

_設定檔與對象_

* Adobe Campaign現在會提供一份報表，顯示作用中設定檔的數量。 此報告僅提供資訊，對帳單沒有直接影響。 如需詳細資訊，請參閱[詳細文件](../../audiences/using/active-profiles.md)以瞭解詳情。
* 修正使用Profiles and Services API時，設定檔無法訂閱服務的問題。

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
   <td> 多語言電子郵件和簡訊傳遞<br /> </td> 
   <td> 根據自動細分客戶偏好的語言，透過單一傳送來定義並執行多語言電子郵件和簡訊傳送。 報告每次傳送的效能，包括語言和個別層級。<br />越來越多的公司面臨著在國內外成長過程中提供多國語言內容的挑戰。 因此，簡化本地化訊息的傳遞，是跨國公司、擁有多種語言的國家/地區公司，以及無論客戶身在何處，都想進一步個人化語言層級內容的公司，有效客戶溝通策略的重要一環。 如需詳細資訊，請參閱<a href="../../channels/using/creating-a-multilingual-email.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign通知<br /> </td> 
   <td> 直接在Adobe Campaign Standard中接收有關重要系統活動的通知。 例如，您將會收到進行中傳遞的進度或工作流程發生錯誤時的通知。<br />即時通知可隨時通知相關利害關係人，並讓使用者能夠立即直接從應用程式內對活動通知採取行動。 對團隊來說，結果就是進階的靈活性、效率以及行銷活動的更順暢執行。 如需詳細資訊，請參閱<a href="../../administration/using/sending-internal-notifications.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞警報<br /> </td> 
   <td> 除了直接在Adobe Campaign Standard中檢視通知外，Adobe Campaign現在還提供電子郵件警報系統，以觸發向使用者或重要系統活動的外部利益關係人傳送電子郵件警報。 建立、管理和接收可自訂的警示和儀表板，以追蹤傳送成功或失敗。<br /> Adobe Campaign傳遞警示可透過電子郵件和儀表板，讓公司中所有涉及的Adobe Campaign使用者自動得知傳遞執行狀態，以提高效率。 如需詳細資訊，請參閱<a href="../../sending/using/receiving-alerts-when-failures-happen.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 資料來源<br />中的加密宣告ID </td> 
   <td> 使用加密的聯絡資訊（電子郵件地址或電話號碼）作為宣告ID，傳送電子郵件和簡訊觸發器，而無需Campaign中的現有設定檔。 由於加密的宣告ID可由Adobe Campaign Standard解碼，因此Campaign現在可在接收來自其他Experience Cloud解決方案（包含先前未知的聯絡人）的對象時，建立新的可銷售的設定檔。<br />透過電子郵件和簡訊即時鎖定客戶和未知的潛在客戶，以提高現有客戶群的忠誠度，並取得新客戶。 一旦潛在客戶在Adobe Campaign中驗證並運用這些深入分析，就能充分利用您的第一方Cookie資料(來自Adobe Audience Manager*)。 <br /> *需要Adobe Audience Manager。 如需詳細資訊，請參閱<a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 從Campaign到Analytics的KPI共用<br /> </td> 
   <td> 與Adobe Analytics共用行銷活動資料，以透過轉換、統一點按前後的行為，測量行銷活動的電子郵件行銷量度以及其他行銷和廣告工作。<br />直接追蹤整體效能，並在Analytics中發掘與外部程式的協同效益。 將來自此整合檢視的學習套用回您的行銷活動；最終改善開放、點進和轉換率，以提高收入和整體行銷活動績效。 需要<br /> Adobe Analytics。 如需詳細資訊，請參閱<a href="../../integrating/using/about-campaign-analytics-integration.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 直接郵件通道 — 傳回給寄件者<br /> </td> 
   <td> 現在支援與直接郵件提供者交換包含退回寄件者資訊的平面檔案。 此直接郵件通道的增強功能可將對應的郵寄地址排除在未來的通訊之外。<br />這可讓行銷人員收到地址錯誤的通知，並透過其他管道與客戶互動，或鼓勵他們更新郵寄地址。 這也減少了行銷人員避免傳送郵件至錯誤地址所浪費的行銷金額。 <br />直接郵件可作為附加元件通道使用。 如需詳細資訊，請參閱<a href="../../channels/using/return-to-sender.md">詳細檔案</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 修正讓任何使用者匯出清單的問題。 現在，僅允許具有&#x200B;**[!UICONTROL Export]**&#x200B;角色的使用者使用。

_電子郵件、簡訊和直接郵件_

* 修正SMS傳遞之&#x200B;**updateDeliveryExecInfo**&#x200B;工作流程將&#x200B;**To delivery**&#x200B;指標設為0的問題。
* 在傳遞範本屬性的&#x200B;**進階引數**&#x200B;中，**路由**&#x200B;下拉式清單現在只會顯示對應至範本訊息型別的外部帳戶。 例如，電子郵件傳遞範本只會顯示電子郵件外部帳戶。
* 修正為測試設定檔定義&#x200B;**[!UICONTROL Text]**&#x200B;偏好電子郵件格式的問題。
* 修正在傳送的排程定義畫面中選取預設時區時，中導致發生Javascript錯誤的問題。
* 修正傳送記錄檔中無法顯示陷阱的問題。
* 在傳遞建立精靈的範本選擇畫面中，後續和A/B測試範本現在預設為隱藏。 如需詳細資訊，請參閱[詳細檔案](../../channels/using/creating-an-email.md)。
* 修正讓任何使用者傳送傳遞的問題。 現在，僅允許具有&#x200B;**[!UICONTROL Start deliveries]**&#x200B;角色的使用者使用。 如需詳細資訊，請參閱[詳細檔案](../../sending/using/confirming-the-send.md)。

_推播通知_

* 已修正&#x200B;**行銷活動追蹤端點** URL阻止報告的問題。
* 修正無法在Android裝置上顯示推播通知標題的問題。
* 修正當推播通知僅包含標題（且訊息內文不含任何內容）時，無法在iOS裝置上顯示推播通知的問題。
* 修正強制追蹤傳遞中的媒體附件URL，導致無法將視訊和圖片內嵌在傳遞中的問題。 對於推播通知，現在預設會停用mediaAttachmentURL型別的URL追蹤。

_報告_

* 修正圖表和表格之間值顯示不同的問題。
* 修正將推播通知值顯示為電子郵件值的問題。
* 修正在行銷活動之外建立傳遞時，顯示值為未知的問題。
* 修正了將SMS報表資料顯示為行動應用程式資料的問題。

_工作流程_

* 您現在可以篩選工作流程記錄（時段和文字搜尋）。 如需詳細資訊，請參閱[詳細檔案](../../automating/using/monitoring-workflow-execution.md)。
* 現在工作流程傳送中有一個選項，可在傳送前停用確認。
* 修正無法在循環傳遞的建立精靈中設定出站轉變的問題。
* 修正根據具有大量值的自訂資源欄位，使用工作流程查詢活動時發生的問題

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
   <td> 透過Adobe Campaign Standard的第一個離線頻道Direct Mail，突破數位障礙，連線到實體世界。 此功能可讓您個人化並產生直接郵件供應商所需的檔案，作為跨頻道行銷活動的一部分。 利用Direct Mail，以吸引人的觸覺式接觸點將客戶引導至您的應用程式、網站或商店，重新與客戶互動或提升客戶體驗。<br />如需詳細資訊，請參閱<a href="../../channels/using/about-direct-mail.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件密件副本<br /> </td> 
   <td> 電子郵件密件副本可儲存傳送給個別收件者的不重複電子郵件訊息，因此允許品牌封存這些訊息。 透過將「密件副本」電子郵件地址新增至所有電子郵件，Adobe Campaign Standard客戶可以使用此功能保留每封電子郵件的精確副本。 這是金融服務業的常見法律要求，有助於協助客戶服務中心即時解決衝突。<br />如需詳細資訊，請參閱<a href="../../sending/using/archiving.md">詳細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_介面更新_

* 在頂端列中，**[!UICONTROL Timeline]**&#x200B;連結已移除，並取代為&#x200B;**[!UICONTROL Programs & Campaigns]**&#x200B;的連結。

_電子郵件和簡訊訊息_

* 修正&#x200B;**[!UICONTROL Retry in progress]**&#x200B;傳遞狀態顯示錯誤顏色的問題。 顏色是灰色而非藍色。

_工作流程_

* 修正變更動作以在&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動中執行時發生的問題。

_報告_

* **[!UICONTROL Spam]**&#x200B;和&#x200B;**[!UICONTROL Spam rate]**&#x200B;指標計算已變更。
* 已改善&#x200B;**[!UICONTROL Bounce]**&#x200B;量度，以取得更準確的結果。

_推播通知_

* 修正無法點按設定檔行銷歷史記錄中推播事件的問題。
* 在工作流程中，推播通知的使用已得到改善。

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
   <td> Creative SDK<br />的增強影像版本功能 </td> 
   <td> 您現在可以存取由Creative SDK支援的完整功能集，以便在編輯電子郵件或登入頁面時直接在內容編輯器中增強影像。<br />此功能不需要取得其他Creative Cloud解決方案。<br />如需詳細資訊，請參閱<a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 異動推播通知<br /> </td> 
   <td> 行動應用程式頻道已新增至Adobe Campaign的交易式傳訊功能。 異動訊息現在支援三個通道：電子郵件、簡訊和推播通知。<br />如需詳細資訊，請參閱<a href="../../channels/using/transactional-push-notifications.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 循環推播通知<br /> </td> 
   <td> 您現在可以在工作流程中設定循環推播通知。 如果您的客戶預期會定期更新（如每週提醒），以簽出新內容或促銷活動，則您可以使用循環推播通知。<br />如需詳細資訊，請參閱<a href="../../automating/using/push-notification-delivery.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service (S3)聯結器<br /> </td> 
   <td> Amazon Simple Storage Service (S3)聯結器現在可用來匯入或匯出資料至Adobe Campaign。 您可以在工作流程活動中設定它。 設定是在外部帳戶中完成。<br />如需詳細資訊，請參閱<a href="../../administration/using/external-accounts.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver整合即時<br /> </td> 
   <td> Adobe Campaign與Dreamweaver之間的整合現已上線。 現在可與官方最後發行版本的Dreamweaver (17.0.2)搭配使用。<br />您必須安裝Adobe Campaign Integration延伸模組。 如需詳細資訊，請參閱此<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hant">影片</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 修正記憶體耗用問題。

_電子郵件和簡訊訊息_

* 修正預覽訊息時，內容無法正確與最新變更同步的問題。
* 修正無法建立或刪除MX或網域電子郵件處理規則的問題。
* 修正了無法傳送具有多個別名的電子郵件的問題。
* 修正傳送的傳送記錄中無法顯示陷阱傳送記錄的問題。
* 修正顯示內容中沒有URL的傳送的追蹤URL時，導致錯誤的問題。
* 修正無法正確套用傳送訊息中影像大小屬性的問題。

_異動訊息_

* rtEventHistoId欄位不再顯示為交易式訊息範本中的個人化欄位。

_登陸頁面_

* 我們已最佳化登入頁面中使用的&#x200B;**[!UICONTROL by email]**&#x200B;篩選器，以協調新訂閱者與資料庫設定檔。
* 修正在表單設定中使用布林欄位時，顯示自由文字輸入而非核取方塊的問題。
* 修正無法產生登入頁面縮圖的問題。

_工作流程_

* 修正編輯&#x200B;**[!UICONTROL End]**&#x200B;或&#x200B;**[!UICONTROL External Signal]**&#x200B;活動時的顯示錯誤（僅適用於Safari）。
* 改善編輯包含錯誤對象的&#x200B;**[!UICONTROL Read Audience]**&#x200B;活動時顯示的錯誤訊息。
* 修正執行訂閱活動時，可能導致SQL錯誤的問題。

_整合_

* 興趣點資料：修正計算位置訂閱者人數時發生錯誤。

_對象和查詢_

* 修正無法在查詢編輯器的集合上使用sum和average彙總的問題。
* 修正在變更篩選器的資源後，查詢編輯器無法重新載入的問題。

_報告_

* 修正在表格中選擇多個列時，無法正確計算開啟率量度的問題。
* 修正僅將量度顯示為整數值的錯誤。 量度現在可以顯示小數。

_推播通知_

* 修正建立連結至行動應用程式的Android應用程式（在MCPNS上建立時失敗）時，未顯示錯誤訊息的問題。
* 修正允許使用者將聲音新增至無訊息通知的問題。

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
   <td> Dynamic Reporting提供新一代可完全自訂的即時業務報表。 此功能以視覺化動態樞紐表格和圖形為基礎，可讓您拖放變數和維度，以分析行銷活動的效率和成效。 動態報告也可讓您從頭開始建立自己的業務報告，並儲存以供日後使用。<br />如需詳細資訊，請參閱<a href="../../reporting/using/about-dynamic-reports.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver整合(Labs)<br /> </td> 
   <td> 透過Adobe Campaign和Dreamweaver整合，您現在已擁有使用Adobe解決方案建立電子郵件行銷活動的整合程式。<br />您可以在Dreamweaver中編輯Adobe Campaign電子郵件，並讓內容在兩個解決方案之間無縫同步。<br />在初始發行中，整合是以「Labs」功能提供，僅適用於Dreamweaver發行前Beta。 如果您想要啟用該功能，請連絡AC-DW-integration@adobe.com。<br />如需詳細資訊，請參閱此<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hant">影片</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 手動傳送時間最佳化<br /> </td> 
   <td> 您現在可以在傳送層級或使用工作流程，手動定義每個收件者的自訂傳送時間。 <br />兩個新選項可供使用： <br /> 
    <ul> 
     <li> 所有收件者都會收到訊息，其時區已納入考量。 </li> 
     <li> 每個收件者都會在公式所定義的計算日期和時間收到訊息。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../sending/using/optimizing-the-sending-time.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播通知新功能<br /> </td> 
   <td> 推播通知通道已增強，具備幾項新功能： <br /> 
    <ul> 
     <li> 新的撰寫介面 </li> 
     <li> 靜音通知 </li> 
     <li> 互動式推播 </li> 
     <li> 豐富的內容支援 </li> 
     <li> 承載大小電腦 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../channels/using/about-push-notifications.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：新訊號活動<br /> </td> 
   <td> 使用新的<span class="uicontrol">訊號</span>活動，從其他工作流程觸發工作流程。<br />由於您能夠從另一個工作流程開始，您現在可以支援更複雜的客戶歷程。 您可以更好地監視客戶歷程，並在發生問題時做出反應。<br />已更新數個工作流程活動：<br /> 
    <ul> 
     <li> <span class="uicontrol">結束</span>活動：新的索引標籤可讓您指定此活動執行後要觸發的工作流程。 </li> 
     <li> <span class="uicontrol">更新資料</span>活動：使用新的空的匯出轉變來新增觸發另一個工作流程的<strong>End</strong>活動。 空的匯出轉變不攜帶任何資料，也不會消耗系統上不必要的空間 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../automating/using/external-signal.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：新的讀取對象活動<br /> </td> 
   <td> 以現有對象開始您的目標定位程式，您可以輕鬆選取這些對象，並在一個活動中加以調整。<br />如需詳細資訊，請參閱<a href="../../automating/using/read-audience.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 興趣點資料<br /> </td> 
   <td> 興趣點資料已整合Adobe Campaign與適用於行動裝置的Adobe Analytics。 當使用者開啟品牌的應用程式時，品牌可以從使用者的行動裝置位置（稱為<strong>地標</strong>）收集資料。 這可讓品牌運用Adobe Campaign工作流程，根據使用者的位置傳送個人化訊息。 此管道採用行動核心服務的SDK。<br />請注意，使用此功能需要Analytics for Mobile，此為付費解決方案。<br />如需詳細資訊，請參閱<a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API<br /> </td> 
   <td> 現在，任何層級連結到設定檔或服務資源的資源可在API中使用。<br />如需詳細資訊，請參閱<a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">詳細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 現在可以在匯出傳送記錄檔時新增設定檔資料。

_電子郵件和簡訊訊息_

* 修正在取消核取並儲存傳遞後，**[!UICONTROL Request confirmation before sending messages]**&#x200B;選項仍保持選取狀態的問題。
* 修正無法取消發佈交易式電子郵件的問題。
* 修正在預覽傳送前，內容無法正確與最新變更同步的問題。

_登陸頁面_

* 修正使用者按一下登入頁面內容時無法編輯的錯誤。

_工作流程_

* 修正無法讀取&#x200B;**[!UICONTROL Load file]**&#x200B;活動之拒絕轉變內容的問題。
* 修正設定&#x200B;**[!UICONTROL Load file]**&#x200B;活動時，無法正確考慮已交換欄的問題。

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
   <td> 外部報告的記錄檔匯出<br /> </td> 
   <td> 匯出傳送和追蹤記錄等記錄檔，以便在您偏好的報告或BI工具中處理。 您可以使用簡單工作流程搭配增量查詢，以自動定期匯出新記錄。<br />除了資源選擇器的記錄資源可用性之外，還增強了<a href="../../automating/using/incremental-query.md">增量查詢</a>和<a href="../../automating/using/extract-file.md">擷取檔案</a>活動：<br /> 
    <ul> 
     <li> <span class="uicontrol">增量查詢</span>現在可讓您使用日期欄位來擷取新的或更新後的資料。 以前，即使先前執行的所有結果在上次執行後已更新，也會自動排除。 </li> 
     <li> <span class="uicontrol">擷取檔案</span>現在可以匯出列舉值的標籤，而不是ID。 </li> 
    </ul> 管理員可使用這些活動來存取所有地理和組織單位。<br />如需匯出記錄檔的詳細資訊，請參閱<a href="../../automating/using/exporting-logs.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 異動訊息的行銷功能<br /> </td> 
   <td> 行銷人員現在可以根據客戶行銷設定檔傳送交易式訊息。 這允許他們：<br /> 
    <ul> 
     <li> 套用行銷型別規則，例如<span class="uicontrol">封鎖清單</span>上的地址。 </li> 
     <li> 在訊息中包含取消訂閱連結。 </li> 
     <li> 將交易式訊息新增至全域傳送報告。 </li> 
     <li> 在客戶歷程中善用交易式訊息。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 異動訊息API<br /> </td> 
   <td> 異動訊息API現在可以使用，使其更易於使用和監視：<br /> 
    <ul> 
     <li> 您可以從Adobe Developer平台報告和監視功能中獲益。 </li> 
     <li> 現在使用adobe.io權杖式驗證（而不是IP允許清單）來執行驗證，使得安全性程式更簡單。 </li> 
     <li> 現在，所有API都整合在單一平台上，如果您已支援設定檔和服務API，將交易訊息功能新增到整合比以往更簡單。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* **[!UICONTROL Access authorization]**&#x200B;選項已傳回至登入頁面屬性。
* 修正可能導致呈現舊影像而非正確影像的問題。 如果來源影像已在傳遞或登入頁面的內容定義中更新，就會發生此狀況。
* 修正使用者無法編輯現有SFTP外部帳戶中特定欄位的問題。
* 已修正數個UI問題。 例如，使用者現在可以編輯設定檔屬性並儲存修改，而不遇到UI問題。

_電子郵件和簡訊訊息_

* 修正了傳送範本的問題，其HTML內容包含

_推播通知_

* 修正了無法從應用程式回傳至Adobe Campaign伺服器的問題。
* 修正了無法將&#x200B;**[!UICONTROL Play a sound]**&#x200B;和&#x200B;**[!UICONTROL Custom fields]**&#x200B;納入Android的問題。
* 修正可能導致在用於Emoji的Unicode字元中新增額外逸出字元的問題。
* 將訂閱者的註冊權杖新增到封鎖清單時，對應的狀態現在會在Adobe Campaign中的應用程式訂閱者清單中立即更新。

_工作流程_

* 修正無法預覽事件資源（例如rtEvent）查詢的問題。
* **[!UICONTROL Load file]**&#x200B;活動產生的拒絕檔案現在可以在其出站轉變中擷取，並在下一個活動中處理。 例如，使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;透過SFTP伺服器上傳拒絕檔案。
* 修正在&#x200B;**[!UICONTROL Segmentation]**&#x200B;的&#x200B;**[!UICONTROL General]**&#x200B;索引標籤中選取&#x200B;**[!UICONTROL Temporary resource]**&#x200B;時，使用者無法限制區段母體的問題。
* **[!UICONTROL Scheduler]**&#x200B;個活動不能再設定為每10分鐘觸發一次以上的工作流程。
* 修正了可能導致&#x200B;**[!UICONTROL Use common columns]**&#x200B;無法在&#x200B;**[!UICONTROL Union]**&#x200B;活動中正常運作的問題。

_整合_

* 修正在Adobe Campaign中部署事件觸發程式時，可能導致錯誤的問題。 將「30天內回訪的可能性」中繼資料新增至Adobe Marketing Cloud中的放棄觸發程式時，就會發生此錯誤。
* 修正從People核心服務匯入受眾時，技術工作流程可能清除TargetDimension欄位的問題。 後續查詢無法擷取匯入的對象。
* 修正核取選項&#x200B;**[!UICONTROL Share in Adobe Marketing Cloud]**&#x200B;時，工作流程的&#x200B;**[!UICONTROL Save audience]**&#x200B;活動可能失敗的問題。
