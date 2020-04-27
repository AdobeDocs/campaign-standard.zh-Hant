---
title: 資源狀態
description: 根據不同的資源狀態來發現其發佈狀態。
page-status-flag: never-activated
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# 資源狀態{#resource-statuses}

視資源的發佈或啟動狀態而定，資源可能有不同的狀態。

有兩欄專用於在畫面中顯示這些 **[!UICONTROL Custom resources]** 狀態。

![](assets/schema_colonne_1.png)

**出版物狀態**

* **草稿**:資源剛剛建立或重新起草。 要建立資料庫表以及相應的API，必須重新發佈資源。 如果正在重新起草資源，則在發佈步驟後，該資源將自動變為非活動狀態。
* **待重擬**:資源被重新起草。 重新草稿程式將在下次發佈期間進行。 重新起草是不可逆轉的。 在重新起草和準備發佈時，會顯示數個警告訊息以通知使用者。

   有關重新起草的詳細資訊，請參 [閱刪除資源](../../developing/using/deleting-a-resource.md)。

   >[!NOTE]
   >
   >當您 **[!UICONTROL Cancel re-draft]** 要重新草擬的資源仍包含其他資源的連結，且其狀態為「已發佈」時，就可使用此選項。 此選項允許您恢復「重新繪製」進程。 然後，自訂資源將返回其原始狀態。

* **已發佈**:資源已發佈。 如果資源在上次修改日期之後被修改，則會顯示一條消息，要求您重新發佈資源，以便考慮到最新修改。

此欄 **[!UICONTROL Do not publish latest modifications]** 位可防止在未來發佈期間考慮修改。

可以在自定義資源定義中配置此欄位。
