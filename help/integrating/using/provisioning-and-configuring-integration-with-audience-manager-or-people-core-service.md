---
title: 佈建及設定與 Audience Manager 或 People 核心服務的整合
description: '瞭解如何配置Audience Manager/人員核心服務整合，以開始使用不同的Adobe Experience Cloud解決方案共用受眾或網段。 '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 602878233e919d01f3972167cb6d3a1acc4cfc02
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 10%

---

# 佈建及設定與 Audience Manager 或 People 核心服務的整合{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

Adobe CampaignAudience Manager和人員核心的配置和配置分兩步進行： [將請求提交到Adobe](#submitting-request-to-adobe) 然後 [在Adobe Campaign配置整合](#configuring-the-integration-in-adobe-campaign)。

## 向 Adobe 提交請求 {#submitting-request-to-adobe}

Audience Manager(AAM)或人員核心服務整合使您能夠導入和導出Adobe Campaign的受眾或部門。

必須先設定此整合。若要請求佈建此整合，請傳送電子郵件寄至 [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com)，並提供下列資訊：

<table> 
 <tbody> 
  <tr> 
   <td> <strong>請求類型：</strong><br /> </td> 
   <td> 配置AAM/人員核心服務 — 市場活動整合 </td> 
  </tr> 
  <tr> 
   <td> <strong>組織名稱：</strong><br /> </td> 
   <td> 您的組織名稱 </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS 組織 ID</strong><br /> </td> 
   <td> 您的組織ID。 <br> 要查找組織ID，請參閱 <a href="https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=zh-Hant">此頁</a></td> 
  </tr> 
  <tr> 
   <td> <strong>環境:</strong><br /> </td> 
   <td> 示例：生產 </td> 
  </tr> 
  <tr> 
   <td> <strong>或AAM人員服務</strong><br /> </td> 
   <td> 示例：Adobe Audience Manager。 請務必向預配團隊提及您是否擁有Audience Manager許可證。</td> 
  </tr> 
  <tr> 
   <td> <strong>聲明的ID或訪問者ID</strong><br /> </td> 
   <td> 示例：聲明的ID </td> 
  </tr> 
  <tr> 
   <td> <strong>其他資訊</strong><br /> </td> 
   <td> 您可能擁有的任何有用資訊或注釋 </td> 
  </tr> 
 </tbody> 
</table>

## 在Adobe Campaign配置整合 {#configuring-the-integration-in-adobe-campaign}

提交此請求後，Adobe將繼續為您預配整合，並與您聯繫以提供您必須完成配置的詳細資訊和資訊：

* [步驟1:配置或檢查Adobe Campaign的外部帳戶](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [步驟2:配置資料源](#step-2--configure-the-data-sources)
* [第3步：配置市場活動跟蹤伺服器](#step-3--configure-campaign-tracking-server)
* [第4步：配置訪問者ID服務](#step-4--configure-the-visitor-id-service)

### 步驟1:配置或檢查Adobe Campaign的外部帳戶 {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

我們首先需要配置或檢查Adobe Campaign的外部帳戶。 這些帳戶應通過Adobe配置，並應將必要的資訊傳達給您。

若要這麼做：

1. 從高級菜單中，選擇 **管理>應用程式設定>外部帳戶**。

   選擇以下可用於此整合的外部帳戶之一：

   ![](assets/integration_aam_1.png)

1. 輸入 **[!UICONTROL Receiver server]** 格式
1. 輸入 **[!UICONTROL AWS Access Key ID]**。 **[!UICONTROL Secret Access Key]** 和 **[!UICONTROL AWS Region]**。

您的外部帳戶現在已配置為進行此整合。

### 步驟2:配置資料源 {#step-2--configure-the-data-sources}

以下兩個資料源在「受眾管理器」內建立：Adobe Campaign(MID)和Adobe Campaign(AlkedId)。 同時，Adobe Campaign提供了以下兩個資料源：

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:這是預設為訪問者ID配置的現成資料源。 從市場活動建立的段將是此資料源的一部分。
* **聲明的ID** 資料源：此資料源需要建立並映射 **[!UICONTROL DeclaredId]** 資料源定義(來自Audience Manager)。

請注意，如果多個網站具有不同的域，Adobe Campaign不支援基於ECID的協調。

配置 **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** 資料源：

1. 在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;選中 **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**。

   ![](assets/integration_aam_2.png)

1. 選擇 **[!UICONTROL Adobe Campaign]** 的 **[!UICONTROL Data Source/ Alias]** 下拉。
1. 輸入 **[!UICONTROL AAM Destination ID]** 由Adobe提供。

   ![](assets/integration_aam_3.png)

1. 在 **[!UICONTROL Reconciliation process]** 類別，我們建議您不要更改協調標準並始終使用 **[!UICONTROL Visitor ID]**。
1. 按一下&#x200B;**[!UICONTROL Save]**。

建立 **[!UICONTROL Declared ID]** 資料源：

1. 在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**，按一下 **[!UICONTROL Create]** 按鈕
1. 編輯 **[!UICONTROL Label]** 資料源。
1. 在 **[!UICONTROL Data Source/ Alias]** 下拉，選擇與 **[!UICONTROL DeclaredID]** 資料源來自Audience Manager。
1. 通過輸入 **[!UICONTROL Data Source / Alias]** 和 **[!UICONTROL AAM Destination ID]** 由Adobe提供。
1. 設定 **[!UICONTROL Reconciliation process]** 按需要。
1. 按一下&#x200B;**[!UICONTROL Save]**。

>[!NOTE]
>
>的 **[!UICONTROL AAM Destination ID]** 如果要為 [市場活動 — 觸發器整合](../../integrating/using/configuring-triggers-in-experience-cloud.md)。 **[!UICONTROL Priority]** 僅在配置「觸發器 — 市場活動整合」時才需要。 優先順序決定首先配置哪個資料源。 優先順序可以是任意數字，如1或100。 優先順序越高，協調期間的優先順序越高。

### 第3步：配置市場活動跟蹤伺服器 {#step-3--configure-campaign-tracking-server}

為了配置與「人員核心」服務或「受眾經理」的整合，我們還需要配置「活動跟蹤」伺服器。

在此，您需要確保市場活動跟蹤伺服器已在域(CNAME)上註冊。 您可以在中查找有關域名配置的詳細資訊 [這篇文章](https://helpx.adobe.com/tw/campaign/kb/domain-name-delegation.html)。

### 第4步：配置訪問者ID服務 {#step-4--configure-the-visitor-id-service}

如果您的訪問者ID服務從未在您的Web屬性或網站上配置過，請參閱以下內容 [文檔](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html) 瞭解如何配置服務或以下內容 [視頻](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html#step-two)。

您的配置和設定已完成，現在可以使用整合來導入和導出受眾或段。
