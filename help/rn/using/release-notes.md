---
title: 最新版本
description: 本頁列出Adobe Campaign Standard的所有最新版本。
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
source-git-commit: e59562bd4f258c4259b8e8e5d9648397d5718792
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 0%

---


# 最新版本{#latest-release}

[發行計畫](../../rn/using/release-planning.md) |控 [制面板版本](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |文 [件更新](../../rn/using/documentation-updates.md) |先前 [的發行說明](../../rn/using/release-notes-2020.md) |已過 [時的功能](../../rn/using/deprecated-features.md)

## 版本20.3 - 2020年5月 {#release-20-3---may-2020}

**新增功能?**

<table> 
<thead> 
<tr> 
<th> <strong>泰國的個人資料保護法(PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>泰國的個人資料保護法(PDPA)是一項新的隱私法，協調並現代化泰國的資料保護要求。 本規定適用於持有此國家／地區資料主體資料的Adobe Campaign客戶。</p>
<p>除了Adobe Campaign中已提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）外，我們還將利用這個機會加入其他功能，以協助您做好PDPA的準備：</p>
<ul>
<li>存取權與刪除權： 我們運用了GDPR和CCPA新增的功能。 <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">進一步瞭解</a> </li>
<li><p>建立隱私權要求時，PDPA規則類型已新增至隱私權核心服務。 此方法應用於所有存取和刪除請求。 不建議使用促銷活動API和介面來存取和刪除請求。  請參閱「已過 <a href="../../rn/using/deprecated-features.md">時和已移除的功能」文章</a>。</p></li>
</ul>
<p>請參閱 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">how-to影片</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>外部API活動(GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>外部 <strong>API活動</strong> ，正從測試版轉換為正式發佈。 此版本為JSON回應本體剖析器提供額外的彈性。 您現在可以：</p>
<ul>
<li>剖析最大深度為10個層級的巢狀JSON。 </li>
<li>從JSON將選取的屬性剖析為葉節點，並將其平面化為單一表格列。</li>
<li>從JSON選取並使用陣列物件，而不需將物件命名為"data"，或讓它位於頂層。</li>
</ul>
<p><strong>注意：</strong> 客戶在工作流程 <strong>中，需要將所有測試版外部API活動</strong> ，換成GA外部API活動。  使用External API測試版的工作流程將在20.3中停止運作。</p>
<p>如需詳細資訊，請參 <a href="../../automating/using/external-api.md">閱詳細說明</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">檔案和操作視訊</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

>[!NOTE]
>
>CNAME子網域的憑證續約將於5月於「促銷活動控制面板」中發行。 有關詳細資訊，請參閱「 [Control Panel Release Note（控制面板發行說明）](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)」。

**改進**

* 「首碼」欄位中可使用的字 **元數** ，可 [用來測試使用目標描述檔的訊息](../../sending/using/testing-messages-using-target.md) ，已從32個字元增加到500個字元。
* 可在例項上發佈的即時事件數上限已從350增加到2000。 (CAMP-41608)
* 使用syncWithLaunch技術工作流程，已改善Adobe Launch和Campaign Standard之間的同步化。 此工作流程可讓您自動將所有Adobe Launch行動裝置屬性匯入Adobe Campaign Standard。 For more information, refer to [this page](../../administration/using/technical-workflows.md).

   您必須提交票證至Adobe客戶服務（直接或透過您的Adobe聯絡人），才能在您的Campaign實例中啟用syncWithLaunch技術工作流程。 (CAMP-40082)

**電子郵件設計人員增強功能**

* 與嚴格的W3C相比，電子郵件設計人員現在可以處理更有彈性的HTML格式。 (CAMP-42529)
* 修正可點選影 [像的問題](../../designing/using/links.md#inserting-a-link) ，防止連結在內容區塊中顯示在影像旁。 (CAMP-41586)
* 修正當追蹤的URL在範本中新增類別時，無 [法重新導向至](../../designing/using/links.md#about-tracked-urls) 著陸頁面的問題。 (CAMP-41537)
* 修正Outlook中按鈕間距的問題。
* 修正HTML標籤顯示為純文字的問題。
* 內容區塊搜尋現在會顯示伺服器搜尋結果以及預先載入的結果。 (CAMP-41870)

**其他變更**

* 自訂資源發佈介面已改善，並有更清楚的錯誤訊息。
* 未使用的傳送映射已從介面中刪除。
* 已從介面中刪除了不必要的管理員角色。
* 現在，登陸頁面中的核取方塊是強制的。
* 下載動態報表的CSV檔案時，已移除200列的限制。 您現在可以將報表的每一列納入其中。 (CAMP-40810)
* 在多語言電子郵件的現成可用語言清單中新增ES-US語言。 (CAMP-42279)
* 隨「傳輸檔案」活動下載的檔案現在會在X天后刪除，其中X由「工作流程」屬性中「執行 **** 」功能表下的「歷史記錄(History in days **** )」欄位決定。 [閱讀更多資訊](../../automating/using/managing-execution-options.md)

**體驗平台整合**

* 從「讀取」 [觀眾活動啟動Adobe](../../automating/using/aep-targeting-audiences.md) Experience Platform Audiences **** 已改進，以提供更佳的效能和穩定性。 此外，工作流程記錄檔已更清楚、更詳細地記錄啟動工作，讓您在閱讀Adobe Experience Platform受眾時更容易進行監控和疑難排解。

**修補程式**

* 修正導致在自訂資源的發佈工作期間建立Ghost資源的錯誤。
* 修正當描述檔資源已擴充至自訂資源時，可能無法顯示描述檔行銷歷史記錄的問題。 (CAMP-41009)
* 已修正開啟編輯器時，以法文顯示其內容的現成可用著陸頁面範本問題。 (CAMP-41639)
* 修正動態內容的推播通知無法顯示表情符號的問題。 (CAMP-40715)
* 修正重複資料消 **除活動** ，可能導致將錯誤的段代碼分配給其中一個出站補充過渡的問題。 (CAMP-41400)
* 修正無法刪除排程報表的錯誤。 (CAMP-41302)
* 修正傳送控制面板與「傳送摘要」報表之 **間不一致的問** 題。 (CAMP-41145)
* 修正導致下載報表中出現字元重疊顯示問題的問題。
* 修正傳送預覽無法用於證明替代的問題。
* 修正刪除應用程式內本機通知的自訂欄位時的錯誤。
* 修正charIndex函式無法在工作流程中處理 **End** 或 **** File傳輸活動的問題。
* 修正工作流中，將 **Enrichment** 活動與兩個輸入活動（包括目標資源之間有連結）搭配使用時可能發生的問題。 (CAMP-42133)
* 修正使用未知函式時，工作流程無法執行的問題。 (CAMP-41873)
* 修正工作流程中，使用數個「儲存觀眾」活動來建立觀眾時，可能會發生的 **問題** ，這些活動會補充對外轉場。 (CAMP-39992)
* 修正在交易電子郵件中使用個人化時造成資料不一致的問題。 (CAMP-41842)
* 修正刪除推播通知傳送中的自訂欄位時發生的問題。 (CAMP-37586)
* 修正使用者無法變更報表的錯誤。 (CAMP-42505)
