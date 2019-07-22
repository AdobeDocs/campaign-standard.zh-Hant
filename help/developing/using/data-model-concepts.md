---
title: 資料模型概念
seo-title: 資料模型概念
description: 資料模型概念
seo-description: 瞭解Adobe Campaign資料模型以及如何修改。
page-status-flag: 從未啓動
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 開發
content-type: reference
topic-tags: 關於自訂資源
discoiquuid: 4e0468da-3052-4ce5-8174-45aa1f5c4
context-tags: CusResource，概觀；eventCusResource，總覽
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4d95fe00c1958399ff4d22d5f0e7762f895b4032

---


# Data model concepts{#data-model-concepts}

Adobe Campaign隨附預先定義的資料模型。[管理員](../../administration/using/users-management.md#functional-administrators) 可以修改此資料模型，管理員可以在現有資源中新增資源或擴充功能。

>[!CAUTION]
>
>建立和修改資源是敏感作業，僅由專家使用者執行。

**[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** 功能表(透過Adobe Campaign標誌存取)可讓您管理 **自訂資源**、 **發佈** 並 **存取診斷工具**。

Adobe Campaign使用的資料是透過不同的資源來定義。

You can **enrich the data template** that is provided by creating your own custom resources, such as purchase or product tables.

無法修改立即可用的資源(例如促銷活動、電子郵件或觀眾)。不過，可擴充自訂資源以新增欄位。

>[!NOTE]
>
>You can find a datamodel representation for the out-of-the-box resources [here](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html).

You can also **configure the navigation** in the screens corresponding to the resource created.

副檔名會以前置詞產生，因此不會與立即可用的欄位衝突。
