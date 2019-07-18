---
title: 提供並設定與Audience Manager或People核心服務的整合
seo-title: 提供並設定與Audience Manager或People核心服務的整合
description: 提供並設定與Audience Manager或People核心服務的整合
seo-description: '瞭解如何設定Audience Manager/人員核心服務整合，以開始與不同的Adobe Experience Cloud解決方案共用觀眾或區段。 '
page-status-flag: 從未啓動
uuid: e7329644-0033-4729-b4 a7-61bef137 f4 b
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: working-with-campaign-and-udience-manager-or-ople-core-service
discoiquuid: eb24f4ea-325f-433a-91a-91a-c45906320 bcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Provisioning and configuring integration with Audience Manager or People core service{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

The provisioning and configuring of Audience Manager and People core in Adobe Campaign take two steps: [Submitting request to Adobe](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#submitting-request-to-adobe) then [Configuring the integration in Adobe Campaign](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#configuring-the-integration-in-adobe-campaign).

## Submitting request to Adobe {#submitting-request-to-adobe}

Audience Manager(AAM)或人員核心服務整合可讓您在Adobe Campaign中匯入及匯出對象或區段。

此整合必須先設定。To request provisioning of this integration, write an email to [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) with the following information:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>請求類型：</strong><br /> </td> 
   <td> 設定AAM/人員核心服務促銷活動整合 </td> 
  </tr> 
  <tr> 
   <td> <strong>組織名稱：</strong><br /> </td> 
   <td> 您的組織名稱 </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS組織ID</strong><br /> </td> 
   <td> 您的IMS組織ID* </td> 
  </tr> 
  <tr> 
   <td> <strong>環境：</strong><br /> </td> 
   <td> 範例：Production </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM或人員服務</strong><br /> </td> 
   <td> 範例：Adobe Audience Manager </td> 
  </tr> 
  <tr> 
   <td> <strong>宣告ID或訪客ID</strong><br /> </td> 
   <td> 範例：宣告ID </td> 
  </tr> 
  <tr> 
   <td> <strong>其他資訊</strong><br /> </td> 
   <td> 任何有用的資訊或留言， </td> 
  </tr> 
 </tbody> 
</table>

* You can find your IMS Org ID on the Experience Cloud, in the **Administration** menu. 您也可以在第一次連線至Adobe Experience Cloud時提供。

## Configuring the integration in Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

提交此請求後，Adobe將繼續為您提供整合，並與您聯絡以提供詳細資訊和資訊，您必須先完成設定：

* [步驟1：在Adobe Campaign中設定或檢查外部帳戶](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [步驟2：設定資料來源](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)
* [步驟3：設定促銷活動追蹤伺服器](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-3--configure-campaign-tracking-server)
* [步驟4：設定訪客ID服務](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-4--configure-the-visitor-id-service)

### Step 1: Configure or check the external accounts in Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

我們首先需要在Adobe Campaign中設定或檢查外部帳戶。這些帳戶應由Adobe設定，且應告知您必要的資訊。

若要這麼做：

1. From the advanced menu, select **Administration &gt; Application settings &gt; External accounts**.

   選取下列整合可用的其中一個外部帳戶：

   ![](assets/integration_aam_1.png)

1. Enter **[!UICONTROL Receiver server]** in following format
1. Enter the **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** and **[!UICONTROL AWS Region]**.

現在已為此整合設定外部帳戶。

### Step 2: Configure the Data Sources {#step-2--configure-the-data-sources}

Audience Manager中會建立下列兩個資料來源：Adobe Campaign(MID)和Adobe Campaign(陳述式)。同時，這兩個資料來源可用於Adobe Campaign：

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**：此為訪客ID預設設定的預設資料來源。從促銷活動建立的區段將屬於此資料來源的一部分。
* **宣告ID** 資料來源：必須使用Audience Manager的 **[!UICONTROL DeclaredId]** 資料來源定義建立並對應此資料來源。

請注意，若是有多個不同網域的網站，Adobe Campaign不支援以EID為基礎的協調。

To configure the **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** data source:

1. In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, select **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Choose **[!UICONTROL Adobe Campaign]** in the **[!UICONTROL Data Source/ Alias]** drop-down.
1. Enter the **[!UICONTROL AAM Destination ID]** provided by Adobe.

   ![](assets/integration_aam_3.png)

1. In the **[!UICONTROL Reconciliation process]** category, we advise you not to change the reconciliation criteria and always use the **[!UICONTROL Visitor ID]**.
1. Click **[!UICONTROL Save]**.

To create the **[!UICONTROL Declared ID]** data source:

1. In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, click the **[!UICONTROL Create]** button.
1. Edit the **[!UICONTROL Label]** of your data source.
1. In the **[!UICONTROL Data Source/ Alias]** drop-down, choose the Data Source corresponding to the **[!UICONTROL DeclaredID]** data source from Audience Manager.
1. Configure your data source by entering the **[!UICONTROL Data Source / Alias]** and **[!UICONTROL AAM Destination ID]** provided by Adobe.
1. Set the **[!UICONTROL Reconciliation process]** as needed.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>**[!UICONTROL AAM Destination ID]** 如果您要設定 [促銷活動觸發項目整合](../../integrating/using/configuring-triggers-in-experience-cloud.md)的共用資料來源，則不需要此欄位。**[!UICONTROL Priority]** 僅在設定觸發器-促銷活動整合時才需要。優先順序決定首先設定的資料來源。優先順序可以是任何數字，例如或100。優先順序愈高，協調期間的偏好設定愈高。

### Step 3: Configure Campaign Tracking server {#step-3--configure-campaign-tracking-server}

如需與People Core服務或Audience Manager整合的設定，我們也需要設定促銷活動追蹤伺服器。

在這裡，您必須確定Campaign追蹤伺服器已註冊在網域(CNAME)上。You can find more information about domain name delegation in [this article](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf).

### Step 4: Configure the Visitor ID Service {#step-4--configure-the-visitor-id-service}

In the case that your Visitor ID service has never been configured on your web properties or websites, refer to the following [document](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-aam-analytics.html) to learn how to configure your service or the following [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

您的設定和布建完成後，整合現在可以用來匯入和匯出對象或區段。
