---
title: 管理 Campaign 中的選擇加入和選擇退出
description: 瞭解如何在Adobe Campaign管理選擇加入和退出。
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

## 管理配置檔案中的選擇加入和選擇退出 {#managing-opt-in-and-opt-out-from-a-profile}

操作員可以直接從配置檔案選擇用戶進出 **[!UICONTROL General]** 頁籤。

在 **[!UICONTROL No longer contact (on denylist)]** 部分，選中的複選框對應於用戶選擇退出的頻道。 根據用戶的需要選擇頻道。

![](assets/optin_landingpage_3.png)

## 設定選擇加入和選擇退出登錄頁 {#setting-up-opt-in-and-opt-out-landing-pages}

要讓用戶能夠選擇加入或退出，您必須建立並發佈 **[!UICONTROL Profile acquisition]** 登錄頁。 然後他們就可以根據自己的需要來選擇頻道。 請依照下列步驟以執行此操作。

也可以設定 **[!UICONTROL Denylist]** 登錄頁，使用戶能夠選擇退出所有交貨。 有關此內容的詳細資訊，請參閱 [設定登錄頁以選擇退出所有交貨](#setting-up-a-landing-page-to-opt-out-from-all-deliveries)。

>[!NOTE]
>
>登錄頁也可用於啟用服務訂閱。 如需詳細資訊，請參閱[此頁面](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)。

1. 建立 **[!UICONTROL Profile acquisition]** 登錄頁（請參見） [此部分](../../channels/using/getting-started-with-landing-pages.md))。
1. 在登錄頁內容中為每個所需渠道添加一個複選框，然後將其連結到市場活動資料庫中的相應欄位。

   ![](assets/optin_landingpage_1.png)

1. 保存登錄頁並發佈。
1. 在登錄頁中，已根據配置檔案選中複選框 **[!UICONTROL General]** 頁籤。 用戶可以根據需要選擇或取消選擇頻道並提交表格。

   ![](assets/optin_landingpage_2.png)

1. 提交表單後，配置檔案 **[!UICONTROL General]** 頁籤

   ![](assets/optin_landingpage_3.png)

### 設定登錄頁以選擇退出所有交貨 {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

要讓用戶能夠選擇退出所有交貨，您必須建立並發佈 **[!UICONTROL Denylist]** 登錄頁。 有關登錄頁建立的詳細資訊，請參閱 [此頁](../../channels/using/getting-started-with-landing-pages.md)。

用戶按一下登錄頁連結後， **[!UICONTROL No longer contact (by any channel)]** 的子菜單。

![](assets/blocklisting_allchannels.png)
