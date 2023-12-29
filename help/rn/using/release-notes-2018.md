---
title: 發行說明 2018 年
description: 本頁列出 2018 年的所有 Adobe Campaign Standard 版本。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '5386'
ht-degree: 3%

---

# 發行說明 2018 年{#release-notes}

## 發行版本 18.9 – 2018 年 9 月 {#release-18-9---september-2018}

**有哪些新功能？**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 應用程式內傳訊(Beta)<br /> </td> 
   <td> 應用程式內傳訊功能可讓您提供情境式互動，並觸及停用推播通知的使用者，更有效與行動應用程式使用者互動。 搭配推播通知使用應用程式內傳訊，建立高度個人化和相關的體驗。 這可讓您的應用程式使用者獲得更好的轉換和保留率。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/about-in-app-messaging.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式的Adobe Launch整合（測試版）<br /> </td> 
   <td> 透過Adobe Campaign整合Adobe Launch現在採用Mobile SDK V5，簡化並自動化Campaign的行動應用程式啟用流程。<br /> 如需詳細資訊，請參閱 <a href="https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html">詳細檔案</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* Adobe Campaign Standard現在支援Amazon S3 API第4版。

**其他變更**

* 在broadlog中，現在連線數目上限和每小時訊息數上限之間有所差異。 當達到限制時，就可以知道輸送量為何受限。 先前，相同的訊息（「達到配額」）會套用至兩種情況。
* 在Campaign中設定行動應用程式時，使用者現在可以知道iOS憑證和Android伺服器金鑰是否已成功上傳及其到期日。

  如需詳細資訊，請參閱有關如何使用設定行動應用程式的詳細檔案 [SDK V4](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html) 和 [SDK V5](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html).

* 在定義促銷活動屬性時，藉由選取行動應用程式來鎖定特定行動應用程式上的使用者。 此功能同時適用於推送和應用程式內傳訊頻道。

  如需詳細資訊，請參閱[詳細文件](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)以瞭解詳情。

