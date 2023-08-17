---
title: 資源狀態
description: 根據其發佈狀態探索不同的資源狀態。
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: 7290ebc5-8a58-4b7f-99bf-d942e37c944e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---

# 資源狀態{#resource-statuses}

視其發佈或啟用狀態而定，資源可能會有不同的狀態。

有兩個欄專門用來在 **[!UICONTROL Custom resources]** 畫面。

![](assets/schema_colonne_1.png)

**發佈狀態**

* **草稿**：資源剛剛建立或重新起草。 若要建立資料庫表格及對應的API，必須重新發佈資源。 如果正在重新草擬資源，在發佈步驟後，該資源會自動變成非使用中。
* **待處理的重新草稿**：資源已重新起草。 重新草稿程式將在下次發佈時進行。 重新起草是不可逆的。 在重新起草和準備發佈時，會顯示數個警告訊息以通知使用者。

  如需重新起草的詳細資訊，請參閱 [刪除資源](../../developing/using/deleting-a-resource.md).

  >[!NOTE]
  >
  >此 **[!UICONTROL Cancel re-draft]** 當您要重新草稿的資源仍然包含其他資源的連結，且連結狀態為「已發佈」時，此選項可供使用。 此選項可讓您還原「重新草稿」程式。 接著，自訂資源會回到其原始狀態。

* **已發佈**：資源已發佈。 如果資源在最後一次修改日期之後修改，則會顯示一則訊息，邀請您重新發佈資源，以考慮最新的修改。

此 **[!UICONTROL Do not publish latest modifications]** 欄位可防止在未來發佈期間考慮修改。

此欄位可在自訂資源定義中設定。
