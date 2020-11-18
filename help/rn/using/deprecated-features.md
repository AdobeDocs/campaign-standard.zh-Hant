---
title: 已過時和移除的促銷活動標準功能
description: 本頁列出Adobe Campaign Standard已過時和已移除的功能。
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
discoiquuid: null
translation-type: tm+mt
source-git-commit: 2dc4ac62e3b10753f7b8681d86cfe7f3b3a30a20
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 18%

---


# 被取代和已移除的功能 {#deprecated-and-removed-features}

Adobe 持續評估產品功能，尋找應以更現代的替代方式來取代舊的功能，以提升整體客戶價值，並時時考慮回溯相容性。

若要通知即將移除／取代Campaign Standard功能，請套用下列規則：

* 首先我們發佈功能棄用的消息。雖然已過時的功能仍可供現有使用者使用，但無法進一步增強，也無法記錄。
* 後續最新發行版本，則將最先移除已棄用的功能。本頁面將公佈實際的移除日期。

此流程讓客戶在實際移除之前，至少可以適應一個版本發行週期，以調整實作方式，及適應已棄用功能的新版本或後繼功能。

>[!NOTE]
>Adobe Campaign Standard releases and new capabilities are listed in the [Release Notes](../../rn/using/release-notes.md).


## 已棄用的功能 {#deprecated-features}

本節列出最新Campaign Standard版本中已標示為已過時的功能。

通常，計畫在未來版本中移除的功能會先設為不建議使用，並提供其他選項。 這些新的Campaign Standard客戶不再可使用這些功能，或不應用於任何新的實作。 產品文件亦將移除這些功能。

建議客戶在目前的部署中是否運用了功能／功能，並規劃變更實施以使用提供的替代方案。 請參閱目標刪除版本以規劃您的環境和項目更新。

<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK v4的推播通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 從20.1版開始，SDK v4已過時。 <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">進一步瞭解</a>。</p><br/>
   <p>Adobe <a href="https://aep-sdks.gitbook.io/docs/">Experience Platform Mobile SDK</a> （先前稱為v5）將獨家支援即將推出的Adobe Experience Cloud功能。</p></br>
     <p>
     <em>目標刪除日期：2020年9月30日</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>隱私權要求——促銷活動API和介面</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>在啟動Campaign 19.4發行時，已不再使用Campaign API和介面來存取和刪除請求。 2步驟描述檔刪除將無法使用。 使用 <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe隱私權核心服務</a>。</p></br>
   <p>另請參閱管 <a href="https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html">理隱私權要求</a>。</p>
  <p> 
  <em>目標移除日期：2021 年</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>電子郵件設計——舊版電子郵件編輯器</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>在啟動Campaign 19.0版本時，舊版電子郵件編輯器已過時。 使用 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">全新的電子郵件設計工具</a> ，建立並個人化您的電子郵件內容。 </p></br>
   <p>閱讀本 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">節</a> ，瞭解如何針對新編輯者調整您的電子郵件範本。</p></br>
  <p> 
  <em>目標移除日期：2021 年</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>用戶與安全性——地理單位</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>從18.7版開始，「地理單位」已過時。 「組織」和「地理」單位是Campaign中相同的結構。 使用者應單獨使用組織單位來建立其使用者權限／資料存取階層。 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">進一步瞭解</a>。請注意，新的「促銷活動標準」例項，以及未建立地理單位的現有例項，無法從18.7版開始實作此功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Removed Features {#removed-features}

本節列出已從Campaign Standard移除的功能。

<table> 
 <thead> 
  <tr> 
   <th> <strong>使用Experience Cloud觸發器的傾向分數</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>「傾 <b>向分數</b> 」已從Adobe Experience Cloud觸發程式終止服務。 因此，此選項已從Adobe Campaign Standard中移除。 為避免Enrichment結構描述中「傾向」分數的任何過時值，建議更新結構以擷取最新變更並重新發佈現有的觸發器。 如需詳細資訊，請參閱「 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html#publishing-trigger-in-campaign"> 在促銷活動中發佈觸發器」 </a>。
</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK for Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>[!DNL Adobe Creative SDK]已終止服務。 因此，從Campaign 20.2版開始，Campaign Standard電子郵件中由[!DNL Creative SDK]提供的影像版本已不再提供。</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

## 相容性終止{#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Campaign和Adobe Experience Cloud已從2019年春季起停止支援Microsoft Internet Explorer 11和Campaign 19.2版本。 請切換至Microsoft Edge或其他支援的瀏覽器。 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/about-configuration-guidelines.html#compatible-browsers">進一步瞭解</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>