* 使用Creative Designer介面選取內容區塊時，現在會載入並顯示清單中的所有內容區塊。 (CAMP-27311)

  有關詳細資訊，請參閱 [詳細檔案](../../designing/using/personalization.md#adding-a-content-block).

**修補程式**

* 修正電子郵件控制面板與異動電子郵件的電子郵件摘要報告之間記錄計數不一致的問題。 (CAMP-28237
* 修正工作流程中，透過檔案傳輸活動匯入檔案時可能顯示錯誤訊息的問題。 (CAMP-27435)
* 修正包含超過25項服務的登入頁面，導致在表單中隨機取消選取服務的問題。 (CAMP-26572)
* 修正工作流程中，使用檔案傳輸活動時無法以SFTP URL設定外部帳戶的問題。 (CAMP-26475)
* 修正無法更新服務摘要報表的問題。 (CAMP-26301)
* 修正使用擴充活動時，工作流程中導致自訂欄位無法顯示正確日期的問題。 (CAMP-26242)
* 修正透過檔案匯入匯入時，無法更新服務訂閱日期的問題。
* 修正載入檔案活動的錯誤，該錯誤阻止工作流程匯入檔案(CAMP-27068)。
* 修正了在服務摘要報告中顯示錯誤訂閱數量的問題(CAMP-25587)。
* 修正Adobe Analytics和Adobe Campaign報表之間資料不一致的問題。 (CAMP-25393)
* 修正限制存取使用者無法登入的問題。 (CAMP-27381)
* 修正使用Creative Designer編輯電子郵件時，無法顯示Adobe Experience Manager內容清單的問題。 (CAMP-27181)
* 修正無法開啟Creative Designer而導致錯誤的問題。 (CAMP-27304)
* 修正使用Internet Explorer 11時，拖放作業無法在Creative Designer中正常運作的問題。
* 修正從相機上傳並以直向模式拍攝的圖片在不需要的旋轉位置顯示的問題。
* 修正在Creative Designer中使用查詢編輯器介面時，顯示不清楚選取專案資訊的問題。
* 修正在Creative Designer中使用查詢編輯器介面時，無法正確複製元素的問題。
* 修正即使收件者已透過自動回覆取消訂閱，仍持續傳送SMS訊息給封鎖清單上收件者的問題。 (CAMP-27128)
* 修正無法顯示造成錯誤的問題。 **資料庫清理** 工作流程失敗。 (CAMP-26876)
* 修正無法刪除推播通知定義中自訂欄位的問題。 (CAMP-25588)

## 發行版本 18.7 – 2018 年 7 月 {#release-18-7---july-2018}

**有哪些新功能？**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Android推播通知的高優先順序旗標<br /> </td> 
   <td> Android的高優先順序旗標 — 啟用對Android應用程式傳送高優先順序的推播通知，這會導致睡眠裝置喚醒並執行某些有限處理。 請注意，預設優先順序為「正常」，可能會延遲訊息傳送以節省電池。 <br /> 如需詳細資訊，請參閱 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 適用於行動應用程式訂閱者的型別篩選器<br /> </td> 
   <td> 型別篩選器中的支援訂閱 — 為型別規則指定篩選條件時，可以選取應用程式訂閱作為篩選和定位維度，為具有或不具有設定檔的使用者提供篩選屬性的功能。 <br /> 如需詳細資訊，請參閱 <a href="../../sending/using/about-typology-rules.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息準備期間從URL自動匯入內容<br /> </td> 
   <td> 現在，您可以在準備階段從URL匯入電子郵件內容。 對於循環電子郵件傳遞，每當準備訊息時會擷取最新的HTML內容，以確保在傳送電子郵件時內容永遠為最新。 此功能也可讓您從URL建立包含內容的排程傳送，即使內容尚未準備就緒。<br /> 如需詳細資訊，請參閱 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign發行通知訊息<br /> </td> 
   <td> 當執行個體升級至新版本後，當使用者登入時，現在會出現快顯訊息。 此訊息會指出版本編號，並包含發行說明的連結。 您可以選擇隱藏訊息，直到下一次發行為止。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 使用者管理<br /> </td> 
   <td> 從18.7版開始，新Campaign Standard執行個體以及未建立地理單位的現有執行個體現在無法使用地理單位功能。<br /> 如需詳細資訊，請參閱此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hant#release-notes">頁面</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* Adobe Campaign和Adobe Target整合現在可讓您運用Target的 [許可權](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html) 功能。 在電子郵件中加入Adobe Target的動態影像時，您現在可以指定Target屬性（at_property程式碼）。
* GDPR隱私權存取/刪除請求現在會考量具有設定檔資源擁有複製連結的自訂資源。 針對1個基數簡易連結和N個基數集合連結，您必須在自訂資源中選取「刪除/複製目標籤錄表示刪除/複製連結參考的記錄」。 對於0或1個基數簡單連結，選取「刪除/複製記錄表示刪除/複製連結參照的目標籤錄」。

**其他變更**

* 報告共用逾時已從一分鐘增加至四分鐘，以避免發生任何逾時錯誤。
* 編輯電子郵件內容時，新的Creative Designer預設為開啟。 如果願意，您仍然可以在儲存變更後隨時返回預設內容編輯器。 有關詳細資訊，請參閱 [詳細檔案](../../designing/using/designing-content-in-adobe-campaign.md).
* 在Creative Designer中，新的內容元件現在可以新增到電子郵件中：輪播。 有關詳細資訊，請參閱 [詳細檔案](../../designing/using/designing-from-scratch.md#about-content-components).
* 在交易式訊息的熱鍵報告中，當您按一下 **變更設定檔** 按鈕，現在只會列出連結至您為交易式訊息定義之事件的測試設定檔。

**修補程式**

* 修正byEmail查詢篩選器無法傳回任何結果的問題。 (CAMP-23420)
* 修正允許標準使用者存取限制給管理員的特定功能或畫面的問題(/rest/head/&#42; 端點、異動訊息畫面、設定檔與對象匯入畫面)。
* 修正GDPR隱私權刪除請求無法處理自訂資源（若名稱以數字開頭）的問題。
* 修正導致「儲存對象」活動無法在Adobe Experience Cloud中共用應用程式訂閱者的錯誤。
* 修正檔案名稱包含空格時，檔案傳輸活動可能發生的問題。 (CAMP-25936)
* 修正工作階段過期後使用重新連線按鈕時可能發生的問題。 (CAMP-25560)
* 修正傳送與疲勞規則相關聯時區最佳化的傳遞時，可能導致排除的問題。 (CAMP-25425)
* 修正使用API GDPR功能時，無法刪除具有0-1型別連結之資料的問題。
* 修正取消疲勞型別規則版本時可能導致錯誤訊息的問題。
* 修正編輯傳送內容後，預覽傳送內容時可能發生的問題。
* 修正使用「解壓縮」選項時處理CSV zip檔案時可能發生的問題。
* 修正Creative Designer中，將內建樣式的部分文字變更為連結或編輯該連結時，造成不想要的顏色字型和格式的問題。 (CAMP-26001)
* 修正熱點選報告無法顯示包含動態內容之傳送中每個條件的百分比的問題。 以前，只顯示對預設變體的點選。

## 發行版本 18.6 – 2018 年 6 月 {#release-18-6---june-2018}

**功能改進**

* 此 **[!UICONTROL History]** API已新增至Adobe.IO。 它可讓您存取與設定檔行銷記錄相關的資訊：接觸點數目、已傳送內容、映象頁面URL等。 有關詳細資訊，請參閱 [專用使用案例](../../api/using/interacting-with-marketing-history.md) .
* 此 **[!UICONTROL Database cleanup]** 技術工作流程已最佳化，以確保資料庫備份有更優異的效能。
* 適用於電子郵件的Creative Designer現在也提供法文和德文版。

**其他變更**

* A **[!UICONTROL Compute stats]** 按鈕已新增至 **[!UICONTROL Deployment]** 已傳送傳遞的視窗。 它可讓您擷取最新的KPI，例如，如果傳送的結果更新時間過長或未考慮在內。 如需詳細資訊，請參閱本[區段](../../sending/using/confirming-the-send.md)。
* 在 **傳遞能力更新** 現成可用的技術工作流程，功能管理員現在可以在 **更新規則** javascript活動。 預設情況下，欄位值設為0，這表示將忽略所有錯誤。
* 已最佳化管理單位存取限制條件時所產生的SQL。
* 此 **[!UICONTROL Update]** 活動現在可讓您新增、更新或刪除與訂閱相關的資料（nms：appSubscriptionRcp表格）。
* 此 **[!UICONTROL Update delivery execution]** 為了最佳化效能，技術工作流程已分成兩個工作流程： - **[!UICONTROL Update delivery execution]**：更新傳送的追蹤。 預設會每10分鐘啟動一次。 **[!UICONTROL Update delivery indicators]**：更新傳送的KPI，預設會每小時啟動一次。 如需技術工作流程的詳細資訊，請參閱本 [區段](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* 當傳遞傳送訊息時，狀態 **[!UICONTROL Deployment]** 部分現在可以有兩個值： **[!UICONTROL Sending]**：正在傳送訊息。 **[!UICONTROL Sending (retry)]**：正在重新嘗試階段。
* 使用者具有 **[!UICONTROL Delivery preparation]** 角色現在可以傳送校樣。 (CAMP-24313)
* 此 **透過SMPP啟用TLS** 選項已新增至 **透過SMPP的簡訊路由** 外部帳戶。 如需詳細資訊，請參閱本節 [區段](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**修補程式**

* 修正從Adobe Target加入動態影像時，無法傳送電子郵件的問題(CAMP-24848)。
* 已修正的問題 **[!UICONTROL Privacy Access/Delete Request]** 技術工作流程，若有任何要求失敗，則無法完成。
* 修正隱私權核心服務無法從Campaign接收請求狀態更新的問題。
* 修正了可能導致 **[!UICONTROL Import shared audience]** 技術工作流程正常運作(CAMP-25465)。
* 修正在核心Privacy Service中無法將Campaign隱私權要求標示為已完成的問題。
* 修正當Adobe ID太長時，某些使用者無法透過IMS驗證登入Campaign Standard的問題。 (CAMP-24095)
* 修正Creative Designer中移除內容模組時可能發生的問題。 (CAMP-25242)
* 針對資料庫中無設定檔的訂閱者，修正使用推播通知疲勞規則的問題。 (CAMP-25344)
* 修正存取傳遞排除記錄檔時，可能顯示錯誤訊息的問題。 (CAMP-24724)
* 修正無法在具有延伸傳送記錄檔的執行個體中準備校樣的問題。
* 修正使用發佈自訂資源時可能發生的兩個問題 **[!UICONTROL Sending log]** 擴充功能已啟用。
* 修正定期傳送未考慮傳送期間的情況下可能發生的問題。
* 修正排序中的資料時可能發生的問題 **[!UICONTROL Client data]** 功能表，適用於擁有超過100,000筆記錄的自訂資源。 (CAMP-24308)
* 修正使用動態報告中的搜尋功能時，未考慮自訂設定檔維度的問題。
* 修正動態報告中顯示帳戶層級國際資料的問題。
* 現在無需訂閱或取消訂閱確認訊息即可建立服務。

## 發行版本 18.5 – 2018 年 5 月 {#release-18-5---may-2018}

**有哪些新功能？**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 說明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR：核心服務整合<br /> </td> 
   <td> 隱私權核心服務整合可讓您透過單一JSON API呼叫，在多解決方案內容中自動化GDPR請求。 <br /> 從「隱私權核心服務」推送至所有Experience Cloud解決方案的GDPR請求，現在會由Campaign自動處理。 <br /> 如需詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播改良功能 — 詳細的傳送回饋<br /> </td> 
   <td> Adobe Campaign現在能夠透過MCPNS接收來自提供者(APNS/GCM)的推播訊息的詳細意見反應（傳送記錄檔和排除記錄檔）。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞記錄擴充功能<br /> </td> 
   <td> 傳送記錄擴充功能可讓您使用來自工作流程的設定檔資料和區段程式碼來擴充傳送記錄檔。 這些資訊隨後可用於動態報告中，並可讓您在傳送時保留某些資訊的快照。<br /> 此外還有2個使用案例：<br /> 
    <ul> 
     <li> 匯出包含「凍結」資料的擴充broadlog：作為行銷人員，我想匯出區段代碼等於「A」（來自工作流程引擎）的所有設定檔。 </li> 
     <li> 「凍結」資料的分段：身為行銷人員，我希望 <strong>重新目標定位</strong> 自上次傳送以來或區段代碼等於「A」時，已獲得1000個忠誠點的所有設定檔。 </li> 
    </ul> 如需詳細資訊，請參閱 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用自訂設定檔資料建立動態報告<br /> </td> 
   <td> 此功能可讓您根據在設定檔資源擴充期間建立的自訂設定檔資料，建立和管理報表。 您可以依個人資料屬性（例如，忠誠度方案、偏好的管道等）劃分報表。<br /> 如需詳細資訊，請參閱 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細檔案</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* 應用程式的整體記憶體和CPU使用量已提升

**其他變更**

* 「讀取對象」工作流程活動現在可以讀取Experience Cloud對象。 以前，此活動只能讀取「查詢」和「清單」對象。 請參閱 [詳細檔案](../../automating/using/read-audience.md). (CAMP-23623)
* 預設共用資料來源的識別碼現在處於唯讀模式，無法再變更。 變更此識別碼可能會導致與Experience Cloud共用對象時發生一些問題。
* 從Audience Manager匯入對象現在適用於分割檔案。 之前，importSharedAudience技術工作流程只會匯入區段的最後一個檔案。
* AWS S3外部帳戶現在支援地區和版本4驗證機制。 請參閱 [詳細檔案](../../administration/using/external-accounts.md).
* 資產選取視窗現在應該會更快載入，並允許選取資產，然後毫無問題地退出視窗。
* 具有管理許可權且屬於「全部」組織和地理單位的使用者現在可以修改技術工作流程的屬性和結構。
* 建立新區段時，已在區段活動介面中進行了增強：限制標籤現在新增限制後會直接顯示。 新區段的名稱現在會增加（「區段1」、「區段2」等）。
* 「nextProcessingDate」欄位已新增至「工作流程」資源。 此欄位只能透過REST API呼叫顯示，可讓您視覺化工作流程下一個處理日期。
* 「sourceId」欄位現在會在追蹤記錄資源(nms：trackingLog)中公開。
* 「總開啟次數」和「總點按次數」值現在可以透過工作流程匯出為一般檔案。 (CAMP-24186)
* 設定檔的「偏好語言」清單中現在提供「英文 — Danmark」。 (CAMP-23728)
* 使用具有其他資料(targetData)連結的分段活動時，訊息現在會通知您資料在工作流程之外無法使用。 按一下「細分」活動的「計數」或「預覽」按鈕時，會顯示此訊息。 (CAMP-23651)
* 已進行增強功能以最佳化工作流程使用的磁碟空間：(CAMP-21979)：「載入檔案」活動處理的檔案現在預設會刪除。 選項可讓您根據特定需求保留這些值。 刪除工作流程時，其專用資料夾會自動從伺服器目錄中隱藏。

**修補程式**

* 修正部分原始報告事件沒有關聯的追蹤事件，因為eventDate欄位未正確填入的問題。
* 修正個人化欄位無法顯示在推播通知傳遞的預覽視窗中的問題。
* 修正無法在預覽視窗中，以文字繞排推播通知之訊息本文的問題。
* 修正主要目標為空白時，從工作流程傳送循環傳遞的問題。
* 修正連結到不存在之結構描述時無法存取目標對應的問題。
* 修正透過檔案載入活動匯入zip檔案時可能發生的問題。 (CAMP-24309)
* 修正傳送循環傳遞時，導致PostgreSQL錯誤的問題。 (CAMP-23613)
* 修正傳送具有空白JSON屬性的REST API請求時顯示錯誤訊息的問題。 (CAMP-23506)
* 修正設定檔中設定為大寫「ß」字元後的字元的問題。 (CAMP-23136)
* 修正傳送搭配個人化或動態內容區塊資格條件使用的傳遞時，使用來自設定檔之連結結構的屬性的問題。 (CAMP-22751)
* 修正無法刪除服務的問題。 (CAMP-22050)
* 修正無法變更測試設定檔中國家或州值的問題。 (CAMP-20426)
* 修正無法載入Creative Designer的問題。 (CAMP-24573)
* 修正移除電子郵件主旨中個人化欄位後新增字元的問題。 (CAMP-24113)

## 發行版本 18.4 – 2018 年 4 月 {#release-18-4---april-2018}

**修補程式**

_Platform_

* 修正了無法正確處理GDPR存取或刪除請求的錯誤。 在某些極少數的情況下，當擷取的資料包含以下字元之一時，就會發現此行為： &amp; &lt; > &quot; &#39;。

_電子郵件、簡訊和直接郵件_

* 修正當broadlog同步處理超過一小時時，可能導致KPI被錯誤值覆寫的問題。

_工作流程_

* 改善記憶體管理，以及最佳化工作流程效能。

_報告_

* KPI共用工作流程現在會擷取過去2個月（而非過去6個月）的傳遞值。 修正KPI共用外部帳戶顯示截斷日期的問題。
* 修正可能導致某些訊息未被納入考量的問題 **已傳送**， **已傳遞** 和 **退回**&#x200B;量度。
* 修正在「 」中選擇的時間範圍時發生的錯誤 **傳遞摘要報告** 太長。

_自訂資源_

* 修正導致自訂資源準備失敗的錯誤。

## 發行版本 18.3 – 2018 年 3 月 {#release-18-3---march-2018}

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
   <td> 歐盟一般資料保護規範(GDPR)<br /> </td> 
   <td> GDPR是歐盟(EU)的新隱私權法律，協調資料保護要求並以現代化方式規範這些要求，於2018年5月25日生效。 GDPR 適用於所持有資料的主體居住於歐盟的 Adobe Campaign 客戶。<br /> 除了Adobe Campaign所提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）之外，我們還將以資料處理者的角色利用此機會，加入其他功能，以協助您做好準備，以利您作為資料控制者，處理特定GDPR請求：<br /> 
    <ul> 
     <li> 存取許可權：允許資料主體接收資料控制者擷取的個人資料副本，其中可能包括儲存在Adobe Campaign中的資料。 </li> 
     <li> 刪除權：資料主體有權清除資料控制者擷取的個人資料，可能包括儲存在Adobe Campaign中的資料。 </li> 
    </ul> 如需詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 適用於電子郵件的Creative Designer （測試版）<br /> </td> 
   <td> Adobe Campaign的全新Creative Designer提供Campaign中完全整合的建立體驗，讓您輕鬆快速地建立吸引人、個人化的電子郵件，而不需要編寫程式碼的一行。 透過其強大的拖放介面，Creative Designer有助於縮放電子郵件建立，無論使用者是從空白顯示窗開始，還是運用現有的內容片段或範本。 <br /> 主要功能包括：<br /> 
    <ul> 
     <li> 透過拖放介面，透過原生Creative Cloud整合強化，以視覺化方式設計和建立完全個人化、回應式電子郵件 </li> 
     <li> 建立和儲存電子郵件內容範本，並利用儲存的範本來協助縮放電子郵件的建立 </li> 
     <li> 建立並儲存內容片段（例如頁首、頁尾、文章等） 簡化內容建立並確保品牌一致性 </li> 
     <li> 順暢地在拖放介面中建立與按一下按鈕直接編輯電子郵件HTML之間切換 </li> 
    </ul> 適用於電子郵件的Creative Designer只有英文版。<br /> 如需詳細資訊，請參閱 <a href="../../designing/using/designing-content-in-adobe-campaign.md">詳細檔案</a> 並觀看此影片 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">視訊</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 多語言推播傳遞<br /> </td> 
   <td> 推播頻道已新增電子郵件和簡訊頻道中已有的相同簡單多語言介面，不論客戶偏好的語言為何，都能協助您與客戶互動。<br /> 此功能為管理跨多個區域的推播行銷活動，並想要以偏好語言鎖定使用者的客戶提供可擴充的自動解決方案。 它可讓您按一下滑鼠，即可透過範本化試算表將所有語言變體上傳至單一推送傳送。 Adobe Campaign接著會根據使用者的語言偏好執行自動分段，透過簡化工作流程和報表，協助減少重複勞動。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/creating-a-multilingual-push-notification.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 在異動訊息傳遞中使用自訂資源<br /> </td> 
   <td> 除了現成可用的欄位外，異動訊息現在可讓您使用自訂資源豐富訊息的內容。<br /> 例如：<br /> 
    <ul> 
     <li> 利用自訂欄位作為調解標準，將交易式訊息與設定檔進行比對 </li> 
     <li> 運用完整的設定檔、服務和連結資料，進一步個人化異動訊息 </li> 
    </ul> 如需詳細資訊，請參閱 <a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">詳細檔案</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_Platform_

* 修正無法從清單匯出超過5000筆記錄的問題。
* 修正將資料匯出至名為且包含個人化欄位的檔案時的問題。

_電子郵件、簡訊和直接郵件_

* 修正因部分大小是以字元而非位元組計算而造成多部分SMS截斷的問題。
* 新增允許 **[!UICONTROL Delivered]** 或 **[!UICONTROL Bounces + Errors]** 在傳送您的傳遞後要即時更新的KPI。 系統會直接從提供者接收的SR （狀態報告）重新計算事件。
* 修正傳送排程器中的行事曆Widget問題。
* 修正在已傳送的傳遞中第二次開啟目標時的顯示問題。
* 修正建立具有延遲傳送日期的電子郵件範本時，導致請求開始日期的錯誤訊息的問題。
* 修正編輯傳送內容時，可能導致影像轉譯問題的問題。
* 修正重複行銷活動時的校樣問題。
* 修正在將傳送新增至工作流程後，透過導覽列存取行銷活動範本時導致錯誤訊息的問題。
* 修正無法自動選取A/B測試電子郵件獲勝者的問題，導致未傳送電子郵件。 如果傳送是在，就可能會發生此行為 **[!UICONTROL retryInProgress]** 州別。
* 修正在重新開啟A/B測試電子郵件的引數時，可能導致出現錯誤訊息的問題。

_對象和查詢_

* 修正無法存取資料以及為從Adobe Campaign Classic復寫至Standard的收件者設定查詢的問題。
* 修正使用查詢編輯器中的篩選器型別欄位後，使用 **計數** 或 **預覽** 按鈕。

_工作流程_

* 此 **帳單** 已最佳化工作流程，以改善傳送準備延遲。
* 修正使用循環傳送活動時，無法在出站轉變中顯示母體資料的問題。
* 修正了無法在轉換之後顯示拒絕記錄的問題。 **更新資料** 活動。
* 修正可能導致 **deliverabilityUpdate** 技術工作流程失敗。

_整合_

* 修正無法將國際字元正確傳送至Adobe Analytics的問題。
* 嘗試從訊息的Experience Cloud資產庫插入影像時，資產現在應該會載入得更快。
* 修正某些情況下無法關閉資產選擇視窗的問題。
* 現在，您可以從資料來源詳細資料直接存取其相關工作流程，以檢查工作流程的狀態。
* 您現在可以在定義或編輯觸發程式事件時，直接更新觸發程式綱要。 經過此變更後，您不再需要取消發佈觸發程式並建立另一個觸發程式。

_異動訊息_

* 修正擴充傳送資源時，異動訊息範本的錯誤。
* 現在可以刪除交易式訊息。

## 發行版本 18.2 – 2018 年 2 月 {#release-18-2---february-2018}

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
   <td> 訂閱 — 訂閱或取消訂閱多項服務的設定檔清單<br /> </td> 
   <td> 此 <strong>訂閱服務</strong> 工作流程活動現在可讓您訂閱或取消訂閱多項服務的設定檔清單。 在工作流程中，匯入包含設定檔的檔案，並針對每個設定檔，匯入操作型別和服務。 此 <strong>訂閱服務</strong> 活動將能使用此資訊，並一次動態處理您的所有設定檔訂閱和取消訂閱。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/subscription-services.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 擴充活動 — 根據先前的轉變來擴充資料<br /> </td> 
   <td> 新的 <span class="uicontrol">擴充</span> 工作流程活動可讓您運用入站轉變，並使用其他資料完成輸出轉變。 如果您目標設定檔，擴充活動可讓您使用未儲存在資料庫中的其他資料（例如來自匯入的檔案）擴充設定檔資訊。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/enrichment.md">詳細檔案</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_Platform_

* Adobe Campaign介面的頂端列已更新為新的Experience Cloud功能表。
* 修正連結至時發生的問題 **[!UICONTROL Offers]** ，以免在解決方案下拉式清單中顯示。

_電子郵件、簡訊和直接郵件_

* 已增強傳送準備階段以改善效能。
* 修正某些利基情況下追蹤記錄檔可能損毀的問題。
* 修正在傳送準備與確認之間變更聯絡日期時發生的聯絡日期更新問題。 現在，當您在準備後變更聯絡日期時，必須再次準備傳送才能確認傳送。 請參閱 [詳細檔案](../../sending/using/preparing-the-send.md).

_推播通知_

* 修正部分個人化欄位無法在iOS推播通知中運作的錯誤。
* 修正在推播通知控制面板中將點按和開啟率顯示為0%的錯誤。

_報告_

* 修正某些瀏覽器將報表清單顯示為空白的錯誤。
* 修正中發生的錯誤 **[!UICONTROL Report sharing]** 技術工作流程即將達到其到期限制。

_工作流程_

* 修正拖放活動後無法存取活動的問題。
* 修正可能導致輸出轉換順序的問題 **[!UICONTROL Segmentation]** 活動以在某些情況下變更。
* 修正讀取包含列舉型別欄位且先前已從工作流程儲存的對象時發生的錯誤
* 修正造成的問題 **[!UICONTROL Request confirmation before sending messages]** 即使在定義在工作流程中建立的傳送的排程屬性時取消核取該選項後，該選項仍可保持已核取狀態。
* 現在可以在中停用自動移除重複列（DISTINCT子句） **[!UICONTROL Query]** 活動，透過位於 **[!UICONTROL Additional data]** 標籤。 基於效能考量，建議在定義許多（超過100個）其他元素時停用此選項。

_整合_

* 改善了 **[!UICONTROL Data sources]** 設定畫面。

_已知問題_

建議您不要使用Internet Explorer版本11，因為可能會出現顯示問題。

從Campaign介面使用內容說明連結時，可能會發生一些問題。 將在18.3中修正。

## 發行版本 18.1 – 2018 年 1 月 {#release-18-1---january-2018}

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
   <td> 疲勞管理報告是專用的可設定報告，可顯示疲勞規則在傳送前指定日期範圍內對電子郵件、推播、簡訊和直接郵件通道之傳送的影響。 由於新增可在單一檢視中快速檢視所有衝突行銷活動的深入分析，行銷人員可依據更有效設定疲勞規則來計畫行銷活動，並排定通訊的優先順序。<br /> 如需詳細資訊，請參閱 <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 報告共用<br /> </td> 
   <td> 「報表共用」可讓您以電子郵件附件的形式與Adobe Campaign使用者共用報表，包括自動循環共用報表。 收到週期性報表的使用者可透過每封電子郵件中的專用連結，取消訂閱這些通訊。<br /> 如需詳細資訊，請參閱 <a href="../../reporting/using/reporting-interface.md#share-tab">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播新功能<br /> </td> 
   <td> 推送訊息預覽 — 從推送通知內容編輯器預覽在iOS和Android裝置上顯示的推送通知，在測試或執行傳送前可先檢視收件者所見到的內容。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">詳細檔案</a>.<br /> 可用內容 — 如果使用者在一段時間後都未開啟應用程式，系統便會將其資料視為過時。 這會導致在使用者最終開啟應用程式時，必須更新或取代資料，這可能會造成使用應用程式發生延遲。 透過新增的「可用內容」支援，Adobe Campaign使用者在傳送推播通知時，可喚醒其應用程式以重新整理背景中的資料，進而增進一致性和對使用者應用程式內體驗的控制。<br /> 可變動內容 — 透過新增的「可變動內容」支援，Adobe Campaign使用者現在可運用行動應用程式延伸模組，進一步修改來自Adobe Campaign之推送通知的內容或呈現方式。 例如，使用者可利用可變內容來： <br /> 
    <ul> 
     <li> 解密以加密格式傳送的資料 </li> 
     <li> 下載影像或其他媒體檔案，並將它們新增為通知的附件 </li> 
     <li> 變更通知的正文或標題文字 </li> 
     <li> 將執行緒識別碼新增至通知 </li> 
    </ul> 有關可用內容和可變內容的詳細資訊，請參閱 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">詳細檔案</a>.<br /> <strong>警告：</strong> 這些推播通知更新會要求客戶升級其行動應用程式。 請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html">此技術檔案</a> 以取得詳細資訊。<br /> </td> 
  </tr> 
  <tr> 
   <td> 時區最佳化傳送<br /> </td> 
   <td> 排程在每個收件者時區的特定日期/時間傳送週期性電子郵件、簡訊和推播通知，確保您的訊息在正確時間傳送，而不需要設定多個傳送。 <br /> 如需詳細資訊，請參閱 <a href="../../automating/using/scheduler.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API Signal活動觸發<br /> </td> 
   <td> 現在可直接從Adobe Campaign Standard API觸發工作流程的訊號活動。<br /> 如需詳細資訊，請參閱 <a href="/help/api/using/triggering-a-signal-activity.md">詳細檔案</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_Platform_

* 設定檔搜尋已最佳化，以提升效能。
* 對於標準使用者，預設安全性群組的內部識別碼現在處於唯讀模式。

_電子郵件、簡訊和直接郵件_

* 修正將表情符號插入傳遞內容時發生的顯示問題。
* 修正當傳送仍在編輯時，允許使用者存取傳送記錄的問題。
* 此 **[!UICONTROL Scheduler]** 活動現在可讓您根據收件者的時區傳送傳遞。
* 簡訊：選項 **[!UICONTROL Store incoming MO]** 資料庫中已新增至外部帳戶。 選取後，所有傳入的SMS將儲存至 **inSMS** 表格。
* SMS：服務現在會附加至事件，而非交易式範本。
* SMS：預設的SMTP連線逾時已減少到30秒。

_推播通知_

* 修正無法停止推播通知傳遞的錯誤。
* 在推播通知進階選項中新增選項，以使用推播通知喚醒應用程式。
* 為推播通知預覽視訊新增暫停按鈕。
* 推播通知預覽現在可供iPhone、Android、平板電腦等不同裝置使用。

_報告_

* 修正顯示超過100%的費率的錯誤。
* 修正使用者無法以CSV格式下載報表的問題。
* 已新增 **[!UICONTROL Report]** 個專案。

_工作流程_

* 修正在查詢中使用其他資料並新增包含空格的別名時，導致錯誤訊息的問題。 非英數字元現在由「_」取代。
* 修正某些情況下，計算KPI的技術工作流程可能預設停止的問題。

_設定檔與對象_

* 修正在對象的查詢中新增多個篩選器時發生的錯誤。
* 修正變更設定檔圖片時發生的顯示問題。
* 新增工具提示，在計數查詢母體後顯示準確的結果編號。
* 修正可能導致使用者無法選取對象或關閉對象選擇器視窗的問題。
* 已更新運算式編輯器中可用函式的清單。 此 **格式貨幣** 和 **ConvertCurrency** 函式已移除。
