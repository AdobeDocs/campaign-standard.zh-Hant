---
title: 使用與定位維度不同的資源
description: 瞭解如何使用與定位維度不同的資源。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f3a668860659e40645ce3e4aab879cae5ad90083
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# 使用與定位維度不同的資源 {#using-resources-different-from-targeting-dimensions}

此使用案例說明如何使用與定位維度不同的資源，例如，在遠端表格中尋找特定記錄。

如需定位維度和資源的詳細資訊，請參閱 [本節](../../automating/using/query.md#targeting-dimensions-and-resources)

**範例1: 使用標籤「歡迎回來！」識別傳送所定位的描述檔**。

* 在此案例中，我們要定位描述檔。 我們會將定位維度設為 **[!UICONTROL Profiles (profile)]**。
* 我們想要根據傳送標籤來篩選選取的描述檔。 因此，我們將資源設定為 **[!UICONTROL Delivery logs]**。 這樣，我們就直接在傳送記錄表中進行篩選，提供更佳的效能。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**範例2: 識別傳送時未鎖定的描述檔，並標示為「歡迎返回！」**

在上個範例中，我們使用與定位維度不同的資源。 只有在您想要查找位於遠程表中 **的記錄** （在我們的示例中是交付日誌）時，才能執行此操作。

如果我們想要尋找不在遠端表格中的記錄 **** （例如，未由特定傳送定位的設定檔），您必須使用相同的資源和定位維度，因為該記錄不會出現在遠端表格中（傳送記錄）。

* 在此案例中，我們要定位描述檔。 我們會將定位維度設為 **[!UICONTROL Profiles (profile)]**。
* 我們想要根據傳送標籤來篩選選取的描述檔。 無法直接篩選傳送記錄，因為我們正在尋找不在傳送記錄表格中的記錄。 因此，我們將資源設定為 **[!UICONTROL Profile (profile)]** 並在配置檔案表上構建查詢。

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
