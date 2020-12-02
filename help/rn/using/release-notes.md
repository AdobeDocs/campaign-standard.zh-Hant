---
solution: Campaign Standard
product: campaign
title: 最新版本
description: 本頁詳細說明最新 Campaign Standard 版本的內容
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '2412'
ht-degree: 100%

---


# 最新版本{#latest-release}

[發行計畫](../../rn/using/release-planning.md) | [控制面板版本](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/release-notes.html) | [文件更新](../../rn/using/documentation-updates.md) | [先前的發行版本](../../rn/using/release-notes-2020.md) | [已過時的功能](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **新控制面板 10 月發行版本**，其中包含使用 CNAME 的網域設定及新的資料庫監控功能。[進一步瞭解](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)。

## 發行版本 20.4 – 2020 年 10 月 {#release-20-4---october-2020}

**新增功能？**

<table> 
<thead> 
<tr> 
<th> <strong>控制組</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>您現在可以使用<strong>控制組組</strong>，透過排除其閱聽眾的一部分來評估行銷活動的影響。然後，您將能夠將接收到消息的目標人口的行為與未作為目標的聯絡人的行為進行比較。根據傳送日誌，您也可以在未來的行銷活動中定位控制群。
</p>
<p>如需詳細資訊，請參閱<a href="../../sending/using/control-group.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html?lang=zh-Hant#communication-channels">作法影片</a>。
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>外部 API - Oauth 支援</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Adobe Campaign 現在支援 OAuth，以便在<strong>外部 API</strong> 工作流程活動中進行驗證。這項新功能使此活動能夠與需要 OAuth 支援的系統進行通訊。
</p>
<p>如需詳細資訊，請參閱<a href="../../automating/using/external-api.md">詳細文件</a>。
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Journey AI 整合</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>我們很高興能向所有 Adobe Campaign Standard 客戶宣佈 Journey AI。</p>
  <p>Journey AI 使用進階的機器學習 (ML)，讓公司透過預測每個人的參與偏好以最佳化客戶旅程的設計和傳遞。</p>
  <P>Journey AI 包含兩種 ML 功能：</p>
<ul> 
     <li> <strong>預測性參與計分</strong> - 智慧地識別客戶的首選參與層級，以便更佳地定位和個人化訊息，從而提高轉換率與保留率。觀看<a href="https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">作法影片</a>。</li> 
     <li> <strong>預測性傳送時間最佳化</strong> - 預測向行銷活動中的每個人傳送電子郵件的最佳時機，以最大化參與率並改善電子郵件行銷活動的 ROI。觀看<a href="https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">作法影片</a>。</li>
    </ul>
  <p>如果您想要瞭解如何開始使用 Journey AI，請查閱此<a href="../../sending/using/predictive.md">詳細文件</a>，並聯繫您的帳戶高階主管。請注意，雖然 Journey AI 可供現有的 Campaign 客戶免費使用，但實作成本約為 50 小時。</p>
    </td> 
</tr> 
</tbody> 
</table>

**功能改善**

* **隱私權管理**：**CCPA選擇**&#x200B;退出欄位現在透過 Campaign 介面和 API 提供，現在也可以透過隱私權核心服務提供支援。此欄位可讓 Adobe Campaign 使用者追蹤消費者是否已選擇退出個人資訊的出售。[進一步瞭解](https://helpx.adobe.com/content/help/tw/campaign/kb/acs-privacy.html#ccpa)
* **工作流程執行改善** （測試版）：在圍繞工作流程的全球計畫背景下，已經開發了一些主要的改善，以穩定記憶體管理、減少延遲並最佳化工作流程在執行過程中所消耗的記憶體。這些改善功能目前為測試版，僅適用於特定客戶。預計於 2021 年初全面上市。
* 為了改善安全性，Campaign 現在使用&#x200B;**簽名機制**，來追蹤電子郵件中的連結。
* 上傳 iOS 憑證或 Android 金鑰時，行動應用程式設定已改良為顯示&#x200B;**更清楚的錯誤訊息**。
* **SMS 錯誤管理**&#x200B;已得到改善，以防止將過多的設定檔新增到隔離清單中。依預設，SMS 錯誤現在會設定為軟錯誤，而非硬錯誤。請參見[此頁面](https://helpx.adobe.com/tw/campaign/kb/sms-connector-protocol-and-settings.html)。

**電子郵件設計工具增強功能**

* 我們透過&#x200B;**新的動態上下文幫助**&#x200B;改善電子郵件設計工具中的使用者體驗，該幫助完全連接了使用者介面和文件，從而可以輕鬆存取最新的幫助內容。
* 修正編輯文字版本時移除訊息中分行符號的問題。(CAMP-44483)
* 修正 HTML 範本的防止純文字版本無法自動產生及同步的問題。(CAMP-44195)
* 修正調整影像大小時可能發生的問題。傳送訊息後，影像無法在 Microsoft Outlook 中正確顯示。(CAMP-44656)
* 修正插入按鈕並將其寬度設為「自動」時發生的問題。傳送訊息後，按鈕的內容未完全顯示。(CAMP-44560)
* 修正從附加的 HTML 檔案上傳內容時發生的問題。訊息傳送至 Gmail 位址後，就無法套用 CSS，而會造成轉譯問題。(CAMP-44085)
* 修正在內容範本中直接修改之前用於訊息的內容片段時，無法更新片段的問題。(CAMP-43973)
* 修正&#x200B;**片段**&#x200B;搜尋列的問題。搜尋現有片段時，該搜尋列未顯示任何結果。(CAMP-44223)
* 修正&#x200B;**內容區塊**&#x200B;和&#x200B;**片段**&#x200B;搜尋列的問題。使用其中一個搜尋列時，僅當在您按一下&#x200B;**顯示更多結果…**&#x200B;時，才會顯示結果。(CAMP-44205)
* 修正防止在 Microsoft Outlook 中無法套用文字和影像填補的問題。(CAMP-45370)
* 修正重複片段時的問題。重複片段後，原始片段遺失 HTML 行。(CAMP-45207)
* 修正 Microsoft Outlook 中造成轉譯問題的錯誤。(CAMP-44749)
* 修正修改傳送範本中的&#x200B;**結構元件**&#x200B;填補時發生的錯誤。CSS 標籤沒有保留對填補所做的變更，從而導致轉譯問題。(CAMP-45381)
* 修正上傳影像時的問題。影像的高度自動設為 0，而造成轉譯的問題。(CAMP-45366)

**其他變更**

* 已新增重試機制，以防止嘗試使用&#x200B;**讀取閱聽眾**&#x200B;活動匯入 Experience Platform 閱聽眾時發生錯誤。(CAMP-43947, CAMP-43366)
* 現在會自動設定組織單位，以符合建立設定檔或實體之使用者的組織單位。不得再移除組織單位並將其留空白。
* 發佈自訂資源時，準備後將顯示確認快顯視窗。
* 自訂資源失敗時顯示的快顯視窗訊息已改善，以更清楚明瞭。
* 工作流程中的運算式編輯器已經過改善，以防止執行錯誤。[新功能](../../automating/using/customizing-workflow-external-parameters.md)可供使用：可以用於所有允許您在使用外部參數調用工作流程後使用事件變數的活動中。此外，運算式編輯器中現在會顯示工具提示，其中包含功能說明。
* [交易事件清單中已新增篩選器。](../../administration/using/configuring-transactional-messaging.md#searching-transactional-events)它們允許您根據事件設定的狀態，以及上次接收事件的時間來篩選事件設定。
* 匯出套件時顯示的日誌已更具體，並且詳細地說明在出現故障時遇到的錯誤。
* 傳送訊息後，您現在可以搜尋、篩選及匯出[追蹤的 URL](../../sending/using/tracking-messages.md) 清單。
* [Launch 和 Campaign 之間的自動同步](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)現在為 GA，並且依預設啟用。
* 透過移除發送校樣匯出，工作流程匯出套件的大小已得到最佳化。
* 已新增新訊息，以顯示&#x200B;**檔案傳輸**&#x200B;活動中已下載檔案的大小。
* 無效工作階段權限的錯誤訊息已得到改善。
* 現在，新的機制可防止將目標定位事件的 proxy 新增至追蹤記錄檔和報告中。
* 已新增警告訊息，以協助偵錯連接至傳送活動的資料管理活動。
* 報告工作區中的標籤已得到改善。
* 已新增新驗證步驟，以防止刪除交易式訊息中的科技物件。
* 已在交易式訊息的 **Execution list** 索引標籤中新增傳送狀態的篩選，以改善疑難排解。
* 為了改善效能並最佳化執行時間，根據 350 多個客戶的初步分析中識別資料表的使用情況統計，已移除未使用的索引。受影響的資料表格包括：nmsaddressStatus、nmscampaign、nmsdelivery、nmslandingpage、nmsprogram、nmsrecipient、nmsseedmember、nmsservice、nmssubhistorcp、nmsaudience、xtkworkflow

**修補程式**

* 修正在啟用追蹤時，您無法使用推播通知或應用程式內訊息的目標連結的問題。
* 修正大量傳送時，交易訊息中高優先順序未正確排列的問題。
* 修正無法將品牌指派給交易式電子郵件的問題。發佈步驟中可能會顯示數個錯誤訊息。(CAMP-44988)
* 修正工作流程使用者介面中，無法將資訊儲存在要求數值之欄位中的問題。(CAMP-44025)
* 修正在匯入範本工作流程中使用&#x200B;**測試**&#x200B;活動時，錯誤訊息可能會顯示的問題。(CAMP-42910)
* 修正使用包含列舉類型欄位且連結至&#x200B;**聯合**&#x200B;或&#x200B;**擴充**&#x200B;活動的&#x200B;**讀取對象**&#x200B;活動時發生的問題。(CAMP-42795)
* 修正動態報告中使用現成可用區段來篩選報告資料的問題。(CAMP-42627)
* 修正無法將&#x200B;**排程器**&#x200B;活動設定為 12 AM 的問題。(CAMP-42674)
* 修正當 SMPP 連線不穩定時，可能會中斷 SMS 訊息傳送的問題。(CAMP-42789)
* 修正重新整理頁面後無法顯示&#x200B;**停止準備**&#x200B;按鈕的問題。(CAMP-42721)
* 修正從 URL 匯入內容時，無法顯示點按報告百分比的問題。(CAMP-44468)
* 修正選取要用於設定檔替代內容的設定檔時，可能會顯示逾時錯誤的問題。(CAMP-44746)
* 修正部署包含錯誤連結定義的自訂資源後，執行個體無法運作的問題。(CAMP-44406)
* 修正複製及貼上傳送至行銷活動範本後，建立空白連結實體（類型、品牌等）的問題。(CAMP-44765)
* 修正當資料庫當機或 Azure 上簡單資料庫重新啟動時，由於傳送準備資料表處理不正確，無法傳送校樣的問題。
* 修正在設定多語言內容的傳送中，無法刪除包含 Experience Manager 內容的連結的問題。(CAMP-44029)
* 修正動態報告中嘗試篩選維度時可能顯示錯誤訊息的問題。(CAMP-43097)
* 修正嘗試存取設定有包含特定連結定義之自訂資源執行個體的設定檔時，可能會顯示空白畫面的問題。(CAMP-41009)
* 修正在工作流程中，將&#x200B;**擴充**&#x200B;活動與兩個輸入活動包含兩個目標資源連結在一起時，可能出現的問題。(CAMP-42133)
* 修正使用&#x200B;**檔案傳輸**&#x200B;活動時，匯入工作流程會重複播放的問題。(CAMP-43754)
* 修正當建立包含已匯出日誌的設定檔時，造成未考慮重複項目的問題。(CAMP-45031)
* 修正 Adobe Campaign 中的報告與匯出為 PDF 檔案的報告之間資料不一致的問題。(CAMP-43010)
* 修正在函式中使用現有資料欄位時，造成直接郵件傳送工作流程失敗的錯誤。(CAMP-42737)
* 修正匯入包含交易事件和訊息範本的套件時的問題。匯入程式停止在 5%。(CAMP-42544)
* 修正修改&#x200B;**擴充**&#x200B;活動並在工作流程中新增其他資料後，造成錯誤 (Uncated TypeError) 的問題。(CAMP-41877)
* 修正無法刪除工作流程的錯誤。必須清除日誌才可以刪除工作流程。(CAMP-44144)
* 修正使用 HTML 代碼建立登陸頁面時的錯誤。Campaign 中未識別強制核取方塊，並且無法在已發佈的登陸頁面中使用。(CAMP-44181)
* 修正使用&#x200B;**等待**&#x200B;活動時，導致工作流程重複播放的問題。(CAMP-43981)
* 修正傳送交易式訊息時，造成多個電子郵件地址在同一傳送中多次目標定位的問題。(CAMP-44202)
* 修正將設定檔替代與 targetData 個人化搭配使用時的錯誤。(CAMP-44996)
* 修正匯出套件中的傳送範本時，傳送預覽失敗的問題。(CAMP-44084)
* 修正使用自訂目標對應時，無法將校樣傳送至測試設定檔的問題。(CAMP-43701)
* 修正使用&#x200B;**讀取對象**&#x200B;活動並定位使用&#x200B;**設定檔**&#x200B;以外之目標維度設定之對象時，在工作流程中發生的錯誤。(CAMP-41885)
* 修正當 **updateEventsStatus** 技術工作流程擷取事件歷史記錄（當工作流程停止時）所花費的時間過長時，導致錯誤的問題。未使用的 &quot;sumQueueTime&quot; 彙總欄位已從工作流程中移除，以解決此問題。(CAMP-43920)
* 修正部署自訂資源時的記憶體問題。(CAMP-42909)
* 修正交易式傳訊中，在系列中遺失屬性的問題。現在，所有遺失的屬性都已定義為預設值，並包含在有效負載中。(CAMP-42882)
* 修正查詢即時事件傳送記錄檔時可能影響效能的問題。(CAMP-42759)
* 修正將大寫檔案副檔名與共用資產搭配使用時發生的錯誤。(CAMP-44159)
* 修正在建立外部帳戶之前，測試連線時顯示錯誤訊息的問題。現在僅當已建立外部帳戶後，才會顯示 **Test connection** 按鈕。
* 修正在設定共用的執行個體上重新啟動 Enhanced MTA 後，訊息仍為待處理的問題。
* 修正活動設定檔檔計數與已傳遞傳送之有效數量不符的問題。
* 修正在工作流程的查詢編輯器中搜尋資源時，可能會造成延遲的問題。
* 修正在自訂資源中選取&#x200B;**指定要納入文字搜尋選項的欄位**&#x200B;時的問題。如果欄位清單為空白，則自訂資源發佈失敗。
* 修正顯示包含大量資料之自訂資源的概觀時的效能問題。
* 修正無法使用設定檔替代匯入傳送的問題。
* 修正使用設定檔替代時，如果排程已傳送，無法立即傳送校樣的問題。
* 修正上傳行動應用程式的 Android 金鑰時發生的問題。成功上傳金鑰後顯示的訊息會顯示前一個金鑰的值。
* 修正在建立包含不含屬性之集合的事件設定後，無法從交易式訊息建立測試設定檔的問題。
* 修正當您使用彙總建立新篩選器後，無法發佈自訂資源的問題。
* 修正 Gmail 影像 proxy 造成 Gmail 收件者追蹤開啟率不正確的問題。
* 修正匯入套件時造成記憶體不足錯誤的問題。
* 修正當 Experience Manager 內容包含具有「%20」字元的路徑時，造成 Experience Manager 取消連結動作失敗的問題。
* 修正重複工作流程活動時的標籤錯誤。
* 修正當選取&#x200B;**開始傳送訊息**&#x200B;選項時，登陸頁面中的交易 式訊息選擇的問題。
* 修正交易式訊息或循環傳送無法使用右側預設值初始化傳送狀態的問題。錯誤日誌也得到改善。
* 修正使用自訂欄位將&#x200B;**訂閱擴充至具有設定檔連結的應用程式** (appSubscriptionRcp) 架構的問題。未自動建立索引，這可能會影響推播傳送時間。(CAMP-41120)

