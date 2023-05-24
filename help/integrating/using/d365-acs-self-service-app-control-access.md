---
title: 訪問與Dynamics 365自助服務應用的Adobe Campaign Standard整合
description: Adobe Campaign Standard與Dynamics 365自助應用整合
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

# 訪問Adobe Campaign Standard與MicrosoftDynamics 365自助服務應用的整合

此配置將要求您為您的組織與Experience Cloud(EC)管理員協作。 這些是授予您訪問自助服務整合應用程式介面所需的初始步驟。 訪問該工具後，您將設定到資料的連接，並配置Adobe Campaign和MicrosoftDynamics 365之間的資料流。

>[!NOTE]
>
>您需要聯繫您的Adobe代表並提供Adobe Campaign Standard組織和實例名稱。 將記錄票證，以請求為您的組織啟用整合應用。

## 添加產品配置檔案

在本節中，您將學習如何授予與MicrosoftDynamics 365自助服務應用的Adobe Campaign Standard整合的訪問權限。 對您在Adobe Experience Cloud的組織具有訪問權限的用戶將無權訪問整合自助應用程式，除非您按照以下步驟授予他們訪問權限。

>[!IMPORTANT]
>
> 這些步驟需要 **管理員** 在您組織的Experience Cloud中的角色。

1. 瀏覽https://experience.adobe.com/並登錄Adobe Experience Cloud。
1. 訪問 **Admin Console**。

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. 按一下 **[!UICONTROL Products]** 訪問您的Experience Cloud解決方案。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >本節中的其餘步驟將針對您的每個市場活動實例（開發、文本、生產）執行。

1. 按一下要配置的第一個實例。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   實例頁應如下所示：

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. 按一下 **[!UICONTROL New Profile]** 按鈕，然後添加名為： **Campaign Standard — 您的生產實例名稱 — D365/ACS整合**

   * 如果在清單中看到此條目，則無需繼續。 按一下 **Adobe Campaign Standard** 框中，並選中其他「市場活動」實例。

   * 確保用實例的實際名稱替換「您的prod-instance-name」。

1. 你可以離開 **[!UICONTROL Permission Group]** 下拉框。

1. 如果您的條目看起來與以下內容類似，則按一下 **[!UICONTROL Done]** 按鈕

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   已添加新產品配置檔案。

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## 授予用戶訪問權限 {#add-users-to-profile}

從 **[!UICONTROL Products]**  頁，選擇「促銷活動」實例，然後執行以下步驟：

1. 按一下您先前建立的新配置檔案：  **Campaign Standard — 您的生產實例名稱 — D365/ACS整合**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. 按一下 **[!UICONTROL Developers]** 頁籤。

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. 按一下 **[!UICONTROL Add Developer]** 按鈕

1. 輸入要添加的用戶的名稱或電子郵件地址。  選擇與用戶匹配的結果。

   如果這是用戶首次添加到組織，請輸入詳細資訊。

1. 按一下 **[!UICONTROL Save]** 確認。
