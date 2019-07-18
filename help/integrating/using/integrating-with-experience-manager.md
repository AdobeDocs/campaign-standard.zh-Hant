---
title: 與Experience Manager整合
seo-title: 與Experience Manager整合
description: 與Experience Manager整合
seo-description: 借助Adobe Experience Manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用它。
page-status-flag: 從未啓動
uuid: ed6c1b76-87f7-4d23-b5 e2-076297a905 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06 bb7 d633 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Integrating with Experience Manager{#integrating-with-experience-manager}

Adobe Campaign Standard與Adobe Experience Manager之間的整合可讓您使用Adobe Campaign電子郵件中的Adobe Experience Manager建立的內容。

因此，您可以充分運用Adobe Experience Manager內容編輯功能以及Adobe Campaign的傳送和資料管理功能。

>[!NOTE]
>
>您無法對從Adobe Experience Manager匯入的內容執行A/B測試。

Adobe Campaign Standard與Adobe Experience Manager6.1、6.2、6.3和6.4相容。以下章節概述您可執行的動作。For more information, refer to the sections dedicated to [configuration](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html) and the [use](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/campaign.html) of the integration.

## Prerequisites {#prerequisites}

您應事先確認下列元素：

* An Adobe Experience Manager **authoring** instance
* An Adobe Experience Manager **publishing** instance
* Adobe Campaign實例

## Use case {#use-case}

若要在Adobe Experience Manager中建立電子郵件內容：

1. 使用專為Adobe Campaign建立的範本建立電子郵件內容。
1. In the content properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.
1. 插入文字、影像、個人化等，以編輯內容。
1. 驗證內容。

For more information, refer to the [detailed documentation](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/campaign.html).

![](assets/aem_content.png)

若要擷取Adobe Campaign中的內容：

1. 根據Adobe Experience Manager類型內容範本建立電子郵件。
1. 使用Adobe Campaign電子郵件內容定義畫面連結使用Adobe Experience Manager建立的內容。

![](assets/aem_linked_content.png)

## Configuration {#configuration}

若要將這兩個解決方案一起使用，您必須設定它們彼此連接。

1. 設定Adobe Campaign。若要這麼做：

   * 設定Adobe Experience Manager類型外部帳戶。
   * Configure the **AEMResourceTypeFilter** option, which recognizes the content types created in Adobe Experience Manager for Adobe Campaign.
   * 建立電子郵件範本，指定它是Adobe Experience Manager內容，並將先前建立的外部帳戶連結至此範本。

1. 設定Adobe Experience Manager。若要這麼做：

   * 設定Adobe Experience Manager編寫與發佈例項之間的複製。
   * Connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**.

