---
title: 開始使用 Campaign 整合
description: 使用其他 Adobe 解決方案，並將其不同的功能與 Campaign 結合。
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ecf88c7d-6729-4b3a-85c4-60427bb57442
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 77%

---

# 關於 Campaign 整合{#get-started-campaign-integrations}

本節詳細說明目前版本的 Adobe Campaign 與其他解決方案和服務之間的功能整合。

如以下所呈現的不同整合，您可以將 Adobe Campaign 的傳遞和進階行銷活動管理功能與協助您個人化使用者體驗的解決方案結合使用。

>[!NOTE]
>
> 依預設，Adobe Campaign 已經連結至 Adobe Experience Cloud 帳戶。

根據您的環境而定，其他解決方案也可以連結至 Adobe Experience Cloud。它們作為「組織」（又稱為「租戶」）連結。

組織是可以讓管理員設定群組和使用者，以及控制 Experience Cloud 中單一登入的實體。組織的運作方式類似登入公司，其涵蓋所有 Experience Cloud 產品和解決方案。通常，組織就是您的公司名稱。但是，一個公司可以有許多組織。使用者和組織管理在 [Adobe Experience Cloud 說明入口網站](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)中有詳細解說。

如果您想要將其他系統的資料流程與 Adobe Campaign 整合，請參閱我們的 [API 文件](../../api/using/get-started-apis.md)。

>[!NOTE]
>
>Adobe Campaign Standard 也可以連線至 Microsoft Dynamics 365：此整合可以同步 CRM 系統中所有可用的連絡資料，讓所有相關的連絡資料都可在行銷活動中使用。如需此整合的詳細資訊，請參閱[使用行銷活動和 Dynamics 365](../../integrating/using/d365-acs-get-started.md)。


<table> 
 <thead> 
  <tr> 
   <th> 解決方案<br /> </th> 
   <th> 使用案例<br /> </th> 
   <th> 請參閱<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Adobe Experience Manager<br /> </td> 
   <td> 可讓您直接在 Adobe Experience Manager 中建立對應至 Adobe Campaign 資料庫的電子郵件內容或表單。<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">合作使用行銷活動與Experience Manager</a>， <a href="https://helpx.adobe.com/tw/experience-manager/6-4/sites/administering/using/campaignstandard.html">整合Experience Manager和Campaign Standard</a>， <a href="https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html">使用Experience Manager和行銷活動建立電子郵件</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Target<br /> </td> 
   <td> 可讓您在開啟由 Adobe Campaign 建立和發傳送的電子郵件活動時插入由 Adobe Target 動態運算的影像。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">合作使用Campaign與Target</a>， <a href="https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html">整合Campaign和Target</a>， <a href="https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html">即時個人化電子郵件影像</a> 影片（步驟3）
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Analytics<br /> </td> 
   <td> 可讓您直接在 Adobe Analytics 中追蹤電子郵件傳送的成功情況。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">與 Analytics 共用行銷活動資料</a>，<a href="https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html">共用 KPI 以整合行銷活動報告</a>影片（步驟 1）
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager 與人員核心服務（設定檔與觀眾）<br /> </td> 
   <td> 可讓您使用的不同 Adobe Experience Cloud 應用程式交換受眾。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People 服務核心（設定檔與觀眾）</a><br /> </td> 
  </tr> 
   <tr> 
   <td> Adobe Real-time Customer Data Platform (RTCDP)<br /> </td> 
   <td> Adobe Campaign與Adobe Real-time Customer Data Platform (RTCDP)的整合可讓您共用區段資料，並將受眾匯入至Adobe Campaign。</td>
   <td><a href="../../integrating/using/get-started-sources-destinations.md">開始使用來源和目標</a></td>
  </tr> 
  <tr> 
   <td> Adobe資產核心服務與隨選資產<br /> </td> 
   <td> 可讓您將 Adobe Experience Cloud 資料庫中的資產插入到 Adobe Campaign 中建立的電子郵件和登錄頁中。<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">資產核心服務</a> 或隨選資產<br /> </td> 
  </tr> 
  <tr> 
   <td> 興趣點（行動裝置分析）<br /> </td> 
   <td> 可讓您從行動裝置應用程式的訂閱者收集興趣點資料，以便透過 Adobe Campaign 傳送個人化行銷訊息。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">傳送含有 Campaign 和興趣點資料的位置型行銷訊息</a> （行動裝置分析）<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Experience Cloud 觸發因子<br /> </td> 
   <td> 可讓您在 Adobe Campaign 中向您的客戶傳送個人化電子郵件，作為對 Adobe Analytics 在您的網站上追蹤的特定行為的反應。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">在 Campaign Standard 中使用 Experience Cloud 觸發器</a>、<a href="../../integrating/using/abandonment-triggers-use-cases.md">放棄觸發器 Campaign 使用案例</a>，<a href="https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html">根據網站活動影片觸發再行銷訊息</a>（步驟 2）
    </td> 
  </tr> 
    <tr> 
   <td> AdobeJourney Orchestration<br /> </td> 
   <td> 允許透過開箱即用的動作，在AdobeJourney Orchestration的內容中使用Adobe Campaign Standard的交易式訊息功能來傳送電子郵件、推播通知和簡訊。<br /> </td> 
   <td> <a href="https://experienceleague.adobe.com/docs/journeys/using/action-journeys/working-with-adobe-campaign.html">合作使用AdobeJourney Orchestration與Adobe Campaign Standard</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Dreamweaver<br /> </td> 
   <td> 可讓您從 Dreamweaver 編輯電子郵件內容，並與 Adobe Campaign 同步化。<br /> </td> 
   <td> 
    <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hant">使用Dreamweaver建立個人化電子郵件</a> 視訊， <a href="https://helpx.adobe.com/tw/dreamweaver/using/working-with-dreamweaver-and-campaign.html">針對Dreamweaver使用Campaign擴充功能</a> 
  </td> 
  </tr> 
  <tr> 
   <td> ADOBE EXPERIENCE PLATFORM SDK<br /> </td> 
   <td> 允許使用 Experience Platform SDK 在 Adobe Campaign 中自動化行動應用程式屬性啟用程序。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html">使用 Experience Platform SDK 設定行動應用程式</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
