---
solution: Campaign Standard
product: campaign
title: 將資料從 Campaign 匯出至 Adobe Experience Platform
description: 瞭解如何將資料從Campaign Standard匯出至Adobe Experience Platform。
audience: integrating
content-type: reference
feature: 來源和目標
role: Data Architect
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
translation-type: tm+mt
source-git-commit: 4855585539653a0bb496d210b001765b5b557570
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 4%

---

# 將資料從 Campaign 匯出至 Adobe Experience Platform {#sources}

要將Campaign Standard資料導出到Adobe即時客戶資料平台(RTCDP)，首先需要構建Campaign Standard工作流，以便將要共用的資料導出到Amazon儲存服務(S3)或Azure Blob儲存位置。

在設定工作流程並將資料傳送至您的儲存位置後，您必須將S3或Azure blob儲存位置連接為Adobe體驗平台中的&#x200B;**Source**。

>[!NOTE]
>
>請注意，我們建議僅匯出促銷活動產生的資料（例如傳送、開啟、點按等） Adobe Experience Platform。 從第三方來源（如您的CRM）擷取的資料應直接匯入Adobe Experience Platform。

## 在Campaign Standard中建立匯出工作流程

若要將資料從Campaign Standard匯出至S3或Azure Blob儲存位置，您必須建立工作流程，以定位您要匯出的資料，並將它傳送至儲存位置。

若要這麼做，請新增及設定：

* **[!UICONTROL Extract file]**&#x200B;活動，將目標資料擷取為CSV檔案。 有關如何配置此活動的詳細資訊，請參閱[本節](../../automating/using/extract-file.md)。

   ![](assets/rtcdp-extract-file.png)

* **[!UICONTROL Transfer file]**&#x200B;活動，將CSV檔案傳輸至您的儲存位置。 有關如何配置此活動的詳細資訊，請參閱[本節](../../automating/using/transfer-file.md)。

   ![](assets/rtcdp-transfer-file.png)

例如，以下工作流會定期將記錄檔擷取為CSV檔案，然後將檔案傳輸至儲存位置。

![](assets/aep-export.png)

[工作流程使用案例](../../automating/using/about-workflow-use-cases.md#management)區段中提供資料管理工作流程的範例。

相關主題：

* [資料管理活動](../../automating/using/about-data-management-activities.md)
* [關於資料匯入和匯出](../../automating/using/about-data-import-and-export.md)


## 將儲存位置作為源連接

以下列出了將您的Amazon儲存服務(S3)或Azure Blob儲存位置連接為Adobe體驗平台中&#x200B;**源**&#x200B;的主要步驟。 [源連接器文檔](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html)中提供了有關這些步驟的詳細資訊。

1. 在Adobe Experience Platform **[!UICONTROL Sources]**&#x200B;功能表中，建立儲存位置的連線：

   * [建立AmazonS3源連接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html)
   * [Azure Blob連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html)

   >[!NOTE]
   >
   >儲存位置可以是AmazonS3、帶密碼的SFTP、帶SSH密鑰的SFTP或Azure Blob連接。 傳送資料至Adobe Campaign的偏好方法是透過AmazonS3或Azure Blob:

   ![](assets/rtcdp-connector.png)

1. 為雲儲存批處理連接配置資料流。 資料流是從儲存位置檢索資料並將資料提取到Adobe Experience Platform資料集的計畫任務。 此步驟可讓您從儲存位置設定資料擷取，包括資料選擇和CSV欄位對應至XDM架構。

   如需詳細資訊，請參閱[本頁](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html)。

   ![](assets/rtcdp-map-xdm.png)

1. 配置源後，Adobe Experience Platform將從您提供的儲存位置導入檔案。

   此操作可以根據您的需要進行計畫。 我們建議您每天最多執行6次匯出，視例項上已有的載入而定。
