---
solution: Campaign Standard
product: campaign
title: 建立或擴充資源
description: 瞭解如何從頭開始定義資源。
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 11%

---


# 建立或擴充資源{#creating-or-extending-the-resource}

如果您需要處理不屬於內建資料模型的資料，管理員可以從頭開始建立新資源，或建立現有資源的擴充功能。

僅可擴充下列內建資源：

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

要建立或擴展資源，請執行以下操作：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**&#x200B;中，按一下&#x200B;**[!UICONTROL Create]**&#x200B;按鈕。
1. 選擇要執行的動作：

   * **[!UICONTROL Create a new resource]**:輸入 **[!UICONTROL Label]** 和字 **[!UICONTROL ID]** 段。**[!UICONTROL ID]** 欄位為必填欄位。如果將「標籤」欄位保留為空白，則會自動從ID完成。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >最多使用 30 個字元。

   * **[!UICONTROL Extend an existing resource]**:選擇要擴展的資源。

      ![](assets/schema_extension_10.png)

1. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;建立資源，在出現新資源時，該資源將處於&#x200B;**[!UICONTROL Draft]**&#x200B;狀態，如果擴展，則處於&#x200B;**[!UICONTROL Editing]**&#x200B;狀態。

新資源已建立，現在可以配置。 有關資源配置的詳細資訊，請參閱[配置資源的資料結構](../../developing/using/configuring-the-resource-s-data-structure.md)。
