---
title: 存取Adobe Campaign Standard與Dynamics 365自助服務應用程式的整合
description: Adobe Campaign Standard與Dynamics 365自助式應用程式整合
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
source-wordcount: '415'
ht-degree: 0%

---

# 存取Adobe Campaign Standard與Microsoft Dynamics 365自助服務應用程式的整合

此設定需要您與組織的Experience Cloud(EC)管理員合作。 這些是存取自助服務整合應用程式介面所需的初始步驟。 取得工具存取權後，即可設定資料的連線，並設定Adobe Campaign與Microsoft Dynamics 365之間的資料流程。

>[!NOTE]
>
>您需要聯絡您的Adobe代表，並提供Adobe Campaign Standard組織和執行個體名稱。 系統會記錄一個票證，要求為您的組織啟用整合應用程式。

## 新增產品設定檔

在本節中，您將瞭解如何授予Adobe Campaign Standard與Microsoft Dynamics 365自助服務應用程式整合的存取權。 在Adobe Experience Cloud中擁有貴組織存取許可權的使用者，將無法存取整合自助應用程式，除非您依照下列步驟授予他們存取許可權。

>[!IMPORTANT]
>
> 這些步驟需要 **管理員** 在您組織的Experience Cloud中的角色。
>

1. 瀏覽至https://experience.adobe.com/並登入Adobe Experience Cloud。
1. 存取 **Admin Console**.

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. 按一下 **[!UICONTROL Products]** 以存取您的Experience Cloud解決方案。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >本節中的其餘步驟將會針對您的每個Campaign執行個體（開發、文字、生產）執行。
   >

1. 按一下要設定的第一個執行個體。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   執行個體頁面看起來應該像這樣：

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. 按一下 **[!UICONTROL New Profile]** 按鈕並新增以下名稱的專案： **Campaign Standard- your-prod-instance-name - D365/ACS整合**

   * 如果您在清單中看到此專案，則不需要繼續。 按一下 **Adobe Campaign Standard** ，並檢查其他Campaign執行個體。

   * 請務必將「your-prod-instance-name」取代為您的例項的實際名稱。

1. 您可以離開 **[!UICONTROL Permission Group]** 具有預設值的下拉式清單。

1. 如果您的專案看起來類似下列，請按一下 **[!UICONTROL Done]** 按鈕。

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   已新增新的產品設定檔。

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## 授予使用者存取許可權 {#add-users-to-profile}

從 **[!UICONTROL Products]**  請選取您的Campaign執行個體，然後遵循下列步驟：

1. 按一下您先前建立的新設定檔：  **Campaign Standard- your-prod-instance-name - D365/ACS整合**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. 按一下 **[!UICONTROL Developers]** 標籤。

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. 按一下 **[!UICONTROL Add Developer]** 按鈕

1. 輸入要新增的使用者名稱或電子郵件地址。  選取符合使用者的結果。

   如果這是第一次將使用者新增至組織，請輸入詳細資料。

1. 按一下 **[!UICONTROL Save]** 確認。
