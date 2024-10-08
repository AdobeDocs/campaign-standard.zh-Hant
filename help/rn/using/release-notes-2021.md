---
title: 發行說明 2021 年
description: 本頁列出 2021 年的所有 Adobe Campaign Standard 版本。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 225c65cc-2964-4b71-84a9-30fcd22d75bf
source-git-commit: 63cd437c5a19791ffb9d3c0b8690ee1532a4774d
workflow-type: tm+mt
source-wordcount: '4695'
ht-degree: 100%

---

# 2021 年發行說明{#release-notes-2021}

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
* 已改善&#x200B;**更新傳傳送指標** (updateDeliveryIndicators) 技術工作流程，以提升效能。
* 應用程式內的傳送訊息範本現在可供 Campaign Standard 支援的所有語言使用。
* 透過減少傳遞分析期間對追蹤伺服器的呼叫次數，已針對異動訊息最佳化傳遞準備時間。
* 新的警報訊息會通知用戶高跳出率。
* 改善記錄錯誤訊息和警告，以便在無法正確擷取追蹤記錄時能更輕鬆地進行偵錯。 (CAMP-48939, CAMP-47360)
* 您現在可以完全個人化 URL，包含網域名稱。 [了解更多](../../designing/using/personalization.md#personalizing-urls)
* 證明和補漏白設定檔現已排除在「動態報告」的傳遞效能計算之外。 (CAMP-47338)

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


## 發行版本 21.2 – 2021 年 6 月 {#release-21-2---june-2021}

以下列出下一版 Campaign Standard 發行版本中包含的新功能、改良和修正。以下列出此 Campaign Standard 發行中包含的新功能、改良和修正。

**功能改善**

* 您現在可以在設計登陸頁面時，新增必要核取方塊，要求設定檔在提交表單前先選取該核取方塊。 如需詳細資訊，請參閱[詳細文件](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)。

* 針對觸發程式整合，已改善觸發程式裝載中沒有調和資料時顯示的錯誤訊息：「裝載中缺少別名資料」。

* 已改善從佇列擷取推播通知的效能。

**其他變更**

* 已停用追蹤連結的 URL 簽章機制，以防止在第三方安全工具修改後，造成某些有效且已簽署的追蹤連結遭到錯誤封鎖的問題。

* 在多變體傳送中，如果已刪除預設變體，則使用者無法再建立語言副本。 現在會在語言副本建立期間顯示訊息。 (CAMP-48235)

* 現在預設會停用兩步驟設定檔刪除程式 (自 Campaign 19.4 版本起即淘汰)。 之前，您必須先從 Campaign 介面手動停用，才能使用隱私權核心服務。 若未這麼做，會導致刪除請求在未完成的情況下維持擱置狀態。

* 在動態報告中，已移除&#x200B;**「排除校樣」**&#x200B;區段。 (CAMP-46161)

* 已新增警告訊息，以在上傳 iOS 憑證時 (未在 Campaign 應用程式中使用 platformPrincipal 值) 通知使用者。

* 電子郵件的最大大小現在預設為 100 MB。 此限制可防止任何可能無限增加電子郵件大小而導致系統當機的錯誤。 (CAMP-47445)[ 進一步瞭解](../../sending/using/design-and-personalize.md#email-size)

* 標準使用者現在可以使用電子郵件設計工具的資產核心服務整合。

* 已新增新訊息，以確認成功從 v4 推送應用程式移轉至 v5 推送應用程式。

* 在建立 JSONWeb Token 以驗證 Campaign Standard API 期間，產品設定檔現在為&#x200B;**已考量**。 這表示分配給安全性群組 (符合 AdobeIO 上的產品設定檔) 的組織單位和角色，將套用至 Campaign Standard Rest API 呼叫所需的 IMS 技術帳戶。 (CAMP-47479)

**修補程式**

* 修正了無法套用批次處理記錄表格 (**xtkjoblog**) 之到期選項的問題。 這會使表格無法正確清除。

* 修正無法變更&#x200B;**細分**&#x200B;工作流程活動中篩選器順序的問題。 (CAMP-48357)

* 修正 20.4 的回歸，該回歸可能導致傳送失敗，並產生 null 值錯誤。 (CAMP-48591)

* 修正無法透過&#x200B;**共用** > **「立即傳送報告」**&#x200B;或&#x200B;**「依排程傳送報告」**&#x200B;功能表傳送報告的問題。 (CAMP-47798)

* 修正由於篩選從 Gmail 帳戶收到的追蹤事件可能導致 Gmail 開啟率不正確的回歸。(CAMP-46504)

* 修正 Adobe Campaign Standard 中的報告與 Adobe Analytics 中的報告之間資料不一致的各種問題。 (CAMP-47671, CAMP-47296)

* 修正準備失敗後無法存取傳遞記錄的問題。 (CAMP-48296)

* 修正嘗試編輯、刪除或傳送自訂報告時，可能顯示錯誤訊息的問題。 (CAMP-47789, CAMP-47798)

* 修正建立新自訂資源並啟用&#x200B;**「不要同步」**&#x200B;選項時，API 呼叫失敗的問題。 (CAMP-48014)

* 修正啟用&#x200B;**「不要同步」**&#x200B;選項的自訂資源可參考已重新起草或刪除的綱要的問題。 此問題會在發佈自訂資源時造成錯誤。

* 修正在相同外部帳戶上使用多個短程式碼時，簡訊選擇退出的問題。

* 修正發佈資料庫後，無法存取新傳送警示準則 (「您嘗試存取的資源無法連線」) 的問題。 (CAMP-48221)

* 修正某些具有動態報告的 Campaign 執行個體中缺少追蹤記錄的問題。 已新增新的[技術工作流程](../../administration/using/technical-workflows.md)，以還原這些追蹤記錄。 (CAMP-47885)

* 修正動態報告中未顯示傳遞資料的問題。 報告已設定為 0。 (CAMP-47480)

* 修正伺服器 JavaScript HTTP 用戶端無法連線至外部 URL 的問題。

* 修正在變更工作流程的內部名稱後，重設&#x200B;**增量查詢**&#x200B;活動的問題。 將日期欄位用作增量模式時，就會發生此問題。 (CAMP-47674)

* 修正當使用 Adobe Experience Manager 整合建立多語言電子郵件時，傳遞摘要無法顯示預覽縮圖的問題。 使用&#x200B;**建立語言副本**&#x200B;按鈕建立電子郵件變體時，就會發生此問題。 (CAMP-47810)

* 修正使用者無法透過電子郵件或簡訊子傳遞存取父傳遞的問題。 (CAMP-47986)

* 修正透過 REST API 傳送異動訊息，但遺失自訂事件時，可能導致 CPU 和記憶體耗用過量的問題。 (CAMP-47147)

* 修正異動訊息 API 錯誤，該錯誤有時會阻止即時訊息的傳送。

* 修正使用&#x200B;**依排程傳送報告**&#x200B;選項後未收到報告的問題。 (CAMP-48583, CAMP-47786)

* 修正使用&#x200B;**立即傳送報告選項**&#x200B;後收到的報告不完整且遺失資料的問題。 (CAMP-48583)

* 修正電子郵件設計工具上傳影像時，影像尺寸縮小的問題。 (CAMP-47017)

* 修正建立傳遞時，無法顯示所有可用 Experience Manager 範本的問題。 (CAMP-48132)

* 修正已傳送傳遞之「摘要」頁面中的 Campaign 連結無法將使用者重新導向至相關行銷活動的錯誤。 (CAMP-48012)

* 修正電子郵件設計工具中，當嘗試選取資產時，資產核心服務整合持續失敗的問題。 (CAMP-47446)

* 修正由於 Campaign 不支援來自 Journey Orchestration 之事件所傳送具有確切值 (即結尾為 00) 的時間戳記，而封鎖某些 Journey Orchestration 傳送的問題。

## 版本 21.1 – 2021 年 2 月 {#release-21-1---february-2021}

**新增功能？**

<table> 
<thead> 
<tr> 
<th> <strong>電子郵件回饋服務</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>電子郵件回饋服務 (EFS) 是一種可擴展的服務，它直接從增強型 MTA 中擷取回饋，從而提高報告的準確性。這項功能會以私人測試版發佈，未來發佈的版本將逐步提供給所有客戶。</p>
<ul>
<li>現在，您可擷取所有類別的回饋，以進行完整精確的報告。</li>
<li><b>傳遞的</b>指標的計算現在基於來自增強型 MTA 的即時回饋，以改進精確度和反應性。</li>
<li>EFS 可解決同步軟退信的延遲問題。</li>
</ul>
<p>如需詳細資訊，請參閱<a href="../../sending/using/confirming-the-send.md">詳細文件</a>。
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Adobe Experience Manager 整合改進</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>已改善與 Adobe Experience Manager 的促銷活動整合：您現在可以更輕鬆地從 Adobe Experience Manager 匯入多語言內容。 <p>
<p>Adobe Campaign Standard 現在會自動從 Adobe Experience Manager 內容中偵測語言變體，並允許大量變體匯入和建立，大幅簡化從業人員根據 Adobe Experience Manager 內容建立多語言促銷活動所需執行的步驟。</p>
<p>如需詳細資訊，請參閱<a href="../../integrating/using/creating-multilingual-email-aem.md">詳細文件</a>。
</p>
</td> 
</tr> 
</tbody> 
</table>

<!--
<table> 
<thead> 
<tr> 
<th> <strong>Unified Experience Cloud interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign header bar has been changed to unify and improve your experience across all Experience Cloud products and services. These changes are designed to make your life easier, including:</p>
<ul>
<li>Easier switching between your organizations or to a different application.</li>
<li>Improved User Help – Bringing the Experience League into the product, search results also include results from community forums and more video content, giving you easier access to more content to help get the most out of the application. We've also added a feedback mechanism right in the Help menu, making it easier to report issues or share your ideas.</li>
<li>Improved Notifications – Notifications drop-down now has two tabs: one for your own product notifications, and one for more global product announcements.</li>
</ul>
<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>
<p>NOTE: This change will be progressively rolled out to all customer environments between Feb 10 and March 1st.
</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**功能改善**

* **Microsoft Dynamics 365 整合**&#x200B;已增強，並具備專屬的自助服務整合應用程式和改進的實作程序。[進一步瞭解](../../integrating/using/d365-acs-get-started.md)

* 已進行改進，以便在遇到異動訊息程序的問題時，方便疑難排解。Adobe 技術管理員現在可以在任何程式上使用追蹤，而不需重新啟動。

* **設定檔**&#x200B;清單現在可讓您根據以下欄位之一搜尋記錄：擴充設定檔資源時，已在進階篩選中新增的電子郵件、名字、姓氏或自訂欄位。此功能也可在使用 filterType 參數的 Campaign Standard API 中使用。[進一步瞭解](../../audiences/using/integrated-customer-profile.md)

* 參數已調整為執行「異動訊息」資料庫集區流程的容器數。這可讓負載均勻分佈於所有使用的容器，並達到最佳效能。

* 使用事件變數的活動現在可使用新的 **GetOption** 函式，在呼叫具有外部參數的工作流程後即可使用。這可讓您傳回指定函式的值。[進一步瞭解](../../automating/using/customizing-workflow-external-parameters.md)

* 新選項可讓 Campaign Standard 在啟動工作流程之前，先&#x200B;**檢查系統上的實體記憶體**&#x200B;可用性。如果記憶體量太低，工作流程執行將延遲，直到系統記憶體達到此臨界值。這樣可以避免效能進一步降低並降低停機風險。當伺服器上的負載降低，而記憶體增加時，工作流程就會自動恢復。請注意，此選項為唯讀且無法修改。[進一步瞭解](../../automating/using/best-practices-workflows.md#execution)

* Adobe Campaign Standard 提供新的流程，可讓您更輕鬆地從舊版 SDK v4 行動應用程式移轉至 **Adobe Experience Platform Mobile SDK**。請參見[此頁面](../../administration/using/sdkv4-migration.md)。

**其他變更**

* 當達到每個滾動小時 100 個內容下載的限制時，將訊息準備期間的錯誤變更為警告。現在，當達到限制時會顯示警告，而可繼續傳遞。

* 擴充異動訊息內容時，不會在從設定檔表格中提取資料時擷取連結，這減少了訊息準備期間的延遲，並且避免了由於與設定檔表格定義的不正確關係而導致的空設定檔資料。

* 執行個體技術設定已經過最佳化，而可確保穩定性。(CAMP-45681)

* 工作階段管理已經過改善，而可最佳化記憶體。(CAMP-45901, CAMP-46767)

* **傳輸檔案**&#x200B;活動現在會產生另一個變數 (filesCount)，其中包含已上傳或已下載的檔案數目。(CAMP-45842)[ 進一步瞭解](../../automating/using/transfer-file.md#output-variables)

* 簡訊連接器現在可以隨每則訊息傳送多個可選參數。[進一步瞭解](../../administration/using/sms-protocol.md)

* 具有 DATAMODEL 角色的使用者現在可以發佈傳遞記錄擴充功能。(CAMP-46604)

* 嘗試發佈已不再存在的自訂資源為目標定位的資源時，所顯示的錯誤訊息已變得更加清晰。(CAMP-46893)

* **首選語言**&#x200B;清單中已新增了以下語言：印尼 - 印尼 (in-id)、英文 - 瑞典 (en-se)、英文 - 亞太 (en-ap)、英文 - 日本 (en-jp)、西班牙 - 拉丁美洲 (es-la)。(CAMP-46351)

* 測試登陸頁面時，設定檔選取的選擇器現在會使用 profilBase 資源，而非設定檔，以防止逾時。

* SMPP 記錄檔格式已改善。

* 已新增 cryptString 與 decryptString JS 函式的可選參數，以符合 Adobe Campaign Standard API。

* 已改善傳遞準備記錄檔中的警告或錯誤訊息。

* 已改善嘗試連線至 Adobe Identity Management Service (IMS) 時的錯誤記錄檔。

* 您現在可以使用動態報告中的搜尋列，進一步篩選&#x200B;**傳遞**&#x200B;和&#x200B;**促銷活動**&#x200B;維度。

* 異動的簡訊訊息有效日期現在可由「異動訊息 API」中為有效期參數設定的值來定義。(CAMP-36600)

* 在動態報告中，**傳送摘要**&#x200B;內建報告顯示取消訂閱比率量度的不正確資料。已新增名為 **Unique unsubscription** 的新量度來修正此問題。(CAMP-46445)

**修補程式**

* 已修正由於某些流程而導致傳送執行非常緩慢的問題。這是由於為數個參數定義的單位不正確（例如毫秒，而非秒）。

* 修正 Mobile SDK 根據 deliveryId/MessageID 非 null 的條件，傳送開啟追蹤要求的問題。若停用追蹤，則會導致 404 傳送錯誤。現在，有效負載中會傳送另一個變數 (acsDeliveryTracking)，內含傳送追蹤狀態的資訊。此變數可以有兩個開啟或關閉的值，視設定的追蹤狀態而定。[進一步瞭解](../../administration/using/push-tracking.md)。

* 修正工作流程中複製貼上&#x200B;**重複資料刪除**&#x200B;活動時，可能發生且已執行一次，使用暫時資源的問題。重複後，活動的資源會自動設定為空，導致工作流程中其他活動出現問題。貼上後，活動的資源現在會維持不變，以便盡快觸發錯誤，而不是稍後在工作流程中觸發。(CAMP-46903)

* 修正傳送異動推播訊息目標定位設定檔時，傳送分析失敗的問題，方法是引入新的[目標定位對應](../../administration/using/target-mappings-in-campaign.md): **設定檔 - 推播的即時事件** (*mapRtEventAppSubRcp*)。[設定檔異動推播通知](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)的傳遞、排除和追蹤記錄現在會儲存在 *broadLogAppSubRcp*、*excludeLogAppSubRcp* 和 *trackingLogAppSubRcp* 表格。

  >[!IMPORTANT]
  >
  >由於此變更，如果您使用現有的設定檔推播異動通知 (在升級至 Adobe Campaign 21.1 之前建立)，建議您將目標對應更新至新版，然後再次發佈訊息。 請參閱[此處](../../channels/using/transactional-push-notifications.md#change-target-mapping)的詳細步驟。 使用先前的目標對應&#x200B;**設定檔 — 即時事件**(*mapRtEventRcp*) 可能導致傳遞準備時間較長且效能降低。

* 修正顯示 5000 列時無法執行傳遞報告的問題。
* 修正 A/B 測試的問題，此問題會導致變數 B 的內容在修改傳遞範本後無法更新。(CAMP-45235)
* 修正造成異動訊息過程卡住、無法傳送訊息的問題。
* 修正在按一下內部連結後（例如從證明摘要畫面存取父傳送時），可能導致導覽問題的問題。
* 修正建立傳送時，無法顯示所有可用 Experience Manager 內容範本的問題。(CAMP-45990)
* 修正在將&#x200B;**原因**&#x200B;欄新增至其他資料標籤後，工作流程中無法顯示失敗訊息的問題。(CAMP-45139)
* 修正兩個應用程式訂閱呼叫具有相同 Marketing Cloud ID（「重複金鑰值違反唯一限制」錯誤）時可能發生的問題。
* 修正將活動拖放至包含大量&#x200B;**查詢**&#x200B;和&#x200B;**讀取客群**&#x200B;活動的工作流程時，可能會導致速度緩慢的問題。(CAMP-44511)
* 修正異動訊息準備結束時可能發生的錯誤，防止重新導向資訊上傳至追蹤伺服器。
* 修正嘗試開啟匯入範本或自訂工作流程資源後貼上匯入工作時，可能顯示錯誤訊息的問題。(CAMP-46183)
* 修正當&#x200B;**讀取客群**&#x200B;活動設定為動態客群名稱時，可能無法執行的問題。(CAMP-46047)
* 修正無法顯示&#x200B;**匯出清單**&#x200B;按鈕的問題
* 修正可能導致&#x200B;**報告彙總**&#x200B;工作流程失敗的問題。(CAMP-45979)
* 修正使用自訂合成索引鍵（文字/日期動態內容）建立自訂資源的問題。
* 修正無法顯示查詢轉變資料的問題。(CAMP-45669)
* 修正與自訂資源發佈相關的記憶體耗用問題。
* 修正設定要在特定日期傳送的傳送時所發生的問題。如果在確認後立即傳送，則傳遞準備失敗，並且仍將考慮最初指定的日期。(CAMP-44107)
* 修正無法開啟交易範本的問題。(CAMP-47181)
* 修正異動訊息發佈程式中，名稱超過允許字串大小時，可能導致重複類型和類型規則的問題。(CAMP-47104)
* 修正當輸入參數傳回不存在的記錄時，發生在&#x200B;**外部 API** 活動中的問題。(CAMP-47023)
* 修正 SMPP 連接器無法重新連接的問題。
* 修正下載名稱中包含點的檔案時，在&#x200B;**檔案傳輸**&#x200B;活動中發生的問題。點後面的字元被視為檔案的延伸。(CAMP-46624)
* 修正無法執行資料庫集區，導致異動訊息卡在路由器佇列中的問題。
* 修正無法避免傳送出取消傳送記錄的錯誤。
* 修正使用&#x200B;**合併連結**&#x200B;活動時，工作流程可能失敗的問題。活動會自動將「主要」集更改為與其連接的最後一個轉變，即使它在視覺上顯示第一個連接的轉變。(CAMP-46900)
* 修正成功隔離的地址狀態錯誤地設定為「有效」，從而將其從隔離中移除的問題。
* 修正當個人化欄位包含特殊字元時，無法顯示的問題。(CAMP-46805)
* 修正無法顯示設定檔之特定詳細檢視的問題。如果設定檔資源已擴展，並啟用了&#x200B;**新增個人化欄位部分**&#x200B;選項的自定義欄位，則會發生此情況。
* 修正傳送交易事件時，可能傳回錯誤代碼 500 的問題。(CAMP-46811)
* 修正無法接收電子郵件排程報告的問題。(CAMP-46891)
* 修正將自訂資源連結至具有 1 個基數簡單連結的設定檔資源時所發生的問題。當存取自訂資源欄位為空的設定檔時，將會顯示錯誤訊息，而非空白清單。
* 修正在工作流程中使用設定檔替代時，頁面在選取要取代的設定檔時無法載入傳送設定檔的問題。(CAMP-46522)
* 修正&#x200B;**資料庫清理**&#x200B;技術工作流程嘗試刪除逾期傳送工作表而導致下列錯誤的回歸：(CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* 修正在自訂資源上使用自訂篩選時，在某些情況下會發生的下列錯誤：(CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* 修正&#x200B;**推播通知準備**&#x200B;耗費太多時間才能完成的問題。這是由於暫時性工作表上缺少索引所導致。
* 修正當在自定義資源和設定檔資源之間已定義關係時，使用&#x200B;**維度在工作流程中**&#x200B;的&#x200B;**協調**&#x200B;活動中協調選項時可能發生的錯誤。
* 修正透過&#x200B;**協調**&#x200B;或&#x200B;**擴充**&#x200B;活動新增連結時發生的問題。所選的連結不會顯示在輸出轉變中。
* 修正在工作流程中使用具有週期性傳送的&#x200B;**分段**&#x200B;活動時，造成傳送給錯誤客群的問題。(CAMP-46275, CAMP-46470)
* 修正當嘗試擴充設定檔資源以建立動態報告的自訂設定檔維度時，自訂資源發佈失敗的錯誤。(CAMP-46266)
* 修正將連結新增至檔案匯入表格時發生的錯誤。將&#x200B;**擴充**&#x200B;活動新增至&#x200B;**檔案匯入**&#x200B;活動後，先前設定的連結消失。(CAMP-46557)
* 修正使用連結至描述檔資料的自訂資源時，在儲存時，**詳細說明**&#x200B;設定畫面中的顯示順序已變更的問題。(CAMP-46312)
* 修正基於自訂傳送對應的傳送，導致您無法在動態報告中顯示資料的問題。
* 修正在工作流程&#x200B;**查詢**&#x200B;活動中，無法選擇資源目標不正確的集合的錯誤。
* 修正 InMail 程式驗證硬退信數時可能發生錯誤的問題。
* 修正開啟設定檔畫面時，因連結錯誤而發生的錯誤。
* 修正無法從清除工作流程中刪除 GDPR 資料的問題。
* 修正在電子郵件傳送排程參數中以鍵盤手動更新排程設定時發生的錯誤。
* 修正因組織單位中的參數不正確而無法編輯設定檔的問題。
* 修正即使在傳送範本中設定&#x200B;**電子郵件屬性**、**服務擴充功能**&#x200B;欄位卻空白且無法設定的問題。
* 修正可能導致證明處理時間較長的問題。(CAMP-45048)
* 修正無法排序設定檔概述畫面中欄的問題。
* 修正 Azure 在包含中文字元的電子郵件變體中，可能發生的縮圖產生問題。(CAMP-47152)
* 修正 Campaign 20.4 中引入的回歸，由於篩選從 Gmail 帳戶收到的追蹤事件，可能導致 Gmail 開啟率不正確。(CAMP-46504)
* 修正無法將 HTML 內容匯入異動訊息範本的問題。(CAMP-47318)
* 修正在&#x200B;**電子郵件轉譯報告**&#x200B;中顯示轉譯的速度變慢的問題。(CAMP-46226)
* 修正無法發佈自訂資源的問題，此自訂資源在畫面定義中設定為「清單類型」元素。(CAMP-47217)
* 修正電子郵件設計工具中，當行分隔符號置於電子郵件內容頂端時，無法在 **Microsoft Outlook** 中正確顯示的問題。(CAMP-46294)
* 修正 KPI 與 **Adobe Analytics** 技術工作流程協調的問題。(CAMP-46576)
* 修正&#x200B;**電子郵件設計工具**&#x200B;中，在插入內容區塊時無法自動在搜尋方塊中顯示片段的問題。(CAMP-44205)
* 修正&#x200B;**電子郵件設計工具**&#x200B;中，當在片段中使用 emoji 時，在傳送的電子郵件中顯示不想要的字元的問題。(CAMP-46621)
* 修正&#x200B;**電子郵件設計工具**&#x200B;中 20.4 引入的回歸對分隔線元件造成影響，這會導致額外的行高和內容的影像失真。(CAMP-46663)
* 修正即使這些按鈕在&#x200B;**電子郵件設計工具**&#x200B;中對齊了右或左側，但是將郵件發送到 Outlook 電子信箱時，現成按鈕保持置中的問題。(CAMP-46466)
* 修正在&#x200B;**電子郵件設計工具**&#x200B;預覽中搜尋設定檔時，測試設定檔清單無法重新整理的問題。(CAMP-45265)
* 修正在&#x200B;**電子郵件設計工具**&#x200B;預覽中搜尋設定檔時，自訂測試設定檔無法顯示在清單中的問題。(CAMP-45589)
* 修正從&#x200B;**傳送摘要報告**&#x200B;產生趨勢圖形時，顯示不符合日期的問題。(CAMP-45521)
