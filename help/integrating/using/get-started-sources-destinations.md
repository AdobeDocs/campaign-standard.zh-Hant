---
title: 開始使用來源和目標
description: 進一步了解Adobe Experience Platform來源和目的地。
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 17%

---

# 開始使用來源和目標 {#rtcdp}

## 關於來源和目的地

透過Adobe Experience Platform，您可以在Campaign Standard和Adobe Real-time Customer Data Platform(RTCDP)之間共用資料。 這可讓您在促銷活動工作流程中鎖定Adobe Experience Platform對象，然後傳回與這些對象相關的Adobe Real-time Customer Data Platform資料，例如傳送、開啟和點按。

* 使用 **目的地**，將對象從Adobe Experience Platform擷取至Campaign Standard。 這可讓您為行銷活動啟用已知和未知的資料。
* 使用 **來源**，將Campaign Standard資料（例如傳送、開啟、點按）匯出至Adobe Experience Platform。 這可讓您將從不同來源收集的資料集中到單一位置，並利用從中獲得的分析功能完成更多工作。


>[!IMPORTANT]
>
>執行此整合時，請記得您的Adobe Campaign合約所規定的SFTP儲存限制、資料庫儲存限制和作用中設定檔限制。

如需Adobe Real-time Customer Data Platform、目的地和來源的更詳細概覽，請參閱下列頁面：

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant)
* [目的地文件](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=zh-Hant)
* [來源文件](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant)

## 連線Campaign Standard與Adobe Experience Platform

若要在Adobe Experience Platform和Campaign Standard之間共用資料，您必須先將Adobe Campaign連線為 **目的地**，並將您的AWS S3或Azure Blob儲存位置連結為 **來源** Adobe體驗平台。

在設定連接器後，您可以使用工作流程來設定資料匯入或匯出至Campaign Standard。

![](assets/rtcdp-schema.png)

有關如何設定這些匯入和匯出程式的詳細資訊，請參閱以下章節：

* [將 Adobe Experience Platform 對象內嵌至 Campaign](../../integrating/using/ingest-aep-data.md)
* [將資料從 Campaign 匯出至 Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
