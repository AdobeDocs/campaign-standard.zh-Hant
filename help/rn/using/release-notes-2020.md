---
solution: Campaign Standard
product: campaign
title: 發行說明 2020 年
description: 本頁列出 2020 年的所有 Adobe Campaign Standard 版本。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: 36e0f6be4dc8c1a6e4b0d8878d190f2abce99fcd
workflow-type: tm+mt
source-wordcount: '5323'
ht-degree: 100%

---


# 發行說明 2020 年{#release-notes-2020}

[發行計畫](https://helpx.adobe.com/tw/campaign/kb/acs-release-planning.html) | [控制面板版本](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/release-notes.html) | [文件更新](../../rn/using/documentation-updates.md) | [先前的發行版本](../../rn/using/release-notes-2019.md) | [已過時的功能](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hant#release-notes)

![](assets/do-not-localize/cp-icon.png) **新的控制面板 6 月版本**，包含作用中設定檔監控、子網域傳遞送能力稽核及 GPG 金鑰管理。[進一步瞭解](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)。

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
* [交易事件清單中已新增篩選器。](../../channels/using/configuring-transactional-event.md#searching-transactional-events)它們允許您根據事件設定的狀態，以及上次接收事件的時間來篩選事件設定。
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



## 版本 20.3 - 2020 年 5 月{#release-20-3---may-2020}

**新增功能？**

<table> 
<thead> 
<tr> 
<th> <strong>泰國個人資料保護法 (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>泰國個人資料保護法 (PDPA) 是一項新的隱私法律，協調並現代化泰國的資料保護要求。此法規適用於持有資料且居住在此國家之「資料主體」的 Adobe Campaign 客戶。</p>
<p>除了 Adobe Campaign 中已提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）外，我們還將利用這個機會加入其他功能，以協助您作好 PDPA 的準備：</p>
<ul>
<li>存取權限與刪除權限：我們已運用 GDPR 和 CCPA 新增的功能。<a href="https://helpx.adobe.com/content/help/tw/campaign/kb/acs-privacy.html#righttoaccess">進一步瞭解</a> </li>
<li><p>建立隱私權要求時，PDPA 規則類型已新增至隱私權核心服務。此方法是您應該用於所有存取和刪除請求的方法。不建議使用促銷活動 API 和介面來存取和刪除請求。請參閱「<a href="../../rn/using/deprecated-features.md">已過時和已移除的功能</a>」文章。</p></li>
</ul>
<p>請參閱<a href="https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/privacy/privacy-overview.translate.html">作法影片</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>External API 活動 (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p><strong>External API</strong> 活動正在從測試版轉換為 GA。此版本為 JSON 回應本體剖析器提供額外的彈性。您現在可以：</p>
<ul>
<li>剖析最大深度為 10 個層級的巢狀 JSON。 </li>
<li>從 JSON 將選取的屬性剖析為葉節點，並將其平面化為單一表格列。</li>
<li>從 JSON 選取並使用陣列物件，而不需將物件命名為 "data"，或讓它位於頂層。</li>
</ul>
<p><strong>注意：</strong>客戶在其工作流程中，需要使用 GA External API 活動來<strong>取代所有測試版 External API 活動</strong>。使用 External API 測試版的工作流程將在 20.3 中停止運作。</p>
<p>如需詳細資訊，請參閱<a href="../../automating/using/external-api.md">詳細文件</a>及<a href="https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.translate.html">作法影片</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

**其他功能**（從 7 月 13 日起）

* **由 AI 支援的傳送時間最佳化和設定檔計分** - 您現在可以最佳化客戶歷程的設計和傳遞，以預測每個人的參與偏好。Adobe Campaign 採用 Journey AI，可根據歷史參與量度來分析和預測開放率、最佳傳送時間和可能的流失率。[進一步瞭解](../../sending/using/predictive.md)
* **巴西的新隱私權規範** - 除了 Campaign 中已提供的隱私權功能以外，Adobe 協助您做好準備，以迎接巴西的 Lei Geral de Proteçao de Datos (LGPD)。建立隱私權要求時，LGPD 規則類型已新增至 Adobe 隱私權核心服務。[進一步瞭解](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy-overview.html)

**改進**

* 在 **Prefix** 欄位中可用於[使用目標設定檔之測試訊息](../../sending/using/testing-messages-using-target.md)的字元數，已經從 32 增加為 500 個字元。
* 可在執行個體上發佈的即時事件數上限，已經從 350 增加為 2000。(CAMP-41608)
* 使用 syncWithLaunch 技術工作流程，已改善 Adobe Launch 和 Campaign Standard 之間的同步化。此工作流程可自動將所有 Adobe Launch 行動裝置屬性匯入 Adobe Campaign Standard。如需詳細資訊，請參閱[本頁面](../../administration/using/technical-workflows.md)。

   您必須將票證提交至 Adobe 客戶服務（直接或透過您的 Adobe 聯絡人），才能在您的 Campaign 執行個體中啟用 syncWithLaunch 技術工作流程。(CAMP-40082)

**電子郵件設計工具增強功能**

* 與嚴格的 W3C 相比，電子郵件設計人員現在可以處理更有彈性的 HTML 格式。(CAMP-42529)
* 修正[可點選影像](../../designing/using/links.md#inserting-a-link)的問題，以防止連結在內容區塊中顯示在影像旁邊。(CAMP-41586)
* 修正當[追蹤的 URL](../../designing/using/links.md#about-tracked-urls) 在範本中新增類別時，無法重新導向至登錄頁面的問題。(CAMP-41537)
* 修正 Outlook 中按鈕間距的問題。
* 修正 HTML 標籤顯示為純文字的問題。
* 內容區塊搜尋現在會顯示伺服器搜尋結果以及預先載入的結果。(CAMP-41870)

**其他變更**

* 自訂資源發佈介面已改善，並包含更清楚的錯誤訊息。
* 未使用的傳送對應已從介面中刪除。
* 已從介面中刪除不必要的管理員角色。
* 現在，登錄頁面中的核取方塊是強制性的。
* 下載動態報告的 CSV 檔案時，已移除 200 列的限制。您現在可以將報告的每一列納入其中。(CAMP-40810)
* 在多語言電子郵件的現成可用語言清單中新增 ES-US 語言。(CAMP-42279)
* 隨「傳輸檔案」活動下載的檔案現在會在 X 天後刪除，其中 X 由「工作流程」屬性中 **Execution** 功能表的 **History in days** 欄位決定。[瞭解詳情](../../automating/using/managing-execution-options.md)

**體驗平台整合**

* 從&#x200B;**讀取閱聽眾**&#x200B;活動啟動 Adobe [Experience Platform Audiences](../../automating/using/aep-targeting-audiences.md) 已經有所改善，而可提供較出色的效能及穩定性。此外，工作流程記錄檔已經更清楚且更詳細地記錄啟動工作，讓您在讀取 Adobe Experience Platform 閱聽眾時，能夠更輕鬆地進行監控和疑難排解。

**修補程式**

* 修正導致在自訂資源的發佈工作期間建立 Ghost 資源的錯誤。
* 修正當設定檔資源已擴充至自訂資源時，可能無法顯示設定檔行銷歷史記錄的問題。(CAMP-41009)
* 已修正開啟編輯器時，以法文顯示其內容的現成可用登錄頁面範本問題。(CAMP-41639)
* 修正動態內容的推播通知無法顯示表情符號的問題。(CAMP-40715)
* 修正&#x200B;**重複資料刪除**&#x200B;活動，可能導致將錯誤的段代碼分配給其中一個出站補充轉變的問題。(CAMP-41400)
* 修正無法刪除排程報告的錯誤。(CAMP-41302)
* 修正傳送控制面板與&#x200B;**傳送摘要**&#x200B;報告之間不一致的問題。(CAMP-41145)
* 修正導致下載報告中出現字元重疊顯示問題的問題。
* 修正傳送預覽無法用於校樣替代的問題。
* 修正刪除應用程式內本機通知的自訂欄位時的錯誤。
* 修正 charIndex 函式無法在工作流程中處理&#x200B;**結束**&#x200B;或&#x200B;**檔案傳輸**&#x200B;活動的問題。
* 修正工作流程中，將&#x200B;**擴充**&#x200B;活動與兩個輸入活動（包括目標資源之間有連結）搭配使用時可能發生的問題。(CAMP-42133)
* 修正使用未知函式時，工作流程無法執行的問題。(CAMP-41873)
* 修正工作流程中，使用數個&#x200B;**儲存閱聽眾**&#x200B;活動來建立閱聽眾時可能會發生的問題，這些活動會補充外站轉變。(CAMP-39992)
* 修正在交易電子郵件中使用個人化時造成資料不一致的問題。(CAMP-41842)
* 修正刪除推播通知傳送中的自訂欄位時發生的問題。(CAMP-37586)
* 修正使用者無法變更報告的錯誤。(CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **新的控制面板可能會與 CNAME 子網域發行**&#x200B;憑證續約。[進一步瞭解](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)。

## 版本 20.2 – 2020 年 4 月 {#release-20-2---april-2020}

**新增功能？**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob 整合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure Blob 儲存連接器現在可用來使用<strong>傳輸檔案</strong>工作流程活動，將資料匯入或匯出至 Adobe Campaign。 </p>
    <p>如需詳細資訊，請參閱<a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">詳細文件</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>使用目標設定檔進行電子郵件測試</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>除了測試設定檔以外，您現在還可以在真正的目標設定檔上測試電子郵件。這可讓您獲得設定檔將會收到的訊息的精確表示：自訂欄位、動態和個人化資訊，包括工作流程的其他資料等。 </p>
    <p>如需詳細資訊，請參閱<a href="../../sending/using/testing-messages-using-target.md">詳細文件</a>及<a href="https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.translate.html">教學影片</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>新功能將於 4 月在「Campaign 控制面板」中發佈，包括 Google TXT 記錄管理、資料庫空間監控和電子郵件警報。有關這些功能的詳細資訊，請參閱[控制面板發行說明](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)。

**改進**

* 交易式訊息使用者體驗已增強，介面一致性也已獲改善。[瞭解詳情](../../channels/using/getting-started-with-transactional-msg.md)
* Campaign Standard 現在可讓您使用工作流程的其他資料，將校樣傳送至測試設定檔。
* 外部 API 活動的護欄已更新。[瞭解詳情](../../automating/using/external-api.md)

**電子郵件設計工具增強功能**

* 修正在個人化影像上多次點按時影響逸出的問題。
* 修正複製動態文字元件時，可能導致重複的錯誤行問題。(CAMP-41249)
* 在表格層級進行填補（而非 div 層級）時，藉由在 Outlook 中進行填補以修正問題。
* 修正在切換至 HTML 模式時，影像寬度遭到修改的問題。(CAMP-41116)
* 修正當為圖示提供替代文字時，無法存取社交媒體元件的問題。(CAMP-41345)
* 修正在「電子郵件設計工具」中使用複製貼上時，顯示可見 `<br>` 標籤的問題。
* 修正從 HTML 內容切換為純文字後，HTML 索引標籤顯示在電子郵件中的問題。(CAMP-41138)
* 修正無法呈現只定義一個邊框之按鈕的問題。
* 修正 HTML 縮排中，造成 Microsoft Outlook 中電子郵件頁尾向左移動的問題。(CAMP-40987)
* 修正當切換為純文字模式時，HTML 中定義的系列屬性個人化欄位會複製到純文字內容的問題。(CAMP-40365)
* 修正無法在選取的文字區段上插入連結的問題。(CAMP-41406)
* 修正在查詢編輯器中選取時區時，日期變更的問題。(CAMP-38277)

**其他變更**

* **使用 Adobe Analytics 進行 KPI 調解**&#x200B;現在會執行至目前日期，而非在一天內執行。
* MCPNS 不支援將 APNS 和 APNS-SANDBOX 新增為應用程式中的平台。在 Adobe Campaign Standard 中成功新增憑證後，您現在無法再將設定變更回原來，因為 MCPNS 應用程式只能新增一個 APNS 平台（生產或沙盒）。

**體驗平台整合**

>[!NOTE]
>
>Campaign Standard 中的 Adobe Experience Platform 功能目前為測試版，可能會經常更新，恕不另行通知。請參閱詳細說明文件：[體驗平台資料連接器](../../developing/using/aep-about-data-connector.md)，[對象目的地](../../audiences/using/aep-about-audience-destinations-service.md)

* 在工作流程記錄中，每隔 10 分鐘，Campaign 現在會顯示目前執行中的工作已處理的記錄數。
* 修正匯入已從資料庫刪除的 Adobe Experience Platform 設定檔時可能發生的問題。
* 修正工作流程記錄中，針對匯入記錄總數顯示錯誤結果的問題。

**修補程式**

* 修正在 **Alias** 欄位中新增空格後，接著建立新列項目時，**擴充**&#x200B;工作流程活動可能發生的問題。(CAMP-39229)
* 修正傳送證明訊息時，每個測試設定檔都可定位的問題。
* 修正取消發佈和刪除事件設定後發生的問題。[瞭解詳情](../../channels/using/publishing-transactional-event.md#deleting-an-event)
* 修正變更工作流程時 **Save** 按鈕消失的問題。
* 修正在 Campaign 處理後手動刪除隱私權要求時，即使在清除後，與要求相關的資料也無法刪除的問題。
* 修正預覽或傳送包含 Adobe Experience Manager 特殊字元之訊息時可能發生的問題。
* 修正執行具有數個入站轉變的活動時，工作流程中可能發生的問題。
* 修正標準使用者無法在工作流程查詢或傳送中將「訂閱應用程式」作為目標維度的問題。(CAMP-37618)

## 版本 20.1.4 - 2020 年 2 月 {#release-20-1-4---february-2020}

* 修正在現有工作流程中開啟&#x200B;**讀取對象**&#x200B;活動的問題。(CAMP-41002)

## 版本 20.1.3 - 2020 年 2 月 {#release-20-1-3---february-2020}

* 修正 CAMP-39273 在 20.1 中針對使用漏洞之客戶所引進的回歸問題。已反轉 CAMP-39273。

## 版本 20.1.2 - 2020 年 2 月 {#release-20-1-2---february-2020}

**電子郵件設計工具增強功能**

* 修正修補過期片段並儲存內容時，在過期片段中新增 HTML 索引標籤元素的問題。(CAMP-40685)
* 修正使用動態內容時新增空格的問題。(CAMP-40605)
* 修正設定交易式電子郵件範本時的問題。(CAMP-40604)

## 版本 20.1 – 2020 年 2 月 {#release-20-1---february-2020}

**新增功能？**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector (beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector 現在已與 Adobe Campaign Standard 整合。您可以將 XTK 資料（在 Campaign 中收錄的資料）對應至 Adobe Experience Platform 資料模型 (XDM)，讓您的 Campaign 資料可在 Adobe Experience Platform 上使用。 </p>
    <p>請注意，此功能僅適用於 Azure 上代管的客戶。如需啟動此功能與條件的詳細資訊，請參閱<a href="../../developing/using/aep-about-data-connector.md">詳細文件</a>及<a href="https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.translate.html">作法影片</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>對象目標（測試版）</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>對象目標可讓您將 Adobe Experience Platform 的分段共用給 Adobe Campaign。</p>
    <p>請注意，此功能僅適用於 Azure 上代管的客戶。如需啟動此功能與條件的詳細資訊，請參閱<a href="../../audiences/using/aep-about-audience-destinations-service.md">詳細文件</a>及<a href="https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html">作法影片</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**改進**

* Enhanced MTA 的全球可用性：訊息（包括交易訊息）現在由 Adobe Campaign Enhanced MTA 傳送，此 MTA 提供升級的傳送基礎架構，可改善傳送能力、吞吐量和退信處理。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/campaign-enhanced-mta.html)

* 已增強時區管理。您現在可以為整個工作流程定義[特定時區](../../automating/using/building-a-workflow.md)。所選時區將應用於工作流程的所有活動。為運算子或伺服器設定的時區資訊現在顯示在介面中（在日誌中，在選取時區後）。(CAMP-37672)

* 現在，透過將 `_forcePagination=true` 參數新增至呼叫 URL，您可在使用大型表格時，使用 Campaign Standard API 來執行分頁。[瞭解詳情](../../api/using/pagination.md)

* 「傳送記錄檔 ID」（每個記錄檔的唯一識別碼）現在可用於所有定位維度的「傳送記錄檔」和「追蹤記錄檔」資源。舉例來說，這可在匯出時識別傳送或追蹤記錄檔。[瞭解詳情](../../automating/using/exporting-logs.md)

**電子郵件設計工具增強功能**

* 已新增在建立對象時遺漏的強制文字指示。
* 修正按一下舊版電子郵件編輯器精靈中 **Change content** 按鈕的問題。
* 修正無法將標題與「服務摘要」報表上的內容對齊的問題。(CAMP-38103)
* 修正無法刪除動態內容變體而不會影響主題行其餘部分的問題。(CAMP-40096)
* 修正在主旨行上使用 B 變體時的 A/B 測試問題。(CAMP-40327)
* 修正使用「上傳 HTML」匯入功能時無法拖放檔案的問題。(CAMP-39326)
* 修正無法從文字編輯器複製和貼上文字的問題。(CAMP-39028)
* 修正無法顯示字詞建議的問題。(CAMP-38970)
* 修正使用者無法儲存片段的問題。(ATU-2447)
* 修正動態結構無法複製的問題。(CAMP-38367)
* 修正複製動態內容時無法保留條件的問題。(CAMP-39051)

**其他變更**

* 「已準備的傳送失敗」篩選條件現在會考量傳送的建立日期，而非上次修改日期。
* 管理員安全組的組織單元不能再更改。
* 建立設定檔案時，現在必須填寫「組織單位」欄位。
* 現在，只有刪除連結至 Experience Cloud 的事件和交易範本時，才能刪除 Experience Cloud 觸發器。
* [!DNL Adobe Creative SDK] 已終止服務。現在已在 Campaign Standard 中停用。請參閱[已過時和已移除的功能](../../rn/using/deprecated-features.md)頁面。


**修補程式**

* 修正執行刪除隱私權要求時，排除記錄中無法刪除使用者資料的問題。(CAMP-39003)
* 修正在容器元素中調整文字大小時導致協助工具問題。
* 修正使用者無法關閉行銷活動暫留中顯示之「行事曆」快顯視窗的問題。
* 修正即使未修改任何資料，仍顯示 **[!UICONTROL Confirm]** 按鈕的 **[!UICONTROL External API]** 活動問題。
* 修正針對不同目標維度的查詢使用 **[!UICONTROL Union]** 活動的問題。轉變資料只顯示主要集定位維度的記錄。(CAMP-36831)
* 修正在特定內容中使用活動（例如，如有兩個入站　**[!UICONTROL Reconciliation]** 活動，其中一個是排除活動）時，可能導致錯誤的問題。(CAMP-37490)
* 已修正選取和更新測試設定檔時可能發生的效能問題。(CAMP-37976)
* 修正透過登錄頁面訂閱或取消訂閱時，可能顯示錯誤頁面的問題。(CAMP-37771)
* 已修正以郵遞區號格式上傳內容時，HTML 中參照的 PNG 檔案副檔名為大寫字母的問題。(CAMP-37913)
* 修正在傳送中新增測試設定檔時，無法傳送應用程式內訊息的問題。
* 修正連結至擴充活動時，外部 API 工作流程活動失敗的錯誤。
* 修正可能導致 SMS 訊息狀態顯示錯誤的問題。
* 修正自訂資源造成重複項目出現在不同 API 端點下的問題。
* 修正發佈後無法使用登錄頁面的問題。(CAMP-38695)
* 已修正顯示來自兩個不同資源之「交叉點」轉場的資料時發生的錯誤。(CAMP-38974)
* 修正傳遞範本中的分項清單設定不正確的問題。(CAMP-38388)
* 修正電子郵件大量傳送的錯誤，此錯誤會將傳送的狀態顯示為「擱置中」，而「傳送的狀態」顯示為「已完成」。(CAMP-35355)
* 修正「動態」報表中錯誤顯示傳送者網域的錯誤。(CAMP-33123)
* 修正動態報表中「取消訂閱」計數不一致的問題。(CAMP-39949)
* 修正傳送應用程式內訊息時，「傳送記錄檔」畫面無法顯示位址的問題。
* 修正 SMS 傳送記錄檔無法以正確退信更新的問題。(CAMP-38395)
* 已修正允許應用程式訂閱貼文呼叫更新推播通知權杖的漏洞。(CAMP-39273)
