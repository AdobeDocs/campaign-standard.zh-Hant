---
solution: Campaign Standard
product: campaign
title: 將 Adobe Experience Platform 對象內嵌至 Campaign
description: 了解如何將Adobe Experience Platform受眾內嵌至Campaign Standard。
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
source-git-commit: ca8473f50b132b2d5ca58c6403d144fbf62741b0
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 7%

---

# 將 Adobe Experience Platform 對象內嵌至 Campaign {#destinations}

若要將Adobe Experience Platform對象內嵌至Campaign並在工作流程中使用這些對象，您必須先將Adobe Campaign連結為Adobe Experience Platform **目的地**，並使用要匯出的區段進行設定。

設定目標後，資料將導出到您的儲存位置，您需要在Campaign Standard中構建專用的工作流以進行內嵌。

## 連線Adobe Campaign作為目的地

在Adobe Experience Platform中，為匯出的區段選取儲存位置，以設定與Adobe Campaign的連線。 此步驟也可讓您選取要匯出的區段，並指定要包含的其他XDM欄位。

如需詳細資訊，請參閱[目標檔案](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html)。

設定目標後，Adobe Experience Platform會在您提供的儲存位置中建立以Tab分隔的.txt或.csv檔案。 此操作已排程，每24小時執行一次。

您現在可以設定Campaign Standard工作流程，將區段內嵌至促銷活動。

## 在Campaign Standard中建立匯入工作流程

將Campaign Standard設定為目的地後，您需要建立專用的工作流程，以匯入Adobe Experience Platform已匯出的檔案。

要執行此操作，您需要新增和設定&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動。 有關如何配置此活動的詳細資訊，請參閱[此部分](../../automating/using/transfer-file.md)。

![](assets/rtcdp-transfer-file.png)

然後，您就可以根據您的需求建立工作流程（使用區段資料更新資料庫、傳送跨通道傳送至區段等）

例如，下列工作流程每天從您的儲存位置下載檔案，然後使用區段資料更新Campaign資料庫。

![](assets/rtcdp-workflow.png)

[工作流程使用案例](../../automating/using/about-workflow-use-cases.md#management)區段中提供資料管理工作流程的範例。

相關主題：

* [資料管理活動](../../automating/using/about-data-management-activities.md)
* [關於資料匯入和匯出](../../automating/using/about-data-import-and-export.md)
