---
title: 將 Adobe Experience Platform 客群內嵌至 Campaign
description: 瞭解如何將Adobe Experience Platform受眾內嵌至Campaign Standard。
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
TQID: https://experienceleague.adobe.com/LdVWEXa90p4yOKgPGG5LUOGRk3xWE8kJ8SkKM7ODBXk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2:
  - id: b70f632b-2cfd-43d0-9266-284281100d70
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 7%

---

# 將 Adobe Experience Platform 客群內嵌至 Campaign {#destinations}

若要將Adobe Experience Platform對象擷取至Campaign並用於您的工作流程，您首先需要將Adobe Campaign as a Adobe Experience Platform **目的地**&#x200B;連線，並使用要匯出的區段進行設定。

設定目的地後，系統會將資料匯出至您的儲存位置，而且您將需要在Campaign Standard中建置專用的工作流程來擷取資料。

## 將Adobe Campaign連線為目的地

在Adobe Experience Platform中，選取匯出區段的儲存位置，以設定與Adobe Campaign的連線。 此步驟也可讓您選取要匯出的區段，並指定要包含的其他XDM欄位。

如需詳細資訊，請參閱[Destinations檔案](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html)。

設定目的地後，Adobe Experience Platform會在您提供的儲存位置中建立以Tab分隔的.txt或.csv檔案。 此作業會排程並每24小時執行一次。

您現在可以設定Campaign Standard工作流程，將區段擷取至Campaign。

## 在Campaign Standard中建立匯入工作流程

將Campaign Standard設定為目的地後，您需要建立專用的工作流程，以匯入Adobe Experience Platform已匯出的檔案。

若要這麼做，您必須新增及設定&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動。 如需如何設定此活動的詳細資訊，請參閱[本節](../../automating/using/transfer-file.md)。

![](assets/rtcdp-transfer-file.png)

接著，您就可以根據需求建立工作流程（使用區段資料更新資料庫、傳送跨管道傳遞至區段等）

例如，以下工作流程會每天從您的儲存位置下載檔案，然後使用區段資料更新Campaign資料庫。

![](assets/rtcdp-workflow.png)

資料管理工作流程範例可在[工作流程使用案例](../../automating/using/about-workflow-use-cases.md#management)區段中取得。

相關主題：

* [資料管理活動](../../automating/using/about-data-management-activities.md)
* [關於資料匯入和匯出](../../automating/using/about-data-import-and-export.md)
