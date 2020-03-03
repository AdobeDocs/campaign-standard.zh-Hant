---
title: 設定Campaign-Experience manager整合
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
source-git-commit: 37b1c17234a300b092db3c810a32de3600bb8f2f

---


# 設定Campaign-Experience manager整合 {#configuration-aem}

Adobe Campaign standard與Adobe Experience manager的整合可讓您在Adobe Campaign電子郵件中使用在Adobe Experience manager中建立的內容。

透過此使用案例，您將學習如何在Adobe Experience Manager中建立和管理電子郵件內容，然後將這些內容匯入Adobe Campaign Standard，以用於您的行銷宣傳。

## 必要條件 {#prerequisites}

您應事先確定您有下列元素：

* Adobe Experience Manager製作 **實例**
* Adobe Experience Manager發佈 **實例**
* Adobe Campaign例項

## Adobe Campaign standard中的設定 {#config-acs}

若要搭配使用這兩個解決方案，您必須將它們設定為彼此連線。
若要設定Adobe Campaign:

1. 您必須先在> **[!UICONTROL Adobe Experience Manager instance]** >下設定外部帳戶 **[!UICONTROL Administration]****[!UICONTROL Application settings]****[!UICONTROL External accounts menu]**。

1. 使用您的 **[!UICONTROL Server]** URL設定Adobe Experience Manager輸入外部帳戶 **[!UICONTROL Account]** 和 **[!UICONTROL Password]**。

   ![](assets/aem_1.png)

1. 檢查選項 **[!UICONTROL AEMResourceTypeFilter]** 是否已正確配置。 存取「 > **[!UICONTROL Options]** > >功能表 **[!UICONTROL Administration]** 」 **[!UICONTROL Application settings]** 下的功 **[!UICONTROL Options]** 能表。

1. 在欄位 **[!UICONTROL Value (text)]** 中，檢查下列語法是否正確：

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 然後，在「 > > **[!UICONTROL Resources]** > **[!UICONTROL Templates]****[!UICONTROL Delivery templates]**」下的進階功能表中，複製其中一個現有範本，以建立Adobe Experience Manager專用的電子郵件範本。

   ![](assets/aem_3.png)

1. 按一下 **[!UICONTROL Edit properties]** 圖示。

   ![](assets/aem_4.png)

1. 在下拉 **[!UICONTROL Content]** 式清單下，選取欄 **[!UICONTROL Adobe Experience Manager]** 位中的 **[!UICONTROL Content source]** ，然後在中選取您先前建立的外部帳戶 **[!UICONTROL Adobe Experience Manager account]**。

您現在需要在Adobe Experience manager中設定整合。

## Adobe Experience manager中的設定 {#config-aem}

若要使用Adobe Campaign standard設定Adobe Experience Manager，您必須遵循下列步驟：

1. 您首先需要在Adobe Experience Manager編寫和發佈實例之間配置複製。 請參閱本 [節](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)。

1. 然後，設定專屬的Adobe Experience manager與Adobe Campaign連接 **[!UICONTROL Cloud Service]**。 請參閱本 [節](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)。

1. 您現在需要在作者實例的Adobe Experience manager中設定外部化程式。 請參閱本 [節](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)。

