---
title: 擴充
description: 「擴充」活動是進階活動，可讓您定義要在工作流程中處理的其他資料。
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 96%

---


# 擴充{#enrichment}

## 說明 {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** 活動是進階活動，可讓您定義要在工作流程中處理的其他資料。

## 使用內容 {#context-of-use}

**[!UICONTROL Enrichment]** 活動通常用於目標定位活動後或匯入檔案後，以及允許使用目標定位資料之活動前。

此活動包含比 **[!UICONTROL Query]** 活動更進階的擴充函式。某些簡單的擴充案例可直接在[查詢活動](../../automating/using/query.md#enriching-data)中執行。

使用 **[!UICONTROL Enrichment]** 活動時，您可以利用入站轉變，並設定活動以使用其他資料完成出站轉變。它可結合來自多組資料，或建立臨時資源的連結。

**相關主題**

* [使用案例：使用檔案中包含的資料豐富描述檔資料](../../automating/using/enriching-profile-data-file.md)。
* [使用案例：傳送包含豐富欄位的電子郵件](../../automating/using/sending-email-enriched-fields.md)

## 設定 {#configuration}

要設定 **[!UICONTROL Enrichment]** 活動：

1. 將 **[!UICONTROL Enrichment]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 如果活動有數個入站轉變，請選取 **[!UICONTROL Primary set]**。此活動中設定的其他資料將新增到出站轉換中的這個主要集。

   如果主要集已包含其他資料，您可以選取保留或刪除這些資料。如果取消核取 **[!UICONTROL Keep all additional data from the main set]** 選項，則只有在　**[!UICONTROL Enrichment]**　設定的其他資料才會保留在出站轉變中。

1. 如果有數個入站轉變，請在活動的標籤中定義主要集與活動之 **[!UICONTROL Advanced Relations]** 索引標籤的其他入站資料之間的關係。您可以使用 **[!UICONTROL Add element]** 按鈕新增多個關係。

   定義新關係時，選取要連結到主要集的入站資料集。然後定義關係類型。根據入站資料和您的資料模型，有數種關係可供使用：

   * **[!UICONTROL 1 cardinality simple link]**：每個入站資料的記錄都與來自主要集的一個及唯一一個記錄相關聯。來自主要集的每個記錄在連結資料中具有一個關聯記錄。
   * **[!UICONTROL N cardinality collection link]**：來自連結資料的 0、1 或更多 (N) 記錄可以與主要集的 1 個記錄相關聯。
   * **[!UICONTROL 0 or 1 cardinality simple link]**：來自主要集的記錄可以與來自連結資料的 0 或 1 個記錄相關聯，但不能與多個記錄相關聯。

   定義 **[!UICONTROL Cardinality]** 後，定義 **[!UICONTROL Reconciliation criteria]**。調解標準的 **[!UICONTROL Source expression]** 可以是目標資源的欄位、[運算式](../../automating/using/advanced-expression-editing.md)或直接是引號之間指定的值。

   定義 **[!UICONTROL Label]** 及 **[!UICONTROL ID]**，以便在稍後工作流程中易於識別。

   >[!NOTE]
   >
   >您只能定義主要集和連接到 **[!UICONTROL Enrichment]** 活動的其他入站轉變之間的關係。對於旨在定義與資料庫資源關係的簡單案例，請使用[調解](../../automating/using/reconciliation.md)活動。

1. 從活動的 **[!UICONTROL Additional data]** 索引標籤中定義其他資料。您可以定義與主要集目標維度相關的其他資料（簡單欄位、彙總和系列），或是以 **[!UICONTROL Enrichment]** 活動的 **[!UICONTROL Advanced relations]** 索引標籤中建立的連結為基礎。

   請參閱[擴充資料](../../automating/using/query.md#enriching-data)區段。

1. 確認活動的設定並儲存工作流程。

現在，資料可用於 **[!UICONTROL Enrichment]** 之後連接的活動。例如，您可以在電子郵件內容中個人化欄位檔案總管的 **[!UICONTROL Additional data (targetData)]** 連結下找到它。
