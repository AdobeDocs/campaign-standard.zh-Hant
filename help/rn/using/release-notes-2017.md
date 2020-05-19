---
title: 發行說明 2017 年
description: 本頁列出2017年版本的所有Adobe Campaign Standard。
page-status-flag: never-activated
uuid: d73f8186-e309-441b-969d-71d0a1c33cf4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 1cfd9b3b-9b3e-4587-9c46-b6fb02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '4623'
ht-degree: 0%

---


# 發行說明 2017 年{#release-notes}

想要尋找2017年版Adobe Campaign Standard嗎？

每個版本都提供新功能和修補程式。 按一下某個版本以檢視其內容。

檢視Adobe Campaign Standard的 [最新檔案](../../rn/using/documentation-updates.md) 更新。 如果您要尋找較新的版本，請參閱本 [頁](../../rn/using/release-notes.md)。

## 發行版本17.10 - 2017年10月 {#release-17-10---october-2017}

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
   <td> 「疲勞管理」(Fatigue Management)允許您建立疲勞規則，以管理與配置檔案的過度通信。 疲勞規則建立起來很容易，但極具彈性，可計算多個通道（包括交易訊息）的訊息、只計算特定傳送，或將規則套用至特定描述檔。<br /> 如需詳細資訊，請參閱詳 <a href="../../sending/using/fatigue-rules.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 內容建立： 從URL匯入<br /> </td> 
   <td> 從URL匯入可讓您從網站快速擷取創意內容，以建立任何遞送的電子郵件。 此外，您還可讓協力廠商直接透過URL分享內容，以簡化您的創作流程。 匯入的內容可彈性地用作單一傳送的一部分，或在範本層級使用，以確保所有相關促銷活動（不論是以工作流程為基礎或交易性訊息）的品牌一致性，並包含A/B或多變數測試。 從URL匯入會自動轉換並追蹤所有連結，以透過動態報表監控電子郵件效能。<br /> 如需詳細資訊，請參閱詳 <a href="../../designing/using/using-existing-content.md#importing-content-from-a-url">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 修正無法正確解壓縮大型壓縮檔案的問題。
* 品牌管理的安全性已改善。 現在，Adobe技術管理員已保留修改品牌名稱和傳送者位址。
* 為改善安全性，使用者產生的內容（影像、鏡像頁面、著陸頁面等） 無法再由adobe.com網域提供服務。 現在，您必須使用您自己的網域來處理這些資源，並透過品牌的使用。
* 修正顯示及篩選行銷活動時的介面問題。
* 修正無法使用POST Rest API呼叫更新訂閱日期欄位的問題。

_電子郵件、簡訊訊息和直效郵件_

* 修正無法定位訊息中清單類型對象，導致準備失敗的問題。
* 多語言電子郵件傳送功能中新增的語言遺失。
* 當使用者修改內容並儲存時，顯示在傳送控制面板上的內容縮圖現在會自動更新。
* 修正無法開啟傳送的時區相關問題。

_推播通知_

* 在設定推播通知頻道時，iOS的推播提供者平台應為 **apns** ,Android **gcm**&#x200B;平台。
* 修正iOS行動應用程式無法新增至Adobe Campaign介面的錯誤。
* 推播通知現在在GCM和啟用FCM的Android行動應用程式上都受支援。
* 修正複製推播通知範本時無法儲存內容的錯誤。
* 現在，您可以協調行動應用程式使用者的資料，從Adobe Campaign資料庫建立或更新個人檔案。
* Adobe Campaign現在會優先處理交易推播通知，而非標準推播通知。

_報表_

* 修正無法在電子郵件內容中顯示熱點按百分比的問題。
* 修正黑名單度量被計為硬性反彈而非反彈的問題。
* 修正導致摘要資料顯示負數的問題。
* 修正在錯誤年齡區段中計算描述檔的問題。
* 軟彈跳和硬彈跳計算公式已變更。

_工作流程_

* 修正活動中手動 **[!UICONTROL Load file]** 新增和移除活動中的欄後，可能導致錯誤的問題。
* 技術 **[!UICONTROL deliverabilityUpdate]** 工作流程現在排定在伺服器時間凌晨2點執行。
* 修正允許執行不含匯出角色的清單匯出的安全性問題。
* 已修正活動的問 **[!UICONTROL Reconciliation]** 題。
* 修正活動中使用萬用字元的問 **[!UICONTROL File Transfer]** 題。

