---
title: 最新版本
description: 本頁詳細說明最新 Campaign Standard 版本的內容
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 7066cf1d8454ffdefa29bff5092ba2c3e1bac705
workflow-type: tm+mt
source-wordcount: '1766'
ht-degree: 99%

---


# 最新版本{#latest-release}

## 發行版本 22.1 – 2022 年 2 月 {#feb-2022}

**有哪些新功能？**

<table> 
<thead> 
<tr> 
<th> <strong>Apache Log4j 安全漏洞的安全更新</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j 修復了 Apache log4j v2.17.1 發行版本中報告的漏洞。 Adobe Campaign Standard 使用 Apache log4j，在此版本中包括此最新的 Apache log4j v2.17.1 </p>
</td> 
</tr> 
</tbody> 
</table>

**安全性修正**

* 此發行版本中包含用於追蹤的新 URL 簽章機制。 已停用先前的追蹤連結機制，以防止在第三方安全工具修改後，造成某些有效且已簽署的追蹤連結遭到錯誤封鎖的問題。(CAMP-48983)

**功能改進**

* 改進了報告資料的處理，以避免系統過載。 (CAMP-47578)
* 在傳送您的應用程式內訊息後，您現在可以選擇停用您的傳遞。 這樣，您便可刪除傳遞內容，而不會遺失任何報告資料。 (CAMP-48469)
* 為防止出現任何問題，對於自訂表格欄名稱，使用者無法再使用跟資料庫自動化主要金鑰相同的名稱， `"<dataType><resourceName>Id"`。 (CAMP-49358)
* 您現在可以監視您的傳遞，並在您的訊息控制面板使用新的&#x200B;**作業歷史記錄**&#x200B;下拉式清單。 (CAMP-49840)
* 在一段時間內跨所有通道傳送大量訊息時，透過減少無作用的元組，提高了穩定性和資料庫健康情況。 (CAMP-49755、CAMP-49792、CAMP-49849)
* 為確保在資料庫當機或重新啟動時自動重新整理資料庫連線，改進了 Campaign 郵件傳輸代理程式 (MTA)。 (CAMP-48063)


**修補程式**

