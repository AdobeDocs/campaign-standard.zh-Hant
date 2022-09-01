---
title: 發行說明 2018 年
description: 本頁列出 2018 年的所有 Adobe Campaign Standard 版本。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: 177d9e0f8d61c000f01ac5e148dbd98fef0538ff
workflow-type: tm+mt
source-wordcount: '5401'
ht-degree: 4%

---

# 發行說明 2018 年{#release-notes}

正在尋找2018年的特定Adobe Campaign Standard版本？

每個版本都提供新功能和修補程式。 按一下某個版本以檢視其內容。

檢視最新 [檔案更新](../../rn/using/documentation-updates.md) Adobe Campaign Standard。 如果您想要尋找較新的版本，請參閱以下資訊 [頁面](../../rn/using/release-notes.md).

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
   <td> 應用程式內傳訊（測試版）<br /> </td> 
   <td> 應用程式內傳訊功能可讓您提供情境式互動，並觸及已選擇退出推播通知的使用者，更有效與行動應用程式使用者互動。 搭配推播通知使用應用程式內訊息，以建立高度個人化且相關的體驗。 這可提高應用程式使用者的轉換率和保留率。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/about-in-app-messaging.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> AdobeLaunch整合行動應用程式（測試版）<br /> </td> 
   <td> Adobe與Adobe Campaign的整合現在使用行動SDK V5，簡化並自動化Campaign中的行動應用程式啟用程式。<br /> 如需詳細資訊，請參閱 <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">詳細檔案</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* Adobe Campaign Standard現在支援Amazon S3 API第4版。

**其他變更**

* 在broadlogs中，現在會區分每小時的連線數量上限和訊息數量上限。 當達到限制時，就可以知道吞吐量為何受到限制。 以前，這兩種情況都會套用相同的訊息（「符合配額」）。
* 在Campaign中設定行動應用程式時，使用者現在可以知道iOS憑證和Android伺服器金鑰是否已成功上傳及其到期日。

   如需詳細資訊，請參閱如何使用設定行動應用程式的詳細檔案 [SDK V4](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html) 和 [SDK V5](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html).

* 定義促銷活動屬性時選取行動應用程式，以鎖定特定行動應用程式上的使用者。 此功能適用於推播和應用程式內傳訊通道。

   如需詳細資訊，請參閱[詳細文件](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)以瞭解詳情。

