---
title: 資源狀態
seo-title: 資源狀態
description: 資源狀態
seo-description: 根據其出版狀態探索不同的資源狀態。
page-status-flag: 從未啓動
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 開發
content-type: reference
topic-tags: 關於自訂資源
discoiquuid: 855164777-1b95-4273-a0 a7-d2 cbb9950 afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Resource statuses{#resource-statuses}

資源可以根據其出版或啓動狀態有不同的狀態。

There are two columns dedicated to displaying these statuses in the **[!UICONTROL Custom resources]** screen.

![](assets/schema_colonne_1.png)

**出版物狀態**

* **草稿**：資源剛建立或重新草擬。若要建立資料庫表格以及對應的API，必須重新發佈資源。如果正在重新草擬資源，則會在出版物步驟後自動轉換為非活動中。
* **擱置中的重新草稿**：資源重新草擬。重新草稿程序將會發生在下一出版物期間。重新草擬不可撤銷。在重新草擬時，有數個警告訊息會警告使用者，然後準備發佈。

   For more on re-drafting, see [Deleting a resource](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >**[!UICONTROL Cancel re-draft]** 如果您要重新草稿的資源仍包含透過其他資源(已「已發佈」狀態)的連結，則可使用此選項。此選項可讓您回復「重新草稿」程序。然後自訂資源就會返回其原始狀態。

* **已發佈**：資源已發佈。如果資源在最後修改日期後經過修改，則會出現一則訊息，要求使用者重新發佈，並考量最新修改。

**[!UICONTROL Do not publish latest modifications]** 欄位可防止在日後的出版物中納入修改。

此欄位可在自訂資源定義中設定。
