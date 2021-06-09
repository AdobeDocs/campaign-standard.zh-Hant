---
solution: Campaign Standard
product: campaign
title: 體驗資料模型概觀
description: Experience Data Model(XDM)是一組標準資料結構，可將資料擷取至其中，以便與Adobe Experience Platform解決方案和產品搭配使用。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM整合
role: Data Architect
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# 體驗資料模型概述{#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上托管（目前測試版僅供北美使用），才能存取這些功能。 如果您想要存取權限，請聯絡Adobe客戶服務。

Experience Data Model(XDM)是一組標準資料結構，可將資料擷取至其中，以便與Adobe Experience Platform解決方案和產品搭配使用。

您可透過專用的API或XDM使用者介面，建立及管理XDM結構描述。

## XDM工作區{#xdm-workspace}

XDM工作區可讓您檢視、建立和擴充資料結構。

若要存取XDM使用者介面，請開啟Adobe Experience Platform。 導覽至「資料模型」視窗，以建立或擴充XDM架構。

請參閱完整的[XDM工作區檔案](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

您可以透過XDM結構API執行下列動作：

* 檢視現有結構的清單
* 查看特定架構擴展現有架構
* 新增欄位至擴充功能
* 建立和更新新結構
* 查看架構描述符
* 建立、更新和刪除架構描述符

所有處理API呼叫的詳細資訊都可在[開發人員指南](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)中取得。