* 已修復動態報告中的&#x200B;**立即傳送報告**&#x200B;選項的問題：產生 PDF 作業失敗，因傳遞包括多個變體。 (CAMP-49120)
* 已修復問題，該問題在 AEM 的重複內容共用相同金鑰時，阻止使用者重新整理 Adobe Campaign Standard 傳遞或取消連結 Adobe Experience Manager (AEM) 內容。 (CAMP-49161)
* 修復了存取頁面無法載入、無法開啟傳遞或無法儲存任何待修改內容的執行個體時出現問題。 (CAMP-50195)
* 針對在未填入由標準套用的&#x200B;**傳遞篩選器**&#x200B;欄位時，修復阻止開啟傳遞提醒條件的問題。 (CAMP-49093)
* 針對在編輯應用程式內傳遞的&#x200B;**次要**&#x200B;按鈕時，修復無法納入變更的問題。 (CAMP-50250)
* 修復了日文執行個體的錯誤，該錯誤阻止使用者在&#x200B;**排程器**&#x200B;活動中選擇一天數次作為&#x200B;**執行頻率**。 (CAMP-50247)
* 修復了日文使用者介面的問題，該介面在「排程器」活動中選擇時間時顯示錯誤訊息。 (CAMP-49289)
* 修復推送通知報告錯誤，該報告將推送通知顯示為&#x200B;**開啟**&#x200B;而非&#x200B;**印象**。 (CAMP-45980)
* 修復在開啟報告時可能導致錯誤的問題。 (CAMP-49222)
* 修復在刪除指向 AEM 內容的連結後可能導致電子郵件準備失敗的問題。 (CAMP-49877)
* 為了解決各種問題，針對包括從 URL 匯入的內容改進了遞送的重試機制。 [瞭解更多資訊](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* 修復了在自訂資源中建立新篩選器後發生的問題，然後將其作為登陸頁面中的調解金鑰。 如再次發佈自訂資源，則會從登陸頁面的可用調解金鑰清單中刪除該篩選器。 (CAMP-49516)
* 針對當登陸頁面使用帶有核取方塊的動態條件時，修復其中的問題。 (CAMP-48604)
* 修復當&#x200B;**查詢**&#x200B;活動使用「十月或之前」篩選器條件時發生的問題。 當利用設定為歐洲時區的執行個體時，由於轉換時區出現問題，篩選器的選定月份顯示為 9 月而非 10 月。 (CAMP-48602)
* 為了最佳化傳遞能力，在 Adobe Campaign 傳送電子郵件時現在使用 7 位元編碼而非 8 位元編碼。 此舉避免因中繼緣故使 DKIM 簽名失效，而可能影響訊息的真實性。 (CAMP-49016)
* 為了避免當與大數量受眾合作時出現任何問題，加強了複製受眾時的效能。 (CAMP-49639)
* 修復可能會阻止自訂篩選器在用於&#x200B;**查詢**&#x200B;活動時顯示正確結果的問題。 (CAMP-49417)
* 針對在名稱中帶有逗號的情況下嘗試在傳遞中使用該片段時顯示錯誤訊息，修復了錯誤。問題已解決，現在可以在片段名稱中使用逗號。 (CAMP-49216)


## 發行版本 21.3 – 2021 年 9 月 {#release-21-3---sept-2021}

以下列出最新 Campaign Standard 發行版本中包含的新功能、改善和修正。

**有哪些新增功能？**

<table> 
<thead> 
<tr> 
<th> <strong>統一的 Experience Cloud 介面</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign 頁首已變更，以統一並改善您所有 Experience Cloud 產品和服務的體驗。這些變更旨在讓您的生活更輕鬆，包括：</p>
<ul>
<li>更輕鬆地在組織之間切換，或切換至不同的應用程式。</li>
<li>改進的使用者說明 - 將 Experience League 帶入產品中，搜尋結果也包含社群論壇的結果和更多視訊內容，讓您更輕鬆地存取更多內容，以協助您充分運用應用程式。我們也在「說明」功能表中新增了意見回饋機制，讓您更輕鬆地報告問題或分享您的想法。</li>
<li>改進的通知 - 通知下拉式清單現在有兩個索引標籤：一個用於您自己的產品通知，另一個用於更多全球產品公告。</li>
</ul>
<p>如需詳細資訊，請參閱<a href="../../start/using/interface-description.md#top-bar">詳細文件</a>。
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>稽核軌跡</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>新的稽核軌跡功能可以針對在 Adobe Campaign 內發生的動作和事件即時擷取完整清單。功能包括自助式存取歷史資料記錄，以協助回答下列問題：</p>
<ul>
<li>此工作流程有什麼改變，上次更新的是誰？</li>
<li>上次進行變更的是誰？</li>
<li>上一個狀態是什麼？</li>
</ul>
<p>Adobe Campaign 現在會稽核下列項目的建立、編輯和刪除動作：工作流程、選項、自訂資源。 也會追蹤這些項目的修改。</p>
<p>如需詳細資訊，請參閱<a href="../../administration/using/audit.md">詳細文件</a>。</p>
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>工作流程診斷模式</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>您現在可以透過診斷模式執行 Campaign 工作流程。 此模式會記錄資訊，以協助疑難排解執行問題。 如果工作流程查詢預設需要超過一分鐘的時間，則記錄整個執行計劃。</p>
<p>如需詳細資訊，請參閱<a href="../../automating/using/managing-execution-options.md">詳細文件</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

**安全性改善**

* 已增強安全性，以防止 SSRF 攻擊。 (CAMP-47836)
* 使用者清單現在僅限管理員使用。 (CAMP-47260)
* 無法繼續於 URL 中的參數展開環境變數。 (CAMP-47268)

**功能改善**

* 在連結至 Adobe Experience Manager 內容的工作流程中建立循環傳送時，現在會在傳送前檢查內容核准狀態。
* 資料庫連線限制現在已與 Campaign 套件對齊，以避免連線錯誤。
* 自訂資源發佈中的新一致性檢查會防止使用者建立重複索引，進而導致發佈失敗。 改善的錯誤訊息會視需求要求用戶重新命名索引。[了解更多](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)

**其他變更**

* Adobe Experience Platform Data Connector 和 Audience Destinations 服務現已透過 Campaign Standard 被棄用。 如果您正在使用這些功能，則需移至 Adobe Sources 和 Destinations，並調整您的實作。 [了解更多](../../integrating/using/get-started-sources-destinations.md)
* [此頁面](deprecated-features.md)中列出已棄用和已移除的功能。
* 引入新的「StringAgg」匯總函式以串連字串類型欄的值。 (CAMP-47077)[ 進一步瞭解](../../automating/using/list-of-functions.md#aggregates)
* 已改善&#x200B;**更新傳傳遞指標** (updateDeliveryIndicators) 技術工作流程，以提升效能。
* 應用程式內的傳送訊息範本現在可供 Campaign Standard 支援的所有語言使用。
* 透過減少傳遞分析期間對追蹤伺服器的呼叫次數，已針對異動訊息最佳化傳遞準備時間。
* 新的警報訊息會通知用戶高跳出率。
* 改善記錄錯誤訊息和警告，以便在無法正確擷取追蹤記錄時能更輕鬆地進行偵錯。 (CAMP-48939, CAMP-47360)
* 您現在可以完全個人化 URL，包含網域名稱。 [進一步了解](../../designing/using/personalization.md#personalizing-urls)

**修補程式**

* 修正從 URL 匯入電子郵件內容時的逾時錯誤。 (CAMP-49054)
* 存取已建立書籤的 URL，或從瀏覽器重新整理頁面時，修正工作階段結束所造成的錯誤 (-69)。 (CAMP-49003、CAMP-48930、CAMP-48894)
* 修正了將規則從舊版傳遞能力伺服器同步至新傳遞能力伺服器的問題。 (CAMP-48923)
* 修正當在「電子郵件設計工具」中載入含有 HTML 標籤的電子郵件範本時所發生的問題。 (CAMP-48243)
* 使用 Email designer 建立異動訊息時，修正 Adobe Experience Manager 內容未載入的錯誤。 (CAMP-49075)
* 修正介面中頂端列與內容之間新增過多邊框間距的問題。
* 在 Adobe Experience Manager 內容中使用 Campaign 內容區塊時，修正異動訊息的問題可能導致發佈錯誤。 (CAMP-49233)
* 修正驗證失敗時可能導致錯誤訊息的問題。 系統現在會將用戶重新導向至登入頁面。
* 修正權杖顯示問題，此問題可能導致用戶無法編輯或共用報告。
* 使用具有 1-n 個表格關係的篩選運算式來修正發佈自訂資源時的問題。 (CAMP-48740)
* 修正無法在工作流程轉變中擷取傳遞聯絡日期的日期格式問題。 (CAMP-48871)
* 修正在建立自訂設定檔維度期間無法擴充傳送記錄的問題。
* 修正可能導致多語言變體傳送失敗的問題。 從現在開始，如果用戶刪除了預設語言變體，則必須先將另一個語言變體設定為預設語言變體，然後才能建立語言副本。 (CAMP-48235)
* 修正當用戶在設計訊息時選取 **Only show on mobile devices** 選項時，造成電子郵件訊息在 Outlook 中顯示額外空白字元的問題。 (CAMP-48902)
* 修正了在執行增量查詢工作流程後， **Processed Data** 標籤中遺失增量查詢活動欄位的最後執行日期的問題。 (CAMP-48879)
* 修正無法在 **Segmentation** 工作流程活動中正確定義動態區段代碼的問題。 (CAMP-48727)
* 修正在編輯工作流程後嘗試儲存工作流程時隨機發生的錯誤。(CAMP-48695)
* 修正即使觸發器被刪除，但由於觸發器的資料方案仍保留，無法發佈自訂資源的問題。 (CAMP-48523)
* 修正因為 InMail 程式無法擷取要更新的傳遞記錄，而無法接受回饋迴圈請求的問題。 (CAMP-48705)
* 修正無法正確定義 **Exclusion** 工作流程活動中排除選項的問題。(CAMP-48355)
* 修正工作流程中擴充活動涉及訂閱或取消訂閱服務時發生的問題。 此問題導致當機。
* 修正工作流程無法執行的問題。
* 修正用戶無法從使用者介面重新命名或刪除現成安全性群組的問題。
* 修正用戶無法刪除不完整事件發佈作業的問題。
* 修正資料庫清理工作流程失敗並出現錯誤的問題。 (CAMP-49097)
