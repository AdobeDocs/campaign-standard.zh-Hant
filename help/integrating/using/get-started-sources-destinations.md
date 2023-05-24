---
title: 開始使用來源和目標
description: 瞭解有關Adobe Experience Platform源和目的地的詳細資訊。
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

## 關於源和目標

使用Adobe Experience Platform，您可以在Campaign Standard和Adobe Real-time Customer Data Platform(RTCDP)之間共用資料。 這樣，您就可以在活動工作流中將Adobe Experience Platform受眾作為目標，然後將與這些受眾相關的資料發回Adobe Real-time Customer Data Platform，如發送、開啟和按一下。

* 與 **目標**&#x200B;把Adobe Experience Platform的觀眾吸引到Campaign Standard。 這樣，您就可以激活市場營銷活動的已知和未知資料。
* 與 **源**，將Campaign Standard資料（如發送、開啟、按一下）導出到Adobe Experience Platform。 這允許您將從不同來源收集的資料集中到一個位置，並利用從中獲得的洞察力做更多工作。


>[!IMPORTANT]
>
>執行此整合時，請根據您的Adobe Campaign合同，記住SFTP儲存限制、資料庫儲存限制和活動配置檔案限制。

有關Adobe Real-time Customer Data Platform、目標和來源的更詳細概述，請參閱以下頁：

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant)
* [目的地文件](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=zh-Hant)
* [來源文件](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant)

## 連接Campaign Standard與Adobe Experience Platform

要在Adobe Experience Platform和Campaign Standard之間共用資料，您首先需要將Adobe Campaign連接為 **目標**，並將你的AWSS3或Azure Blob儲存位置連接為 **源** Adobe體驗平台。

配置連接器後，可以使用工作流設定資料導入或導出到Campaign Standard。

![](assets/rtcdp-schema.png)

有關如何設定這些導入和導出流程的詳細資訊，請參閱以下各節：

* [將 Adobe Experience Platform 對象內嵌至 Campaign](../../integrating/using/ingest-aep-data.md)
* [將資料從 Campaign 匯出至 Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
