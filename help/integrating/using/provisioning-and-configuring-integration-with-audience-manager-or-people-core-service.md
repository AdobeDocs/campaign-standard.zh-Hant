---
title: 布建和設定與Audience manager或People核心服務的整合
seo-title: 布建和設定與Audience manager或People核心服務的整合
description: 布建和設定與Audience manager或People核心服務的整合
seo-description: '瞭解如何設定Audience Manager / People核心服務整合，以便開始使用不同的Adobe Experience cloud解決方案來分享受眾或細分。 '
page-status-flag: 從未激活
uuid: e7329644-0033-4729-b4a7-61bef137f4b5
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 整合
content-type: 參考
topic-tags: 使用促銷活動與觀眾管理員或人員核心服務
discoiquuid: eb24f4ea-325f-433a-91a0-c45906320bcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 布建和設定與Audience manager或People核心服務的整合{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

在Adobe Campaign中布建和設定Audience manager和People核心的步驟有兩個：請 [求提交至Adobe](#submitting-request-to-adobe) , [然後在Adobe Campaign中設定整合](#configuring-the-integration-in-adobe-campaign)。

## 向Adobe提交請求 {#submitting-request-to-adobe}

Audience Manager(AAM)或People核心服務整合可讓您在Adobe Campaign中匯入和匯出觀眾或區段。

必須先設定此整合。 若要要求提供此整合，請寄送電子郵件至 [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) ，內含下列資訊：

<table> 
 <tbody> 
  <tr> 
   <td> <strong>請求類型：</strong><br /> </td> 
   <td> 設定AAM/People核心服務——促銷活動整合 </td> 
  </tr> 
  <tr> 
   <td> <strong>組織名稱：</strong><br /> </td> 
   <td> 您的組織名稱 </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS組織ID</strong><br /> </td> 
   <td> 您的IMS組織ID。 <br> 您可以在Experience cloud的「管理」功能表中找到您的IMS組織ID。 當您第一次連線至Adobe Experience cloud時，也會提供。 </td> 
  </tr> 
  <tr> 
   <td> <strong>環境：</strong><br /> </td> 
   <td> 範例：製作 </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM或人員服務</strong><br /> </td> 
   <td> 範例：Adobe Audience Manager </td> 
  </tr> 
  <tr> 
   <td> <strong>宣告的ID或訪客ID</strong><br /> </td> 
   <td> 範例：宣告的ID </td> 
  </tr> 
  <tr> 
   <td> <strong>其他資訊</strong><br /> </td> 
   <td> 您可能擁有的任何有用資訊或註解 </td> 
  </tr> 
 </tbody> 
</table>

*適 **[!UICONTROL Declared ID]** 用於所有共用的觀眾整合。 請注意，如果您使用「人員核心服務」，則使用的 **[!UICONTROL Declared ID]** 情況可能會隨解決方案而改變：

* 如果觀眾是透過People核心服務從Adobe Campaign分享到Adobe Target，則可 **[!UICONTROL Declared ID]** 以布建觀眾。
* 如果觀眾是透過People核心服務從Adobe Campaign分享到Ad Cloud，您將無法使用布建來回填 **[!UICONTROL Declared ID]** 觀眾的歷史回填。 在建立觀眾時，也會有延遲。
* 如果觀眾是透過People Core Service從Adobe Analytics分享到Adobe Campaign,Adobe Campaign中將不會填入區段 **[!UICONTROL Declared ID]**。

如果您使用Adobe Audience manager而非People Core Service，則所有 **[!UICONTROL Declared ID]** 案例都適用。

您可以向以下地址 **[!UICONTROL Declared ID]** 請求設定： [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com)。

## 在Adobe Campaign中設定整合 {#configuring-the-integration-in-adobe-campaign}

提交此要求後，Adobe會繼續為您提供整合，並聯絡您，提供您必須完成設定的詳細資訊：

* [步驟1:設定或檢查Adobe Campaign中的外部帳戶](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [步驟2:設定資料來源](#step-2--configure-the-data-sources)
* [步驟3:設定促銷活動追蹤伺服器](#step-3--configure-campaign-tracking-server)
* [步驟4:設定訪客ID服務](#step-4--configure-the-visitor-id-service)

### 步驟1:設定或檢查Adobe Campaign中的外部帳戶 {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

我們首先需要在Adobe Campaign中設定或檢查外部帳戶。 這些帳戶應由Adobe設定，且必要的資訊應已傳達給您。

若要這麼做：

1. 從進階功能表中，選取「管 **理&gt;應用程式設定&gt;外部帳戶」**。

   選擇下列其中一個可用於此整合的外部帳戶：

   ![](assets/integration_aam_1.png)

1. 以下 **[!UICONTROL Receiver server]** 格式輸入
1. 輸入 **[!UICONTROL AWS Access Key ID]**&#x200B;和 **[!UICONTROL Secret Access Key]** 和 **[!UICONTROL AWS Region]**。

您的外部帳戶現在已設定為此整合。

### 步驟2:設定資料來源 {#step-2--configure-the-data-sources}

在Audience manager中建立下列兩個資料來源：Adobe Campaign(MID)和Adobe Campaign(DeclaredId)。 同時，Adobe Campaign提供下列兩個資料來源：

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:這是預設為訪客ID設定的現成可用資料來源。 從「促銷活動」建立的區段將是此資料來源的一部分。
* **宣告的ID** 資料來源：此資料來源需要建立並對應至Audience Manager **[!UICONTROL DeclaredId]** 的資料來源定義。

請注意，若有多個網域的網站不同，Adobe Campaign不支援根據ECID進行協調。

要配置數 **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** 據源：

1. 在 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**&#x200B;中，選擇 **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**。

   ![](assets/integration_aam_2.png)

1. 在下 **[!UICONTROL Adobe Campaign]** 拉式清 **[!UICONTROL Data Source/ Alias]** 單中選擇。
1. 輸入Adobe **[!UICONTROL AAM Destination ID]** 提供的。

   ![](assets/integration_aam_3.png)

1. 在類別 **[!UICONTROL Reconciliation process]** 中，我們建議您不要更改協調標準並始終使用 **[!UICONTROL Visitor ID]**。
1. Click **[!UICONTROL Save]**.

要建立數 **[!UICONTROL Declared ID]** 據源：

1. 在 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**&#x200B;中，按一下按 **[!UICONTROL Create]** 鈕。
1. 編輯 **[!UICONTROL Label]** 資料來源。
1. 在下拉 **[!UICONTROL Data Source/ Alias]** 式清單中，選擇與Audience manager中資料來源對 **[!UICONTROL DeclaredID]** 應的資料來源。
1. 輸入Adobe提供的資料來 **[!UICONTROL Data Source / Alias]** 設定 **[!UICONTROL AAM Destination ID]** 您的資料來源。
1. 視需要 **[!UICONTROL Reconciliation process]** 設定。
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>如果 **[!UICONTROL AAM Destination ID]** 您要設定促銷活動——觸發器整合的共用資料來源，則 [不需要此欄位](../../integrating/using/configuring-triggers-in-experience-cloud.md)。 **[!UICONTROL Priority]** 只有在設定「觸發器——促銷活動」整合時才需要。 優先順序決定要先設定哪個資料來源。 優先順序可以是任何數字，例如1或100。 優先順序越高，協調期間的優先順序越高。

### 步驟3:設定促銷活動追蹤伺服器 {#step-3--configure-campaign-tracking-server}

若要設定與People Core服務或Audience Manager的整合，我們還需要設定促銷活動追蹤伺服器。

在這裡，您必須確定促銷活動追蹤伺服器已註冊在網域(CNAME)上。 您可在本文中找到有關網域名稱委派的 [詳細資訊](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf)。

### 步驟4:設定訪客ID服務 {#step-4--configure-the-visitor-id-service}

如果您的訪客ID服務從未在您的Web屬性或網站上設定，請參閱下列檔案 [](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-aam-analytics.html) ，以瞭解如何設定您的服務或下列視 [訊](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)。

您的設定和布建已完成，整合現在可用來匯入和匯出觀眾或區段。
