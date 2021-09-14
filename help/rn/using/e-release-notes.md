---
title: 早期發行說明
description: 早期發行說明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 42%

---

# 早期發行說明 {#new-release}

本頁說明下一版 Campaign Standard 中包含的新功能、改善和修正。

>[!CAUTION]
>
> 在預備環境升級日期前，此內容可能會有所變更，恕不另行通知。 請參閱[發行計劃頁面](../../rn/using/release-planning.md)以瞭解更多資訊。

## 發行版本 21.3 – 2021 年 9 月 {#release-21-3---sept-2021}

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
<p>如需詳細資訊，請參閱<a href="../../administration/using/audit.md">詳細文件</a>，以瞭解詳情。</p>
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

* 已增強安全性，以防止SSRF攻擊。 (CAMP-47836)
* 使用者清單現在僅限管理員使用。 (CAMP-47260)
* 環境變數不再能用於URL中的參數展開。 (CAMP-47268)

**功能改善**

* 在連結至 Adobe Experience Manager 內容的工作流程中建立循環傳送時，現在會在傳送前檢查內容核准狀態。
* 資料庫連線限制現在已與 Campaign 套件對齊，以避免連線錯誤。
* 新增在自訂資源中建立索引時的一致性檢查，並改善錯誤訊息。

**其他變更**

* Adobe Experience Platform Data Connector和Audience Destinations服務現已透過Campaign Standard淘汰。 如果您使用這些功能，則需移至「Adobe來源」和「目的地」，並調整實作。 [瞭解更多](../../integrating/using/get-started-sources-destinations.md)
* [此頁面](deprecated-features.md)中列出已棄用和已移除的功能。
* 引入新的「StringAgg」匯總函式以串連字串類型欄的值。 (CAMP-47077)
* 已改善&#x200B;**更新傳送指標**(updateDeliveryIndicators)技術工作流程，以提升效能。
* 應用程式內訊息範本現在可供Campaign Standard支援的所有語言使用。
* 透過減少傳遞分析期間對追蹤伺服器的呼叫數，已針對交易式訊息最佳化傳送準備時間。
* 新的警報訊息會通知使用者高跳出率。
* 改善記錄錯誤訊息和警告，以便在無法正確擷取追蹤記錄時更輕鬆進行除錯。 (CAMP-48939, CAMP-47360)
* 您現在可以完全個人化URL，包括網域名稱。 [進一步了解](../../designing/using/personalization.md#personalizing-urls)

**修補程式**

* 修正從 URL 匯入電子郵件內容時的逾時錯誤。 (CAMP-49054)
* 修正存取已建立書籤的URL或從瀏覽器重新整理頁面時，作業結束所造成的錯誤(-69)。 (CAMP-49003、CAMP-48930、CAMP-48894)
* 修正了將規則從舊版傳遞能力伺服器同步至新傳遞能力伺服器的問題。 (CAMP-48923)
* 修正當在「電子郵件設計工具」中載入含有 HTML 標籤的電子郵件範本時所發生的問題。 (CAMP-48243)
* 修正使用電子郵件設計工具建立交易式訊息時，Adobe Experience Manager內容未載入的錯誤。 (CAMP-49075)
* 修正介面中，頂端列與內容之間新增過多邊框間距的問題。
* 修正交易式訊息的問題，在Adobe Experience Manager內容中使用促銷活動內容區塊時，可能導致發佈錯誤。 (CAMP-49233)
* 修正驗證失敗時可能導致錯誤訊息的問題。 系統現在會將使用者重新導向至登入頁面。
* 修正Token顯示問題，此問題可能導致使用者無法編輯或共用報表。
* 修正使用具有1-n個表格關係的篩選運算式來發佈自訂資源時的問題。 (CAMP-48740)
* 修正了無法在工作流程轉變中擷取傳送聯絡日期的日期格式問題。 (CAMP-48871)
* 修正在建立自訂設定檔維度期間無法擴充傳送記錄檔的問題。
* 修正可能導致多語言變體傳送失敗的問題。 從現在開始，如果用戶刪除了預設語言變體，則必須先將另一個語言變體設定為預設語言變體，然後才能建立語言副本。 (CAMP-48235)
* 修正當使用者在設計訊息時選取「**僅顯示於行動裝置**」選項時，造成電子郵件訊息在Outlook中顯示額外空白字元的問題。 (CAMP-48902)
* 修正了在執行增量查詢工作流程後， 「已處理資料」標籤中遺失增量查詢活動欄位的最後執行日期的問題。 ****(CAMP-48879)
* 修正無法在&#x200B;**Segmentation**&#x200B;工作流程活動中正確定義動態區段代碼的問題。 (CAMP-48727)
* 修正在編輯工作流程後嘗試儲存工作流程時隨機發生的錯誤。 (CAMP-48695)
* 修正由於觸發器的資料結構仍保留，即使觸發器被刪除，仍無法發佈自訂資源的問題。 (CAMP-48523)
* 修正因為InMail程式無法擷取要更新的傳送記錄，而無法接受回饋回圈請求的問題。 (CAMP-48705)
* 修正無法正確定義&#x200B;**Exclusion**&#x200B;工作流程活動中排除選項的問題。(CAMP-48355)
* 修正工作流程中擴充活動涉及訂閱或取消訂閱服務時發生的問題。 此問題導致崩潰。
* 修正了工作流程無法執行的問題。
* 修正使用者無法從使用者介面重新命名或刪除現成安全性群組的問題。
* 修正使用者無法刪除不完整事件發佈作業的問題。
* 修正資料庫清理工作流程失敗並出現錯誤的問題。 (CAMP-49097)
