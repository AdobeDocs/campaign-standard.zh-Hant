---
title: 將 Adobe Experience Platform 對象內嵌至 Campaign
description: 學習如何吸引Adobe Experience Platform觀眾加入Campaign Standard。
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 7%

---

# 將 Adobe Experience Platform 對象內嵌至 Campaign {#destinations}

要將Adobe Experience Platform受眾吸引到活動中並在您的工作流中使用，您首先需要將Adobe Campaign作為Adobe Experience Platform **目標** 並配置要導出的段。

配置目標後，資料將導出到您的儲存位置，您需要構建一個專用的工作流來Campaign Standard接收它。

## 將Adobe Campaign連接為目標

在Adobe Experience平台中，通過為導出的段選擇儲存位置來配置與Adobe Campaign的連接。 此步驟還允許您選擇要導出的段並指定要包括的附加XDM欄位。

有關詳細資訊，請參閱 [目標文檔](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html)。

配置目標後，Adobe Experience Platform會在您提供的儲存位置建立一個制表符分隔的.txt或.csv檔案。 此操作每24小時計劃一次並執行一次。

現在，您可以配置Campaign Standard工作流，將段插入市場活動。

## 在Campaign Standard中建立導入工作流

Campaign Standard配置為目標後，您需要構建專用工作流以導入Adobe Experience Platform導出的檔案。

為此，您需要添加和配置 **[!UICONTROL Transfer file]** 的子菜單。 有關如何配置此活動的詳細資訊，請參閱 [此部分](../../automating/using/transfer-file.md)。

![](assets/rtcdp-transfer-file.png)

然後，您可以根據需要構建工作流（使用段資料更新資料庫，向段發送跨渠道交貨等）

例如，下面的工作流每天從您的儲存位置下載檔案，然後使用段資料更新市場活動資料庫。

![](assets/rtcdp-workflow.png)

資料管理工作流示例 [工作流使用案例](../../automating/using/about-workflow-use-cases.md#management) 的子菜單。

相關主題：

* [資料管理活動](../../automating/using/about-data-management-activities.md)
* [關於資料匯入和匯出](../../automating/using/about-data-import-and-export.md)
