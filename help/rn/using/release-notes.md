---
title: 最新版本
description: 本頁列出 Adobe Campaign Standard 的所有最新版本。
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f45985c030c3d5059bfef444287c10b842298f49
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 88%

---


# 最新版本{#latest-release}

[發行計畫](../../rn/using/release-planning.md) | [控制面板版本](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/release-notes.html) | [文件更新](../../rn/using/documentation-updates.md) | [先前的發行版本](../../rn/using/release-notes-2020.md) | [已過時的功能](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **新的控制面板6月發行** ，包含作用中描述檔監控、子網域傳送能力稽核和GPG金鑰管理。 [進一步瞭解](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/release-notes.html).

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
<li><p>建立隱私權要求時，PDPA 規則類型已新增至隱私權核心服務。此方法是您應該用於所有存取和刪除請求的方法。不建議使用促銷活動 API 和介面來存取和刪除請求。請參閱<a href="../../rn/using/deprecated-features.md">「已過時和已移除的功能」文章</a>。</p></li>
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

**其他功能** （從7月13日起）

* **人工智慧支援的傳送時間最佳化和描述檔計分** -您現在可以最佳化客戶歷程的設計和傳遞，以預測每個人的參與偏好。 Adobe Campaign採用Journey AI，可根據歷史參與度量來分析和預測開放率、最佳傳送時間和可能的流失率。 [進一步瞭解](../../sending/using/predictive.md)
* **巴西的新隱私權規範** -除了Campaign中已提供的隱私權功能外，Adobe還協助您做好準備，以迎接巴西的Lei Geral de Proteçao de Datos(LGPD)。 建立隱私權要求時，LGPD規定已新增至Adobe隱私權核心服務。 [進一步瞭解](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html)

**改進**

* 在 **Prefix** 欄位中可用於[使用目標設定檔之測試訊息](../../sending/using/testing-messages-using-target.md)的字元數，已經從 32 增加為 500 個字元。
* 可在執行個體上發佈的即時事件數上限，已經從 350 增加為 2000。(CAMP-41608)
* 使用 syncWithLaunch 技術工作流程，已改善 Adobe Launch 和 Campaign Standard 之間的同步化。此工作流程可自動將所有 Adobe Launch 行動裝置屬性匯入 Adobe Campaign Standard。如需詳細資訊，請參閱[本頁面](../../administration/using/technical-workflows.md)。

   您必須將票證提交至 Adobe 客戶服務（直接或透過您的 Adobe 聯絡人），才能在您的 Campaign 執行個體中啟用 syncWithLaunch 技術工作流程。(CAMP-40082)

**電子郵件設計人員增強功能**

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

* 從&#x200B;**讀取閱聽眾** 活動啟動 Adobe [Experience Platform Audiences](../../automating/using/aep-targeting-audiences.md) 已經有所改善，而可提供較出色的效能及穩定性。此外，工作流程記錄檔已經更清楚且更詳細地記錄啟動工作，讓您在讀取 Adobe Experience Platform 閱聽眾時，能夠更輕鬆地進行監控和疑難排解。

**修補程式**

* 修正導致在自訂資源的發佈工作期間建立 Ghost 資源的錯誤。
* 修正當描述檔資源已擴充至自訂資源時，可能無法顯示描述檔行銷歷史記錄的問題。(CAMP-41009)
* 已修正開啟編輯器時，以法文顯示其內容的現成可用登錄頁面範本問題。(CAMP-41639)
* 修正動態內容的推播通知無法顯示表情符號的問題。(CAMP-40715)
* 修正&#x200B;**重複資料刪除**&#x200B;活動，可能導致將錯誤的段代碼分配給其中一個出站補充轉變的問題。(CAMP-41400)
* 修正無法刪除排程報告的錯誤。(CAMP-41302)
* 修正傳送控制面板與&#x200B;**傳送摘要**&#x200B;報告之間不一致的問題。(CAMP-41145)
* 修正導致下載報告中出現字元重疊顯示問題的問題。
* 修正傳送預覽無法用於校樣替代的問題。
* 修正刪除應用程式內本機通知的自訂欄位時的錯誤。
* 修正 charIndex 函式無法在工作流程中處理&#x200B;**結束**&#x200B;或&#x200B;**檔檔案傳輸**&#x200B;活動的問題。
* 修正工作流程中，將&#x200B;**擴充**&#x200B;活動與兩個輸入活動（包括目標資源之間有連結）搭配使用時可能發生的問題。(CAMP-42133)
* 修正使用未知函式時，工作流程無法執行的問題。(CAMP-41873)
* 修正工作流程中，使用數個&#x200B;**儲存閱聽眾**&#x200B;活動來建立閱聽眾時可能會發生的問題，這些活動會補充外站轉變。(CAMP-39992)
* 修正在交易電子郵件中使用個人化時造成資料不一致的問題。(CAMP-41842)
* 修正刪除推播通知傳送中的自訂欄位時發生的問題。(CAMP-37586)
* 修正使用者無法變更報告的錯誤。(CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **新的控制面板可能會針對** CNAME子網域發行憑證續約。 [進一步瞭解](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/release-notes.html).
