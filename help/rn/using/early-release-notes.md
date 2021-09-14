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
source-wordcount: '413'
ht-degree: 100%

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
<!--<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>-->
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
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
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
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

**功能改善**

* 在連結至 Adobe Experience Manager 內容的工作流程中建立循環傳送時，現在會在傳送前檢查內容核准狀態。
* 資料庫連線限制現在已與 Campaign 套件對齊，以避免連線錯誤。
* 新增在自訂資源中建立索引時的一致性檢查，並改善錯誤訊息。

**修補程式**

* 修正從 URL 匯入電子郵件內容時的逾時錯誤。 (CAMP-49054)
* 修正存取已建立書籤的 URL 或從瀏覽器重新整理頁面時，工作階段結束所造成的錯誤 (-69)。 (CAMP-49003、CAMP-48930、CAMP-48894)
* 修正了將規則從舊版傳遞能力伺服器同步至新傳遞能力伺服器的問題。 (CAMP-48923)
* 修正當在「電子郵件設計工具」中載入含有 HTML 標籤的電子郵件範本時所發生的問題。 (CAMP-48243)
