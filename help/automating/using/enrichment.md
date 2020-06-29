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
ht-degree: 0%

---


# 擴充{#enrichment}

## 說明 {#description}

![](assets/enrichment.png)

活 **[!UICONTROL Enrichment]** 動是進階活動，可讓您定義要在工作流程中處理的其他資料。

## 使用內容 {#context-of-use}

活動 **[!UICONTROL Enrichment]** 通常用於定位活動後或匯入檔案後，以及允許使用定位資料之活動前。

此活動包含比活動更高級的富集函 **[!UICONTROL Query]** 數。 某些簡單的擴充案例可直接在查詢活動 [中執行](../../automating/using/query.md#enriching-data)。

使用活 **[!UICONTROL Enrichment]** 動時，您可以利用傳入的轉場，並設定活動以使用其他資料完成輸出轉場。 它可結合來自多組資料，或建立臨時資源的連結。

**相關主題**

* [使用案例： 使用檔案中包含的資料豐富描述檔資料](../../automating/using/enriching-profile-data-file.md)。
* [使用案例： 傳送包含豐富欄位的電子郵件](../../automating/using/sending-email-enriched-fields.md)

## 配置 {#configuration}

要配置活 **[!UICONTROL Enrichment]** 動：

1. 將活動拖放 **[!UICONTROL Enrichment]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 如果活動有數個傳入轉場，請選取 **[!UICONTROL Primary set]**。 此活動中配置的其他資料將添加到出站轉換中的此主集。

   如果主集已包含其他資料，您可以選擇保留或刪除這些資料。 如果取消選中該 **[!UICONTROL Keep all additional data from the main set]** 選項，則只有在中配置的其 **[!UICONTROL Enrichment]** 他資料會保留在出站過渡中。

1. 如果有數個傳入轉場，請在活動的標籤中定義主要集與其他傳入資料 **[!UICONTROL Advanced Relations]** 之間的關係。 您可以使用按鈕添加多個關 **[!UICONTROL Add element]** 系。

   定義新關係時，選擇要連結到主集的入站資料集。 然後定義關係類型。 根據傳入的資料和您的資料模型，可使用數種關係：

   * **[!UICONTROL 1 cardinality simple link]**: 每個傳入資料的記錄都與來自主集的一個且僅一個記錄相關聯。 來自主集的每個記錄在連結資料中具有一個關聯記錄。
   * **[!UICONTROL N cardinality collection link]**: 來自連結資料的0、1或更多(N)記錄可以關聯到主集的1個記錄。
   * **[!UICONTROL 0 or 1 cardinality simple link]**: 來自主集的記錄可以與來自連結資料的0或1個記錄關聯，但不能與多個記錄關聯。
   定義 **[!UICONTROL Cardinality]** 後，定義 **[!UICONTROL Reconciliation criteria]**。 協 **[!UICONTROL Source expression]** 調標準可以是目標資源中的欄位、表達 [式](../../automating/using/advanced-expression-editing.md) ，或直接是引號之間指定的值。

   定義 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 在稍後工作流程中易於識別。

   >[!NOTE]
   >
   >您只能定義主集和連接到活動的其它入站過渡之間的關 **[!UICONTROL Enrichment]** 系。 對於旨在定義與資料庫資源關係的簡單案例，請使用「協調 [」活動](../../automating/using/reconciliation.md) 。

1. 從活動的標籤中定 **[!UICONTROL Additional data]** 義其他資料。 您可以定義與主要集的目標維度相關的其他資料（簡單欄位、匯總和系列），或根據在活動標籤中建立 **[!UICONTROL Advanced relations]** 的連結 **[!UICONTROL Enrichment]** 定義。

   請參閱「 [豐富資料](../../automating/using/query.md#enriching-data) 」一節。

1. 確認活動的設定並儲存工作流程。

現在，資料可用於在之後連接的活動中 **[!UICONTROL Enrichment]**。 例如，您可以在電子郵件內容中 **[!UICONTROL Additional data (targetData)]** 個人化欄位檔案總管的連結下找到它。
