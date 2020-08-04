---
title: 發行說明 2020 年
description: 本頁列出 2020 年的所有 Adobe Campaign Standard 版本。
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
translation-type: ht
source-git-commit: f4c6b74d9b80d80befed65d853cf82b32084c49d
workflow-type: ht
source-wordcount: '1825'
ht-degree: 100%

---


# 發行說明 2020 年{#release-notes-2020}

[發行計畫](https://helpx.adobe.com/tw/campaign/kb/acs-release-planning.html) | [控制面板版本](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/release-notes.html) | [文件更新](../../rn/using/documentation-updates.md) | [先前的發行版本](../../rn/using/release-notes-2019.md) | [已過時的功能](https://helpx.adobe.com/tw/campaign/kb/acs-deprecated-and-removed-features.html)

## 版本 20.2 – 2020 年 4 月 {#release-20-2---april-2020}

**新增功能？**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob整合</strong><br /> </th> 
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
   <td> <p>除了測試個人檔案外，您現在還可以在真正的目標個人檔案上測試電子郵件。這可讓您獲得設定檔將會收到的訊息的精確表示：自訂欄位、動態和個人化資訊，包括工作流程的其他資料等。 </p>
    <p>如需詳細資訊，請參閱<a href="../../sending/using/testing-messages-using-target.md">詳細文件</a>及<a href="https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.translate.html">教學影片</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>新功能將於 4 月在「Campaign 控制面板」中發佈，包括 Google TXT 記錄管理、資料庫空間監控和電子郵件警報。有關這些功能的詳細資訊，請參閱[控制面板發行說明](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/release-notes.html)。

**改進**

* 交易式訊息使用者體驗已增強，介面一致性也已獲改善。[瞭解詳情](../../channels/using/about-transactional-messaging.md)
* Campaign Standard 現在可讓您使用工作流程的其他資料，將校樣傳送至測試設定檔。
* 外部API活動的護欄已更新。[瞭解詳情](../../automating/using/external-api.md)

**電子郵件設計人員增強功能**

* 修正在個人化影像上多次點按時影響逸出的問題。
* 修正複製動態文字元件時，可能導致重複的錯誤行問題。(CAMP-41249)
* 在表格層級進行填補（而非 div 層級）時，藉由在 Outlook 中進行填補以修正問題。
* 修正在切換至 HTML 模式時，影像寬度遭到修改的問題。(CAMP-41116)
* 修正當為圖示提供替代文字時，無法存取社交媒體元件的問題。(CAMP-41345)
* 修正在「電子郵件設計工具」中使用複製貼上時，顯示可見 `<br>` 標籤的問題。
* 修正從 HTML 內容切換為純文字後，HTML 標籤顯示在電子郵件中的問題。(CAMP-41138)
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
>Campaign Standard 中的 Adobe Experience Platform 功能目前為測試版，可能會經常更新，恕不另行通知。請參閱詳細說明檔案：[體驗平台資料連接器](../../developing/using/aep-about-data-connector.md)，[對象目的地](../../audiences/using/aep-about-audience-destinations-service.md)

* 在工作流程記錄中，每隔 10 分鐘，Campaign 現在會顯示目前執行中的工作已處理的記錄數。
* 修正匯入已從資料庫刪除的 Adobe Experience Platform 設定檔時可能發生的問題。
* 修正工作流程記錄中，針對匯入記錄總數顯示錯誤結果的問題。

**修補程式**

* 修正在 **Alias** 欄位中新增空格後，接著建立新列項目時，**擴充**&#x200B;工作流程活動可能發生的問題。(CAMP-39229)
* 修正傳送證明訊息時，每個測試設定檔都可定位的問題。
* 修正取消發佈和刪除事件設定後發生的問題。[瞭解詳情](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* 修正變更工作流程時 **Save** 按鈕消失的問題。
* 修正在促銷活動處理後手動刪除隱私權要求時，即使在清除後，與要求相關的資料也無法刪除的問題。
* 修正預覽或傳送包含 Adobe Experience Manager 特殊字元之訊息時可能發生的問題。
* 修正執行具有數個入站轉變的活動時，工作流程中可能發生的問題。
* 修正標準使用者無法在工作流程查詢或傳送中將「訂閱應用程式」作為目標維度的問題。(CAMP-37618)

## 版本 20.1.4 - 2020 年 2 月 {#release-20-1-4---february-2020}

* 修正在現有工作流程中開啟&#x200B;**讀取對象**&#x200B;活動的問題。(CAMP-41002)

## 版本 20.1.3 - 2020 年 2 月 {#release-20-1-3---february-2020}

* 修正 CAMP-39273 在 20.1 中針對使用漏洞之客戶所引進的回歸問題。已反轉 CAMP-39273。

## 版本 20.1.2 - 2020 年 2 月 {#release-20-1-2---february-2020}

**電子郵件設計人員增強功能**

* 修正修補過期片段並儲存內容時，在過期片段中新增 HTML 標籤元素的問題。(CAMP-40685)
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

**電子郵件設計人員增強功能**

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
* Adobe Creative SDK 已終止服務。現在已在 Campaign Standard 中停用。請參閱[已過時和已移除的功能](https://helpx.adobe.com/tw/campaign/kb/acs-deprecated-and-removed-features.html)頁面。


**修補程式**

* 修正執行刪除隱私權要求時，排除記錄中無法刪除使用者資料的問題。(CAMP-39003)
* 修正在容器元素中調整文字大小時導致協助工具問題。
* 修正使用者無法關閉行銷活動暫留中顯示之「行事曆」快顯視窗的問題。
* 修正即使未修改任何資料，仍顯示 **[!UICONTROL Confirm]** 按鈕的 **[!UICONTROL External API]** 活動問題。
* 修正針對不同目標維度的查詢使用 **[!UICONTROL Union]** 活動的問題。轉變資料只顯示主要集定位維度的記錄。(CAMP-36831)
* 修正在特定內容中使用活動（例如，如有兩個入站　**[!UICONTROL Reconciliation]**　活動，其中一個是排除活動）時，可能導致錯誤的問題。(CAMP-37490)
* 已修正選取和更新測試設定檔時可能發生的效能問題。(CAMP-37976)
* 修正透過登錄頁面訂閱或取消訂閱時，可能顯示錯誤頁面的問題。(CAMP-37771)
* 已修正以郵遞區號格式上傳內容時，HTML　中參照的　PNG　檔案副檔名為大寫字母的問題。(CAMP-37913)
* 修正在傳送中新增測試設定檔時，無法傳送應用程式內訊息的問題。
* 修正連結至擴充活動時，外部　API　工作流程活動失敗的錯誤。
* 修正可能導致　SMS　訊息狀態顯示錯誤的問題。
* 修正自訂資源造成重複項目出現在不同　API　端點下的問題。
* 修正發佈後無法使用登錄頁面的問題。(CAMP-38695)
* 已修正顯示來自兩個不同資源之「交叉點」轉場的資料時發生的錯誤。(CAMP-38974)
* 修正傳遞範本中的分項清單設定不正確的問題。(CAMP-38388)
* 修正電子郵件大量傳送的錯誤，此錯誤會將傳送的狀態顯示為「擱置中」，而「傳送的狀態」顯示為「已完成」。(CAMP-35355)
* 修正「動態」報表中錯誤顯示傳送者網域的錯誤。(CAMP-33123)
* 修正動態報表中「取消訂閱」計數不一致的問題。(CAMP-39949)
* 修正傳送應用程式內訊息時，「傳送記錄檔」畫面無法顯示位址的問題。
* 修正SMS傳送記錄檔無法以正確退信更新的問題。(CAMP-38395)
* 已修正允許應用程式訂閱貼文呼叫更新推播通知　Token　的漏洞。(CAMP-39273)
