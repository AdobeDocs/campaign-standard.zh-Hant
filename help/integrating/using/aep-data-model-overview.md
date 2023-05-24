---
title: 體驗資料模型概述
description: 經驗資料模型(XDM)是一組標準的資料架構，可以將資料導入其中，以便與Adobe Experience Platform解決方案和產品配合使用。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# 體驗資料模型概述 {#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform資料連接器目前處於測試版，可能需要頻繁更新，恕不另行通知。 客戶需要在Azure上托管（目前僅在北美試用版）才能訪問這些功能。 如果您想訪問，請聯繫Adobe客戶服務。

經驗資料模型(XDM)是一組標準的資料架構，可以將資料導入其中，以便與Adobe Experience Platform解決方案和產品配合使用。

XDM模式的建立和管理可通過專用API或XDM用戶介面進行。

## XDM工作區 {#xdm-workspace}

XDM Workspace提供了查看、建立和擴展資料架構的功能。

要訪問XDM用戶介面，請開啟Adobe Experience Platform。 導航到「資料模型」窗口以建立或擴展XDM方案。

查閱完整 [XDM工作區文檔](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

可以通過XDM架構API執行以下操作：

* 查看現有架構的清單
* 查看特定架構擴展現有架構
* 將欄位添加到擴展
* 建立和更新新架構
* 查看架構描述符
* 建立、更新和刪除架構描述符

可在中找到處理API調用的所有詳細資訊 [開發人員指南](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)。
