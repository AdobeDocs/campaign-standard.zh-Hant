---
solution: Campaign Standard
product: campaign
title: 設定 Campaign-Experience Manager 整合
description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 3%

---


# 設定 Campaign-Experience Manager 整合 {#configuration-aem}

Adobe Campaign Standard與Adobe Experience Manager之間的整合可讓您在Adobe Campaign電子郵件中使用Adobe Experience Manager中建立的內容。

透過此使用案例，您將學習如何在Adobe Experience Manager中建立和管理電子郵件內容，然後將這些內容匯入Adobe Campaign Standard，以用於您的行銷宣傳。

## 必要條件 {#prerequisites}

您應事先確定您有下列元素：

* Adobe Experience Manager **編寫**&#x200B;實例
* Adobe Experience Manager **publishing**&#x200B;實例
* Adobe Campaign例項

## Adobe Campaign Standard {#config-acs}中的設定

若要搭配使用這兩個解決方案，您必須將它們設定為彼此連線。
若要設定Adobe Campaign:

1. 您首先需要在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**&#x200B;下配置&#x200B;**[!UICONTROL Adobe Experience Manager instance]**&#x200B;外部帳戶。

1. 使用您的&#x200B;**[!UICONTROL Server]** URL、**[!UICONTROL Account]**&#x200B;和&#x200B;**[!UICONTROL Password]**&#x200B;設定Adobe Experience Manager輸入外部帳戶。

   ![](assets/aem_1.png)

1. 檢查&#x200B;**[!UICONTROL AEMResourceTypeFilter]**&#x200B;選項是否已正確配置。 訪問&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;菜單下的&#x200B;**[!UICONTROL Options]**&#x200B;菜單。

1. 在&#x200B;**[!UICONTROL Value (text)]**&#x200B;欄位中，檢查下列語法是否正確：

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 然後，在&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;下的進階功能表中，複製其中一個現有範本，以建立Adobe Experience Manager專用的電子郵件範本。

   ![](assets/aem_3.png)

1. 按一下&#x200B;**[!UICONTROL Edit properties]**&#x200B;表徵圖。

   ![](assets/aem_4.png)

1. 在&#x200B;**[!UICONTROL Content]**&#x200B;下拉式清單中，在&#x200B;**[!UICONTROL Content source]**&#x200B;欄位中選取&#x200B;**[!UICONTROL Adobe Experience Manager]**，然後在&#x200B;**[!UICONTROL Adobe Experience Manager account]**&#x200B;中選取您先前建立的外部帳戶。

您現在需要在Adobe Experience Manager中設定整合。

## Adobe Experience Manager {#config-aem}中的設定

若要使用Adobe Campaign Standard設定Adobe Experience Manager，您必須遵循下列步驟：

1. 您首先需要在Adobe Experience Manager編寫和發佈實例之間配置複製。 請參閱此[節](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)。

1. 然後，設定專用的&#x200B;**[!UICONTROL Cloud Service]**，將Adobe Experience Manager連接至Adobe Campaign。 請參閱此[節](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)。

1. 您現在需要在作者實例的Adobe Experience Manager中設定外部化程式。 請參閱此[節](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)。

