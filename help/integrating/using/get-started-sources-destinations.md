---
title: 開始使用來源和目標
description: 進一步瞭解Adobe Experience Platform來源和目標。
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

透過Adobe Experience Platform，您可以在Campaign Standard和Adobe Real-time Customer Data Platform (RTCDP)之間共用資料。 這可讓您在行銷活動工作流程中鎖定Adobe Experience Platform對象，然後傳回Adobe Real-time Customer Data Platform中與這些對象相關的資料，例如傳送、開啟和點按。

* 替換為 **目的地**，將對象從Adobe Experience Platform擷取至Campaign Standard。 這可讓您針對行銷活動啟用已知和未知的資料。
* 替換為 **來源**，將Campaign Standard資料（例如傳送、開啟、點按）匯出至Adobe Experience Platform。 這可讓您將從不同來源收集到的資料集中到單一位置，並使用從中獲得的見解做更多事情。


>[!IMPORTANT]
>
>在執行此整合時，請記住Adobe Campaign合約規定的SFTP儲存空間限制、資料庫儲存空間限制和作用中設定檔限制。

如需Adobe Real-time Customer Data Platform、目的地和來源的詳細總覽，請參閱以下頁面：

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant)
* [目的地文件](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=zh-Hant)
* [來源文件](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant)

## 將Campaign Standard與Adobe Experience Platform連線

為了能夠在Adobe Experience Platform和Campaign Standard之間共用資料，您首先需要將Adobe Campaign as a **目的地**，並連線您的AWS S3或Azure Blob儲存位置，做為 **來源** 在Adobe Experience Platform中。

在設定聯結器後，您可以使用工作流程設定資料匯入或匯出至Campaign Standard。

![](assets/rtcdp-schema.png)

如需如何設定這些匯入和匯出程式的詳細資訊，請參閱以下章節：

* [將 Adobe Experience Platform 對象內嵌至 Campaign](../../integrating/using/ingest-aep-data.md)
* [將資料從 Campaign 匯出至 Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
