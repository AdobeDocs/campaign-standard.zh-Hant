---
title: 存取Adobe Campaign Standard與Dynamics 365自助服務應用程式整合
description: Adobe Campaign Standard與Dynamics 365自助服務應用程式整合
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 44b59f56-99be-41ae-af8d-76272bb94d18
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# 存取Adobe Campaign Standard與Microsoft Dynamics 365自助服務應用程式整合

此配置將要求您與貴組織的Experience Cloud(EC)管理員合作。 這些是提供自助服務整合應用程式介面存取權限所需的初始步驟。 存取此工具後，您將設定資料的連線，並設定Adobe Campaign與Microsoft Dynamics 365之間的資料流。

>[!NOTE]
>
>您需要聯絡您的Adobe代表，並提供Adobe Campaign Standard組織和執行個體名稱。 系統會記錄票證，要求為貴組織啟用整合應用程式。

## 新增產品設定檔

在本節中，您將學習如何授與Microsoft Dynamics 365自助應用程式的Adobe Campaign Standard整合存取權。 在Adobe Experience Cloud中擁有您組織存取權的使用者將無法存取整合自助應用程式，除非您依照下列步驟授予他們存取權。

>[!IMPORTANT]
>
> 這些步驟需要 **管理員** 角色。

1. 瀏覽至https://experience.adobe.com/並登入Adobe Experience Cloud。
1. 存取 **Admin Console**.

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. 按一下 **[!UICONTROL Products]** 存取您的Experience Cloud解決方案。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >本節中的其餘步驟將針對您的每個Campaign執行個體（開發、文字、生產）執行。

1. 按一下要設定的第一個例項。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   例項頁面應如下所示：

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. 按一下 **[!UICONTROL New Profile]** 按鈕，然後新增名為的項目： **Campaign Standard- your-prod-instance-name - D365/ACS整合**

   * 如果您在清單中看到此項目，則無需繼續。 按一下 **Adobe Campaign Standard** 在左側功能表中，並檢查其他Campaign執行個體。

   * 請務必將「your-prod-instance-name」取代為執行個體的實際名稱。

1. 您可以將 **[!UICONTROL Permission Group]** 預設值的下拉式清單。

1. 如果您的項目看起來類似下列項目，請按一下 **[!UICONTROL Done]** 按鈕。

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   已新增新產品設定檔。

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## 授予使用者存取權 {#add-users-to-profile}

從 **[!UICONTROL Products]**  頁面中，選取您的Campaign執行個體，並遵循下列步驟：

1. 按一下您先前建立的新設定檔：  **Campaign Standard- your-prod-instance-name - D365/ACS整合**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. 按一下 **[!UICONTROL Developers]** 標籤。

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. 按一下 **[!UICONTROL Add Developer]** 按鈕

1. 輸入要添加的用戶的名稱或電子郵件地址。  選擇與用戶匹配的結果。

   如果這是第一次將使用者新增至組織，請輸入詳細資訊。

1. 按一下 **[!UICONTROL Save]** 確認。
