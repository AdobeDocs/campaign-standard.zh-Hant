---
title: 在Adobe Experience manager中建立電子郵件內容。
description: 透過Adobe Experience manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1d89c8afad835810292689f4b77b0c4d6ba6a86c

---


# 在Adobe Experience manager中建立電子郵件內容 {#creating-email-aem}

Adobe Campaign standard與Adobe Experience manager的整合可讓您在Adobe Campaign電子郵件中使用在Adobe Experience manager中建立的內容。

此使用案例將示範如何在Adobe Experience manager中建立電子郵件內容。

## 必要條件 {#prerequisites}

您應事先確定您有下列元素：

* Adobe Experience Manager製作 **實例**
* Adobe Experience Manager發佈 **實例**
* Adobe Campaign例項

## 配置 {#configuration}

若要搭配使用這兩個解決方案，您必須將它們設定為彼此連線。

1. 設定Adobe Campaign。 操作步驟：

   * 設定Adobe Experience manager類型外部帳戶。
   * 設定選 **[!UICONTROL AEMResourceTypeFilter]**項，此選項可識別在Adobe Experience Manager for Adobe Campaign中建立的內容類型。
   * 建立電子郵件範本，指定其為Adobe Experience manager內容，並將先前建立的外部帳戶連結至此範本。

1. 設定Adobe Experience Manager。 操作步驟：

   * 在Adobe Experience Manager編寫和發佈實例之間配置複製。
   * 透過設定專屬的Adobe Experience manager與Adobe Campaign建立關聯 **[!UICONTROL Cloud Service]**。

## 在Adobe Experience manager中建立電子郵件內容 {#use-case}

若要在Adobe Experience manager中建立電子郵件內容：

1. 使用專為Adobe Campaign建立的範本建立電子郵件內容。
1. 在內容屬性中，選取與您 **[!UICONTROL Cloud Service]**的Adobe Campaign例項對應的項目。
1. 插入文字、影像、個人化等，以編輯內容。
1. 驗證內容。

如需詳細資訊，請參閱詳 [細檔案](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/campaign.html)。

![](assets/aem_content.png)

若要擷取Adobe Campaign中的內容：

1. 根據Adobe Experience Manager類型內容範本建立電子郵件。
1. 使用Adobe Campaign電子郵件內容定義畫面連結使用Adobe Experience manager建立的內容。

![](assets/aem_linked_content.png)

