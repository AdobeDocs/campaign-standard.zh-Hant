---
title: 傳送包含豐富欄位的電子郵件
description: 以下範例說明如何透過載入檔案活動，使用從外部檔案擷取的其他資料來傳送電子郵件。
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---


# 傳送包含豐富欄位的電子郵件 {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

此外，載入檔案活動也可讓您在相同的工作流程中，從外部檔案傳送內含其他資料的電子郵件。

以下範例說明如何透過載入檔案活動，使用從外部檔案擷取的其他資料來傳送電子郵件。 在此範例中，外部檔案包含描述檔清單及其關聯的帳號。 您想要匯入此資料，以傳送電子郵件給每個設定檔及其帳號。

![](assets/load_file_workflow_ex2.png)

若要建立工作流程，請依照下列步驟進行：

1. 將查詢活動拖 [放到工作流](../../automating/using/query.md) ，然後將其開啟以定義主目標。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. 拖放「載入檔 [案」活動](../../automating/using/load-file.md) ，以指派部分資料至描述檔。 在此示例中，載入包含與資料庫的某些配置檔案相對應的帳戶號的檔案。

   ![](assets/load_file_activity.png)

1. 將Enrichment活動拖 [放至工作流程](../../automating/using/enrichment.md) ，並將載入檔案和查詢活動連結至工作流程。

1. 在擴充 **[!UICONTROL Advanced relations]** 活動的頁籤中，選擇 **[!UICONTROL 0 or 1 cardinality simple link]** 並定義要用於調節的欄位。 在這裡，我們使用姓氏來協調資料與資料庫配置檔案。

   ![](assets/load_file_enrichment_relation.png)

1. 在標籤 **[!UICONTROL Additional data]** 中，選取您要在電子郵件中使用的元素。 在此處選擇帳戶號（從通過載入檔案活動檢索的檔案中的列）。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   有關詳細資訊，請參 [閱Enrichment](../../automating/using/enrichment.md) 節。

1. 將區段活動拖 [放至您的工作](../../automating/using/segmentation.md) 流程，並開啟它以調整主要目標。

   ![](assets/load_file_segmentation.png)

   如需詳細資訊，請參閱「區 [段](../../automating/using/segmentation.md) 」區段。

1. 將電子郵件傳送 [活動拖放至](../../automating/using/email-delivery.md) 「工作流程」中，然後加以開啟。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. 新增個人化欄位，並從節點選取擴充活動（此處為帳戶編號）中定義的其他 **[!UICONTROL Additional data (targetData)]** 資料。 如此可動態擷取電子郵件內容中每個描述檔的帳號。

   ![](assets/load_file_perso_field.png)

1. 儲存電子郵件並啟動工作流程。

電子郵件會傳送至目標。 每個描述檔都會收到含有其對應帳號的電子郵件。

![](assets/load_file_email.png)
