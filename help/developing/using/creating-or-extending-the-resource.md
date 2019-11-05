---
title: 建立或擴充資源
description: 瞭解如何從頭開始定義資源。
page-status-flag: 從未激活
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 開發
content-type: 參考
topic-tags: 添加或擴展資源
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 建立或擴充資源{#creating-or-extending-the-resource}

如果您需要處理非現成資料模型一部分的資料，管理員可以從頭開始建立新資源，或是建立現有資源的擴充功能。

只能擴展下列現成可用的資源：

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

1. 從 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**&#x200B;按一下按 **[!UICONTROL Create]** 鈕。
1. 選擇要執行的動作：

   * **[!UICONTROL Create a new resource]**:輸入和 **[!UICONTROL Label]** 字 **[!UICONTROL ID]** 段。 欄位 **[!UICONTROL ID]** 為必填欄位。 如果將「標籤」欄位保留為空白，則會自動從ID完成。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >建議最多使用30個字元。

   * **[!UICONTROL Extend an existing resource]**:選擇要擴展的資源。

      ![](assets/schema_extension_10.png)

1. 單 **[!UICONTROL Create]** 擊建立資源，在新資源時，該資源將 **[!UICONTROL Draft]** 處於狀態，在擴展時 **[!UICONTROL Editing]** 將處於狀態。

新資源已建立，現在可以配置。 有關資源配置的詳細資訊，請 [參閱配置資源的資料結構](../../developing/using/configuring-the-resource-s-data-structure.md)。
