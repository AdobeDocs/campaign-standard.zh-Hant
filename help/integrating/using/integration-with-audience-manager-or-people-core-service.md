---
title: 佈建及設定與 Audience Manager 或 People 核心服務的整合
description: 瞭解如何設定Audience Manager/人員核心服務整合，以便開始與不同的Adobe Experience Cloud解決方案共用受眾或區段。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 60386a9e6e424d76b1de0f2ecbeab48dd06fb354
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 4%

---

# 佈建及設定與 Audience Manager 或 People 核心服務的整合{#integration-with-audience-manager-or-people-core-service}

在Adobe Campaign中布建及設定Audience Manager與People核心有兩個步驟：[提交要求給Adobe](#submitting-request-to-adobe) [在Adobe Campaign中設定整合](#configuring-the-integration-in-adobe-campaign)。

## 正在提交要求給Adobe {#submitting-request-to-adobe}

Audience Manager (AAM)或People核心服務整合可讓您匯入和匯出Adobe Campaign中的對象或區段。

必須先設定此整合。若要請求布建此整合，請聯絡Adobe支援並提供下列資訊：

<table> 
 <tbody> 
  <tr> 
   <td> <strong>要求型別：</strong><br /> </td> 
   <td> 設定AAM/People核心服務 — Campaign整合 </td> 
  </tr> 
  <tr> 
   <td> <strong>組織名稱：</strong><br /> </td> 
   <td> 您的組織名稱 </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS組織ID</strong><br /> </td> 
   <td> 您的組織ID。 <br>若要尋找您的組織識別碼，請參閱<a href="https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=zh-hant">此頁面</a></td> 
  </tr> 
  <tr> 
   <td> <strong>環境：</strong><br /> </td> 
   <td> 範例：生產 </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM或People服務</strong><br /> </td> 
   <td> 範例： Adobe Audience Manager。 無論您是否擁有Audience Manager授權，請務必向布建團隊說明。</td> 
  </tr> 
  <tr> 
   <td> <strong>宣告識別碼或訪客識別碼</strong><br /> </td> 
   <td> 範例：宣告ID </td> 
  </tr> 
  <tr> 
   <td> <strong>其他資訊</strong><br /> </td> 
   <td> 您可能有的任何有用的資訊或註解 </td> 
  </tr> 
 </tbody> 
</table>

## 在Adobe Campaign中設定整合 {#configuring-the-integration-in-adobe-campaign}

提交此請求後，Adobe將會繼續為您布建整合，並連絡您以提供您必須完成設定的詳細資訊和資訊：

* [步驟1：在Adobe Campaign中設定或檢查外部帳戶](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [步驟2：設定資料來源](#step-2--configure-the-data-sources)
* [步驟3：設定Campaign追蹤伺服器](#step-3--configure-campaign-tracking-server)
* [步驟4：設定訪客ID服務](#step-4--configure-the-visitor-id-service)

### 步驟1：在Adobe Campaign中設定或檢查外部帳戶 {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

我們首先需要在Adobe Campaign中設定或檢查外部帳戶。 這些帳戶應已由Adobe設定，且必要的資訊應已通知您。

若要這麼做：

1. 從進階功能表，選取&#x200B;**管理>應用程式設定>外部帳戶**。

   選取下列其中一個可用於此整合的外部帳戶：

   ![](assets/integration_aam_1.png)

1. 以下列格式輸入&#x200B;**[!UICONTROL Receiver server]**
1. 輸入&#x200B;**[!UICONTROL AWS Access Key ID]**、**[!UICONTROL Secret Access Key]**&#x200B;和&#x200B;**[!UICONTROL AWS Region]**。

您的外部帳戶現在已針對這項整合進行設定。

### 步驟2：設定資料來源 {#step-2--configure-the-data-sources}

在Audience Manager中建立下列兩個資料來源： Adobe Campaign (MID)和Adobe Campaign (DeclaredId)。 同時，這兩個資料來源也可在Adobe Campaign中使用：

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**：這是預設為訪客ID設定的現成資料來源。 從Campaign建立的區段將成為此資料來源的一部分。
* **已宣告的識別碼**&#x200B;資料來源：此資料來源必須以Audience Manager中的&#x200B;**[!UICONTROL DeclaredId]**&#x200B;資料來源定義建立並對應。

請注意，如果有多個網站使用不同的網域，Adobe Campaign不支援根據ECID進行調解。

若要設定&#x200B;**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**&#x200B;資料來源：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，選取&#x200B;**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**。

   ![](assets/integration_aam_2.png)

1. 在&#x200B;**[!UICONTROL Data Source/ Alias]**&#x200B;下拉式清單中選擇&#x200B;**[!UICONTROL Adobe Campaign]**。
1. 輸入Adobe提供的&#x200B;**[!UICONTROL AAM Destination ID]**。

   ![](assets/integration_aam_3.png)

1. 在&#x200B;**[!UICONTROL Reconciliation process]**&#x200B;類別中，我們建議您不要變更調解條件，並一律使用&#x200B;**[!UICONTROL Visitor ID]**。
1. 按一下&#x200B;**[!UICONTROL Save]**。

若要建立&#x200B;**[!UICONTROL Declared ID]**&#x200B;資料來源：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，按一下&#x200B;**[!UICONTROL Create]**&#x200B;按鈕。
1. 編輯資料來源的&#x200B;**[!UICONTROL Label]**。
1. 在&#x200B;**[!UICONTROL Data Source/ Alias]**&#x200B;下拉式清單中，選擇與Audience Manager中&#x200B;**[!UICONTROL DeclaredID]**&#x200B;資料來源對應的資料Source。
1. 輸入Adobe提供的&#x200B;**[!UICONTROL Data Source / Alias]**&#x200B;和&#x200B;**[!UICONTROL AAM Destination ID]**&#x200B;來設定您的資料來源。
1. 視需要設定&#x200B;**[!UICONTROL Reconciliation process]**。
1. 按一下&#x200B;**[!UICONTROL Save]**。

>[!NOTE]
>
>如果您正在設定[Campaign-Triggers整合](../../integrating/using/configuring-triggers-in-experience-cloud.md)的共用資料來源，則不需要&#x200B;**[!UICONTROL AAM Destination ID]**&#x200B;欄位。 只有在設定Triggers - Campaign整合時才需要&#x200B;**[!UICONTROL Priority]**。 優先順序會決定先設定哪個Data Source。 優先順序可以是任何數字，例如1或100。 優先順序越高，調解期間的偏好設定就越高。

### 步驟3：設定Campaign追蹤伺服器 {#step-3--configure-campaign-tracking-server}

若要設定與People核心服務或Audience Manager的整合，我們還需要設定Campaign追蹤伺服器。

若要讓共用對象能與訪客ID搭配運作，追蹤伺服器網域應該是已點按URL的子網域或主要網站。

>[!IMPORTANT]
>
> 您必須確定已在網域(CNAME)上註冊Campaign追蹤伺服器。 您可以在[本文章](https://helpx.adobe.com/tw/campaign/kb/domain-name-delegation.html)中找到網域名稱組態的詳細資訊。

### 步驟4：設定訪客ID服務 {#step-4--configure-the-visitor-id-service}

如果您的訪客ID服務從未在您的Web屬性或網站上設定過，請參閱下列[檔案](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html?lang=zh-Hant)以瞭解如何設定您的服務或下列[影片](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html#step-two)。

使用Experience Cloud識別碼服務中的`setCustomerID`函式將客戶識別碼與宣告的識別碼同步，整合代碼： `AdobeCampaignID`。 `AdobeCampaignID`應該符合[步驟2：設定資料來源](#step-2--configure-the-data-sources)中設定的收件者資料Source中設定的調解金鑰值。

您的設定和布建已完成，整合現在可用於匯入和匯出對象或區段。
