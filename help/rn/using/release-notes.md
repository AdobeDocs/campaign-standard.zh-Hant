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
source-git-commit: 14f764b92fef81c06551fb0f13b11b41e94095f0

---


# 最新版本{#latest-release}

[發行計畫](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) |控 [制面板版本](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |文 [件更新](../../rn/using/documentation-updates.md) |先 [前的發行說明](../../rn/using/release-notes-2019.md) |已過 [時的功能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## 版本20.1.3 - 2020年2月 {#release-20-1-3---february-2020}

* 修正CAMP-39273在20.1中針對使用漏洞的客戶所引入的回歸問題。 39273號營被歸還。

## 版本20.1.2 - 2020年2月 {#release-20-1-2---february-2020}

**電子郵件設計人員增強功能**

* 修正修補過期片段並儲存內容時，在過期片段中新增HTML標籤元素的問題。 (CAMP-40685)
* 修正使用動態內容時新增空格的問題。 (CAMP-40605)
* 修正設定交易式電子郵件範本時的問題。 (CAMP-40604)

## 版本20.1 - 2020年2月 {#release-20-1---february-2020}

**新增功能？**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector（測試版）</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector現在已與Adobe Campaign Standard整合。 您可以將XTK資料（在Campaign中收錄的資料）對應至Adobe Experience platform資料模型(XDM)，讓您的Campaign資料可在Adobe Experience platform上使用。 </p>
    <p>請注意，此功能僅適用於Azure上代管的客戶。 如需啟動此功能與條件的詳細資訊，請參閱詳 <a href="../../administration/using/aep-about-data-connector.md">細說明</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">檔案和操作視訊</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>觀眾目標（測試版） </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>受眾目標可讓您將Adobe Experience platform的細分共用給Adobe Campaign。</p>
    <p>請注意，此功能僅適用於Azure上代管的客戶。 如需啟動此功能與條件的詳細資訊，請參閱詳 <a href="../../audiences/using/aep-about-audience-destinations-service.md">細說明</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">檔案和操作視訊</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**改進**

* 增強的MTA的全球可用性：訊息（包括交易訊息）現在由Adobe Campaign Enhanced MTA傳送，此MTA提供升級的傳送基礎架構，可改善傳送能力、吞吐量和彈回數處理。 [閱讀更多資訊](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* 時區管理已增強。 您現在可以為整個 [工作流程定義](../../automating/using/building-a-workflow.md) 特定時區。 所選時區將應用於工作流的所有活動。 為操作員或伺服器配置的時區資訊現在顯示在介面中（在日誌中，在選擇時區後）。 (CAMP-37672)

* 現在，透過將參數新增至呼叫URL，您可在使用大型表格時， `_forcePagination=true` 使用Campaign Standard API來執行分頁。 [閱讀更多資訊](../../api/using/pagination.md)

* 「傳送記錄檔ID」（每個記錄檔的唯一識別碼）現在可用於所有定位維度的「傳送記錄檔」和「追蹤記錄檔」資源。 這可在匯出時識別傳送或追蹤記錄檔，例如。 [閱讀更多資訊](../../automating/using/exporting-logs.md)

**電子郵件設計人員增強功能**

* 已新增在建立對象時遺漏的強制文字指示。
* 修正按一下舊版電子郵件編輯 **器精靈中** 「變更內容」按鈕的問題。
* 修正無法將標題與「服務摘要」報表上的內容對齊的問題。 (CAMP-38103)
* 修正無法刪除動態內容變體而不會影響主題行其餘部分的問題。 (CAMP-40096)
* 修正在主旨行上使用B變體時的A/B測試問題。 (CAMP-40327)
* 修正使用「上傳HTML」匯入功能時無法拖放檔案的問題。 (CAMP-39326)
* 修正無法從文字編輯器複製和貼上文字的問題。 (CAMP-39028)
* 修正無法顯示字詞建議的問題。 (CAMP-38970)
* 修正使用者無法儲存片段的問題。 (ATU-2447)
* 修正動態結構無法複製的問題。 (CAMP-38367)
* 修正複製動態內容時無法保留條件的問題。 (CAMP-39051)

**其他變更**

* 「已準備的傳送失敗」篩選條件現在會考量傳送的建立日期，而非上次修改日期。
* 管理員安全組的組織單元不能再更改。
* 建立配置檔案時，現在必須填寫「組織單位」欄位。
* 現在，只有刪除連結至Experience cloud的事件和交易範本時，才能刪除Experience cloud觸發器。
* Adobe Creative SDK已終止服務。 現在已在Campaign standard中停用。 請參閱「 [已過時和已移除的功能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)」頁面。


**修補程式**

* 修正執行刪除隱私權要求時，排除記錄中無法刪除使用者資料的問題。 (CAMP-39003)
* 修正在容器元素中調整文字大小時導致協助工具問題。
* 修正使用者無法關閉行銷活動暫留中顯示之「日曆」快顯視窗的問題。
* 修正即使未修改 **[!UICONTROL External API]** 任何資料，仍顯 **[!UICONTROL Confirm]** 示按鈕的活動問題。
* 修正針對不同目標維度 **[!UICONTROL Union]** 的查詢使用活動的問題。 轉場資料只顯示主集定位維度的記錄。 (CAMP-36831)
* 修正在特定上下文中使用活動(例 **[!UICONTROL Reconciliation]** 如有兩個傳入活動，其中一個是排除活動)時，可能導致錯誤的問題。 (CAMP-37490)
* 已修正選取和更新測試設定檔時可能發生的效能問題。 (CAMP-37976)
* 修正透過著陸頁面訂閱或取消訂閱時，可能顯示錯誤頁面的問題。 (CAMP-37771)
* 已修正以郵遞區號格式上傳內容時，HTML中參照的PNG檔案副檔名為大寫字母的問題。 (CAMP-37913)
* 修正在傳送中新增測試設定檔時，無法傳送應用程式內訊息的問題。
* 修正連結至擴充活動時，外部API工作流程活動失敗的錯誤。
* 修正可能導致SMS訊息狀態顯示錯誤的問題。
* 修正自訂資源造成重複項目出現在不同API端點下的問題。
* 修正發佈後無法使用著陸頁面的問題。 (CAMP-38695)
* 已修正顯示來自兩個不同資源之「交叉點」轉場的資料時發生的錯誤。 (CAMP-38974)
* 修正傳送範本中的列舉值設定不正確的問題。 (CAMP-38388)
* 修正電子郵件大量傳送的錯誤，此錯誤會將傳送的狀態顯示為「擱置中」，而「傳送的狀態」顯示為「已完成」。 (CAMP-35355)
* 修正「動態」報表中錯誤顯示傳送者網域的錯誤。 (CAMP-33123)
* 修正動態報表中「取消訂閱」計數不一致的問題。 (CAMP-39949)
* 修正傳送應用程式內訊息時，「傳送記錄檔」畫面無法顯示位址的問題。
* 修正SMS傳送記錄檔無法以正確彈回數更新的問題。 (CAMP-38395)
* 已修正允許應用程式訂閱貼文呼叫更新推播通知Token的漏洞。 (CAMP-39273)
