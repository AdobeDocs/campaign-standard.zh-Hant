---
title: 關於促銷活動整合
seo-title: 關於促銷活動整合
description: 關於促銷活動整合
seo-description: Adobe Campaign可讓您使用其他Adobe解決方案，並結合其不同的功能。
page-status-flag: 從未啓動
uuid: 59d7cd99-a6 f7-47f1-9b5 c-c50 e27 a2 Bef8
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 關於促銷活動整合
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 337f2270f3f66d5172084a4e2a19d6185bf097ff

---


# About Campaign integrations{#about-campaign-integrations}

本節詳細說明目前版本Adobe Campaign與其他解決方案和服務之間可用的功能整合。

下列各項整合可讓您將Adobe Campaign的遞送和進階宣傳管理功能與一組建立的解決方案整合，以幫助您個人化使用者體驗。

>[!NOTE]
>
> 根據預設，Adobe Campaign已連結至Adobe Experience Cloud帳戶。

視您的環境而定，其他解決方案也可以連結至Adobe Experience Cloud。它們會連結為組織(也稱為「租用戶」)。

組織是可讓管理員設定群組和使用者，以及控制Experience Cloud中單一登入的實體。該組織的運作方式就像登入公司，涵蓋所有Experience Cloud產品和解決方案。最常見的組織是您的公司名稱。不過，公司可以有許多組織。User and organization management is detailed in the [Adobe Experience Cloud help portal](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html).

If you would like to integrate data flows from other systems with Adobe Campaign, have a look at our [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

>[!NOTE]
>
>Adobe Campaign Standard也可以連接至Microsoft Dynamics365：此項整合可讓您同步CRM系統中所有可用的連絡人資料，讓所有相關的聯絡資料都能用於促銷活動活動。For more on this integration, refer to [Working with Campaign and Dynamics 365](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).


<table> 
 <thead> 
  <tr> 
   <th> Solution<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Refer to<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4<br /> </td> 
   <td> Allows you to create email contents or forms mapped to the Adobe Campaign database directly in Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">與Campaign和Experience Manager合作</a><br/>， <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">整合Experience Manager和Campaign Standard</a><br/>， <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">透過Experience Manager和Campaign建立電子郵件</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Allows you to insert images that are dynamically computed by Adobe Target when an email created and sent by Adobe Campaign is opened.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">使用Campaign和Target</a><br/>、 <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">整合Campaign和Target</a><br/>、 <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">在即時</a> 視訊中個人化電子郵件影像(步驟3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Allows you to track the success of your email deliveries directly in Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">與Analytics共用促銷活動資料</a><br/>， <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">針對整合的促銷活動報告</a> 視訊共用KPI(步驟1
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager and People core service (Profiles &amp; Audiences)<br /> </td> 
   <td> Allow you to exchange audiences with the different Adobe Experience Cloud applications that you use.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">人員核心服務(Profiles&amp; Audiences)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Asset core service and Assets On Demand<br /> </td> 
   <td> Allows you to insert assets from your Adobe Experience Cloud library into emails and landing pages created in Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets核心服務</a> 或資產隨選<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest (Analytics for Mobile)<br /> </td> 
   <td> Allows you to collect Points of Interest data from your mobile application's subscribers to send personalized marketing messages with Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">使用Campaign和興趣點資料傳送位置型行銷訊息</a> (行動裝置專用的Analytics)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> Allows you to send personalized emails to your customers in Adobe Campaign as a reaction to specific behaviors that are tracked on your website by Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">在Campaign Standard中使用Experience Cloud觸發器</a><br/>、 <a href="../../integrating/using/abandonment-triggers-use-cases.md">放棄觸發項目觸發器促銷活動使用案例</a><br/>、 <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">根據網站活動</a> 視訊觸發重新行銷訊息(步驟2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Allows you to edit an email content from Dreamweaver and synchronize it with Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">使用Dreamweaver</a> 影片建立個人化電子郵件 <br/>， <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">使用適用於Dreamweaver的促銷活動擴充功能</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Creative SDK<br /> </td> 
   <td> Allows you to edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor.<br /> </td> 
   <td> <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">使用Adobe Creative SDK修改影像</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Platform SDKs<br /> </td> 
   <td> Allows automation of the Mobile App Property activation process in Adobe Campaign using the Experience Platform SDKs.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">使用Experience Platform SDK設定行動應用程式</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

