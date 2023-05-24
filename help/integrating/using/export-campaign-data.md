---
title: 將資料從 Campaign 匯出至 Adobe Experience Platform
description: 瞭解如何將資料從Campaign Standard導出到Adobe Experience Platform。
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 6%

---

# 將資料從 Campaign 匯出至 Adobe Experience Platform {#sources}

要將Campaign Standard資料導出到Adobe Real-time Customer Data Platform(RTCDP)，您首先需要構建Campaign Standard工作流以導出到要共用的資料的Amazon儲存服務(S3)或Azure Blob儲存位置。

配置工作流並將資料發送到您的儲存位置後，您需要將S3或Azure Blob儲存位置連接為 **源** Adobe體驗平台。

>[!NOTE]
>
>請注意，我們建議僅導出市場活動生成的資料（例如發送、開啟、按一下等） Adobe Experience Platform。 從第三方源（如您的CRM）接收的資料應直接導入Adobe Experience Platform。

## 在Campaign Standard中建立導出工作流

要將資料從Campaign Standard導出到S3或Azure Blob儲存位置，您需要構建工作流以針對要導出的資料並將其發送到儲存位置。

為此，請添加和配置：

* A **[!UICONTROL Extract file]** 活動，將目標資料提取到CSV檔案中。 有關如何配置此活動的詳細資訊，請參閱 [此部分](../../automating/using/extract-file.md)。

   ![](assets/rtcdp-extract-file.png)

* A **[!UICONTROL Transfer file]** 活動，將CSV檔案傳輸到儲存位置。 有關如何配置此活動的詳細資訊，請參閱 [此部分](../../automating/using/transfer-file.md)。

   ![](assets/rtcdp-transfer-file.png)

例如，下面的工作流定期將日誌提取為CSV檔案，然後將檔案傳輸到儲存位置。

![](assets/aep-export.png)

資料管理工作流示例 [工作流使用案例](../../automating/using/about-workflow-use-cases.md#management) 的子菜單。

相關主題：

* [資料管理活動](../../automating/using/about-data-management-activities.md)
* [關於資料匯入和匯出](../../automating/using/about-data-import-and-export.md)


## 將儲存位置連接為源

將您的Amazon儲存服務(S3)或Azure Blob儲存位置連接為 **源** Adobe體驗平台列於下面。 有關這些步驟的詳細資訊，請參閱 [源連接器文檔](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant)。

1. 在Adobe Experience平台中 **[!UICONTROL Sources]** 菜單，建立到儲存位置的連接：

   * [建立AmazonS3源連接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html)
   * [Azure Blob連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html)

   >[!NOTE]
   >
   >儲存位置可以是AmazonS3、SFTP和密碼、SFTP和SSH密鑰或Azure Blob連接。 向Adobe Campaign發送資料的首選方法是通過AmazonS3或Azure Blob:

   ![](assets/rtcdp-connector.png)

1. 為雲儲存批處理連接配置資料流。 資料流是從儲存位置檢索資料並將資料接收到Adobe Experience Platform資料集的計畫任務。 通過此步驟，您可以配置從儲存位置接收的資料，包括資料選擇和CSV欄位到XDM架構的映射。

   詳細資訊請參閱 [此頁](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html)。

   ![](assets/rtcdp-map-xdm.png)

1. 配置源後，Adobe Experience Platform將從您提供的儲存位置導入該檔案。

   此操作可以根據您的需要進行計畫。 我們建議根據實例上已存在的負載，每天執行最多6次導出。
