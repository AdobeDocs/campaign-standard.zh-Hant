---
title: Experience資料模型概觀
description: Experience Data Model (XDM)是一組標準資料結構描述，其中的資料可能會內嵌以搭配Adobe Experience Platform解決方案和產品使用。
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

# Experience資料模型概觀 {#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前為測試版，可能會經常更新，恕不另行通知。 客戶需在Azure上代管（目前僅限北美地區使用Beta版）才能存取這些功能。 如果您想要存取許可權，請聯絡Adobe客戶服務。

Experience Data Model (XDM)是一組標準資料結構描述，其中的資料可能會內嵌以搭配Adobe Experience Platform解決方案和產品使用。

XDM結構描述的建立和管理可透過專用的API或XDM使用者介面使用。

## XDM工作區 {#xdm-workspace}

XDM工作區可讓您檢視、建立和擴充資料結構。

若要存取XDM使用者介面，請開啟Adobe Experience Platform。 導覽至「資料模型」視窗，以建立或擴充XDM架構。

請參閱完整檔案 [XDM工作區檔案](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

您可以透過XDM結構描述API執行下列動作：

* 檢視現有方案清單
* 檢視特定綱要擴充現有綱要
* 新增欄位至擴充功能
* 建立和更新新結構描述
* 檢視結構描述元
* 建立、更新和刪除結構描述元

操縱API呼叫的所有詳細資訊可在以下網址取得： [開發人員指南](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).
