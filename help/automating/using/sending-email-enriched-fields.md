---
title: 傳遞包含擴充欄位的電子郵件
description: 以下範例說明如何透過載入檔案活動，使用從外部檔案擷取的其他資料來傳送電子郵件。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5ca7571d-d4d2-4b59-86d4-4f1f3a620b54
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 68%

---

# 傳遞包含擴充欄位的電子郵件 {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

此外，載入檔案活動也可讓您在相同的工作流程中，從外部檔案傳送內含其他資料的電子郵件。

以下範例說明如何透過載入檔案活動，使用從外部檔案擷取的其他資料來傳送電子郵件。在此範例中，外部檔案包含設定檔清單及其關聯的帳號。您想要匯入此資料，以傳送電子郵件給每個設定檔及其帳號。

![](assets/load_file_workflow_ex2.png)

若要建置工作流程，請遵循下列步驟：

1. 將[查詢](../../automating/using/query.md)活動拖放到工作流程中，並開啟它以定義主要目標。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. 拖放[載入檔案](../../automating/using/load-file.md)活動，將部分資料指派給設定檔。 在此範例中，載入包含與資料庫之一些設定檔相對應帳號的檔案。

   ![](assets/load_file_activity.png)

1. 將[擴充](../../automating/using/enrichment.md)活動拖放到工作流程中，並將載入檔案和查詢活動連結至工作流程。

1. 在擴充活動的 **[!UICONTROL Advanced relations]** 索引標籤中，選取 **[!UICONTROL 0 or 1 cardinality simple link]** 並定義要用於調和的欄位。在此處，我們會使用姓氏來調整資料和資料庫設定檔。

   ![](assets/load_file_enrichment_relation.png)

1. 在 **[!UICONTROL Additional data]** 索引標籤中，選取您要在電子郵件中使用的元素。在此處選取帳號（從透過載入檔案活動擷取之檔案的欄）。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   如需詳細資訊，請參閱[擴充](../../automating/using/enrichment.md)區段。

1. 將[Segmentation](../../automating/using/segmentation.md)活動拖放到工作流程中，並開啟它以調整主要目標。

   ![](assets/load_file_segmentation.png)

   如需詳細資訊，請參閱[分段](../../automating/using/segmentation.md)區段。

1. 將[電子郵件傳遞](../../automating/using/email-delivery.md)活動拖放到工作流程中並加以開啟。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. 新增個人化欄位，並從 **[!UICONTROL Additional data (targetData)]** 節點選取擴充活動（此處為帳號）中定義的其他資料。如此可動態擷取電子郵件內容中每個設定檔的帳號。

   ![](assets/load_file_perso_field.png)

1. 儲存電子郵件並啟動工作流程。

會將電子郵件傳送至目標。每個設定檔都會收到含有其對應帳號的電子郵件。

![](assets/load_file_email.png)
