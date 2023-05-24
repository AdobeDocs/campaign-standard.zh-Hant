---
title: 設定 Campaign-Experience Manager 整合
description: 通過Adobe Experience Manager整合，您可以直接在中創AEM建內容，稍後在Adobe Campaign使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 6%

---

# 設定 Campaign-Experience Manager 整合 {#configuration-aem}

Adobe Campaign Standard和Adobe Experience Manager之間的這種整合允許您在您的Adobe Campaign電子郵件中使用在Adobe Experience Manager建立的內容。

使用此使用案例，您將學習如何在Adobe Experience Manager建立和管理電子郵件內容，然後將這些內容導入您的電子郵件中以用於您的市場營銷活動。

## 必要條件 {#prerequisites}

您應確保事先具有以下元素：

* 安Adobe Experience Manager **創作** 實例
* 安Adobe Experience Manager **發佈** 實例
* Adobe Campaign案

## Adobe Campaign Standard配置 {#config-acs}

要將這兩個解決方案結合使用，必須將它們配置為彼此連接。
配置Adobe Campaign:

1. 您首先需要配置 **[!UICONTROL Adobe Experience Manager instance]** 外部帳戶 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**。

1. 配置Adobe Experience Manager類型的外部帳戶 **[!UICONTROL Server]** URL, **[!UICONTROL Account]** 和 **[!UICONTROL Password]**。

   ![](assets/aem_1.png)

1. 檢查 **[!UICONTROL AEMResourceTypeFilter]** 已正確配置選項。 訪問 **[!UICONTROL Options]** 菜單 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 的子菜單。

1. 在 **[!UICONTROL Value (text)]** 欄位，檢查以下語法是否正確：

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 然後，在「高級」菜單中， **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**，複製現有模板之一以建立特定於Adobe Experience Manager的電子郵件模板。

   ![](assets/aem_3.png)

1. 按一下 **[!UICONTROL Edit properties]** 表徵圖

   ![](assets/aem_4.png)

1. 在 **[!UICONTROL Content]** 下拉，選擇 **[!UICONTROL Adobe Experience Manager]** 的 **[!UICONTROL Content source]** 欄位，然後在 **[!UICONTROL Adobe Experience Manager account]**。

您現在需要配置Adobe Experience Manager的整合。

## Adobe Experience Manager配置 {#config-aem}

要將Adobe Experience Manager配置為Adobe Campaign Standard，必須執行以下步驟：

1. 您首先需要配置Adobe Experience Manager創作實例和發佈實例之間的複製。 請參閱本[章節](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)。

1. 然後，通過配置專用 **[!UICONTROL Cloud Service]**。 請參閱本[章節](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)。

1. 現在，您需要在作者實例上配置Adobe Experience Manager中的外部化程式。 請參閱本[章節](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)。
