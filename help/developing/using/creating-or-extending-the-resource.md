---
title: 建立或擴充資源
description: 瞭解如何從頭開始定義資源。
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: b8731088-a675-4070-9036-bf2b5254e4e8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 11%

---

# 建立或擴充資源{#creating-or-extending-the-resource}

如果您需要處理不屬於內置資料模型的資料，管理員可以從頭開始建立新資源或建立現有資源的擴展。

只能擴展以下內置資源：

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

1. 從 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**，按一下 **[!UICONTROL Create]** 按鈕
1. 選擇要執行的操作：

   * **[!UICONTROL Create a new resource]**:輸入 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 的子菜單。 **[!UICONTROL ID]** 欄位為必填欄位。如果「標籤」欄位為空，則自動從ID完成。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >最多使用 30 個字元。

   * **[!UICONTROL Extend an existing resource]**:選擇要擴展的資源。

      ![](assets/schema_extension_10.png)

1. 按一下 **[!UICONTROL Create]** 建立資源，然後 **[!UICONTROL Draft]** 新資源或 **[!UICONTROL Editing]** 擴展時的狀態。

新資源已建立，現在可以配置。 有關資源配置的詳細資訊，請參閱 [配置資源的資料結構](../../developing/using/configuring-the-resource-s-data-structure.md)。
