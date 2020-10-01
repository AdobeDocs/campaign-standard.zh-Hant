---
title: 最新版本
description: 本頁詳細說明最新Campaign Standard版本的內容
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: vignes
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7168162baa26c960475d8c9c613989d0338f95c2
workflow-type: tm+mt
source-wordcount: '2387'
ht-degree: 4%

---


# 最新版本{#latest-release}

[發行計畫](../../rn/using/release-planning.md) | [控制面板版本](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/release-notes.html) | [文件更新](../../rn/using/documentation-updates.md) | [先前的發行版本](../../rn/using/release-notes-2020.md) | [已過時的功能](../../rn/using/deprecated-features.md)

## 發行版本 20.4 – 2020 年 10 月 {#release-20-4---october-2020}

**新增了哪些功能？**

<table> 
<thead> 
<tr> 
<th> <strong>控制群組</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>您現在可以使用 <strong>「控制」群組</strong> ，透過排除其受眾的一部分來評估促銷活動的影響。 然後，您就可以比較收到訊息的目標群體行為與未定位之聯絡人的行為。 您也可以根據傳送記錄，在未來的促銷活動中定位控制群組。
</p>
<p>For more information refer to the <a href="../../sending/using/control-group.md">detailed documentation</a> and <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">how-to video</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>外部API - OAuth支援</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Adobe Campaign現在支援OAuth，以便在「外部API」工作 <strong>流程活動中</strong> ，進行驗證。 這項新功能可讓本練習與需要OAuth支援的系統通訊。
</p>
<p>For more information refer to the <a href="../../automating/using/external-api.md">detailed documentation</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Journey AI整合</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>我們很高興為所有Adobe Campaign Standard客戶推出Journey AI。</p>
  <p>Journey AI使用進階的機器學習(ML)，讓公司透過預測每個人的參與偏好，最佳化客戶歷程的設計和傳遞。</p>
  <P>Journey AI包含兩種ML功能：</p>
<ul> 
     <li> <strong>預測性參與計分</strong> -智慧地識別客戶偏好的參與程度，以便更好地鎖定並個人化訊息，以提高轉化率和保留率。 觀看 <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">操作說明影片</a>。</li> 
     <li> <strong>預測性傳送時間最佳化</strong> -預測向促銷活動中的每個人傳送電子郵件的最佳時機，以最大化參與率並改善電子郵件促銷活動的投資報酬率。 觀看 <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">操作說明影片</a>。</li>
    </ul>
  <p>如果您想要瞭解如何開始使用Journey AI，請檢閱詳細的 <a href="../../sending/using/predictive.md">檔案</a> ，並聯絡您的帳戶主管。 請注意，雖然Journey AI可供現有的Campaign客戶免費使用，但實施成本約為50小時。</p>
    </td> 
</tr> 
</tbody> 
</table>

**功能改善**

