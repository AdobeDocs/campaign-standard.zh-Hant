---
title: 與 Experience Manager 整合
description: 透過Adobe Experience manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用。
page-status-flag: 從未激活
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 整合
content-type: 參考
topic-tags: 使用促銷活動與體驗管理員
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 與 Experience Manager 整合{#integrating-with-experience-manager}

Adobe Campaign standard與Adobe Experience manager之間的整合可讓您在Adobe Campaign電子郵件中使用Adobe Experience Manager中建立的內容。

因此，您可以充份運用Adobe Experience manager內容編輯功能以及Adobe Campaign的傳送和資料管理功能。

>[!NOTE]
>
>您無法對從Adobe Experience manager匯入的內容執行A/B測試。

Adobe Campaign standard與Adobe Experience Manager 6.1、6.2、6.3和6.4相容。以下各節概述了您可以執行的操作。 如需詳細資訊，請參閱專用於 [設定](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html)[與整合使用](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/campaign.html) 的章節。

## 必要條件 {#prerequisites}

您應事先確定您有下列元素：

* Adobe Experience Manager製作 **實例**
* Adobe Experience Manager發佈 **實例**
* Adobe Campaign例項

## 使用案例 {#use-case}

若要在Adobe Experience manager中建立電子郵件內容：

1. 使用專為Adobe Campaign建立的範本建立電子郵件內容。
1. 在內容屬性中，選取與您 **[!UICONTROL Cloud Service]** 的Adobe Campaign例項對應的項目。
1. 插入文字、影像、個人化等，以編輯內容。
1. 驗證內容。

 如需詳細資訊，請參閱詳 [細檔案](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/campaign.html)。

![](assets/aem_content.png)

若要擷取Adobe Campaign中的內容：

1. 根據Adobe Experience Manager類型內容範本建立電子郵件。
1. 使用Adobe Campaign電子郵件內容定義畫面連結使用Adobe Experience manager建立的內容。

![](assets/aem_linked_content.png)

## 配置 {#configuration}

若要搭配使用這兩個解決方案，您必須將它們設定為彼此連線。

1. 設定Adobe Campaign。 操作步驟：

   * 設定Adobe Experience manager類型外部帳戶。
   * 設定 **AEMResourceTypeFilter** 選項，此選項可識別在Adobe Experience Manager for Adobe Campaign中建立的內容類型。
   * 建立電子郵件範本，指定其為Adobe Experience manager內容，並將先前建立的外部帳戶連結至此範本。

1. 設定Adobe Experience Manager。 操作步驟：

   * 在Adobe Experience Manager編寫和發佈實例之間配置複製。
   * 透過設定專屬的Adobe Experience manager與Adobe Campaign建立關聯 **[!UICONTROL Cloud Service]**。

