---
solution: Campaign Standard
product: campaign
title: '"步驟 2：發佈擴充"'
description: 了解如何以Campaign Standard發佈擴充功能。 系列第2部分。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: 資料模型
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
source-git-commit: d3482dfad245807aedee6deb36fd67e43c7a66b9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 23%

---

# 步驟 2：發佈擴充{#step-publish-the-extension}

1. 從進階功能表，透過 Adobe Campaign 標誌，依序選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** 及 **[!UICONTROL Publication]**。
1. 按一下 **[!UICONTROL Prepare Publication]** 按鈕。
1. 選擇&#x200B;**[!UICONTROL Create the Profiles & Services Ext API]**&#x200B;選項。

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >如果API已發佈（亦即，您已針對此資源或其他資源核取此選項一次），則會強制進行API更新。

1. 按一下&#x200B;**[!UICONTROL Profiles & Services API Preview]**&#x200B;標籤。

   這將顯示API發佈將套用至目前版本的profilesAndServicesExt API的變更。

   此處為「促銷代碼」欄位(ID:cusBrand)插入API中。

   ![](assets/extendpandsapi_diff.png)

1. 按一下 **[!UICONTROL Publish]** 按鈕。
