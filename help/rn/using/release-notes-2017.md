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
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '4623'
ht-degree: 5%

---

# 發行說明 2017 年{#release-notes}

正在尋找2017年的特定Adobe Campaign Standard版本？

每個版本都提供新功能和修補程式。 按一下某個版本以檢視其內容。

檢視Adobe Campaign Standard的最新[檔案更新](../../rn/using/documentation-updates.md)。 如果您想尋找較新的版本，請參閱此[page](../../rn/using/release-notes.md)。

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
   <td> 疲勞管理可讓您建立疲勞規則，以管理使用設定檔的過度通訊。 疲勞規則可輕鬆建立，但具有極其彈性的功能，例如跨多個通道計算訊息（包括交易式訊息）、僅計算特定傳送，或將規則套用至特定設定檔。<br /> 如需詳細資訊，請參閱詳 <a href="../../sending/using/fatigue-rules.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 內容建立：從URL<br />匯入 </td> 
   <td> 從URL匯入可讓您快速從網站擷取創意內容，以建立任何傳送的電子郵件。 此外，您還可讓協力廠商直接透過URL共用內容，以簡化創意流程。 匯入的內容可以彈性地用作單一傳送的一部分，或在範本層級，確保所有相關行銷活動的品牌一致性（無論是以工作流程為基礎或交易式訊息），並包括A/B或多變數測試。 從URL匯入會自動轉換及追蹤所有連結，以透過動態報告來監控電子郵件效能。<br /> 如需詳細資訊，請參閱詳 <a href="../../designing/using/using-existing-content.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 修正了無法正確解壓縮大型壓縮檔案的問題。
* 品牌管理的安全性已改善。 修改品牌名稱和寄件者地址現在已保留給Adobe技術管理員。
* 為了改善安全性，使用者產生的內容（影像、鏡像頁面、登錄頁面等） 無法再由adobe.com網域提供。 現在，您必須透過品牌推廣，使用自己的網域來處理這些資源。
* 修正顯示及篩選行銷活動時的介面問題。
* 修正無法以POST重設API呼叫更新訂閱日期欄位的問題。

_電子郵件、簡訊和直接郵件_

* 修正無法定位訊息中清單類型對象，導致準備失敗的問題。
* 多語言電子郵件傳送功能中新增的遺漏語言。
* 現在，當使用者修改內容並儲存時，顯示在傳送控制面板上的內容縮圖會自動更新。
* 修正無法開啟傳送的時區相關問題。

_推播通知_

* 設定推播通知通道時，iOS的推播提供者平台應為&#x200B;**apns**&#x200B;和Android **gcm**。
* 修正無法在Adobe Campaign介面中新增iOS行動應用程式的錯誤。
* 現在啟用GCM和FCM的Android行動應用程式均支援推播通知。
* 修正複製推播通知範本時無法儲存內容的錯誤。
* 現在，您可以協調行動應用程式使用者的資料，從Adobe Campaign資料庫建立或更新設定檔。
* Adobe Campaign現在會優先處理交易推播通知，而非標準推播通知。

_報告_

* 修正無法在電子郵件內容中顯示熱門點按百分比的問題。
* 修正封鎖清單量度計為硬跳出而非跳出的問題。
* 修正導致摘要資料中顯示負數的問題。
* 修正計算錯誤年齡區段中之設定檔的問題。
* 軟跳出和硬跳出計算公式已改變。

_工作流程_

* 修正&#x200B;**[!UICONTROL Load file]**&#x200B;活動中手動新增和移除活動中的欄後，可能導致錯誤的問題。
* **[!UICONTROL deliverabilityUpdate]**&#x200B;技術工作流程現在排程在伺服器時間凌晨2:00執行。
* 修正允許在不具有匯出角色的情況下執行清單匯出的安全性問題。
* 修正&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動的問題。
* 修正&#x200B;**[!UICONTROL File Transfer]**&#x200B;活動中使用萬用字元的問題。

_設定檔與對象_

* 修正在某些情況下無法正確考慮查詢條件，而導致錯誤結果的問題。
* 修正如果設定檔是已準備但從未傳送及過期的訊息中的目標定位，則無法存取的問題。

_整合_

* 修正無法為觸發器建立的某些資料來源正確顯示及選取的問題。

_自訂資源_

