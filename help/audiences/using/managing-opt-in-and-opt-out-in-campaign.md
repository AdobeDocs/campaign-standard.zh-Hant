---
solution: Campaign Standard
product: campaign
title: 管理 Campaign 中的選擇加入和選擇退出
description: 了解在Adobe Campaign中管理選擇加入和選擇退出的方式。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: 對象
role: User
level: Intermediate
exl-id: 4aeb90c5-f5b5-4cfe-93fb-2fd01fb8d70e
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 9%

---

# 管理 Campaign 中的選擇加入和選擇退出{#managing-opt-in-and-opt-out-in-campaign}

## 管理設定檔的加入和退出 {#managing-opt-in-and-opt-out-from-a-profile}

操作員可以直接從配置檔案&#x200B;**[!UICONTROL General]**&#x200B;頁簽選擇或退出用戶。

在&#x200B;**[!UICONTROL No longer contact (on denylist)]**&#x200B;區段中，選取的核取方塊對應於使用者選擇退出的通道。 根據使用者的需求選取管道。

![](assets/optin_landingpage_3.png)

## 設定選擇加入和選擇退出登錄頁面 {#setting-up-opt-in-and-opt-out-landing-pages}

若要讓使用者能夠選擇加入或選擇退出，您必須建立並發佈&#x200B;**[!UICONTROL Profile acquisition]**&#x200B;登錄頁面。 然後，他們就能根據需求選取管道。 請依照下列步驟以執行此操作。

您也可以設定&#x200B;**[!UICONTROL Denylist]**&#x200B;登錄頁面，讓使用者能夠選擇退出所有傳送。 如需詳細資訊，請參閱[設定登錄頁面以選擇退出所有傳送](#setting-up-a-landing-page-to-opt-out-from-all-deliveries)。

>[!NOTE]
>
>登錄頁面也可用於啟用服務訂閱。 如需詳細資訊，請參閱[此頁面](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)。

1. 建立&#x200B;**[!UICONTROL Profile acquisition]**&#x200B;登錄頁面（請參閱[此區段](../../channels/using/getting-started-with-landing-pages.md)）。
1. 在登錄頁面內容中新增每個所需頻道的核取方塊，然後從Campaign資料庫連結至對應欄位。

   ![](assets/optin_landingpage_1.png)

1. 儲存登錄頁面並發佈。
1. 在登錄頁面中，已根據設定檔&#x200B;**[!UICONTROL General]**&#x200B;標籤選取核取方塊。 用戶可以根據自己的需要選擇或取消選擇渠道並提交表格。

   ![](assets/optin_landingpage_2.png)

1. 提交表單後，會根據使用者的選擇更新設定檔&#x200B;**[!UICONTROL General]**&#x200B;標籤。

   ![](assets/optin_landingpage_3.png)

### 設定登錄頁面以選擇退出所有傳送 {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

若要讓使用者能夠選擇退出所有傳送，您必須建立並發佈&#x200B;**[!UICONTROL Denylist]**&#x200B;登錄頁面。 如需建立登錄頁面的詳細資訊，請參閱[此頁面](../../channels/using/getting-started-with-landing-pages.md)。

一旦使用者點按登錄頁面連結，即會自動選取設定檔中的&#x200B;**[!UICONTROL No longer contact (by any channel)]**&#x200B;選項。

![](assets/blocklisting_allchannels.png)
