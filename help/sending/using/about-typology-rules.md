---
title: 關於類型與類型規則
description: 探索 Adobe Campaign 中的類型與類型規則如何運作。
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
translation-type: ht
source-git-commit: 396084934a41d103eecd6fe141c700c118000f75
workflow-type: ht
source-wordcount: '190'
ht-degree: 100%

---


# 關於類型與類型規則{#about-typology-rules}

Campaign Standard 可讓您將訊息連結至&#x200B;**類型**，以檢查訊息是否有效並符合您的品質條件。

類型是一組&#x200B;**類型規則**，在訊息分析階段執行。它們可讓您確定您的電子郵件一律包含特定元素（例如，取消訂閱連結或主旨行）或篩選規則，以排除群組不受您預定目標（如取消訂閱者、競爭者或不忠誠客戶）的影響。

![](assets/typology_messagelink.png)

Campaign Standard 提供就緒可使用的類型與類型規則。您也可以視需要建立新規則，並將它們新增至現有或新的類型，以連結至訊息。

建立與套用類型至訊息的步驟如下：

1. 建立類型規則（請參閱[本區段](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)）。
1. 建立類型並參考您建立的規則（請參閱[本區段](../../sending/using/managing-typologies.md#creating-a-typology)）。
1. 設定您的傳遞方式，以使用您建立的類型（請參閱[本區段](../../sending/using/managing-typologies.md#applying-typologies-to-messages)）。
1. 在訊息準備的期間，符合條件時將排除設定檔。您可以檢查日誌以監控排除。
