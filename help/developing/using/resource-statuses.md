---
title: 資源狀態
description: 根據不同的資源狀態發現其發佈狀態。
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

根據資源的發佈或激活狀態，資源可以具有不同的狀態。

有兩列專用於在 **[!UICONTROL Custom resources]** 的上界。

![](assets/schema_colonne_1.png)

**發佈狀態**

* **草稿**:資源剛剛建立或重新起草。 要建立資料庫表和相應的API，必須重新發佈資源。 如果正在重新起草資源，則在發佈步驟後，該資源將自動變為非活動狀態。
* **待重新擬定**:資源重新起草。 下次發佈期間將進行重新起草過程。 重新起草是不可逆轉的。 在重新起草和準備發佈時，顯示若干警告消息以通知用戶。

   有關重新起草的詳細資訊，請參閱 [刪除資源](../../developing/using/deleting-a-resource.md)。

   >[!NOTE]
   >
   >的 **[!UICONTROL Cancel re-draft]** 當要重新起草的資源仍包含通過其他資源的「已發佈」狀態的連結時，此選項可用。 此選項允許您還原「重繪」進程。 然後，自定義資源將返回其原始狀態。

* **已發佈**:資源已發佈。 如果資源在上次修改日期後被修改，則會顯示一條消息，邀請您重新發佈資源以考慮最新修改。

的 **[!UICONTROL Do not publish latest modifications]** 欄位可防止在將來的發佈期間考慮修改。

可以在自定義資源定義中配置此欄位。
