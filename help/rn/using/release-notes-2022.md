---
title: 發行說明 2022 年
description: 本頁列出 2022 年的所有 Adobe Campaign Standard 版本。
feature: Overview
role: User
level: Beginner
exl-id: 8c722084-988d-47bd-98ad-9f5a422980a0
source-git-commit: e7c9c79a72b9f1ce36d0c60464b36be7d36a50a6
workflow-type: tm+mt
source-wordcount: '1248'
ht-degree: 100%

---

# 發行說明 2022 年{#release-notes-2022}

## 發行版本 22.3.2 {#feb-23}

### 安全性更新{#rn-security2}

此發行版本隨附下列安全性升級：Debian 已升級至 v11.0。

## 版本 22.3 - 2022 年秋冬 {#sept-22}

### 安全性更新{#rn-security}

此版本隨附下列安全性升級：Apache Tomcat 已從 v7.0 升級至 v8.0。

### 修正{#rn-fixes}

* 修正排程報告在排程計時前一小時觸發的問題。 (CAMP-51502)
* 修正「傳送」控制面板中傳送指標與「傳送記錄檔」(nms:broadLogRcp) 不符的問題。 (CAMP-51127)
* 修正無法透過 ACS Connector (Prime Offering) 擴充自訂資源的問題。 (CAMP-51033)
* 改善隱私權請求回應的發佈程式，以避免延遲。 (CAMP-50613)

## 發行版本 22.2 – 2022 年 6 月 {#june-2022}

**功能改進**

* **Adobe Notification Service** - Adobe Notification Service 促銷活動，允許 Experience Cloud 解決方案提醒 Experience Cloud 的使用者注意對他們來說很重要的活動。從 22.2 版開始，改善使用者體驗：依照優先順序通知，產品產生的通知與 Adobe 狀態公告分開。 此外，當特定的工作流程通知時，您可以直接從電子郵件或產品通知存取對應的工作流程。  如需 Adobe Campaign 通知的詳細資訊，請參閱 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。

<!--
* **Optimization in Workflow startup** - Adobe has added a new capability which can tune the number of workflows that start around the same time. This would help prevent CPU spikes that could have led to service interruptions or downtime. Adobe would enable it after 22.2 release. There is no further action item on customer regarding the same.
-->

* **協助工具** - Adobe 為提高應用程式的整體易用性已修正許多協助工具。 這些功能目前僅對部分早期採用者啟用，並將在未來版本向所有客戶提供。 協助工具的功能改善範例包括：

   * 確保每個螢幕上的聚焦元件都有可見的聚焦指示器
   * 建立頁面地標讓導覽更輕鬆
   * 新增許多控制項名稱、角色、值和狀態
   * 修復主螢幕動態焦點順序所遇到的問題


**修補程式**

* 已修復由於重複金鑰錯誤而造成的帳單技術工作流程問題。 (CAMP-51029)
* 已在追蹤報告中新增缺少的 Microsoft Edge 瀏覽器類別。 之前是透過 Microsoft Chrome opens 進行分類的。(CAMP-51165)
* 針對 GDPR 的要求，修復未從子表格中刪除資料的問題。 (CAMP-48276)
* 修復電子郵件設計工具的問題，其中會使異動訊息範本無法儲存片段的可見度狀況。 (CAMP-50338)
* 已修復 Campaign 報告未考慮日期範圍的問題。 (CAMP-50991)
* 已修復造成排程電子郵件失敗的錯誤：因傳遞仍處於「重試擱置」狀態而無法開始傳遞分析。 (CAMP-50302)
* 針對當預覽包含設定檔替代的電子郵件時，修復電子郵件設計工具所發生的問題。(CAMP-49312)
* 修復自訂分項清單的空值問題：當使用文字分項清單且只包含一個值的欄位建立自訂資源時，在預設情況下會設定此值，以便您可以在此欄位上簡單請求建立查詢。 (CAMP-50606)


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
* 您現在可以監視您的傳遞，並在您的訊息控制面板使用新的&#x200B;**作業歷史記錄**&#x200B;下拉式清單。 [了解更多資訊](../../sending/using/monitoring-a-delivery.md) (CAMP-49840)
* 在一段時間內跨所有通道傳送大量訊息時，透過減少無作用的元組，提高了穩定性和資料庫健康情況。 (CAMP-49755、CAMP-49792、CAMP-49849)
* 為確保在資料庫當機或重新啟動時自動重新整理資料庫連線，改進了 Campaign 郵件傳輸代理程式 (MTA)。 (CAMP-48063)
* 新追蹤選項&#x200B;**使用電子郵件頂部的「追蹤」像素**&#x200B;已加入電子郵件屬性，允許您移動電子郵件頂部而非底部的追蹤像素。 (CAMP-49672)

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
* 為了解決各種問題，針對包括從 URL 匯入的內容改進了遞送的重試機制。 [了解更多資訊](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* 修復了在自訂資源中建立新篩選器後發生的問題，然後將其作為登陸頁面中的調解金鑰。 如再次發佈自訂資源，則會從登陸頁面的可用調解金鑰清單中刪除該篩選器。 (CAMP-49516)
* 針對當登陸頁面使用帶有核取方塊的動態條件時，修復其中的問題。 (CAMP-48604)
* 已修正當&#x200B;**查詢**&#x200B;活動使用「十月或之前」篩選器條件時發生的問題。 當利用設定為歐洲時區的執行個體時，由於轉換時區出現問題，篩選器的選定月份顯示為 9 月而非 10 月。 (CAMP-48602)
* 為了最佳化傳遞能力，在 Adobe Campaign 傳送電子郵件時現在使用 7 位元編碼而非 8 位元編碼。 此舉避免因中繼緣故使 DKIM 簽名失效，而可能影響訊息的真實性。 (CAMP-49016)
* 為了避免當與大數量受眾合作時出現任何問題，加強了複製受眾時的效能。 (CAMP-49639)
* 修復可能會阻止自訂篩選器在用於&#x200B;**查詢**&#x200B;活動時顯示正確結果的問題。 (CAMP-49417)
* 針對在名稱中帶有逗號的情況下嘗試在傳遞中使用該片段時顯示錯誤訊息，修復了錯誤。問題已解決，現在可以在片段名稱中使用逗號。 (CAMP-49216)