* 使用Creative Designer介面選取內容區塊時，清單中的所有內容區塊現在都會載入並顯示。 (CAMP-27311)

   有關詳細資訊，請參閱 [詳細檔案](../../designing/using/personalization.md#adding-a-content-block).

**修補程式**

* 修正電子郵件控制面板與交易電子郵件的電子郵件摘要報表之間記錄計數不一致的問題。 (CAMP-28237
* 修正了工作流程中，透過檔案傳輸活動匯入檔案時，可能顯示錯誤訊息的問題。 (CAMP-27435)
* 修正登錄頁面包含超過25項服務，導致表單中隨機取消選取服務的問題。 (CAMP-26572)
* 修正工作流程中，使用檔案傳輸活動時無法使用SFTP URL設定外部帳戶的問題。 (CAMP-26475)
* 修正無法更新服務摘要報表的問題。 (CAMP-26301)
* 修正使用擴充活動時，自訂欄位無法顯示正確日期的工作流程問題。 (CAMP-26242)
* 修正透過檔案匯入匯入時，無法更新服務訂閱日期的問題。
* 修正載入檔案活動造成工作流程無法匯入檔案的錯誤(CAMP-27068)。
* 修正「服務」摘要報表中訂閱數量顯示錯誤的問題(CAMP-25587)。
* 修正Adobe Analytics和Adobe Campaign報表之間資料不一致的問題。 (CAMP-25393)
* 修正了限制存取使用者無法登入的問題。 (CAMP-27381)
* 修正了使用Creative Designer編輯電子郵件時，無法顯示Adobe Experience Manager內容清單的問題。 (CAMP-27181)
* 修正了無法開啟「創意設計工具」而造成錯誤的問題。 (CAMP-27304)
* 修正使用Internet Explorer 11時，無法在Creative Designer中正確拖放的問題。
* 修正從相機上傳並以縱向模式拍攝的圖片顯示在不需要的旋轉位置的問題。
* 修正使用Creative Designer中的查詢編輯器介面時，選取資訊顯示不清楚的問題。
* 修正使用Creative Designer中的查詢編輯器介面時，無法正確複製元素的問題。
* 修正即使透過自動回覆取消訂閱收件者，仍持續將SMS訊息傳送至封鎖清單上的收件者的問題。 (CAMP-27128)
* 修正無法顯示導致 **資料庫清理** 工作流程失敗。 (CAMP-26876)
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
   <td> Android推播通知的高優先順序標幟<br /> </td> 
   <td> Android的高優先順序標幟 — 為Android應用程式啟用具有高優先順序的推播通知傳送，這會導致休眠裝置喚醒並執行一些有限的處理。 請注意，預設優先順序為正常，這可能會延遲郵件傳送以節省電池。 <br /> 如需詳細資訊，請參閱 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 行動應用程式訂閱者的類型篩選<br /> </td> 
   <td> 支援類型篩選中的訂閱 — 當指定類型規則的篩選條件時，可選取應用程式訂閱作為篩選和定位維度，讓您能夠針對具有或沒有設定檔的使用者篩選屬性。 <br /> 如需詳細資訊，請參閱 <a href="../../sending/using/about-typology-rules.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息準備期間從URL自動匯入內容<br /> </td> 
   <td> 現在，您可以在準備階段期間從URL匯入電子郵件內容。 對於循環電子郵件傳送，每次準備郵件時都會擷取最新的HTML內容，確保在傳送電子郵件時內容一律為最新。 此功能也可讓您建立排程傳送，內含來自URL的內容，即使內容尚未就緒亦然。<br /> 如需詳細資訊，請參閱 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 行銷活動發行通知訊息<br /> </td> 
   <td> 現在，當使用者在執行個體升級至新版本後登入時，會顯示快顯訊息。 訊息會指出版本號碼，並包含發行說明的連結。 您可以在下一個版本之前選擇隱藏訊息。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 使用者管理<br /> </td> 
   <td> 地理單位功能現在無法用於新的Campaign Standard例項，以及未建立地理單位的現有例項（從18.7版開始）。<br /> 如需詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hant#release-notes">頁面</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* Adobe Campaign和Adobe Target整合現在可讓您運用Target的 [權限](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html) 功能。 在電子郵件中加入來自Adobe Target的動態影像時，您現在可以指定Target屬性（at_property代碼）。
* 具有設定檔資源之下載連結的自訂資源，現在會由GDPR隱私權存取/刪除請求納入考量。 對於1個基數簡單連結和N個基數收集連結，您需要在自訂資源中選擇「刪除/複製目標籤錄意味著刪除/複製連結引用的記錄」。 對於0或1個基數簡單連結，選擇「刪除/複製記錄表示刪除/複製連結引用的目標籤錄」。

**其他變更**

* 報表共用逾時時間已從1分鐘增加為4分鐘，以避免發生任何逾時錯誤。
* 編輯電子郵件內容時，新的創意設計工具會依預設開啟。 如果您願意，在儲存變更後，您仍可隨時返回預設內容編輯器。 有關詳細資訊，請參閱 [詳細檔案](../../designing/using/designing-content-in-adobe-campaign.md).
* 在創意設計工具中，新的內容元件現在可以新增至電子郵件中：輪播。 有關詳細資訊，請參閱 [詳細檔案](../../designing/using/designing-from-scratch.md#about-content-components).
* 在交易式訊息熱點點按報表中，當您按一下 **變更設定檔** 按鈕，現在只會列出連結至您為交易式訊息定義之事件的測試設定檔。

**修補程式**

* 修正byEmail查詢篩選器無法傳回任何結果的問題。 (CAMP-23420)
* 修正標準使用者可存取管理員限制的特定功能或畫面(/rest/head/&#42; 端點、交易式訊息畫面、設定檔和對象匯入畫面)。
* 修正GDPR隱私權刪除請求在名稱以數字開頭時無法處理自訂資源的問題。
* 修正「儲存對象」活動無法在Adobe Experience Cloud中共用應用程式訂閱者的錯誤。
* 修正檔案名稱包含空白字元時，「檔案傳輸」活動可能發生的問題。 (CAMP-25936)
* 修正在工作階段過期後使用重新連線按鈕時可能發生的問題。 (CAMP-25560)
* 修正傳送時，傳送與疲勞規則相關聯的時區最佳化時，可能導致排除的問題。 (CAMP-25425)
* 修正使用API GDPR功能時，無法透過0-1類型連結刪除資料的問題。
* 修正取消疲勞類型規則版本時可能導致錯誤訊息的問題。
* 修正在編輯傳送內容後預覽傳送內容時可能發生的問題。
* 修正使用解壓縮選項處理CSV壓縮檔案時可能發生的問題。
* 修正創意設計工具中，使用內建樣式將部分文字變更為連結或編輯該連結時，造成不想要的顏色字型和格式的問題。 (CAMP-26001)
* 修正熱點點按報表無法顯示包含動態內容之傳遞中每個條件的百分比問題。 以前，只會顯示對預設變體的點按。

## 發行版本 18.6 – 2018 年 6 月 {#release-18-6---june-2018}

**功能改進**

* 此 **[!UICONTROL History]** API已新增至Adobe.IO。 它可讓您存取與設定檔行銷記錄相關的資訊：接觸點數、已傳送、鏡像頁面URL等。 有關詳細資訊，請參閱 [專用使用案例](../../api/using/interacting-with-marketing-history.md) .
* 此 **[!UICONTROL Database cleanup]** 已優化技術工作流，以確保資料庫備份的效能更佳。
* Creative Designer for Email現在也提供法文版和德文版。

**其他變更**

* A **[!UICONTROL Compute stats]** 按鈕已新增至 **[!UICONTROL Deployment]** 傳送的視窗。 它可讓您擷取最新KPI，例如，傳送的結果需要太長時間才能更新或尚未納入考量。 如需詳細資訊，請參閱本[區段](../../sending/using/confirming-the-send.md)。
* 在 **傳遞能力更新** 現在，功能管理員可以定義要在 **更新規則** javascript活動。 依預設，欄位值會設為0，這表示將忽略所有錯誤。
* 管理單元訪問限制條件時生成的SQL已優化。
* 此 **[!UICONTROL Update]** 活動現在可讓您新增、更新或刪除與訂閱相關的資料（nms:appSubscriptionRcp表格）。
* 此 **[!UICONTROL Update delivery execution]** 技術工作流程分為兩個工作流程，以最佳化效能：- **[!UICONTROL Update delivery execution]**:更新傳送的追蹤。 預設會每10分鐘啟動一次。 **[!UICONTROL Update delivery indicators]**:更新傳送的KPI，預設會每小時啟動一次。 如需技術工作流程的詳細資訊，請參閱 [節](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* 當傳送訊息時， **[!UICONTROL Deployment]** 區段現在可以有兩個值： **[!UICONTROL Sending]**:正在傳送訊息。 **[!UICONTROL Sending (retry)]**:正在重試傳遞。
* 具有 **[!UICONTROL Delivery preparation]** 角色現在可以傳送校樣。 (CAMP-24313)
* 此 **透過SMPP啟用TLS** 選項已新增至 **通過SMPP的SMS路由** 外部帳戶。 如需詳細資訊，請參閱 [節](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**修補程式**

* 修正納入Adobe Target動態影像時，無法傳送電子郵件的問題(CAMP-24848)。
* 修正 **[!UICONTROL Privacy Access/Delete Request]** 技術工作流程，若有任何要求失敗，則無法完成。
* 修正隱私權核心服務無法從Campaign接收要求狀態更新的問題。
* 修正了 **[!UICONTROL Import shared audience]** 技術工作流程無法正常運作(CAMP-25465)。
* 修正無法在核心Privacy Service中將促銷活動隱私權要求標示為已完成的問題。
* 修正當Adobe ID過長時，某些使用者無法透過IMS驗證登入Campaign Standard的問題。 (CAMP-24095)
* 修正Creative Designer中移除內容模組時可能發生的問題。 (CAMP-25242)
* 修正針對資料庫中沒有設定檔的訂閱者使用推播通知疲勞規則的問題。 (CAMP-25344)
* 修正了存取傳送排除記錄時，可能顯示錯誤訊息的問題。 (CAMP-24724)
* 修正在具有延伸傳送記錄時，無法準備校樣的問題。
* 修正使用發佈自訂資源時可能發生的兩個問題 **[!UICONTROL Sending log]** 擴充功能已啟用。
* 修正了在循環傳送中可能未考慮傳送持續時間的問題。
* 修正排序 **[!UICONTROL Client data]** 功能表，適用於具有超過10萬筆記錄的自訂資源。 (CAMP-24308)
* 修正使用動態報表中的搜尋功能時，未考慮自訂設定檔維度的問題。
* 修正動態報告中帳戶層級國際資料的顯示問題。
* 現在可以建立不含訂閱或取消訂閱確認訊息的服務。

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
   <td> GDPR:核心服務整合<br /> </td> 
   <td> 隱私權核心服務整合可讓您透過單一JSON API呼叫，在多解決方案內容中自動處理GDPR請求。 <br /> 從隱私權核心服務推送至所有Experience Cloud解決方案的GDPR請求，現在會由Campaign自動處理。 <br /> 如需詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=zh-Hant">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 推播改良功能 — 詳細的傳送意見反應<br /> </td> 
   <td> Adobe Campaign現在提供透過MCPNS從提供者(APNS/GCM)接收推播訊息的詳細意見（傳送記錄和排除記錄）。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送記錄擴充功能<br /> </td> 
   <td> 傳送記錄擴充功能可讓您使用來自工作流程的設定檔資料和區段代碼來擴充傳送記錄檔。 然後，此資訊便可用於動態報表，並可讓您在傳送時保留一些資訊的快照。<br /> 還有2個使用案例：<br /> 
    <ul> 
     <li> 使用「凍結」資料導出擴展廣播：身為行銷人員，我想匯出區段代碼等於「A」（來自工作流程引擎）的所有設定檔。 </li> 
     <li> 「凍結」資料的分段：身為行銷人員，我想 <strong>重新定位</strong> 自上次傳送以來已贏得1000個忠誠度點數的所有設定檔，或其區段代碼等於「A」的位置。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用自訂設定檔資料建立動態報告<br /> </td> 
   <td> 此功能可讓您根據在設定檔資源擴充期間建立的自訂設定檔資料來建立和管理報表。 您可以依設定檔屬性（例如忠誠度計畫、偏好管道等）劃分報表。<br /> 如需詳細資訊，請參閱 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細檔案</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**功能改進**

* 應用程式的整體記憶體和CPU使用已增強

**其他變更**

* 「讀取對象」工作流程活動現在可以讀取Experience Cloud對象。 之前，此活動只能讀取「查詢」和「清單」對象。 請參閱 [詳細檔案](../../automating/using/read-audience.md). (CAMP-23623)
* 預設共用資料來源的識別碼現在為唯讀模式，無法再變更。 變更此識別碼可能會在與Experience Cloud共用對象時造成一些問題。
* 從Audience Manager匯入對象現在可處理分割檔案。 以前，只有匯入SharedAudience技術工作流程匯入了區段的最後一個檔案。
* AWS S3外部帳戶現在支援地區和第4版驗證機制。 請參閱 [詳細檔案](../../administration/using/external-accounts.md).
* 「資產選取」視窗現在載入速度應該會更快，而且可以選取資產，然後退出視窗而不會發生任何問題。
* 具有管理權限且屬於「全部」組織和地理單位的使用者現在可以修改技術工作流程的屬性和結構。
* 建立新區段時，區段活動介面已增強功能：現在新增限制後，「限制」標籤會直接顯示。 新區段的名稱現在會增加（「區段1」、「區段2」等）。
* 「nextProcessingDate」欄位會新增至工作流程資源。 此欄位只會透過REST API呼叫顯示，可讓您將後續處理日期的工作流程視覺化。
* 「sourceId」欄位現在會公開於追蹤記錄資源(nms:trackingLog)中。
* 「開啟總次數」和「點按總次數」值現在可透過工作流程匯出為平面檔案。 (CAMP-24186)
* 「英文 — Danmark」現在可在設定檔的「偏好語言」清單中取得。 (CAMP-23728)
* 將分段活動與其他資料(targetData)連結搭配使用時，現在會出現訊息通知您，該資料無法在工作流程之外使用。 在「細分」活動中按一下「計數」或「預覽」按鈕時，會顯示此訊息。 (CAMP-23651)
* 已增強功能，以最佳化工作流程使用的磁碟空間：(CAMP-21979):「載入檔案」活動處理的檔案現在預設會刪除。 選項可讓您根據特定需求保留這些值。 刪除工作流時，其專用資料夾將從伺服器目錄中自動隱藏。

**修補程式**

* 修正某些原始報表事件因未正確填入eventDate欄位而沒有相關聯追蹤事件的問題。
* 修正推播通知傳送的預覽視窗無法顯示個人化欄位的問題。
* 修正文字無法在預覽視窗中文字包住推播通知的訊息內文的問題。
* 修正當主要目標為空時，從工作流程傳送循環傳送的問題。
* 修正當目標映射連結至不存在的架構時，無法存取該映射的問題。
* 修正透過檔案載入活動匯入zip檔案時可能發生的問題。 (CAMP-24309)
* 修正傳送循環傳送時導致PostgreSQL錯誤的問題。 (CAMP-23613)
* 修正傳送REST API要求並填入空白JSON屬性時，顯示錯誤訊息的問題。 (CAMP-23506)
* 修正設定檔中，&quot;ß&quot;字元後面的字元設為大寫的問題。 (CAMP-23136)
* 修正使用連結設定檔結構中的屬性時，傳送與個人化或動態內容區塊的適用性條件搭配使用的傳送時的問題。 (CAMP-22751)
* 修正無法刪除服務的問題。 (CAMP-22050)
* 修正無法變更測試設定檔中的國家/地區或州值的問題。 (CAMP-20426)
* 修正了無法載入「創作設計工具」的問題。 (CAMP-24573)
* 修正移除電子郵件主旨中個人化欄位後新增之字元的問題。 (CAMP-24113)

## 發行版本 18.4 – 2018 年 4 月 {#release-18-4---april-2018}

**修補程式**

_平台_

* 修正無法正確處理GDPR存取或刪除請求的錯誤。 在某些罕見的情況下，擷取的資料包含下列其中一個字元，就會觀察到此行為：&amp; &lt; > &quot; &#39;。

_電子郵件、簡訊和直接郵件_

* 修正了如果broadlog同步花費超過一小時，可能導致KPI覆寫為錯誤值的問題。

_工作流程_

* 改善工作流程的記憶體管理和最佳化效能。

_報告_

* KPI共用工作流程現在會擷取過去2個月的傳送值，而非過去6個月。 修正KPI共用外部帳戶顯示截斷日期的問題。
* 修正了可能導致某些訊息未納入 **已傳送**, **傳遞** 和 **跳出**&#x200B;量度。
* 修正 **傳送摘要報表** 太長了。

_自訂資源_

* 修正造成自訂資源準備失敗的錯誤。

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
   <td> GDPR是歐盟(EU)的新隱私權法，協調2018年5月25日生效的資料保護要求並以現代化方式規範這些要求。 GDPR 適用於所持有資料的主體居住於歐盟的 Adobe Campaign 客戶。<br /> 除了Adobe Campaign中已提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）之外，我們也趁此次機會，以資料處理者的角色加入其他功能，以協助您做好準備，以便擔任資料控管單位，處理特定GDPR請求：<br /> 
    <ul> 
     <li> 訪問權限：可讓資料主體接收資料控制者擷取的個人資料副本，可能包括儲存在Adobe Campaign中的資料。 </li> 
     <li> 刪除權限：為資料主體賦予權利，讓資料控制者清除其個人資料，可能包括儲存在Adobe Campaign中的資料。 </li> 
    </ul> 如需詳細資訊，請參閱<a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
  <tr> 
   <td> 適用於電子郵件的Creative Designer（測試版）<br /> </td> 
   <td> Adobe Campaign的全新Creative Designer在Campaign中提供完全整合的建立體驗，讓您無需編寫程式碼，即可快速輕鬆地以視覺化方式建立吸引人、個人化的電子郵件。 無論使用者是從空白顯示窗開始，還是運用現有的內容片段或範本，創意設計人員都能透過其強大的拖放介面，協助縮放電子郵件的建立。 <br /> 主要功能包括：<br /> 
    <ul> 
     <li> 透過拖放介面以視覺化方式設計和建立完全個人化、回應式電子郵件，並輔以原生Creative Cloud整合 </li> 
     <li> 建立和儲存電子郵件內容範本，並運用儲存的範本來協助縮放電子郵件建立 </li> 
     <li> 建立並儲存內容片段（例如頁首、頁尾、文章等） 簡化內容建立並確保品牌一致性 </li> 
     <li> 在拖放介面中建立，以及按一下按鈕即可直接編輯電子郵件的HTML之間順暢切換 </li> 
    </ul> 適用於電子郵件的Creative Designer僅提供英文版。<br /> 如需詳細資訊，請參閱 <a href="../../designing/using/designing-content-in-adobe-campaign.md">詳細檔案</a> 看這個 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">影片</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 多語言推播傳送<br /> </td> 
   <td> 推播通道中已新增電子郵件和簡訊通道上已存在的相同簡單多語言介面，無論客戶使用何種偏好語言，均可協助您與客戶互動。<br /> 若客戶管理跨多個地區的推播促銷活動，且想以偏好的語言鎖定使用者，此功能可提供可擴充的自動解決方案。 它可讓您透過範本試算表，按一下即可上傳至單一推送傳送的所有語言變體。 Adobe Campaign接著會根據使用者的語言偏好執行自動分段，透過簡化工作流程和報告來協助減少重複。<br /> 如需詳細資訊，請參閱 <a href="../../channels/using/creating-a-multilingual-push-notification.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 自訂資源在交易式傳訊中的使用<br /> </td> 
   <td> 除了現成欄位外，交易式訊息現在可讓您使用自訂資源，讓訊息的內容更為豐富。<br /> 例如：<br /> 
    <ul> 
     <li> 運用自訂欄位作為調解標準，將交易式訊息與設定檔比對 </li> 
     <li> 運用完整的設定檔、服務和連結資料，進一步個人化交易式訊息 </li> 
    </ul> 如需詳細資訊，請參閱<a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">詳細文件</a>以瞭解詳情。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 修正無法從清單匯出5000多筆記錄的問題。
* 修正將資料匯出至使用個人化欄位命名的檔案時的問題。

_電子郵件、簡訊和直接郵件_

* 修正由於多部分SMS的大小是以字元（而非位元組）計算，因此遭到截斷的問題。
* 新增選項，允許 **[!UICONTROL Delivered]** 或 **[!UICONTROL Bounces + Errors]** 傳送您的內容後，即時更新KPI。 從提供者接收的SR（狀態報表）直接重新計算。
* 修正傳送排程器中日曆介面工具集的問題。
* 修正在已傳送傳送中第二次開啟目標時的顯示問題。
* 修正建立傳送日期延遲的電子郵件範本時，導致要求開始日期的錯誤訊息的問題。
* 修正在編輯傳送內容時，可能造成影像轉譯問題的問題。
* 修正複製促銷活動時的校樣問題。
* 修正透過導覽列存取行銷活動範本時，新增傳遞至工作流程後，導致錯誤訊息的問題。
* 修正無法自動選取A/B測試電子郵件獲勝者，導致電子郵件未傳送的問題。 如果傳送位於 **[!UICONTROL retryInProgress]** 狀態。
* 修正了重新開啟A/B測試電子郵件的參數時，可能顯示錯誤訊息的問題。

_對象與查詢_

* 修正無法存取資料，以及無法設定從Adobe Campaign Classic復寫至Standard之收件者查詢的問題。
* 修正在使用 **計數** 或 **預覽** 按鈕。

_工作流程_

* 此 **帳單** 工作流程已最佳化，以改善傳送準備延遲。
* 修正使用循環傳送活動時，無法在出站轉變中顯示母體資料的問題。
* 修正在 **更新資料** 活動。
* 修正可能導致 **deliverabilityUpdate** 技術工作流程失敗。

_整合_

* 修正無法正確將國際字元傳送至Adobe Analytics的問題。
* 現在，嘗試從訊息中的Experience Cloud資產程式庫插入影像時，資產的載入速度應該會更快。
* 修正了在某些情況下無法關閉資產選擇視窗的問題。
* 從資料源詳細資訊中，您現在可以直接訪問其相關工作流以檢查工作流的狀態。
* 您現在可以在定義或編輯觸發器事件時直接更新觸發器結構。 經過此變更後，您不再需要取消發佈觸發程式並建立另一個觸發器。

_異動訊息_

* 修正了延伸傳送資源時，交易式訊息範本的錯誤。
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
   <td> 此 <strong>訂閱服務</strong> 工作流程活動現在可讓您訂閱或取消訂閱多項服務的設定檔清單。 在工作流程中，匯入包含設定檔的檔案，以及每個設定檔的操作類型和服務。 此 <strong>訂閱服務</strong> 活動將能使用此資訊，並一次動態處理所有設定檔訂閱和取消訂閱。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/subscription-services.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 擴充活動 — 根據先前的轉變來擴充資料<br /> </td> 
   <td> 新 <span class="uicontrol">擴充</span> 工作流程活動可讓您運用入站轉變，並使用其他資料完成輸出轉變。 如果您定位設定檔，擴充活動可讓您使用未儲存在資料庫中的其他資料（例如來自匯入的檔案）擴充設定檔資訊。<br /> 如需詳細資訊，請參閱 <a href="../../automating/using/enrichment.md">詳細檔案</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* Adobe Campaign介面的頂端列已更新為新的Experience Cloud功能表。
* 修正無法連結至 **[!UICONTROL Offers]** 中的任何值。

_電子郵件、簡訊和直接郵件_

* 已增強傳送準備階段，以改善效能。
* 修正了數個問題，這些問題可能會在某些小眾情況下造成追蹤記錄損毀。
* 修正了在傳送準備和確認之間變更聯絡日期時發生的聯絡日期更新問題。 現在，當您在準備後變更聯絡日期時，必須先重新準備傳送，才能確認傳送。 請參閱 [詳細檔案](../../sending/using/preparing-the-send.md).

_推播通知_

* 修正某些個人化欄位無法在iOS推播通知中運作的錯誤。
* 修正在推播通知控制面板中，點按和開啟率顯示為0%的錯誤。

_報告_

* 修正在某些瀏覽器中將報表清單顯示為空白的錯誤。
* 修正 **[!UICONTROL Report sharing]** 技術工作流程到期限之前完成。

_工作流程_

* 修正拖放活動後無法存取活動的問題。
* 修正可能導致 **[!UICONTROL Segmentation]** 活動。
* 修正讀取包含列舉類型欄位且先前已從工作流程儲存的對象時發生的錯誤
* 修正 **[!UICONTROL Request confirmation before sending messages]** 在定義在工作流程中建立之傳送的排程屬性時，即使取消核取傳送後，仍保留核取的選項。
* 現在，可以在 **[!UICONTROL Query]** 活動，透過 **[!UICONTROL Additional data]** 標籤。 基於效能原因，在定義許多（超過100個）其他元素時，建議禁用此選項。

_整合_

* 已對 **[!UICONTROL Data sources]** 設定畫面。

_已知問題_

由於可能的顯示問題，建議您不要使用Internet Explorer 11版。

從Campaign介面使用內容說明連結時，可能會發生一些問題。 18.3版會修正。

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
   <td> 疲勞管理報告是專用的可設定報表，顯示疲勞規則對指定日期範圍內，在傳送前，電子郵件、推送、簡訊和直接郵件通道之間傳送的影響。 透過在單一檢視中快速查看所有衝突促銷活動的深入分析，行銷人員能夠更有效地設定疲勞規則，並排定通訊的優先順序，以規劃行銷活動。<br /> 如需詳細資訊，請參閱 <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 報表共用<br /> </td> 
   <td> 「報表共用」可讓您以電子郵件附件的形式與Adobe Campaign使用者共用報表，包括自動重複執行。 收到循環報表的使用者可以透過每個電子郵件中的專用連結，取消訂閱這些通訊。<br /> 如需詳細資訊，請參閱 <a href="../../reporting/using/reporting-interface.md#share-tab">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送新功能<br /> </td> 
   <td> 推播訊息預覽 — 從推播通知內容編輯器預覽在iOS和Android裝置上顯示的推播通知，在測試或執行傳送前可先檢視收件者所見到的內容。<br />如需詳細資訊，請參閱<a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">詳細文件</a>以瞭解詳情。<br /> 可用內容 — 如果使用者在一段時間後都未開啟應用程式，系統便會將其資料視為過時。 這會導致使用者在最終開啟應用程式時，必須更新或取代資料，而這可能導致使用應用程式的延遲。 透過新增的「可用內容」支援，Adobe Campaign使用者可在傳送推播通知時，喚醒應用程式以在背景重新整理資料，讓使用者的應用程式內體驗更具一致性和控制力。<br /> 可變動內容 — 透過新增的「可變動內容」支援，Adobe Campaign使用者現在可運用行動應用程式擴充功能，進一步修改來自Adobe Campaign之推播通知的內容或呈現方式。 例如，使用者可以運用「可變內容」來： <br /> 
    <ul> 
     <li> 解密以加密格式傳送的資料 </li> 
     <li> 下載影像或其他媒體檔案，並將其新增為通知的附件 </li> 
     <li> 變更通知的正文或標題文字 </li> 
     <li> 向通知添加線程標識符 </li> 
    </ul> 如需「可用內容」和「可變動內容」的詳細資訊，請參閱 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">詳細檔案</a>.<br /> <strong>警告：</strong> 推送通知的這些更新要求客戶升級其行動應用程式。 請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html">此技術檔案</a> 以取得更多資訊。<br /> </td> 
  </tr> 
  <tr> 
   <td> 時區最佳化的傳遞<br /> </td> 
   <td> 排程在每個收件者時區的特定日/時間傳送循環的電子郵件、簡訊和推播通知，確保訊息在正確的時間傳送，而不需設定多個傳送。 <br /> 如需詳細資訊，請參閱 <a href="../../automating/using/scheduler.md">詳細檔案</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API訊號活動觸發<br /> </td> 
   <td> 現在可以直接從Adobe Campaign Standard API觸發工作流程的訊號活動。<br /> 如需詳細資訊，請參閱 <a href="/help/api/using/triggering-a-signal-activity.md">詳細檔案</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修補程式**

_平台_

* 已最佳化設定檔搜尋以改善效能。
* 預設安全性群組的內部識別碼現在為標準使用者的唯讀模式。

_電子郵件、簡訊和直接郵件_

* 修正在傳遞內容中插入表情符號時發生的顯示問題。
* 修正當傳送仍在版本中時，允許使用者存取傳送記錄檔的問題。
* 此 **[!UICONTROL Scheduler]** 活動現在可讓您根據收件者的時區來傳送傳遞。
* 簡訊：選項 **[!UICONTROL Store incoming MO]** 已新增至外部帳戶。 勾選後，所有傳入的SMS都會儲存至 **inSMS** 表格。
* 簡訊：服務現在會附加至事件，而非交易範本。
* 簡訊：預設的SMTP連線逾時已縮短為30秒。

_推播通知_

* 修正推播通知傳送無法停止的錯誤。
* 在推播通知中新增選項進階選項，以使用推播通知喚醒應用程式。
* 為推播通知預覽視訊新增暫停按鈕。
* 推播通知預覽現在可用於不同的裝置，例如iPhone、Android、平板電腦。

_報告_

* 修正了顯示率超過100%的錯誤。
* 修正使用者無法以CSV格式下載報表的問題。
* 新增 **[!UICONTROL Report]** 項目。

_工作流程_

* 修正在查詢中使用其他資料並新增包含空格之別名時，會導致錯誤訊息的問題。 非英數字元現在由「_」取代。
* 修正在某些情況下，技術工作流程計算KPI可預設停止的問題。

_設定檔與對象_

* 修正在對象的查詢中新增多個篩選器時發生的錯誤。
* 修正變更設定檔圖片時發生的顯示問題。
* 新增工具提示，在計算查詢的母體數後顯示確切的結果編號。
* 修正使用者無法選取對象或關閉對象選擇器視窗的問題。
* 已更新運算式編輯器中可用函式的清單。 此 **FormatCurrency** 和 **ConvertCurrency** 函式已移除。
