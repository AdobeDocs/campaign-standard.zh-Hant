---
solution: Campaign Standard
product: campaign
title: 發行說明 2020 年
description: 本頁列出 2020 年的所有 Adobe Campaign Standard 版本。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 發行說明 2020 年{#release-notes-2020}

[發行計畫](https://helpx.adobe.com/tw/campaign/kb/acs-release-planning.html) | [控制面板版本](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/release-notes.html) | [文件更新](../../rn/using/documentation-updates.md) | [先前的發行版本](../../rn/using/release-notes-2019.md) | [已過時的功能](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html)

![](assets/do-not-localize/cp-icon.png) **新的控制面板 6 月版本**，包含作用中設定檔監控、子網域傳遞送能力稽核及 GPG 金鑰管理。[進一步瞭解](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)。

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

* **由 AI 支援的傳送時間最佳化和設定檔計分** - 您現在可以最佳化客戶旅程的設計和傳遞，以預測每個人的參與偏好。Adobe Campaign 採用 Journey AI，可根據歷史參與量度來分析和預測開放率、最佳傳送時間和可能的流失率。[進一步瞭解](../../sending/using/predictive.md)
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
