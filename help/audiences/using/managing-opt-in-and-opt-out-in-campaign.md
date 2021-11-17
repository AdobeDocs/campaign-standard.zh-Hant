---
title: 管理 Campaign 中的選擇加入和選擇退出
description: 了解在Adobe Campaign中管理選擇加入和選擇退出的方式。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Intermediate
exl-id: 4aeb90c5-f5b5-4cfe-93fb-2fd01fb8d70e
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---

# 管理 Campaign 中的選擇加入和選擇退出{#managing-opt-in-and-opt-out-in-campaign}

## 管理設定檔的加入和退出 {#managing-opt-in-and-opt-out-from-a-profile}

運算子可以直接從設定檔選擇加入或退出使用者 **[!UICONTROL General]** 標籤。

在 **[!UICONTROL No longer contact (on denylist)]** 區段中，選取的核取方塊對應於使用者選擇退出的通道。 根據使用者的需求選取管道。

![](assets/optin_landingpage_3.png)

## 設定選擇加入和選擇退出登錄頁面 {#setting-up-opt-in-and-opt-out-landing-pages}

若要讓使用者能夠選擇加入或選擇退出，您必須建立並發佈 **[!UICONTROL Profile acquisition]** 登陸頁面。 然後，他們就能根據需求選取管道。 請依照下列步驟以執行此操作。

您也可以設定 **[!UICONTROL Denylist]** 可讓使用者選擇退出所有傳送的登錄頁面。 有關詳細資訊，請參閱 [設定登錄頁面以選擇退出所有傳送](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>登錄頁面也可用來啟用服務訂閱。 如需詳細資訊，請參閱[此頁面](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)。

1. 建立 **[!UICONTROL Profile acquisition]** 登陸頁面(請參閱 [本節](../../channels/using/getting-started-with-landing-pages.md))。
1. 在登錄頁面內容中新增每個所需頻道的核取方塊，然後從Campaign資料庫連結至對應欄位。

   ![](assets/optin_landingpage_1.png)

1. 儲存登錄頁面並發佈。
1. 在登錄頁面中，核取方塊已根據設定檔選取 **[!UICONTROL General]** 標籤。 使用者可以視需要選擇或取消選擇管道並提交表單。

   ![](assets/optin_landingpage_2.png)

1. 提交表單後，設定檔 **[!UICONTROL General]** 標籤會根據使用者的選取項目而更新。

   ![](assets/optin_landingpage_3.png)

### 設定登錄頁面以選擇退出所有傳送 {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

若要讓使用者能夠選擇退出所有傳送，您必須建立並發佈 **[!UICONTROL Denylist]** 登陸頁面。 如需建立登錄頁面的詳細資訊，請參閱 [本頁](../../channels/using/getting-started-with-landing-pages.md).

當使用者點按登錄頁面連結後， **[!UICONTROL No longer contact (by any channel)]** 選項。

![](assets/blocklisting_allchannels.png)