_設定檔與閱聽眾_

* 修正在某些特定情況下，查詢條件無法正確考慮，導致結果錯誤的問題。
* 修正當描述檔已定位在已準備但從未傳送及過期的訊息中時，可能無法存取的問題。

_整合_

* 修正為觸發器建立的某些資料來源無法正確顯示及選取的問題。

_自訂資源_

* 修正清單畫面中，自訂資源列可顯示而無任何資料的問題。
* 修正自訂資源中無法顯示具有&#39;False&#39;值的布林類型欄位的問題。

## 發行版本17.9 - 2017年9月 {#release-17-9---september-2017}

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
   <td> 隆重介紹以兩種精美主題（Astro和Feather）設計的十八種全新、互動式範本。 這些可自訂的範本不受產業限制，可立即使用。 範本包含多種使用案例的內容，讓您以前所未有的快速、有效率和精美方式設計和發佈電子郵件行銷宣傳。<br /> 如需詳細資訊，請參閱詳 <a href="../../designing/using/using-reusable-content.md#content-templates">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用描述檔資料的動態報表<br /> </td> 
   <td> 動態報表提供可完全自訂和即時的商業報表。 在此版本中，動態報表的強大增強功能新增了對描述檔資料的存取權，除了功能性電子郵件促銷活動資料（如開啟和點按）外，還可依描述檔維度（例如性別、城市、郵遞區號和年齡）來進行人口統計分析。 透過簡單易用的拖放介面，判斷您針對最重要客戶細分的電子郵件促銷活動如何進行，比以往更輕鬆。<br /> 如需詳細資訊，請參閱詳 <a href="../../reporting/using/about-dynamic-reports.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 含來源和日期的成批訂閱<br /> </td> 
   <td> 透過此「大量訂閱」增強功能，您現在可以透過工作流程中的「訂閱服務」活動，直接將訂閱資訊（來源和日期）儲存在Adobe Campaign Standard資料庫中。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/subscription-services.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 有些客戶需要能夠運用Adobe Campaign Standard提供的ID，因為他們無法管理唯一的金鑰來識別自己的記錄。 此ID(**ACS ID**)可匯出，並在更新資料時用作協調金鑰。 如需詳細資訊，請參閱詳 [細檔案](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。
* FTP通訊協定已過時。 您現在應改用SFTP。 為了不封鎖現有實作，FTP上的現有設定仍舊如舊，但新活動不會顯示選項。

_電子郵件、簡訊訊息和直效郵件_

* 現在可以建立新的警報標準，以便在發送警報通知中使用這些標準。 如需詳細資訊，請參閱詳 [細檔案](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 傳送警報通知有了新的設計，傳送警報控制面板的使用體驗也已改善。
* 現在，當傳送外部帳戶停用時，影響的傳送（電子郵件、簡訊和推播）中會顯示警告，而 **Preview** （預覽）按鈕會隱藏在這些傳送中。
* 修正在主旨行中啟用動態文字時，在電子郵件內容上預覽A/B測試時發生錯誤的問題。

_交易式訊息_

* 現在可以定義您要傳送後續訊息的時間，例如在傳送交易訊息3天後。 如需詳細資訊，請參閱詳 [細檔案](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。
* 現在可以定義應傳送連結至事件的交易訊息的日期。
* 修正刪除連結至已接收和已處理事件的描述檔後，執行包含後續訊息的工作流程時，造成SQL錯誤的問題。
* 修正無法刪除連結至事件之描述檔的錯誤。
* 已修正可能無法重新導向追蹤連結的問題。
* 修正無法停用電子郵件或SMS訊息中特定連結追蹤的問題。

_報表_

* 「 **Hot clicks** 」報表已改善。 此外，現在也可以根據傳送中定義的每個條件內容顯示熱點按，並可針對每次執行循環傳送或交易訊息顯示熱點按。 如需詳細資訊，請參閱詳 [細檔案](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 修正隔離度量無法擷取正確資料的問題。
* 新的預設時間範圍已新增至日曆介面工具集。
* 動 [態報表量度](../../reporting/using/indicator-calculation.md) ，與 [促銷活動的KPI](../../sending/using/confirming-the-send.md) （顯示在已傳送訊息的儀表板上）已對齊，以提高一致性。
* 修正可能導致流水線在debian 7上當機的問題。

_工作流程_

* 修正導入的檔案保留無法運作的問題。

_整合_

* eVar和事件現在支援Analytics和Campaign整合。
* 當傳送含有已放棄購物車內容的電子郵件時，從購物車移除的元素的裝載參數現在為選擇性。

_設定檔與閱聽眾_

* Adobe Campaign現在提供顯示作用中描述檔數目的報表。 此報告僅提供資訊，對帳單沒有直接影響。 如需詳細資訊，請參閱詳 [細檔案](../../audiences/using/active-profiles.md)。
* 修正使用「設定檔與服務API」時，設定檔無法訂閱服務的問題。

## 發行版本17.7 - 2017年7月 {#release-17-7---july-2017}

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
   <td> 多語言電子郵件和簡訊傳送<br /> </td> 
   <td> 根據您自動細分的客戶慣用語言，透過單一傳送方式定義並執行多語言電子郵件與簡訊傳送。 報告每次傳送的效能，包括語言和個別層級。<br /> 越來越多的公司面臨挑戰：在國內外發展時，以多種語言提供內容。 因此，簡化本地化訊息傳遞是跨國公司有效客戶溝通策略的關鍵部分； 多語言國家的公司； 以及想要在語言層級進一步個人化其內容的公司，不論客戶居住在何處。 如需詳細資訊，請參閱詳 <a href="../../channels/using/creating-a-multilingual-email.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign通知<br /> </td> 
   <td> 直接在Adobe Campaign Standard中接收有關重要系統活動的通知。 例如，當您正在進行的傳送進度或工作流程發生錯誤時，將會通知您。<br /> 即時通知可讓相關利益相關者隨時得知相關資訊，讓使用者能夠立即直接從應用程式中處理活動通知。 團隊的成果是，提高了靈活性、效率和更順暢地執行宣傳活動。 如需詳細資訊，請參閱詳 <a href="../../administration/using/sending-internal-notifications.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送警報<br /> </td> 
   <td> 除了直接在Adobe Campaign Standard中檢視通知外，Adobe Campaign現在還提供電子郵件警報系統，可針對重要系統活動向使用者或外部利益相關者觸發電子郵件警報。 建立、管理和接收可自訂的警報和儀表板，以追蹤傳送的成功或失敗。<br /> Adobe Campaign傳送快訊透過電子郵件和資料板，讓公司內所有相關的Adobe Campaign使用者自動得知傳送執行狀態，進而大幅提升效率。 如需詳細資訊，請參閱詳 <a href="../../sending/using/receiving-alerts-when-failures-happen.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 資料來源中的加密宣告ID<br /> </td> 
   <td> 使用加密的連絡資訊（電子郵件地址或電話號碼）做為宣告的ID，傳送電子郵件和簡訊觸發器，而不需要Campaign中的現有設定檔。 由於Encrypted Declared ID可由Adobe Campaign Standard解碼，所以當Campaign從包含先前未知聯絡人的其他Experience Cloud解決方案接收受眾時，現在可以建立新的可銷售個人檔案。<br /> 透過電子郵件和簡訊即時鎖定客戶和未知潛在客戶，以分別提高現有客戶群的忠誠度並贏得新客戶。 潛在客戶在Adobe Campaign中驗證並運用這些見解後，就可充份運用您的第一方Cookie資料（來自Adobe Audience Manager*）。 <br /> *需要Adobe Audience Manager。 如需詳細資訊，請參閱詳 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 從促銷活動到Analytics的KPI共用<br /> </td> 
   <td> 與Adobe Analytics共用宣傳資料，以測量來自Campaign的電子郵件行銷量度，以及透過轉換、統一點按前和點按後行為的其他行銷和廣告努力。<br /> 直接追蹤整體效能，並發現與Analytics中外部程式的協同效能。 將您從這個整合檢視中學到的知識，套用回到您的宣傳活動中； 最終改善開放、點進和轉換率，以提升營收和整體宣傳績效。 <br /> 需要Adobe Analytics。 如需詳細資訊，請參閱詳 <a href="../../integrating/using/about-campaign-analytics-integration.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 直接郵件通道——返回發件人<br /> </td> 
   <td> 現在支援與直接郵件提供者交換包含「傳回給寄件者」資訊的平面檔案。 此對「直效郵件」頻道的增強功能可讓對應的郵寄地址排除在未來通訊之外。<br /> 這可讓行銷人員收到錯誤地址的通知，並透過其他通道與客戶互動，或鼓勵他更新其郵遞區號。 此外，由於行銷人員避免將郵件傳送至不正確的位址，因此也會減少浪費的行銷資金。 <br /> Direct Mail可作為附加渠道使用。 如需詳細資訊，請參閱詳 <a href="../../channels/using/return-to-sender.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 修正讓任何使用者匯出清單的問題。 現在，僅允許具 **[!UICONTROL Export]** 有角色的用戶。

_電子郵件、簡訊訊息和直效郵件_

* 修正更新DeliveryExecInfo **工作流程中，將SMS傳送的「傳送** 指示符 **** 」設為0的問題。
* 在傳送 **範本屬性的** 「進階參數」中，「路由選擇 **** 」下拉式清單現在只會顯示與範本訊息類型對應的外部帳戶。 例如，電子郵件傳送範本只會顯示電子郵件外部帳戶。
* 修正為測試設定檔 **[!UICONTROL Text]** 定義之偏好電子郵件格式的問題。
* 修正在傳送的排程定義畫面中選取預設時區時，導致Javascript錯誤的問題。
* 修正傳送記錄檔中無法顯示陷阱的問題。
* 在傳送建立精靈的範本選擇畫面中，後續動作和A/B測試範本現在預設會隱藏。 如需詳細資訊，請參閱詳 [細檔案](../../channels/using/creating-an-email.md)。
* 修正讓任何使用者傳送傳送的問題。 現在，僅允許具 **[!UICONTROL Start deliveries]** 有角色的用戶。 如需詳細資訊，請參閱詳 [細檔案](../../sending/using/confirming-the-send.md)。

_推播通知_

* 修正促銷活動追蹤 **端點** URL無法報告的問題。
* 修正推播通知標題無法在Android裝置上顯示的問題。
* 修正當推播通知只包含標題（而訊息內文中沒有任何內容）時，推播通知無法顯示在iOS裝置上的問題。
* 修正強制要追蹤傳送中的媒體附件URL，導致影片和圖片無法內嵌在傳送中的問題。 推播通知的URL類型追蹤現在預設會停用。

_報表_

* 已修正圖表和表格之間的值顯示不同的問題。
* 修正將推播通知值顯示為電子郵件值的問題。
* 修正在促銷活動外部建立傳送時，其值顯示為未知的問題。
* 修正將SMS報表資料顯示為行動應用程式資料的問題。

_工作流程_

* 您現在可以篩選工作流程記錄檔（時段和文字搜尋）。 如需詳細資訊，請參閱詳 [細檔案](../../automating/using/monitoring-workflow-execution.md)。
* 工作流程傳送中現在提供一個選項，可在傳送前先停用確認。
* 修正無法在循環傳送的建立精靈中設定傳出轉場的問題。
* 修正使用基於自訂資源欄位的工作流程查詢活動，以及具有大量值的列舉時所發生的問題

## 發行版本17.5 - 2017年5月 {#release-17-5---may-2017}

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
   <td> 透過Adobe Campaign Standard的第一個離線通道Direct Mail突破數位障礙，與實體世界連結。 這項功能可讓您個人化並產生直接郵件供應商所需的檔案，做為跨通道宣傳的一部分。 運用Direct Mail透過吸引人的觸點，將客戶帶往您的應用程式、網站或商店，來重新吸引客戶或增強客戶體驗。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/about-direct-mail.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件密件副本<br /> </td> 
   <td> 電子郵件密件副本可儲存傳送給個別收件者的獨特電子郵件訊息，讓品牌可封存這些訊息。 借由將密件副本電子郵件地址新增至所有電子郵件，Adobe Campaign Standard客戶可透過此功能保留每封電子郵件的完整副本。 這是金融服務業的常見法律要求，有助於協助客戶服務中心即時解決衝突。<br /> 如需詳細資訊，請參閱詳 <a href="../../sending/using/archiving.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_介面更新_

* 在頂端列中，連結已 **[!UICONTROL Timeline]** 經移除，並以連結取代 **[!UICONTROL Programs & Campaigns]** 。

_電子郵件和簡訊_

* 修正傳送狀態顯示錯誤顏色 **[!UICONTROL Retry in progress]** 的問題。 顏色是灰色而非藍色。

_工作流程_

* 修正變更動作以在活動中執行時發生的 **[!UICONTROL Transfer file]** 問題。

_報表_

* 計 **[!UICONTROL Spam]** 算和 **[!UICONTROL Spam rate]** 指標已變更。
* 已 **[!UICONTROL Bounce]** 改善量度以取得更精確的結果。

_推播通知_

* 修正無法按一下描述檔行銷歷史記錄中推播事件的問題。
* 已改善推播通知在工作流程中的使用。

## 發行版本17.4 - 2017年4月 {#release-17-4---april-2017}

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
   <td> Creative SDK的增強影像版本功能<br /> </td> 
   <td> 您現在可以存取Creative SDK所提供的完整功能集，以在編輯電子郵件或登陸頁面時，直接在內容編輯器中增強您的影像。<br /> 這項功能不需要購買其他Creative Cloud解決方案。<br /> 如需詳細資訊，請參閱詳 <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易式推播通知<br /> </td> 
   <td> 行動應用程式通道已新增至Adobe Campaign的交易訊息功能。 交易式訊息現在支援三個通道： 電子郵件、簡訊和推播通知。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/transactional-push-notifications.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 循環推播通知<br /> </td> 
   <td> 您現在可以在工作流程中設定週期性推播通知。 您可以在客戶期望定期更新（例如每週提醒以查看新內容或促銷活動）的情況下，使用循環推播通知。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/push-notification-delivery.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service(S3)連接器<br /> </td> 
   <td> Amazon Simple Storage Service(S3)連接器現在可用來匯入或匯出資料至Adobe Campaign。 可在工作流活動中設定。 設定是在外部帳戶中完成。<br /> 如需詳細資訊，請參閱詳 <a href="../../administration/using/external-accounts.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver整合即時<br /> </td> 
   <td> Adobe Campaign與Dreamweaver的整合現已上線。 它現在可與官方上一版Dreamweaver(17.0.2)搭配使用。<br /> 這需要從以下網址安裝Adobe Campaign整合擴充功能： <a href="https://adobe.ly/acdw_addon">https://adobe.ly/acdw_addon如需詳細資訊</a><br /> ，請參閱此影 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">片</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 已修正記憶體耗用問題。

_電子郵件和簡訊_

* 修正預覽訊息時，內容無法與最新變更正確同步的問題。
* 修正無法建立或刪除MX或網域電子郵件處理規則的問題。
* 修正無法傳送具有多個別名之電子郵件的問題。
* 修正傳送的傳送記錄檔無法顯示陷阱傳送記錄檔的問題。
* 修正顯示內容中無URL之傳送之追蹤URL時，發生錯誤的問題。
* 修正影像大小屬性無法正確套用至已傳送訊息的問題。

_交易式訊息_

* rtEventHistoId欄位不再公開為交易訊息範本中的個人化欄位。

_登錄頁面_

* 我們已最佳化登陸頁 **[!UICONTROL by email]** 面中使用的篩選器，以協調新訂閱者與資料庫設定檔。
* 修正在表單設定中使用布林欄位時，顯示免費文字輸入而非核取方塊的問題。
* 修正無法產生著陸頁面縮圖的問題。

_工作流程_

* 修正編輯或活動時 **[!UICONTROL End]** 的顯 **[!UICONTROL External Signal]** 示錯誤（僅限Safari）。
* 改進編輯包含錯誤對象的活 **[!UICONTROL Read Audience]** 動時顯示的錯誤訊息。
* 修正在執行訂閱活動時可能導致SQL錯誤的問題。

_整合_

* 興趣點資料： 修正計算位置訂閱者時發生的錯誤。

_對象與查詢_

* 修正查詢編輯器中的系列無法使用總計和平均匯總的問題。
* 修正變更篩選器資源後，查詢編輯器無法重新載入的問題。

_報表_

* 修正在選取表格中的多列時，無法正確計算「開啟率」度量的問題。
* 修正僅將量度顯示為整數值的錯誤。 量度現在可顯示小數。

_推播通知_

* 修正當建立連結至MCPNS上建立之行動應用程式的Android應用程式時，未顯示錯誤訊息的問題。
* 修正使用者可將聲音新增至無訊息通知的問題。

## 發行版本17.2 - 2017年3月 {#release-17-2---march-2017}

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
   <td> 動態報表提供新一代可完全自訂和即時的商業報表。 此功能以視覺化動態樞紐表格和圖形為基礎，可讓您拖放變數和維度，以分析行銷宣傳的效率和效果。 動態報表也可讓您從頭開始建立自己的商業報表，並儲存以供日後使用。<br /> 如需詳細資訊，請參閱詳 <a href="../../reporting/using/about-dynamic-reports.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver整合(Labs)<br /> </td> 
   <td> 透過Adobe Campaign與Dreamweaver整合，您現在可以透過Adobe解決方案，建立電子郵件宣傳的整合程式。<br /> 您可以在Dreamweaver中編輯Adobe Campaign電子郵件，並讓這兩個解決方案之間的內容順暢地同步化。<br /> 在初始版本中，整合功能是「Labs」功能，僅能與Dreamweaver搶鮮版測試版搭配使用。 如果您想要啟動它，請聯絡AC-DW-integration@adobe.com。<br /> 如需詳細資訊，請參閱此影 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">片</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 手動傳送時間最佳化<br /> </td> 
   <td> 您現在可以在傳送層級或使用工作流程，手動定義每個收件者的自訂傳送時間。 <br /> 有兩個新選項可供使用： <br /> 
    <ul> 
     <li> 所有收件者都會收到訊息，其時區已納入考量。 </li> 
     <li> 每個收件者在公式定義的計算日期和時間接收該消息。 </li> 
    </ul> 如需詳細資訊，請參閱詳 <a href="../../sending/using/optimizing-the-sending-time.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播通知新功能<br /> </td> 
   <td> 推播通知頻道已增強，具備數種新功能：<br /> 
    <ul> 
     <li> 全新的製作介面 </li> 
     <li> 無訊息通知 </li> 
     <li> 互動式推播 </li> 
     <li> 多樣化內容支援 </li> 
     <li> 負載大小計算器 </li> 
    </ul> 如需詳細資訊，請參閱詳 <a href="../../channels/using/about-push-notifications.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程： 新訊號活動<br /> </td> 
   <td> 使用新的Signal活動，從其他工作流程觸發 <span class="uicontrol">工作流程</span> 。<br /> 現在，您可以從另一個工作流程開始，支援更複雜的客戶歷程。 您可以更好地監控客戶歷程，並在有問題時做出反應。<br /> 已更新數個工作流程活動：<br /> 
    <ul> 
     <li> <span class="uicontrol">結束活動</span> : 新的標籤可讓您指定在執行此活動後觸發的工作流程。 </li> 
     <li> <span class="uicontrol">更新資料</span> : 使用新的空出轉場功能來新增 <strong>End</strong> 活動，以觸發另一個工作流程。 空的出站轉場不會攜帶任何資料，也不會佔用系統上不必要的空間 </li> 
    </ul> 如需詳細資訊，請參閱詳 <a href="../../automating/using/external-signal.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程： 新的閱讀對象活動<br /> </td> 
   <td> 從現有受眾開始定位程式，您可以在單一活動中輕鬆選擇和調整這些受眾。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/read-audience.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 興趣點資料<br /> </td> 
   <td> 地標資料整合了Adobe Campaign與Adobe Analytics for Mobile。 當使用者開啟品牌應用程式時，品牌可以從使用者的行 <strong>動位置(稱為地標</strong> )收集資料。 這可讓品牌運用Adobe Campaign工作流程，根據使用者的位置傳送個人化訊息。 此通道運用Mobile核心服務的SDK。<br /> 請注意，使用此功能需要Analytics for Mobile，這是付費解決方案。<br /> 如需詳細資訊，請參閱詳 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API<br /> </td> 
   <td> API現在提供任何層級連結至描述檔或服務資源的資源。<br /> 如需詳細資訊，請參閱詳 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 現在，在匯出傳送記錄檔時，可以新增描述檔資料。

_電子郵件和簡訊_

* 修正即使在取消勾選 **[!UICONTROL Request confirmation before sending messages]** 並儲存傳送後，仍會保留選取選項的問題。
* 已修正無法取消發佈交易電子郵件的問題。
* 修正內容在預覽傳送前無法與最新變更正確同步的問題。

_登錄頁面_

* 修正當使用者在登陸頁面的內容中按一下時，無法編輯的錯誤。

_工作流程_

* 已修正無法讀取活動之拒絕轉換內容的問 **[!UICONTROL Load file]** 題。
* 修正在設定活動時，無法正確考慮交換欄的問 **[!UICONTROL Load file]** 題。

## 發行版本17.1 - 2017年1月 {#release-17-1---january-2017}

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
   <td> 匯出傳送和追蹤記錄檔等記錄檔，以便在您偏好的報表或BI工具中處理。 您可以使用簡單的工作流程和增量查詢，將新記錄檔的定期匯出作業自動化。<br /> 除了資源選擇器提供的日誌資源可用性外，還對增量查詢和提取文 <a href="../../automating/using/incremental-query.md">件活動</a><a href="../../automating/using/extract-file.md"></a> 進行了增強：<br /> 
    <ul> 
     <li> <span class="uicontrol">增量查詢</span> ，現在可讓您使用日期欄位來擷取新的或更新的資料。 以前，即使自上次執行後更新了先前執行的所有結果，也會自動排除這些結果。 </li> 
     <li> <span class="uicontrol">擷取檔案</span> 現在可以匯出列舉值的標籤，而非ID。 </li> 
    </ul> 管理員可存取所有地理和組織單位，可使用這些活動。<br /> 有關導出日誌的詳細資訊，請參閱詳 <a href="../../automating/using/exporting-logs.md">細文檔</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易訊息的行銷功能<br /> </td> 
   <td> 行銷人員現在可以根據客戶行銷個人檔案傳送交易訊息。 這可讓他們：<br /> 
    <ul> 
     <li> 套用行銷類型學規則，例如列入 <span class="uicontrol">黑名單的位址</span> 。 </li> 
     <li> 在訊息中加入取消訂閱連結。 </li> 
     <li> 將交易訊息新增至全域傳送報表。 </li> 
     <li> 在客戶歷程中運用交易訊息。 </li> 
    </ul> 如需詳細資訊，請參閱詳 <a href="../../channels/using/profile-transactional-messages.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易式訊息API<br /> </td> 
   <td> Transactional Messaging API現在可透過 <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io取得</a>，讓使用和監控變得更輕鬆：<br /> 
    <ul> 
     <li> 您可以從adobe.io平台報告與監控功能中獲益。 </li> 
     <li> 驗證現在使用adobe.io Token型驗證來執行，而非IP白名單，讓安全程式更簡單。 </li> 
     <li> 所有API現在都整合在單一平台上，如果您已支援Profile and Services API，就可以比以往更輕鬆地將交易訊息功能加入整合。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 選 **[!UICONTROL Access authorization]** 項已返回著陸頁面屬性。
* 修正可能導致舊影像轉換而非正確影像的問題。 如果來源影像已在傳送或登陸頁面的內容定義中更新，就會發生此情況。
* 修正使用者無法編輯現有SFTP外部帳戶中特定欄位的問題。
* 已修正數個UI問題。 例如，使用者現在可以編輯描述檔屬性並儲存修改，而不會遇到UI的問題。

_電子郵件和簡訊_

* 已修正與包含

_推播通知_

* 修正從應用程式回傳至Adobe Campaign伺服器的問題。
* 已修正Android可能無 **[!UICONTROL Play a sound]** 法 **[!UICONTROL Custom fields]** 考慮的問題。
* 修正可能導致在Emojis的Unicode字元中新增額外逸出字元的問題。
* 當訂閱者的註冊Token列入黑名單時，Adobe Campaign中的訂閱者清單現在會立即更新對應的狀態。

_工作流程_

* 修正可能無法預覽事件資源（例如rtEvent）查詢的問題。
* 活動生成的拒絕文 **[!UICONTROL Load file]** 件現在可以在其出站轉換中檢索，並在下一個活動中處理。 例如，透過SFTP伺服器使用 **[!UICONTROL Transfer file]** 。
* 修正當在的標籤中選取區段時，使用者無法限制區段 **[!UICONTROL Temporary resource]** 人口的 **[!UICONTROL General]** 問題 **[!UICONTROL Segmentation]** 。
* **[!UICONTROL Scheduler]** 活動無法再設為每10分鐘觸發一次以上。
* 修正活動中可能無 **[!UICONTROL Use common columns]** 法正常運作的 **[!UICONTROL Union]** 問題。

_整合_

* 修正在Adobe Campaign中部署事件觸發器時，可能造成錯誤的問題。 當「30天內回傳的可能性」中繼資料已新增至Adobe Marketing Cloud的「放棄」觸發器時，就會發生此錯誤。
* 修正從「人員」核心服務匯入觀眾時，技術工作流程可能會清除「目標維度」欄位的問題。 後續查詢無法擷取匯入的觀眾。
* 修正在勾選選選項時，工 **[!UICONTROL Save audience]** 作流程的活動可能會失敗的 **[!UICONTROL Share in Adobe Marketing Cloud]** 問題。

