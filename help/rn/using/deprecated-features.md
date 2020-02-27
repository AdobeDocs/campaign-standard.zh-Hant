---
title: 已過時和移除的促銷活動標準功能
description: 本頁列出Adobe Campaign standard已過時和已移除的功能。
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6ffbf03a7eb4fc1b5bfbd523c0c5342d41cfd211

---


# 已過時和移除的促銷活動標準功能 {#deprecated-and-removed-features}

Adobe會持續評估產品功能，以找出應以更現代的替代方式來取代的舊功能，以提升整體客戶價值，並時時考慮回溯相容性。

若要通知即將移除／取代Campaign standard功能，請套用下列規則：

* 首先宣佈放棄。 雖然已過時的功能仍可供現有使用者使用，但無法進一步增強，也無法記錄。
* 在以下版本中，將最早移除已過時的功能。 本頁會公佈實際的移除目標日期。

此程式可讓客戶在實際移除之前，至少有一個發行週期，以調整其實作方式，以適應已過時功能的新版本或後繼版本。

>[!NOTE]
>Adobe Campaign Standard版本和新功能列於版本 [說明中](../../rn/using/release-notes.md)。


## 不建議使用的功能 {#deprecated-features}

本節列出最新Campaign Standard版本中已標示為已過時的功能。 通常，計畫在未來版本中移除的功能會先設為不建議使用，並提供其他選項。 這些新的Campaign standard客戶不再可使用這些功能，或不應用於任何新的實作。 也會從產品檔案中移除它們。

建議客戶在目前的部署中是否運用了功能／功能，並規劃變更實施以使用提供的替代方案。 請參閱目標刪除日期以規劃您的環境和項目更新。

<table> 
 <thead> 
  <tr> 
   <th> 發行<br /> </th> 
   <th> 功能<br /> </th> 
   <th> 取代<br /> </th> 
    <th> 目標刪除日期<br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 20.1<br /> </td> 
   <td> Push Notifications<br /> </td> 
    <td> Adobe <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Experience Platform Mobile SDK</a> （先前稱為v5）將獨家支援即將推出的Adobe Experience cloud功能。 <br /> </td> 
    <td> 2020年9月30日<br /> </td> 
  </tr> 
  <tr> 
   <td> 20.1<br /> </td> 
   <td> Creative SDK for Campaign Standard<br /> </td> 
  <td> Adobe Creative SDK已終止服務。 因此，Campaign standard電子郵件中採用Creative SDK架構的影像版本現在已經過時。<br /> </td>
  <td> 2020年3月- Campaign 20.2發行<br /> </td> 
  </tr> 
  <tr> 
   <td> 19.4<br /> </td> 
   <td> 隱私權要求——促銷活動API和介面<br /> </td>
    <td> 不建議使用促銷活動API和介面來存取和刪除請求。 使用隱私權核心服務。 <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">進一步瞭解</a>。 另請參閱 <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">Campaign Standard中的隱私權管理</a>。<br /> </td>
    <td> 2020年7月- Campaign 20.5版本<br /> </td> 
  </tr>
  <tr> 
   <td> 19.0<br /> </td> 
   <td> 電子郵件設計——舊版電子郵件編輯器<br /> </td>
    <td> 舊版電子郵件編輯器現已過時。 使用全新的電子郵件設計工具來建立並個人化您的電子郵件內容。 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">進一步瞭解</a>。 閱讀本 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">節</a> ，瞭解如何針對新編輯者調整您的電子郵件範本。<br /> </td>
    <td> 2020年10月- Campaign 20.6發行<br /> </td> 
  </tr>
  <tr> 
   <td> 18.7<br /> </td> 
   <td> 用戶與安全性——地理單位<br /> </td>
    <td> 「組織」和「地理」單位是Campaign中相同的結構。 使用者應單獨使用組織單位來建立其使用者權限／資料存取階層。 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">進一步瞭解</a>。 請注意，新的「促銷活動標準」例項，以及未建立地理單位的現有例項，無法從18.7版開始實作此功能。<br /> </td>
    <td> 不適用<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 相容性終止 {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> 發行<br /> </th> 
   <th> 功能<br /> </th> 
   <th> 取代<br /> </th> 
 </tr> 
 </thead> 
 <tbody>
<tr> 
   <td> 19.2<br /> </td> 
   <td> 隱私權要求——促銷活動API和介面<br /> </td>
    <td> Adobe Campaign和Adobe Experience cloud已從2019年春季起停止支援Microsoft Internet Explorer 11和Campaign 19.2版本。 請切換至Microsoft edge或其他支援的瀏覽器。  <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">進一步瞭解</a>。<br /> </td>
    <td><br /> </td> 
  </tr>
  </tbody> 
</table>
