---
solution: Campaign Standard
product: campaign
title: 布建與設定與 Audience Manager 或 People 核心服務整合
description: '瞭解如何設定Audience Manager/人員核心服務整合，以便開始使用不同的Adobe Experience Cloud解決方案分享受眾或細分。 '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: 人員核心服務整合
role: 資料架構師
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 9%

---


# 布建與設定與 Audience Manager 或 People 核心服務整合{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

Adobe CampaignAudience Manager和人員核心的設定和配置分為兩個步驟：[向Adobe](#submitting-request-to-adobe)然後[提交請求，在Adobe Campaign配置整合。](#configuring-the-integration-in-adobe-campaign)

## 向 Adobe 提交請求 {#submitting-request-to-adobe}

Audience Manager(AAM)或人員核心服務整合可讓您匯入和匯出Adobe Campaign的觀眾或區段。

必須先設定此整合。若要請求佈建此整合，請傳送電子郵件寄至 [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com)，並提供下列資訊：

<table> 
 <tbody> 
  <tr> 
   <td> <strong>請求類型：</strong><br /> </td> 
   <td> 設定AAM/人員核心服務——促銷活動整合 </td> 
  </tr> 
  <tr> 
   <td> <strong>組織名稱：</strong><br /> </td> 
   <td> 您的組織名稱 </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS 組織 ID</strong><br /> </td> 
   <td> 您的IMS組織ID。 <br> 您可以在「管理」功能表的Experience Cloud上找到您的IMS組織ID。當您第一次連接Adobe Experience Cloud時，也會提供此功能。 </td> 
  </tr> 
  <tr> 
   <td> <strong>環境:</strong><br /> </td> 
   <td> 範例：製作 </td> 
  </tr> 
  <tr> 
   <td> <strong>或AAM人員服務</strong><br /> </td> 
   <td> 範例：Adobe Audience Manager。 請務必向布建團隊提及您是否擁有Audience Manager授權。</td> 
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

## 在Adobe Campaign配置整合{#configuring-the-integration-in-adobe-campaign}

提交此請求後，Adobe將繼續為您提供整合，並聯絡您以提供詳細資訊和資訊，以完成設定：

* [步驟1:在Adobe Campaign配置或檢查外部帳戶](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [步驟2:設定資料來源](#step-2--configure-the-data-sources)
* [步驟3:設定促銷活動追蹤伺服器](#step-3--configure-campaign-tracking-server)
* [步驟4:設定訪客ID服務](#step-4--configure-the-visitor-id-service)

### 步驟1:在Adobe Campaign{#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}中配置或檢查外部帳戶

我們首先需要在Adobe Campaign設定或檢查外部帳戶。 這些帳戶應該由Adobe設定，而且必要的資訊應該已傳達給您。

若要這麼做：

1. 從高級菜單中，選擇「**管理>應用程式設定>外部帳戶**」。

   選擇下列其中一個可用於此整合的外部帳戶：

   ![](assets/integration_aam_1.png)

1. 以下列格式輸入&#x200B;**[!UICONTROL Receiver server]**
1. 輸入&#x200B;**[!UICONTROL AWS Access Key ID]**、**[!UICONTROL Secret Access Key]**&#x200B;和&#x200B;**[!UICONTROL AWS Region]**。

您的外部帳戶現在已設定為此整合。

### 步驟2:設定Data Sources {#step-2--configure-the-data-sources}

在Audience Manager中建立下列兩個資料來源：Adobe Campaign(MID)和Adobe Campaign(DelaredId)。 同時，這兩個資料來源在Adobe Campaign也有：

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:這是預設為訪客ID設定的現成可用資料來源。從「促銷活動」建立的區段將是此資料來源的一部分。
* **宣告** 的ID資料來源：此資料來源需要建立並與Audience Manager中的 **[!UICONTROL DeclaredId]** 資料來源定義對應。

請注意，若是多個網域不同的網站，Adobe Campaign不支援以ECID為基礎的協調。

要配置&#x200B;**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**&#x200B;資料源：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，選擇&#x200B;**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**。

   ![](assets/integration_aam_2.png)

1. 在&#x200B;**[!UICONTROL Data Source/ Alias]**&#x200B;下拉式清單中選擇&#x200B;**[!UICONTROL Adobe Campaign]**。
1. 輸入Adobe提供的&#x200B;**[!UICONTROL AAM Destination ID]**。

   ![](assets/integration_aam_3.png)

1. 在&#x200B;**[!UICONTROL Reconciliation process]**&#x200B;類別中，我們建議您不要更改協調標準，並始終使用&#x200B;**[!UICONTROL Visitor ID]**。
1. 按一下 **[!UICONTROL Save]**。

要建立&#x200B;**[!UICONTROL Declared ID]**&#x200B;資料源：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，按一下&#x200B;**[!UICONTROL Create]**&#x200B;按鈕。
1. 編輯您的資料來源的&#x200B;**[!UICONTROL Label]**。
1. 在&#x200B;**[!UICONTROL Data Source/ Alias]**&#x200B;下拉式清單中，選擇與&#x200B;**[!UICONTROL DeclaredID]**&#x200B;資料來源對應的「資料來源」(來自Audience Manager)。
1. 輸入Adobe提供的&#x200B;**[!UICONTROL Data Source / Alias]**&#x200B;和&#x200B;**[!UICONTROL AAM Destination ID]**，以設定您的資料來源。
1. 視需要設定&#x200B;**[!UICONTROL Reconciliation process]**。
1. 按一下 **[!UICONTROL Save]**。

>[!NOTE]
>
>如果您要設定[促銷活動——觸發器整合](../../integrating/using/configuring-triggers-in-experience-cloud.md)的共用資料來源，則不需要&#x200B;**[!UICONTROL AAM Destination ID]**&#x200B;欄位。 **[!UICONTROL Priority]** 只有在設定「觸發器——促銷活動」整合時才需要。優先順序決定要先設定哪個資料來源。 優先順序可以是任何數字，例如1或100。 優先順序越高，協調期間的優先順序越高。

### 步驟3:設定促銷活動追蹤伺服器{#step-3--configure-campaign-tracking-server}

若要設定與People Core服務或Audience Manager的整合，我們還需要設定促銷活動追蹤伺服器。

在這裡，您必須確定促銷活動追蹤伺服器已註冊在網域(CNAME)上。 您可在[本文](https://helpx.adobe.com/tw/campaign/kb/domain-name-delegation.html)中找到有關域名配置的更多資訊。

### 步驟4:設定訪客ID服務{#step-4--configure-the-visitor-id-service}

若您的訪客ID服務從未在您的網站屬性或網站上設定，請參閱下列[document](https://docs.adobe.com/content/help/en/id-service/using/implementation/setup-aam-analytics.html)以瞭解如何設定您的服務或下列[video](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html#step-two)。

您的設定和布建已完成，整合現在可用來匯入和匯出觀眾或區段。
