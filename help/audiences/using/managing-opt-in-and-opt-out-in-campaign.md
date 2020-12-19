---
solution: Campaign Standard
product: campaign
title: 管理 Campaign 中的加入和退出
description: 瞭解Adobe Campaign中如何管理選擇加入和選擇退出。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---


# 管理 Campaign 中的加入和退出{#managing-opt-in-and-opt-out-in-campaign}

## 管理描述檔{#managing-opt-in-and-opt-out-from-a-profile}中的選擇加入和選擇退出

運算子可直接從描述檔&#x200B;**[!UICONTROL General]**&#x200B;標籤中選擇使用者或退出使用者。

在&#x200B;**[!UICONTROL No longer contact (on denylist)]**&#x200B;區段中，選取的核取方塊對應使用者選擇退出的頻道。 根據使用者需求選擇頻道。

![](assets/optin_landingpage_3.png)

## 設定選擇加入和選擇退出登陸頁面{#setting-up-opt-in-and-opt-out-landing-pages}

若要讓使用者能夠選擇加入或選擇退出，您必須建立並發佈&#x200B;**[!UICONTROL Profile acquisition]**&#x200B;登陸頁面。 然後他們就可以根據自己的需求來選擇頻道。 請依照下列步驟以執行此操作。

您也可以設定&#x200B;**[!UICONTROL Denylist]**&#x200B;著陸頁面，讓使用者可選擇退出所有傳送。 如需詳細資訊，請參閱[設定著陸頁面以選擇退出所有傳送](#setting-up-a-landing-page-to-opt-out-from-all-deliveries)。

>[!NOTE]
>
>著陸頁面也可用來啟用服務訂閱。 有關詳細資訊，請參見[此頁面](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)。

1. 建立&#x200B;**[!UICONTROL Profile acquisition]**&#x200B;著陸頁面（請參閱[本節](../../channels/using/getting-started-with-landing-pages.md)）。
1. 在著陸頁面內容中新增每個所需渠道的核取方塊，然後將其連結至「促銷活動」資料庫的對應欄位。

   ![](assets/optin_landingpage_1.png)

1. 儲存著陸頁面並發佈。
1. 在著陸頁面中，已根據描述檔&#x200B;**[!UICONTROL General]**&#x200B;標籤選取核取方塊。 用戶可以根據自己的需要選擇或取消選擇渠道並提交表單。

   ![](assets/optin_landingpage_2.png)

1. 提交表單後，會根據使用者的選擇更新描述檔&#x200B;**[!UICONTROL General]**&#x200B;標籤。

   ![](assets/optin_landingpage_3.png)

### 設定著陸頁面以選擇退出所有傳送{#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

若要讓使用者能夠選擇退出所有傳送，您必須建立並發佈&#x200B;**[!UICONTROL Denylist]**&#x200B;登陸頁面。 如需建立著陸頁面的詳細資訊，請參閱[本頁](../../channels/using/getting-started-with-landing-pages.md)。

當使用者按一下著陸頁面連結後，會自動選取描述檔中的&#x200B;**[!UICONTROL No longer contact (by any channel)]**&#x200B;選項。

![](assets/blocklisting_allchannels.png)

