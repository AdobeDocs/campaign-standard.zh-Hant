---
title: 關於類型和類型學規則
description: 瞭解Adobe Campaign中的類型和類型學規則如何運作。
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a9c0e3cc4609e747bbfebeb90049862f29c9d8d9

---


# 關於類型和類型學規則{#about-typology-rules}

「促銷活動標準」可讓您將訊息連結至 **類型**，以檢查訊息是否有效並符合您的品質標準。

類型是一組類 **型規則**，在消息分析階段執行。 它們可讓您確定您的電子郵件一律包含特定元素（例如取消訂閱連結或主旨行）或篩選規則，以排除群組不受您預定目標（例如取消訂閱者、競爭者或不忠誠客戶）的影響。

![](assets/typology_messagelink.png)

Campaign Standard提供現成可用的類型和類型學規則。 您也可以視需要建立新規則，並將它們新增至現有或新的類型，以連結至訊息。

建立和套用類型學至訊息的步驟如下：

1. 建立類型學規則(請 [參閱本節](../../sending/using/managing-typology-rules.md#creating-a-typology-rule))。
1. 建立類型並參考您建立的規則(請參 [閱本節](../../sending/using/managing-typologies.md#creating-a-typology))。
1. 設定您的傳送方式，以使用您建立的類型(請參 [閱本節](../../sending/using/managing-typologies.md#applying-typologies-to-messages))。
1. 在消息準備期間，滿足條件時將排除配置檔案。 您可以檢查記錄檔以監控排除。
