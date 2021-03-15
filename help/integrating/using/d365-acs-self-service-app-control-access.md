---
title: 存取Adobe Campaign Standard與Dynamics 365自助服務應用程式整合
description: Adobe Campaign Standard與Dynamics 365自助服務應用程式整合
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM整合
role: 資料架構師
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---


# 存取Adobe Campaign Standard與Microsoft Dynamics 365自助服務應用程式整合

此配置將要求您與Experience Cloud(EC)管理員一起為您的組織工作。 這些是提供您存取自助服務整合應用程式介面的初始步驟。 在您存取該工具後，將設定與資料的連線，並設定Adobe Campaign與Microsoft Dynamics 365之間的資料流。

>[!NOTE]
>
>您需要聯繫您的Adobe代表並提供Adobe Campaign Standard組織和實例名稱。 系統會記錄票證，以要求為您的組織啟用整合應用程式。

## 新增產品設定檔

在本節中，您將學習如何授與Microsoft Dynamics 365自助服務應用程式的Adobe Campaign Standard整合存取權。 擁有Adobe Experience Cloud組織存取權的使用者將無法存取整合自助服務應用程式，除非您依照下列步驟授與他們存取權。

>[!IMPORTANT]
>
> 這些步驟要求在組織的Experience Cloud中&#x200B;**管理員**&#x200B;角色。


1. 瀏覽至https://experience.adobe.com/並登入Adobe Experience Cloud。
1. 訪問&#x200B;**Admin Console**。

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. 按一下&#x200B;**[!UICONTROL Products]**&#x200B;存取您的Experience Cloud解決方案。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >本節中的其餘步驟將針對您的每個促銷活動例項（開發、文字、生產）執行。

1. 按一下要設定的第一個例項。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   例項頁面應如下所示：

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. 按一下&#x200B;**[!UICONTROL New Profile]**&#x200B;按鈕並添加一個名為：**Campaign Standard- your-prod-instance-name - D365/ACS Integration**

   * 如果您在清單中看到此項目，則不需要繼續。 按一下左側功能表中的&#x200B;**Adobe Campaign Standard**，並檢查其他促銷活動例項。

   * 請務必將「your-prod-instance-name」取代為實例的實際名稱。

1. 您可以保留&#x200B;**[!UICONTROL Permission Group]**&#x200B;下拉式清單中的預設值。

1. 如果您的項目看起來類似下列，請按一下&#x200B;**[!UICONTROL Done]**&#x200B;按鈕。

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   已新增產品設定檔。

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## 授予用戶{#add-users-to-profile}訪問權限

從&#x200B;**[!UICONTROL Products]**&#x200B;頁面中，選取您的促銷活動例項，並遵循下列步驟：

1. 按一下您先前建立的新描述檔： **Campaign Standard- your-prod-instance-name - D365/ACS Integration**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. 按一下&#x200B;**[!UICONTROL Developers]**&#x200B;頁籤。

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. 按一下&#x200B;**[!UICONTROL Add Developer]**&#x200B;按鈕

1. 輸入您要新增之使用者的名稱或電子郵件地址。  選擇與用戶匹配的結果。

   如果這是用戶首次被添加到組織中，請輸入詳細資訊。

1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;進行確認。
