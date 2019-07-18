---
title: 建立或擴充資源
seo-title: 建立或擴充資源
description: 建立或擴充資源
seo-description: 瞭解如何從頭定義資源。
page-status-flag: 從未啓動
uuid: 7c26b63d-9587-472b-804f-cde5 c45 dfb3 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 開發
content-type: reference
topic-tags: 新增或延伸-資源
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Creating or extending the resource{#creating-or-extending-the-resource}

如果需要處理不屬於現成可用資料模型一部分的資料，管理員可以從頭開始建立新資源，或建立現有資源的擴充功能。

只有下列現成可用的資源可以延伸：

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

若要建立或延伸資源：

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, click the **[!UICONTROL Create]** button.
1. 選擇您要執行的動作：

   * **[!UICONTROL Create a new resource]**：輸入 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 欄位。**[!UICONTROL ID]** 欄位是強制欄位。如果您將「Label」(標籤)欄位保留空白，它會自動從ID完成。

      ![](assets/schema_extension_2.png)

   * **[!UICONTROL Extend an existing resource]**：選擇要延伸的資源。

      ![](assets/schema_extension_10.png)

1. Click **[!UICONTROL Create]** to create the resource, which will then take on the **[!UICONTROL Draft]** status in case of new resource or the **[!UICONTROL Editing]** status in case of extension.

系統會建立新資源，現在可以設定。For more on resource configuration, refer to [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).
