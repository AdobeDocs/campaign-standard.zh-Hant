---
title: 調解
description: 「協調」活動允許您將未標識的資料連結到現有資源。
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---


# 調解{#reconciliation}

## 說明 {#description}

![](assets/reconciliation.png)

此活 **[!UICONTROL Reconciliation]** 動可讓您將未識別的資料連結至現有資源。

## 使用內容 {#context-of-use}

此活 **[!UICONTROL Reconciliation]** 動主要用於資料管理，並意味著兩種不同的使用案例：

* 添加關係： 標籤 **[!UICONTROL Links]** 可讓您在傳入資料和數個其他Adobe Campaign資料庫維度之間新增連結。

   例如，包含購買資料的檔案也可能包含識別所購買產品及購買者的資訊。 因此，檔案資料會關 **注另外兩個維度**（購買除外）: 「產 **品** 」和「 **描述檔** 」維度。 然後，需要在這些維和「購買」維 **之間建立關係** （請參閱以下示例）。

   定義關係時，將向傳入資料添加列以引用連結維的外鍵。

   >[!NOTE]
   >
   >此操作表示連結維的資料已在資料庫中。 例如，如果您匯入購買檔案，顯示何時購買了哪些產品、客戶等，則產品和客戶端必須已存在於資料庫中。

* 資料識別： 標 **[!UICONTROL Identification]** 簽可讓您將傳入資料連結至Adobe Campaign資料庫中現有維度的欄。 在活動後，資料被標識為屬於定義的維。

   例如，您可以接著執行儲存對象、資料庫更新等。

例如，活動 **[!UICONTROL Reconciliation]** 可放在載入資料活動之後，以便將非標準資料匯入資料庫。

**相關主題：**

* [使用案例： 使用關係進行資料協調](../../automating/using/reconciliation-using-relations.md)
* [使用案例： 使用協調功能更新資料](../../automating/using/data-update-reconciliation.md)
* [使用案例： 協調檔案對象與資料庫](../../automating/using/reconcile-file-audience-with-database.md)

## 配置 {#configuration}

1. 在包含目標維度不直 **[!UICONTROL Reconciliation]** 接來自Adobe Campaign之人口族群的轉場後，將活動拖放至工作流程中。 如需詳細資訊，請參閱「定 [位維度和資源」](../../automating/using/query.md#targeting-dimensions-and-resources)。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 如果要定義傳入資料與其他資料庫維之間的連結，請轉至該選 **[!UICONTROL Links]** 項卡。

   視需要新增關係。 對於每個關係，首先選擇連結的維，然後在連結詳細資訊中指定相應的欄位。

1. 如果您只想識別傳入的資料，請前往標籤並 **[!UICONTROL Identification]** 勾選方 **[!UICONTROL Identify the document from the working data]** 塊。

   選擇要協調傳入資料的目標維度。

   新增協調條件，將傳入的轉換記錄連結至選取的定位維度記錄。 如果指定了多個標準，則必須對這些標準進行驗證，以使其所有資料之間的連結能夠工作。

   選擇模 **[!UICONTROL Processing unidentified source lines]** 式：

   * **[!UICONTROL Ignore them]**: 只有可識別的資料會保留在活動的對外轉移中。
   * **[!UICONTROL Keep in the outbound population]**: 入站轉變中的所有資料都保存在活動的出站轉變中。

1. 確認活動的設定並儲存工作流程。