* 修正清單畫面中，可顯示自訂資源列而不含任何資料的問題。
* 修正自訂資源中無法顯示具有「False」值的布林類型欄位的問題。

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
   <td> 推出18種全新、回應式的範本，以Astro和Feather這兩種美觀的主題設計。 這些可自訂的範本不受產業限制，且隨時可供使用。 範本包含各種使用案例的內容，讓您以前所未有的快速、有效和精美方式設計和傳遞電子郵件行銷活動。<br /> 如需詳細資訊，請參閱詳 <a href="../../designing/using/using-reusable-content.md#content-templates">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用設定檔資料進行動態報告<br /> </td> 
   <td> 動態報告提供完全可自訂的即時業務報告。 透過此版本，動態報告的強大增強功能新增了對設定檔資料的存取權，除了功能性電子郵件促銷活動資料（例如開啟和點按）外，還能依設定檔維度（例如性別、城市、郵遞區號和年齡）進行人口統計分析。 透過相同簡單易用的拖放介面，判斷電子郵件促銷活動對最重要客戶群體的執行方式比以往更為輕鬆。<br /> 如需詳細資訊，請參閱詳 <a href="../../reporting/using/about-dynamic-reports.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 原始日期成批訂閱<br /> </td> 
   <td> 透過此大量訂閱增強功能，您現在可以透過工作流程中的訂閱服務活動，直接將訂閱資訊（來源和日期）儲存在Adobe Campaign Standard資料庫中。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/subscription-services.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 有些客戶需要能善用來自Adobe Campaign Standard的ID，因為他們不需要管理唯一索引鍵來識別自己的記錄。 此ID(**ACS ID**)可匯出，也可在更新資料時作為調解金鑰使用。 如需詳細資訊，請參閱[詳細文件](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。
* FTP通訊協定即將淘汰。 您現在應改用SFTP。 為了不封鎖現有實作，FTP上的現有設定仍如以前般運作，但新活動不會顯示選項。

_電子郵件、簡訊和直接郵件_

* 現在可以建立新的警報標準，以便在傳送警報通知中使用這些標準。 如需詳細資訊，請參閱[詳細文件](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 傳送警報通知有新的設計，傳送警報控制面板的使用者體驗已改善。
* 現在，當傳送外部帳戶遭停用時，受影響的傳送（電子郵件、簡訊及推播）中會顯示警告，而且這些傳送中會隱藏&#x200B;**預覽**&#x200B;按鈕。
* 修正在主旨行中啟用動態文字時，造成電子郵件內容的A/B測試預覽錯誤的問題。

_異動訊息_

* 現在可以定義您要在何時傳送後續訊息，例如在傳送交易式訊息後3天。 如需詳細資訊，請參閱[詳細文件](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。
* 現在可以定義應傳送連結至事件的交易式訊息的開始日期。
* 修正在刪除連結至已接收和已處理事件的設定檔後，執行包含後續訊息的工作流程時，造成SQL錯誤的問題。
* 修正無法刪除連結至事件的設定檔的錯誤。
* 修正了無法重新導向追蹤連結的問題。
* 修正無法停用電子郵件或簡訊中特定連結的追蹤的問題。

_報告_

* 改善「**熱點點按**」報表。 此外，現在可以根據傳送中定義的每個條件式內容顯示熱門點按，並針對每次執行循環傳送或交易式訊息顯示熱門點按。 如需詳細資訊，請參閱[詳細文件](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 修正隔離量度無法擷取正確資料的問題。
* 日曆介面工具集新增了新的預設時間範圍。
* [動態報表量度](../../reporting/using/indicator-calculation.md)和[促銷活動的KPI](../../sending/using/confirming-the-send.md)（顯示在已傳送訊息的控制面板上）已對齊，以提高一致性。
* 修正debian 7上可能導致管道當機的問題。

_工作流程_

* 修正了導入的檔案保留無法運作的問題。

_整合_

* Analytics與Campaign整合現在支援eVar和事件。
* 傳送包含已放棄購物車內容的電子郵件時，從購物車中移除之元素的裝載參數現在為選用。

_設定檔與對象_

* Adobe Campaign現在提供顯示作用中設定檔數目的報表。 此報表僅提供資訊，對帳單沒有直接影響。 如需詳細資訊，請參閱[詳細文件](../../audiences/using/active-profiles.md)。
* 修正使用「設定檔與服務API」時，設定檔無法訂閱服務的問題。

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
   <td> 多語言電子郵件和簡訊傳送<br /> </td> 
   <td> 根據您自動細分客戶偏好的語言，透過單一傳送定義並執行多語言電子郵件和簡訊傳送。 報告每次傳送的效能，包括語言和個別層級。<br /> 隨著內外內容的發展，越來越多的公司面臨著以多種語言提供內容的挑戰。因此，精簡本地化報文傳送是跨國公司有效客戶溝通戰略的關鍵部分；多語言國家/地區的公司；以及想要在語言層級進一步個人化其內容的公司，無論客戶位於何處。 如需詳細資訊，請參閱<a href="../../channels/using/creating-a-multilingual-email.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign通知<br /> </td> 
   <td> 直接在Adobe Campaign Standard內接收有關重要系統活動的通知。 例如，系統會通知您進行中傳送的進度，或工作流程發生錯誤時。<br /> 即時通知可隨時向相關利害關係人提供相關資訊，讓使用者能夠立即直接從應用程式內對活動通知採取行動。團隊的結果是進階的靈活性、效率，以及更順暢的行銷活動執行。 如需詳細資訊，請參閱<a href="../../administration/using/sending-internal-notifications.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送警報<br /> </td> 
   <td> 除了直接在Adobe Campaign Standard中檢視通知外，Adobe Campaign現在也提供電子郵件警報系統，以針對重要系統活動向使用者或外部利害關係人觸發電子郵件警報。 建立、管理和接收可自訂的警報和控制面板，以追蹤傳送的成功或失敗。<br /> Adobe Campaign傳送警報透過電子郵件和控制面板，讓公司中所有參與的Adobe Campaign使用者自動得知傳送執行狀態，進而提高效率。如需詳細資訊，請參閱<a href="../../sending/using/receiving-alerts-when-failures-happen.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 資料源中的加密聲明ID<br /> </td> 
   <td> 使用加密的連絡資訊（電子郵件地址或電話號碼）做為宣告ID，即可直接傳送電子郵件和簡訊觸發器，而不需要Campaign中的現有設定檔。 因為Adobe Campaign Standard可解碼加密宣告ID,Campaign現在可以在接收來自其他Experience Cloud解決方案（包含先前未知的連絡人）的閱聽眾時，建立新的可行銷設定檔。<br /> 透過電子郵件和簡訊即時鎖定客戶和未知潛在客戶，分別提升現有客戶群的忠誠度和贏取新客戶。潛在客戶一經驗證，並在Adobe Campaign中運用這些深入分析後，即可充分利用您的第一方Cookie資料(來自Adobe Audience Manager*)。 <br /> *需要Adobe Audience Manager。如需詳細資訊，請參閱<a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 從Campaign將KPI共用至Analytics<br /> </td> 
   <td> 與Adobe Analytics共用行銷活動資料，以測量Campaign的電子郵件行銷量度，以及透過轉換的其他行銷和廣告工作，統一點按前和點按後行為。<br /> 直接追蹤整體效能，並發現與Analytics中外部程式的協同效應。將您從此整合檢視中學到的內容套用回行銷活動中；最終改善開放、點進和轉換率，提升收入和整體促銷活動績效。 <br /> Adobe Analytics為必要項目。如需詳細資訊，請參閱<a href="../../integrating/using/about-campaign-analytics-integration.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 直接郵件通道 — 返回給發件人<br /> </td> 
   <td> 現在支援與包含「回傳至寄件者」資訊的直接郵件提供者進行一般檔案交換。 這項對「直接郵件」管道的增強功能可將對應的郵遞區號排除在未來通訊之外。<br /> 這可讓行銷人員收到不正確地址的通知，並透過其他管道與客戶互動，或鼓勵他更新其郵遞區號。這也可減少行銷人員避免將郵件傳送至錯誤地址時浪費的行銷資金數量。 <br /> 「直接郵件」可作為附加通道使用。如需詳細資訊，請參閱<a href="../../channels/using/return-to-sender.md">詳細文件</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 修正允許任何使用者匯出清單的問題。 現在，僅允許具有&#x200B;**[!UICONTROL Export]**&#x200B;角色的使用者。

_電子郵件、簡訊和直接郵件_

* 修正了&#x200B;**updateDeliveryExecInfo**&#x200B;工作流程的問題，該工作流程將SMS傳送的&#x200B;**傳送**&#x200B;指標設為0。
* 在傳送範本屬性的&#x200B;**進階參數**&#x200B;中，**Routing**&#x200B;下拉式清單現在只會顯示與範本訊息類型對應的外部帳戶。 例如，電子郵件傳送範本只會顯示電子郵件外部帳戶。
* 修正針對測試設定檔定義之&#x200B;**[!UICONTROL Text]**&#x200B;偏好電子郵件格式的問題。
* 修正在傳送的排程定義畫面中選取預設時區時，導致Javascript錯誤的問題。
* 修正傳送記錄檔中無法顯示陷阱的問題。
* 在傳遞建立精靈的範本選取畫面中，現在預設會隱藏後續和A/B測試範本。 有關詳細資訊，請參閱[詳細文檔](../../channels/using/creating-an-email.md)。
* 修正讓任何使用者傳送傳遞的問題。 現在，僅允許具有&#x200B;**[!UICONTROL Start deliveries]**&#x200B;角色的使用者。 有關詳細資訊，請參閱[詳細文檔](../../sending/using/confirming-the-send.md)。

_推播通知_

* 修正&#x200B;**促銷活動追蹤端點** URL無法報告的問題。
* 修正推播通知標題無法在Android裝置上顯示的問題。
* 修正當推播通知僅包含標題（而訊息內文中無任何內容）時，無法在iOS裝置上顯示推播通知的問題。
* 修正強制追蹤傳送中的媒體附件URL，而無法將視訊和圖片嵌入傳送的問題。 依預設，推播通知的mediaAttachmentURL類型的URL追蹤現已停用。

_報告_

* 修正圖表和表格之間出現不同值的問題。
* 修正推送通知值顯示為電子郵件值的問題。
* 修正在促銷活動外部建立傳遞時，將值顯示為未知的問題。
* 修正將SMS報表資料顯示為行動應用程式資料的問題。

_工作流程_

* 您現在可以篩選工作流程記錄（時段和文字搜尋）。 有關詳細資訊，請參閱[詳細文檔](../../automating/using/monitoring-workflow-execution.md)。
* 工作流程傳送中現在提供選項，以在傳送前停用確認。
* 修正無法在循環傳送的建立精靈中設定出站轉變的問題。
* 修正使用基於自訂資源欄位的工作流程查詢活動，搭配列舉具有大量值時發生的問題

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
   <td> 突破數位障礙，透過Adobe Campaign Standard的第一個離線頻道Direct Mail連線至實體世界。 此功能可讓您個人化並產生直接郵件提供者所需的檔案，以便納入跨通道行銷活動。 利用「直接郵件」，透過引人入勝的觸控點，將客戶引導至您的應用程式、網站或商店，重新與客戶互動或提升客戶體驗。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/about-direct-mail.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 電子郵件密件副本<br /> </td> 
   <td> 電子郵件密件副本可儲存傳送給個別收件者的唯一電子郵件訊息，讓品牌可封存這些訊息。 透過將密件副本電子郵件地址新增至所有電子郵件，Adobe Campaign Standard客戶可透過此功能保留每個電子郵件的完整副本。 這是金融服務行業的常見法律要求，有助於客戶服務中心即時解決衝突。<br /> 如需詳細資訊，請參閱詳 <a href="../../sending/using/archiving.md">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_介面更新_

* 在頂端列中，**[!UICONTROL Timeline]**&#x200B;連結已移除，並取代為&#x200B;**[!UICONTROL Programs & Campaigns]**&#x200B;的連結。

_電子郵件和簡訊_

* 修正&#x200B;**[!UICONTROL Retry in progress]**&#x200B;傳送狀態顯示錯誤顏色的問題。 顏色是灰色而非藍色。

_工作流程_

* 修正將動作變更為在&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動中執行時發生的問題。

_報告_

* **[!UICONTROL Spam]**&#x200B;和&#x200B;**[!UICONTROL Spam rate]**&#x200B;指標計算已更改。
* 已改善&#x200B;**[!UICONTROL Bounce]**&#x200B;量度，以獲得更精確的結果。

_推播通知_

* 修正無法點按設定檔行銷歷史記錄中推送事件的問題。
* 改善工作流程中推播通知的使用方式。

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
   <td> 您現在可以存取Creative SDK提供的完整功能集，以在編輯電子郵件或登錄頁面時，直接在內容編輯器中增強影像。<br /> 此功能不需要購買其他Creative Cloud解決方案。<br /> 如需詳細資訊，請參閱詳 <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 異動推送通知<br /> </td> 
   <td> 行動應用程式通道已新增至Adobe Campaign的交易訊息功能。 交易式訊息現在支援三個通道：電子郵件、簡訊和推播通知。<br /> 如需詳細資訊，請參閱詳 <a href="../../channels/using/transactional-push-notifications.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 循環推播通知<br /> </td> 
   <td> 您現在可以在工作流程中設定循環推播通知。 在客戶預期會定期更新（例如每週提醒以結帳新內容或促銷活動）的情況下，您可以使用循環推播通知。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/push-notification-delivery.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service(S3)連接器<br /> </td> 
   <td> Amazon Simple Storage Service(S3)連接器現在可用來匯入或匯出資料至Adobe Campaign。 可在工作流程活動中設定。 設定是在外部帳戶中完成。<br /> 如需詳細資訊，請參閱詳 <a href="../../administration/using/external-accounts.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver整合live<br /> </td> 
   <td> Adobe Campaign與Dreamweaver的整合現已上線。 現在可與官方上次發行的Dreamweaver版本(17.0.2)搭配使用。<br /> 您必須從以下位置安裝Adobe Campaign整合擴充功能： <a href="https://adobe.ly/acdw_addon">https://adobe.ly/acdw_</a><br /> addon如需詳細資訊，請參閱此 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hant">影片</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 修正記憶體耗用問題。

_電子郵件和簡訊_

* 修正預覽訊息時，無法將內容正確同步至最新變更的問題。
* 修正無法建立或刪除MX或網域電子郵件處理規則的問題。
* 修正了無法傳送多別名電子郵件的問題。
* 修正傳送的傳送記錄中無法顯示補漏白傳送記錄的問題。
* 修正顯示傳送的追蹤URL而內容中沒有URL時導致錯誤的問題。
* 修正無法在已傳送訊息中正確套用影像大小屬性的問題。

_異動訊息_

* rtEventHistoId欄位不再以個人化欄位形式公開於交易式訊息範本中。

_登陸頁面_

* 我們已最佳化登錄頁面中使用的&#x200B;**[!UICONTROL by email]**&#x200B;篩選器，以調解新訂閱者與資料庫設定檔。
* 修正在表單設定中使用布林值欄位時，顯示自由文字輸入而非核取方塊的問題。
* 修正無法產生登錄頁面縮圖的問題。

_工作流程_

* 修正編輯&#x200B;**[!UICONTROL End]**&#x200B;或&#x200B;**[!UICONTROL External Signal]**&#x200B;活動時（僅限Safari上）的顯示錯誤。
* 改善編輯包含錯誤對象的&#x200B;**[!UICONTROL Read Audience]**&#x200B;活動時顯示的錯誤訊息。
* 修正執行訂閱活動時可能導致SQL錯誤的問題。

_整合_

* 地標資料：修正計算位置訂閱者數時發生的錯誤。

_對象與查詢_

* 修正無法在查詢編輯器中的集合上使用總和和平均匯總的問題。
* 修正了在變更篩選器資源後，查詢編輯器無法重新載入的問題。

_報告_

* 修正在表格中選取多列時，無法正確計算開放率量度的問題。
* 修正僅將量度顯示為整數值的錯誤。 量度現在可以顯示為小數。

_推播通知_

* 修正建立連結至行動應用程式且無法在MCPNS上建立的Android應用程式時，未顯示錯誤訊息的問題。
* 修正允許使用者將音效新增至無提示通知的問題。

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
   <td> 動態報告提供新一代完全可自訂的即時業務報告。 此功能可讓您根據視覺化的動態樞紐表格和圖形，拖放變數和維度，以分析行銷活動的效率和效益。 動態報告也可讓您從草稿開始建立自己的業務報告，並儲存以供日後使用。<br /> 如需詳細資訊，請參閱詳 <a href="../../reporting/using/about-dynamic-reports.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver整合(Labs)<br /> </td> 
   <td> 透過Adobe Campaign和Dreamweaver整合，您現在擁有整合的程式，可透過Adobe解決方案建立電子郵件行銷活動。<br /> 您可以在Dreamweaver中編輯Adobe Campaign電子郵件，並讓內容在兩個解決方案之間順暢同步。<br /> 在初始版本中，整合是以「Labs」功能的形式提供，且僅適用於Dreamweaver搶鮮版測試版。如果您想要啟用它，請聯繫AC-DW-integration@adobe.com。<br /> 如需詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">此影片</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 手動發送時間優化<br /> </td> 
   <td> 您現在可以手動定義每個收件者的自訂傳送時間 — 在傳送層級或使用工作流程。 <br /> 有兩個新選項可供使用：  <br /> 
    <ul> 
     <li> 所有收件者都會收到訊息，其時區已納入考量。 </li> 
     <li> 每個收件者在公式定義的計算日期和時間接收訊息。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../sending/using/optimizing-the-sending-time.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播通知新功能<br /> </td> 
   <td> 推播通知通道已增強，並具備數項新功能：<br /> 
    <ul> 
     <li> 全新製作介面 </li> 
     <li> 靜默通知 </li> 
     <li> 互動式推播 </li> 
     <li> 豐富內容支援 </li> 
     <li> 有效負載大小計算器 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../channels/using/about-push-notifications.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：新信號活動<br /> </td> 
   <td> 使用新的<span class="uicontrol">Signal</span>活動，從另一個工作流程觸發工作流程。<br /> 您現在可以從另一個工作流程開始，支援更複雜的客戶歷程。您可以更妥善地監控客戶歷程，並在發生問題時作出反應。<br /> 已更新數個工作流程活動：<br /> 
    <ul> 
     <li> <span class="uicontrol"></span> 結束活動：新索引標籤可讓您指定在此活動執行後觸發的工作流程。 </li> 
     <li> <span class="uicontrol">更新</span> 資料活動：使用新的空的匯出轉變來新增觸發另 <strong></strong> 一個工作流程的結束活動。空的出站轉變不會攜帶任何資料，也不會佔用系統上不必要的空間 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../automating/using/external-signal.md">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流程：新讀取閱聽眾活動<br /> </td> 
   <td> 從您可以輕鬆選取並調整單一活動的現有對象開始鎖定目標程式。<br /> 如需詳細資訊，請參閱詳 <a href="../../automating/using/read-audience.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 地標資料<br /> </td> 
   <td> 地標資料整合了Adobe Campaign與Adobe Analytics for Mobile。 當使用者開啟品牌的應用程式時，品牌可從使用者的行動位置收集資料（稱為<strong>地標</strong>）。 這可讓品牌運用Adobe Campaign工作流程，根據使用者位置傳送個人化訊息。 此管道會運用行動核心服務的SDK。<br /> 請注意，使用此功能需要Analytics for Mobile（付費解決方案）。<br /> 如需詳細資訊，請參閱詳 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API<br /> </td> 
   <td> 任何層級連結至設定檔或服務資源的資源，現在都可在API中使用。<br /> 如需詳細資訊，請參閱詳 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">細檔案</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* 現在可以在匯出傳送記錄檔時新增設定檔資料。

_電子郵件和簡訊_

* 修正即使取消勾選&#x200B;**[!UICONTROL Request confirmation before sending messages]**&#x200B;選項並儲存傳送後，選項仍維持選取狀態的問題。
* 修正無法取消發佈交易式電子郵件的問題。
* 修正預覽傳送前無法與最新變更正確同步內容的問題。

_登陸頁面_

* 修正在登錄頁面的內容中按一下時，使用者無法編輯的錯誤。

_工作流程_

* 修正了無法讀取&#x200B;**[!UICONTROL Load file]**&#x200B;活動之拒絕轉變內容的問題。
* 修正在設定&#x200B;**[!UICONTROL Load file]**&#x200B;活動時，無法正確考慮已交換欄的問題。

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
   <td> 匯出傳送和追蹤記錄等記錄檔，以便在您偏好的報表或BI工具中處理。 您可以使用簡單的工作流程搭配增量查詢來自動定期匯出新記錄檔。<br /> 除了資源選擇器中的日誌資源可用性外，還對增量查詢和提取檔 <a href="../../automating/using/incremental-query.md">案活</a> 動進 <a href="../../automating/using/extract-file.md">行了</a> 增強：<br /> 
    <ul> 
     <li> <span class="uicontrol">增量</span> 查詢現在可讓您使用日期欄位來擷取新資料或更新的資料。以前，即使自上次執行以來更新了先前執行的所有結果，這些結果也會自動排除。 </li> 
     <li> <span class="uicontrol">擷</span> 取檔案現在會匯出分項清單的標籤，而非ID。 </li> 
    </ul> 管理員可存取所有地理和組織單位，使用這些活動。<br /> 如需匯出記錄檔的詳細資訊，請參閱 <a href="../../automating/using/exporting-logs.md">詳細檔案</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易式訊息的行銷功能<br /> </td> 
   <td> 行銷人員現在可以根據客戶行銷設定檔傳送交易式訊息。 這可讓使用者：<br /> 
    <ul> 
     <li> 套用行銷類型規則，例如<span class="uicontrol">封鎖清單上的位址</span> 。 </li> 
     <li> 在訊息中包含取消訂閱連結。 </li> 
     <li> 將交易式訊息新增至全域傳送報告。 </li> 
     <li> 在客戶歷程中善用交易式訊息。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">詳細文件</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易式傳訊API<br /> </td> 
   <td> 交易式訊息API現在可透過<a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>使用，更方便使用和監控：<br /> 
    <ul> 
     <li> 您可以從adobe.io平台報告和監控功能中受益。 </li> 
     <li> 驗證現在是使用adobe.io代號型驗證（而非IP允許清單）來執行，讓安全性程式更簡單。 </li> 
     <li> 所有API現在都整合在單一平台上，如果您已支援設定檔和服務API，可讓您將交易式訊息功能新增至整合比以往更簡單。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_一般_

* **[!UICONTROL Access authorization]**&#x200B;選項已返回至登錄頁面屬性。
* 修正可能導致呈現舊影像而非正確影像的問題。 如果傳送或登錄頁面的內容定義中已更新來源影像，就會發生此問題。
* 修正使用者無法編輯現有SFTP外部帳戶中特定欄位的問題。
* 修正數個UI問題。 例如，使用者現在可以編輯設定檔屬性並儲存修改，而不會遇到UI的問題。

_電子郵件和簡訊_

* 修正與具有包含

_推播通知_

* 修正了無法將應用程式回傳至Adobe Campaign伺服器的問題。
* 修正了可能無法將&#x200B;**[!UICONTROL Play a sound]**&#x200B;和&#x200B;**[!UICONTROL Custom fields]**&#x200B;納入Android的問題。
* 修正可能導致在用於表情符號的Unicode字元中新增額外逸出字元的問題。
* 將訂閱者的註冊代號新增至封鎖清單時，現在會立即更新Adobe Campaign中應用程式訂閱者清單中的對應狀態。

_工作流程_

* 修正事件資源（例如rtEvent）上無法預覽查詢的問題。
* **[!UICONTROL Load file]**&#x200B;活動產生的拒絕檔案現在可以在其出站轉變中擷取，並在下一個活動中處理。 例如，透過使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;的SFTP伺服器上傳拒絕檔案。
* 修正若在&#x200B;**[!UICONTROL Segmentation]**&#x200B;的&#x200B;**[!UICONTROL General]**&#x200B;標籤中選取&#x200B;**[!UICONTROL Temporary resource]**，使用者無法限制區段母體的問題。
* **[!UICONTROL Scheduler]** 活動無法再設為每10分鐘觸發工作流程多次。
* 修正了可能導致&#x200B;**[!UICONTROL Use common columns]**&#x200B;在&#x200B;**[!UICONTROL Union]**&#x200B;活動中無法正常運作的問題。

_整合_

* 修正在Adobe Campaign中部署事件觸發器時，可能導致錯誤的問題。 在Adobe Marketing Cloud中，將「30天內回傳的可能性」中繼資料新增至「放棄」觸發器時，即會發生此錯誤。
* 修正從People核心服務匯入對象時，技術工作流程可能會清除「目標Dimension」欄位的問題。 後續查詢無法擷取匯入的對象。
* 修正當核取選項&#x200B;**[!UICONTROL Share in Adobe Marketing Cloud]**&#x200B;時，可能導致工作流程的&#x200B;**[!UICONTROL Save audience]**&#x200B;活動失敗的問題。
