---
title: 體驗資料模型概觀
description: Experience Data Model(XDM)是一組標準的資料結構，可將資料擷取到其中，以便與Adobe Experience platform解決方案和產品搭配使用。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5f3bf4c2d0bba095182194ac28b3107eae2c54a6

---


# 體驗資料模型概觀 {#experience-data-model-overview}

>[!IMPORTANT]
>
>促銷活動標準資料服務目前處於測試階段，可能會在不另行通知的情況下頻繁更新。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

Experience Data Model(XDM)是一組標準的資料結構，可將資料擷取到其中，以便與Adobe Experience platform解決方案和產品搭配使用。

XDM架構的建立和管理可通過專用的API或XDM用戶介面獲得。

## XDM工作區(#xdm-workspace)

XDM工作區可讓您檢視、建立和擴充資料結構。

若要存取XDM使用者介面，請開啟Adobe Experience Platform。 導航到「資料模型」窗口以建立或擴展XDM架構。

請參閱完整的 [XDM工作區檔案](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/xdm_system/xdm_system_in_experience_platform.md)。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

您可以透過XDM架構API執行下列動作：

* 查看現有方案的清單
* 查看特定方案擴展現有方案
* 新增欄位至擴充功能
* 建立和更新新架構
* 查看模式描述符
* 建立、更新和刪除模式描述符

「開發人員指南」中提供所有控制API呼叫的 [詳細資訊](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/schema_registry_developer_guide.md)。
