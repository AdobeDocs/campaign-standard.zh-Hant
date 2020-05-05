---
title: 開始使用Campaign整合
description: Adobe Campaign可讓您使用其他Adobe解決方案，並結合其不同的功能。
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9

---


# 關於 Campaign 整合{#get-started-campaign-integrations}

本節詳細說明目前版本的Adobe Campaign與其他解決方案與服務之間的功能整合。

下列不同的整合功能可讓您將Adobe Campaign的傳遞和進階促銷活動管理功能與一組建立的解決方案相結合，以協助您個人化使用者體驗。

>[!NOTE]
>
> 依預設，Adobe Campaign已連結至Adobe Experience Cloud帳戶。

其他解決方案也可以連結至Adobe Experience Cloud，視您的環境而定。 它們以「組織」（又稱為「租客」）連結。

組織是可讓管理員設定群組和使用者，以及控制Experience Cloud中單一登入的實體。 組織的運作方式類似登入公司，涵蓋所有Experience Cloud產品和解決方案。 通常，組織就是您的公司名稱。 但是，公司可以有許多組織。 使用者和組織管理在 [Adobe Experience Cloud說明入口網站中有詳細說明](https://marketing.adobe.com/resources/help/zh_TW/mcloud/organizations.html)。

如果您想要將其他系統的資料流與Adobe Campaign整合，請參閱我們的 [API檔案](../../api/using/get-started-apis.md)。

>[!NOTE]
>
>Adobe Campaign Standard也可以連線至Microsoft Dynamics 365: 此整合可同步CRM系統中所有可用的連絡資料，讓所有相關的連絡資料都可用於促銷活動。 如需此整合的詳細資訊，請參閱使 [用促銷活動和動態365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。


<table> 
 <thead> 
  <tr> 
   <th> 解決方案<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Refer to<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1、6.2、6.3、6.4、6.5<br /> </td> 
   <td> 可讓您直接在Adobe Experience Manager中建立對應至Adobe Campaign資料庫的電子郵件內容或表單。<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">使用Campaign和Experience Manager</a><br/>、 <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">整合Experience Manager和Campaign Standard</a> , <br/><a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">使用Experience Manager和Campaign建立電子郵件</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic、Standard<br /> </td> 
   <td> 可讓您插入在開啟由Adobe Campaign建立和傳送的電子郵件時，由Adobe Target動態計算的影像。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">使用Campaign和Target</a> 、整 <br/>合Campaign和Target <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">,</a><br/>即時視訊中個人化電子郵件影像 <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html"></a> （步驟3）
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard、Premium <br /> </td> 
   <td> 可讓您直接在Adobe Analytics中追蹤電子郵件傳送的成功。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">與Analytics共用促銷活動資料</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">共用KPI以整合促銷活動報告視訊</a> （步驟1）
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager與人員核心服務（個人檔案與觀眾）<br /> </td> 
   <td> 可讓您與使用的不同Adobe Experience Cloud應用程式交換受眾。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People Core Service(Profiles &amp; Audiences)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> 資產核心服務與隨選資產<br /> </td> 
   <td> 可讓您將Adobe Experience Cloud資料庫中的資產插入在Adobe Campaign中建立的電子郵件和登陸頁面。<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">資產核心服務</a> ，或隨選資產<br /> </td> 
  </tr> 
  <tr> 
   <td> 興趣點（行動裝置分析）<br /> </td> 
   <td> 可讓您向行動應用程式的訂閱者收集興趣點資料，以便透過Adobe Campaign傳送個人化行銷訊息。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">傳送含有促銷活動和地標資料的位置型行銷訊息</a> （行動裝置分析）<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> 可讓您在Adobe Campaign中傳送個人化電子郵件給客戶，以回應Adobe Analytics在您網站上追蹤的特定行為。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">在Campaign Standard中使用Experience Cloud觸發器</a><br/>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">放棄觸發器——促銷活動使用案例</a><br/>，根據網站活動視訊 <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html"></a> 觸發再行銷訊息（步驟2）
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> 可讓您編輯Dreamweaver的電子郵件內容，並與Adobe Campaign同步化。<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">使用Dreamweaver視訊建立個人化電子郵件</a> , <br/>使 <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">用適用於Dreamweaver的Campaign擴充功能</a> 
  </td> 
  </tr> 
  <tr> 
   <td> 體驗平台SDK<br /> </td> 
   <td> 允許使用Experience Platform SDK在Adobe Campaign中自動執行行動應用程式屬性啟動程式。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">使用Experience Platform SDK設定行動應用程式</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

