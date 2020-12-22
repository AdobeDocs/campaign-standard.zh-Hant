---
solution: Campaign Standard
product: campaign
title: Campaign Standard 已過時和移除的功能
description: 本頁列出 Adobe Campaign Standard 已過時和已移除的功能。
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
translation-type: tm+mt
source-git-commit: 32aba66dd8987414cf90df1e7bfb9c419c5f68ff
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 85%

---


# 被取代和已移除的功能 {#deprecated-and-removed-features}

Adobe 持續評估產品功能，尋找應以更現代的替代方式來取代舊的功能，以提升整體客戶價值，並時時考慮回溯相容性。

為通知即將移除/遭取代的 Campaign Standard 功能，我們採用下列規則：

* 首先我們發佈功能過時的消息。雖然已過時的功能仍可供現有使用者使用，但是這些功能將不會進一步增強或記錄。
* 後續最新發行版本，則將最先移除已過時的功能。本頁面將公佈實際的移除日期。

此流程讓客戶在實際移除之前，至少可以適應一個版本發行週期，以調整實作方式，及適應已過時功能的新版本或後繼功能。

>[!NOTE]
>[發行說明](../../rn/using/release-notes.md)將列出 Adobe Campaign Standard 發行版本和新功能。


## 已過時的功能 {#deprecated-features}

本節列出最新 Campaign Standard 發行版本中已標示為過時的功能。

通常，未來新發行版本預計移除的功能，將先設為過時並提供替代方案。新的 Campaign Standard 客戶將無法使用這些功能，或者這些功能將不用於任何新實施。產品文件亦將移除這些功能。

建議客戶檢視是否在目前部署運用了過時的功能，並規劃實施變更的計畫以使用所提供的替代方案。請參閱目標移除版本，據此規劃您的環境和專案更新。

<table> 
 <thead> 
 <tr> 
   <th> <strong>預測性主旨行</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 自2020年12月15日起，預測性主旨行功能已過時。</p><br/>
   <p>我們建議您利用人工智慧的電子郵件功能，根據歷史參與度量來分析和預測開放率、最佳傳送時間以及可能的流失率。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">進一步瞭解</a></p></br>
     <p>
     <em>目標移除：2021年4月</em></p>
     </td> 
  </tr> 
  </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK v4 的推播通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 自 20.1 版本以來，已過時 SDK v4。<a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">進一步瞭解</a>。</p><br/>
   <p>Adobe <a href="https://aep-sdks.gitbook.io/docs/">Experience Platform Mobile SDK</a>（先前稱為 v5）將獨家支援即將推出的 Adobe Experience Cloud 功能。</p></br>
     <p>
     <em>目標刪除日期：2021年8月31日</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>隱私權要求 – Campaign API 及介面</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>自 Campaign 19.4 版本以來，不建議使用促銷活動 API 和介面來存取和刪除請求。將無法使用兩步驟的設定檔刪除作業。使用 <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe 隱私權核心服務</a>。</p></br>
   <p>另請參閱<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=en">管理隱私權要求</a>。</p>
  <p> 
  <em>目標移除日期：2021 年 4 月</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>電子郵件設計 – 舊版電子郵件編輯器</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>自 Campaign 19.0 版本以來，已過時舊版電子郵件編輯器。使用<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">促銷活動電子郵件設計工具</a>來建立並個人化您的電子郵件內容。 </p></br>
   <p>請參閱<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">本節</a>，瞭解如何針對新的編輯器調整您的電子郵件範本。</p></br>
  <p> 
  <em>目標刪除日期：2021年底</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>使用者及安全性 – 地理單位</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>自 18.7 版本以來，「地理」單位已過時。在 Campaign 中，「組織」和「地理」單位是完全相同的結構。使用者應單獨使用「組織」單位來建立其使用者權限/資料存取階層。<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=zh-Hant#administrating">進一步瞭解</a>。請注意，新的 Campaign Standard 執行個體，以及未建立地理單位的現有執行個體，則無法使用自 18.7 版以來實作的這個功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## 已移除的功能 {#removed-features}

本節列出已從 Campaign Standard 移除的功能。

<table> 
 <thead> 
  <tr> 
   <th> <strong>使用 Experience Cloud 觸發器的傾向分數</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>已經從 Adobe Experience Cloud 觸發器終止「<b>傾向分數</b>」的服務。因此，已從 Adobe Campaign Standard 移除此選項。為避免「擴充」綱要中「傾向」分數的任何過期值，我們建議您更新綱要以擷取最新變更並重新發佈現有的觸發器。如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html">在 Campaign 中發佈觸發器</a>。
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
   <td> <p>[!DNL Adobe Creative SDK] 已終止服務。因此，自 Campaign 20.2 版本以來，即不再提供 Campaign Standard 電子郵件中 [!DNL Creative SDK] 提供技術的影像版本。</p></br>
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
   <td> <p>Adobe Campaign 和 Adobe Experience Cloud 已自 2019 年春季以來，中斷對於 Microsoft Internet Explorer 11 及 Campaign 19.2 版本的支援。請切換至 Microsoft Edge 或其他支援的瀏覽器。<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html">進一步瞭解</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>