* **隱私權管理**:「 **** CCPA選擇退出」欄位現在也透過「促銷活動」介面和API提供，現在也可透過「隱私權核心服務」提供支援。 此欄位可讓Adobe Campaign使用者追蹤消費者是否已選擇退出個人資訊的銷售。 [進一步瞭解](https://helpx.adobe.com/content/help/tw/campaign/kb/acs-privacy.html#ccpa)
* **工作流程執行改進** （測試版）:在全球工作流程倡議的背景下，我們已開發出一些重大改進，以穩定記憶體管理、減少延遲並最佳化執行期間工作流程所耗用的記憶體。 這些改良功能目前為beta版，僅適用於一組客戶。 預計於2021年初全面上市。
* 為了改善安全性，Campaign現在使用簽 **名機制** ，來追蹤電子郵件中的連結。
* 上傳iOS憑證或Android金鑰時，行動應 **用程式設定已改良** ，並出現更清楚的錯誤訊息。
* **SMS錯誤管理已經改進** ，以防止將太多配置檔案添加到隔離清單中。 依預設，SMS錯誤現在會設定為軟錯誤，而非硬錯誤。 請參見[此頁面](https://helpx.adobe.com/tw/campaign/kb/sms-connector-protocol-and-settings.html)。

**電子郵件設計人員增強功能**

* 我們已透過全新動態內容相關說明，將使用者介面與檔案完全連結，讓您輕鬆存取最新說明內容，改善了電子郵件設計人員的使用體驗。 ****
* 修正在編輯訊息文字版本時，移除訊息中分行符號的問題。 (CAMP-44483)
* 修正HTML範本的純文字版本無法自動產生及同步的問題。 (CAMP-44195)
* 修正調整影像大小時可能發生的問題。 傳送訊息後，影像在Microsoft Outlook中無法正確顯示。 (CAMP-44656)
* 修正插入按鈕並將其寬度設為「auto」時發生的問題。 傳送訊息後，按鈕的內容就不會完全顯示。 (CAMP-44560)
* 修正從附加的HTML檔案上傳內容時發生的問題。 訊息傳送至Gmail位址後，就無法套用CSS，造成轉換問題。 (CAMP-44085)
* 修正在內容範本中直接修改先前用於訊息的內容片段時，無法更新這些片段的問題。 (CAMP-43973)
* 修正「片段」搜 **尋列的** 問題。 搜索現有片段時，搜索欄未顯示任何結果。 (CAMP-44223)
* 修正「內容區塊」 **和「片段** 」搜 **尋列的問題** 。 使用其中一個搜尋列時，只有在您按一下「顯示更多結果……」時，才 **會顯示結果。**. (CAMP-44205)
* 修正Microsoft Outlook無法套用文字和影像間距的問題。 (CAMP-45370)
* 修正復製片段時的問題。 復製片段後，原始片段遺失HTML行。 (CAMP-45207)
* 修正Microsoft Outlook中產生問題的錯誤。 (CAMP-44749)
* 修正修改傳送範本中的「結 **構元件** 」填補時發生的錯誤。 CSS標籤不會保留對產生演算問題的間距所做的變更。 (CAMP-45381)
* 修正上傳影像時的問題。 影像的高度會自動設為0，造成轉譯問題。 (CAMP-45366)

**其他變更**

* 已新增重試機制，以防萬一嘗試使用「讀取」對象活動匯入Experience Platform對象時 **發生錯誤** 。 (CAMP-43947,CAMP-43366)
* 現在會自動設定組織單位，以符合建立描述檔或實體之使用者的組織單位。 不能再移除組織單位，而留空。
* 發佈自訂資源時，現在會在準備後顯示確認快顯視窗。
* 自訂資源失敗時顯示的快顯訊息已改善，以更清楚明瞭。
* 工作流程中的運算式編輯器已經過改良，以避免執行錯誤。 [提供新功能](../../automating/using/customizing-workflow-external-parameters.md) :這些變數可用於所有活動中，這些活動可讓您在呼叫具有外部參數的工作流程後使用事件變數。 此外，運算式編輯器中現在會顯示工具提示及函式說明。
* [交易事件清單](../../administration/using/configuring-transactional-messaging.md#searching-transactional-events) ，已新增了新的篩選器。 它們允許您根據事件配置的狀態以及上次接收事件的時間來過濾事件配置。
* 導出軟體包時顯示的日誌已更具體和詳細地說明在出現故障時遇到的錯誤。
* 傳送訊息後，您現在可以搜尋、篩選及匯出追蹤的URL [清單](../../sending/using/tracking-messages.md)。
* Launch [和Campaign之間的自動同步現在](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) GA，並依預設啟用。
* 移除傳送校樣匯出，已最佳化工作流程匯出封裝的大小。
* 已新增新訊息，以顯示「檔案傳輸」活動中已下載檔案 **的大小** 。
* 無效作業Token的錯誤訊息已改進。
* 現在，新的機制可防止將追蹤事件的proxy新增至追蹤記錄檔和報告。
* 已新增警告訊息，以協助除錯連接至傳送活動的資料管理活動。
* 報表工作區中的標籤已改善。
* 已新增驗證步驟，以防止在交易訊息中刪除技術物件。
* 已在事務性訊息的「執行清單」標籤中新增傳送狀態 **的篩選** ，以改善疑難排解。
* 為了改善效能並最佳化執行時間，根據初步分析中針對350位以上客戶所識別之表格的使用統計資料，已移除未使用的索引。 受影響的表格包括：nmsaddressStatus, nmscampaign, nmsdelivery, nmslandingpage, nmsprogram, nmsrecipient, nmsseedmember, nmssubhistorcp, nmssubhistorcp, nmsaudience, xtkworkflow

**修補程式**

* 修正在啟用追蹤時，您無法使用推播通知或應用程式內訊息的目標連結的問題。
* 修正當大量傳送時，交易訊息中的高優先順序不受重視的問題。
* 修正無法將品牌指派給交易電子郵件的問題。 發佈步驟中可能會顯示數個錯誤訊息。 (CAMP-44988)
* 修正工作流程使用者介面中，無法將資訊儲存在要求數值之欄位中的問題。 (CAMP-44025)
* 修正在匯入範本工作流程中使用 **Test** 活動時，可能顯示錯誤訊息的問題。 (CAMP-42910)
* 修正使用包含列舉類型欄位且連結至 **Union** 或Enrichment活動的「讀取對象 **」活動時發生的問題****** 。 (CAMP-42795)
* 修正動態報表中使用現成可用區段來篩選報表資料的問題。 (CAMP-42627)
* 修正無法將「排程器」活動設 **定為** 12 AM的問題。 (CAMP-42674)
* 修正當SMPP連線不穩定時，可能會中斷SMS訊息傳送的問題。 (CAMP-42789)
* 修正重新整理頁面後無 **法顯示** 「停止準備」按鈕的問題。 (CAMP-42721)
* 修正從URL匯入內容時，無法顯示點按報表百分比的問題。 (CAMP-44468)
* 修正選取要用於描述檔替代內容的描述檔時，可能會顯示逾時錯誤的問題。 (CAMP-44746)
* 修正部署包含錯誤連結定義的自訂資源後，例項無法運作的問題。 (CAMP-44406)
* 已修正建立空白連結實體（類型、品牌等）的問題 將傳送複製並貼至促銷活動範本之後。 (CAMP-44765)
* 修正當資料庫當機或Azure上簡單資料庫重新啟動時，由於傳送準備表處理不正確，無法傳送校樣的問題。
* 修正在設定多語言內容的傳送中，無法刪除包含Experience Manager內容的連結的問題。 (CAMP-44029)
* 修正動態報表中嘗試篩選維度時可能顯示錯誤訊息的問題。  (CAMP-43097)
* 修正嘗試存取設定有包含特定連結定義之自訂資源之例項的描述檔時，可能會顯示空白畫面的問題。 (CAMP-41009)
* 修正在工作流程中，將 **Enrichment** 活動與兩個輸入活動搭配使用時，可能會發生的問題。 (CAMP-42133)
* 修正使用檔案傳輸活動時，匯入工作流程會回 **圈的問題** 。 (CAMP-43754)
* 修正當建立包含已匯出記錄的描述檔時，造成未考慮重複項目的問題。 (CAMP-45031)
* 修正Adobe Campaign中的報表與匯出為PDF檔案的報表之間資料不一致的問題。 (CAMP-43010)
* 修正在函式中使用現有資料欄位時，造成直接郵件傳送工作流程失敗的錯誤。 (CAMP-42737)
* 修正匯入包含交易事件和訊息範本的套件時的問題。 匯入程式停止在5%。 (CAMP-42544)
* 修正修正修改Enrichment活動並在工作流程中新增其他資料後，造成錯誤(Uncated TypeError) **的問題** 。 (CAMP-41877)
* 修正無法刪除工作流程的錯誤。 必須清除日誌才能刪除工作流。 (CAMP-44144)
* 修正使用HTML程式碼建立著陸頁面時的錯誤。 「促銷活動」中未識別強制核取方塊，且無法在已發佈的登陸頁面中使用。 (CAMP-44181)
* 修正使用「等待」活動時導致工作流循環 **的問** 題。 (CAMP-43981)
* 修正傳送交易訊息時，導致多個電子郵件地址在同一傳送中多次定位的問題。 (CAMP-44202)
* 修正將描述檔替代與targetData個人化搭配使用時的錯誤。 (CAMP-44996)
* 修正匯出套件中的傳送範本時，傳送預覽失敗的問題。 (CAMP-44084)
* 修正使用自訂目標映射時，無法將校樣傳送至測試描述檔的問題。 (CAMP-43701)
* 修正使用「讀取對象」活動並定位使用「設定檔」以外之定位維度 **設定之對象時** ，在工作流程中發生的 **錯誤**。  (CAMP-41885)
* 修正當 **** updateEventsStatus技術工作流程擷取事件歷史記錄（當工作流程停止時）所花費的時間過長時，導致錯誤的問題。 未使用的&quot;sumQueueTime&quot;聚合欄位已從工作流中刪除，以解決此問題。 (CAMP-43920)
* 修正部署自訂資源時的記憶體問題。 (CAMP-42909)
* 修正交易傳訊中，在系列中遺失屬性的問題。 現在，所有遺失的屬性都已定義為預設值，並包含在裝載中。 (CAMP-42882)
* 修正查詢即時事件傳送記錄時可能影響效能的問題。 (CAMP-42759)
* 修正將大寫檔案副檔名與共用資產搭配使用時發生的錯誤。 (CAMP-44159)
* 修正在建立外部帳戶之前，測試連線時顯示錯誤訊息的問題。 現在 **只有建立外部帳戶後** ，才會顯示「測試連線」按鈕。
* 修正在設定共用的例項上重新啟動「增強MTA」後，訊息仍為擱置的問題。
* 修正活動描述檔計數與已傳送傳送之有效數目不符的問題。
* 修正在工作流程的查詢編輯器中搜尋資源時，可能會造成延遲的問題。
* 修正在自訂資源中選 **取「指定要納入文字搜尋選項的欄位** 」時的問題。 如果欄位清單為空，則自定義資源發佈失敗。
* 修正顯示包含大量資料之自訂資源的概述時的效能問題。
* 修正無法使用描述檔替代匯入傳送的問題。
* 修正使用描述檔替代時，如果排程傳送，無法立即傳送校樣的問題。
* 修正上傳行動應用程式的Android金鑰時發生的問題。 成功上傳索引鍵後顯示的訊息會顯示前一個索引鍵的值。
* 修正在建立包含不含屬性之集合的事件設定後，無法從交易訊息建立測試設定檔的問題。
* 修正當您使用匯整建立新篩選器後，無法發佈自訂資源的問題。
* 修正Gmail影像proxy造成Gmail收件者追蹤開啟率不正確的問題。
* 修正匯入封裝時造成記憶體不足錯誤的問題。
* 修正當Experience Manager內容包含具有「%20」字元的路徑時，導致Experience Manager取消連結動作失敗的問題。
* 修正複製工作流程活動時的標籤錯誤。
* 修正當選取「開始傳送訊息」選項時，著陸頁面中的交易 **式訊息選擇器** ，問題。
* 修正交易訊息或循環傳送無法使用右側預設值初始化傳送狀態的問題。 錯誤記錄也已改進。
* 修正使用自訂欄位將訂閱擴 **充至具有描述檔連結的應用程式** (appSubscriptionRcp)架構的問題。 未自動建立索引，這可能會影響推播傳送時間。 (CAMP-41120)

