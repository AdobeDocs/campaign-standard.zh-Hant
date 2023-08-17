---
title: Campaign Standard 已過時和移除的功能
description: 本頁列出 Adobe Campaign Standard 已過時和已移除的功能。
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 63%

---

# 被取代和已移除的功能 {#deprecated-and-removed-features}

Adobe 持續評估產品功能，尋找應以更現代的替代方式來取代舊的功能，以提升整體客戶價值，並時時考慮回溯相容性。

為通知即將移除/遭取代的 Campaign Standard 功能，我們採用下列規則：

* 首先我們發佈功能過時的消息。雖然已過時的功能仍可供現有使用者使用，但是這些功能將不會進一步增強或記錄。
* 後續最新發行版本，則將最先移除已過時的功能。本頁面將公佈實際的移除日期。

此流程讓客戶在實際移除之前，至少可以適應一個版本發行週期，以調整實作方式，及適應已過時功能的新版本或後繼功能。

>[!NOTE]
>[發行說明](../../rn/using/release-notes.md)將列出 Adobe Campaign Standard 發行版本和新功能。


## 已棄用功能 {#deprecated-features}

本節列出最新 Campaign Standard 發行版本中已標示為過時的功能。

通常，未來新發行版本預計移除的功能，將先設為過時並提供替代方案。新的 Campaign Standard 客戶將無法使用這些功能，或者這些功能將不用於任何新實施。產品文件亦將移除這些功能。

建議客戶檢視是否在目前部署運用了過時的功能，並規劃實施變更的計畫以使用所提供的替代方案。請參閱目標移除版本，據此規劃您的環境和專案更新。

<table> 
 <thead> 
  <tr> 
   <th> <strong>與Audience Destinations服務整合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 自Campaign Standard第21.3發行版本開始，已棄用與Audience Destinations服務整合。 </p>
   <p>若為新的實作，您將無法再整合Audience Destinations服務與Adobe Campaign Standard。 不過，您可以透過來源和目的地整合Campaign和Adobe Experience Platform。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html">了解更多</a>。</p>
     <em>目標移除日期：2023 年</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>與Adobe Experience Platform Data Connector整合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 自Campaign Standard第21.3發行版本開始，已棄用與Adobe Experience Platform Data Connector整合。 </p>
   <p>若為新的實作，您無法再整合Adobe Experience Platform資料聯結器與Adobe Campaign Standard。 不過，您可以透過來源和目的地整合Campaign和Adobe Experience Platform。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html">了解更多</a>。</p>
     <em>目標移除日期：2023 年</em></p>
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
   <td> <p>自 Campaign 19.0 版本以來，已過時舊版電子郵件編輯器。使用 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">Campaign電子郵件設計工具</a> 以建立並個人化您的電子郵件內容。 </p></br>
   <p>請參閱<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">本節</a>，瞭解如何針對新的編輯器調整您的電子郵件範本。</p></br>
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
   <td> <p>自Campaign第18.7發行版本開始，不再使用地理單位。 在 Campaign 中，「組織」和「地理」單位是完全相同的結構。使用者應單獨使用「組織」單位來建立其使用者權限/資料存取階層。<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=zh-Hant#administrating">進一步瞭解</a>。請注意，新的 Campaign Standard 執行個體，以及未建立地理單位的現有執行個體，則無法使用自 18.7 版以來實作的這個功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## 已移除的功能 {#removed-features}

本節列出已從 Campaign Standard 移除的功能。



<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK v4 的推播通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 自Campaign第20.1發行版本開始，已棄用SDK v4。 <a href="https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/">了解更多</a>。</p><br/>
   <p>此 <a href="https://developer.adobe.com/client-sdks/documentation/">Adobe Experience Platform Mobile SDK</a> （先前稱為v5）現在僅支援即將推出的Adobe Experience Cloud功能。</p>
   <p>2021年8月31日後，客戶可以繼續下載及使用第4版SDK，但將無法取得客戶服務支援或存取論壇。</p>
   <p>瞭解如何從SDK v4移轉至Adobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">在此頁面中</a>.</p></br>
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
   <td> <p>自 Campaign 21.2 版本以來，不建議使用促銷活動 API 和介面來存取和刪除請求。將無法使用兩步驟的設定檔刪除作業。使用 <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service">Adobe 隱私權核心服務</a>。</p></br>
   <p>另請參閱<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html">管理隱私權要求</a>。</p>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
 <tr> 
   <th> <strong>預測性主旨列</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 自2021年4月起，「預測性主旨列」功能將停止服務。</p><br/>
   <p>我們建議您利用AI支援的電子郵件功能，根據歷史參與量度來分析和預測開放率、最佳傳送時間和可能的流失率。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">了解更多</a></p></br>
     </td> 
  </tr> 
  </tbody> 
</table>

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
   <td> <p>[!DNL Adobe Creative SDK]  已終止服務。因此，影像版本採用 [!DNL Creative SDK] 自Campaign 20.2發行版本開始，不再提供Campaign Standard中的電子郵件。</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

## 相容性終止 {#end-of-compatibility}

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
