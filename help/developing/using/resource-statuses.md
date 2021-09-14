---
title: 資源狀態
description: 根據其發佈狀態發現不同的資源狀態。
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

視資源的發佈或啟動狀態而定，資源可能會有不同的狀態。

在&#x200B;**[!UICONTROL Custom resources]**&#x200B;螢幕中有兩列專用於顯示這些狀態。

![](assets/schema_colonne_1.png)

**發佈狀態**

* **草稿**:資源剛建立或重新起草。若要建立資料庫表和對應的API，必須重新發佈資源。 如果正在重新起草資源，則在發佈步驟後，該資源會自動變為非活動狀態。
* **待重新起草**:資源重新起草。重新草稿過程將在下次發佈期間進行。 重新起草是不可逆轉的。 會顯示數個警告訊息，以在重新起草及準備發佈時通知使用者。

   有關重新起草的詳細資訊，請參閱[刪除資源](../../developing/using/deleting-a-resource.md)。

   >[!NOTE]
   >
   >當您要重新草稿的資源仍包含連結至其他狀態為「已發佈」的資源時，**[!UICONTROL Cancel re-draft]**&#x200B;選項便可供使用。 此選項可讓您還原「重新草稿」程式。 接著，自訂資源會回到其原始狀態。

* **已發佈**:資源已發佈。如果資源在上次修改日期後修改，則會顯示訊息以邀請您重新發佈資源，以便考慮最新修改。

**[!UICONTROL Do not publish latest modifications]**&#x200B;欄位可防止在未來發佈期間考慮修改。

此欄位可在自訂資源定義中設定。
