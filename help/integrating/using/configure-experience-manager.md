---
title: 設定 Campaign-Experience Manager 整合
description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%

---

# 設定 Campaign-Experience Manager 整合 {#configuration-aem}

Adobe Campaign Standard與Adobe Experience Manager之間的這項整合可讓您在Adobe Campaign電子郵件中使用Adobe Experience Manager中建立的內容。

透過此使用案例，您將瞭解如何在Adobe Experience Manager中建立和管理電子郵件內容，然後將其匯入Adobe Campaign Standard，用於行銷活動。

## 先決條件 {#prerequisites}

您應確定您預先擁有下列元素：

* 一個Adobe Experience Manager **製作** 例項
* 一個Adobe Experience Manager **發佈** 例項
* Adobe Campaign執行個體

## Adobe Campaign Standard中的設定 {#config-acs}

若要同時使用這兩個解決方案，您必須將其設定為彼此連線。
若要設定Adobe Campaign：

1. 您首先需要設定 **[!UICONTROL Adobe Experience Manager instance]** 外部帳戶在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. 使用設定Adobe Experience Manager型別外部帳戶 **[!UICONTROL Server]** URL， **[!UICONTROL Account]** 和 **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. 檢查 **[!UICONTROL AEMResourceTypeFilter]** 選項已正確設定。 存取 **[!UICONTROL Options]** 下的選單 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 功能表。

1. 在 **[!UICONTROL Value (text)]** 欄位，檢查下列語法是否正確：

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 然後，在進階功能表的 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**，複製其中一個現有範本以建立Adobe Experience Manager專屬的電子郵件範本。

   ![](assets/aem_3.png)

1. 按一下 **[!UICONTROL Edit properties]** 圖示。

   ![](assets/aem_4.png)

1. 在 **[!UICONTROL Content]** 下拉式清單，選取 **[!UICONTROL Adobe Experience Manager]** 在 **[!UICONTROL Content source]** 欄位中輸入先前建立的外部帳戶 **[!UICONTROL Adobe Experience Manager account]**.

您現在需要在Adobe Experience Manager中設定整合。

## Adobe Experience Manager中的設定 {#config-aem}

若要使用Adobe Campaign Standard設定Adobe Experience Manager，您必須遵循下列步驟：

1. 您首先需要設定Adobe Experience Manager編寫和發佈執行個體之間的復寫。 請參閱本[章節](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)。

1. Adobe Experience Manager Adobe Campaign然後，透過設定專用的 **[!UICONTROL Cloud Service]**. 請參閱本[章節](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)。

1. 您現在需要在編寫執行個體上設定Adobe Experience Manager中的外部化程式。 請參閱本[章節](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)。
