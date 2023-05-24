---
title: 監控資料模型變更
description: 瞭解如何診斷Adobe Campaign資料模型。
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
source-git-commit: 5fef74296a4790102c75e609c270e52d5ead1d58
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 8%

---

# 監控資料模型變更{#monitoring-data-model-changes}

從 **[!UICONTROL Diagnosis]** 菜單中，您可以查看應用程式生成的技術對象，以便對其進行分析。

>[!NOTE]
>
>此菜單中的螢幕是只讀的。

![](assets/diagnostic.png)

您可以查看以下類型的對象：

* 資料方案
* 網頁
* 篩選
* 導覽
* 元件
* 批次工作

您可以更改清單配置：

* 可以添加和刪除列。
* 可以定義列名。
* 您可以定義列在清單中的顯示順序。
* 您可以在清單中選擇值的排序順序。

您可以篩選清單：

* 可以包括或排除本機資料方案、網頁、篩選器和導航對象。
* 可以按對象名稱搜索對象。
* 您可以按批作業的狀態、起始日期和終止日期篩選批作業。

可以用逗號分隔的值以TXT格式下載顯示的清單。

您可以查看所選對象的詳細資訊。

例如，可以使用此功能查看出廠設定過濾器的過濾標準。 此示例顯示為現成過濾器的過濾標準顯示的代碼：

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)