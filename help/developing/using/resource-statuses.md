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

有兩個欄專用於在&#x200B;**[!UICONTROL Custom resources]**&#x200B;畫面中顯示這些狀態。

![](assets/schema_colonne_1.png)

**發佈狀態**

* **草稿**：資源已建立或重新草稿。 若要建立資料庫表格及對應的API，必須重新發佈資源。 如果正在重新草擬資源，在發佈步驟後，該資源會自動變成非使用中。
* **擱置重新草稿**：資源已重新草稿。 重新草稿程式將在下次發佈時進行。 重新起草是不可逆的。 在重新起草和準備發佈時，會顯示數個警告訊息以通知使用者。

  如需重新起草的詳細資訊，請參閱[刪除資源](../../developing/using/deleting-a-resource.md)。

  >[!NOTE]
  >
  >當您要重新草稿的資源仍包含透過其他資源傳送的具有「已發佈」狀態的連結時，**[!UICONTROL Cancel re-draft]**&#x200B;選項可用。 此選項可讓您還原「重新草稿」程式。 接著，自訂資源會回到其原始狀態。

* **已發佈**：資源已發佈。 如果資源在最後一次修改日期之後修改，則會顯示一則訊息，邀請您重新發佈資源，以考慮最新的修改。

**[!UICONTROL Do not publish latest modifications]**&#x200B;欄位會防止在未來的發行中考慮修改。

此欄位可在自訂資源定義中設定。
