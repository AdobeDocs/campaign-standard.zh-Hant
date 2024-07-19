---
title: 調和
description: 「調和」活動可讓您將未標識的資料連結到現有資源。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: ed2e3793-6164-48af-9043-42dc43fa8ed4
source-git-commit: c2c8d2d05bbc376e2153448ca0a9e6ba0f367420
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 78%

---

# 調和{#reconciliation}

## 說明 {#description}

![](assets/reconciliation.png)

**[!UICONTROL Reconciliation]** 活動可讓您將未識別的資料連結至現有資源。

## 使用內容 {#context-of-use}

**[!UICONTROL Reconciliation]** 活動主要用於資料管理，並代表兩種不同的使用案例：

* 新增關係：**[!UICONTROL Links]** 索引標籤可讓您在傳入資料和數個其他 Adobe Campaign 資料庫維度之間新增連結。

  例如，包含購買資料的檔案也可能包含識別購買產品及購買者的資訊。因此，檔案資料會關注另外兩個維度（**購買**&#x200B;除外）：**產品**&#x200B;及&#x200B;**設定檔**&#x200B;維度。然後，需要在這些&#x200B;**購買**&#x200B;維度之間建立關係（請參閱以下範例）。

  定義關係時，將向入站資料新增欄，以參考連結維度的外部索引鍵。

  >[!NOTE]
  >
  >此操作表示連結維度的資料已在資料庫中。例如，如果您匯入購買檔案，顯示何時購買了哪些產品、哪個客戶等，則產品和客戶必須已存在於資料庫中。

* 資料識別：**[!UICONTROL Identification]** 索引標籤可讓您將入站資料連結至 Adobe Campaign 資料庫中現有維度的欄。在活動後，會將資料識別為屬於定義的維度。

  例如，您之後可以執行儲存對象、資料庫更新等。

例如，**[!UICONTROL Reconciliation]**&#x200B;活動可放置在載入資料活動之後，以將非標準資料匯入資料庫。

雖然&#x200B;**擴充**&#x200B;活動可讓您定義要在工作流程中處理的其他資料（使用&#x200B;**擴充**&#x200B;活動來合併來自多組資料，或建立臨時資源的連結），但&#x200B;**調解**&#x200B;活動可讓您將未識別的資料連結到現有資源。 調解作業表示連結維度的資料已在資料庫中。 [此區段](#use-cases-reconciliation)中有使用案例。


## 設定 {#configuration}

1. 將 **[!UICONTROL Reconciliation]** 活動拖放到您的工作流程，亦即位在包含母體的轉變之後，而且其母體的目標維度不會直接來自於 Adobe Campaign。如需詳細資訊，請參閱[目標維度和資源](../../automating/using/query.md#targeting-dimensions-and-resources)。
1. 選取活動，然後使用所顯示快速動作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 如果要定義傳入資料與其他資料庫維度之間的連結，請移至 **[!UICONTROL Links]** 索引標籤。

   視需要盡量新增關係。對於每個關係，首先選取連結的維度，然後在連結詳細資訊中指定相對應的欄位。

1. 如果您只想識別入站資料，請移至 **[!UICONTROL Identification]** 索引標籤並核取 **[!UICONTROL Identify the document from the working data]** 方塊。

   選取您要調和入站資料的目標維度。

   新增調和條件，將入站轉變記錄連結至選取的目標維度記錄。如果指定了多個標準，則必須對這些標準進行驗證，以使其所有資料之間的連結能夠運作。

   選取 **[!UICONTROL Processing unidentified source lines]** 模式：

   * **[!UICONTROL Ignore them]**：只會將可識別的資料保留在活動的出站轉變中。
   * **[!UICONTROL Keep in the outbound population]**：入站轉變中的所有資料都會保留在活動的出站轉變中。

1. 確認活動的設定並儲存工作流程。


## 使用案例{#use-cases-reconciliation}

瞭解如何在下列使用案例中使用此活動：

* [使用案例：使用關係進行資料協調](../../automating/using/reconciliation-using-relations.md)
* [使用案例：使用協調功能更新資料](../../automating/using/data-update-reconciliation.md)
* [使用案例：使用資料庫調解檔案對象](../../automating/using/reconcile-file-audience-with-database.md)