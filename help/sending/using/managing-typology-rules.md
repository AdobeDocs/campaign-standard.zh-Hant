---
title: 管理排版規則
description: 瞭解如何使用類型學規則。
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
source-git-commit: 7f5bc442b1dae467a6b6de3e048531940f75031f
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 6%

---


# 管理排版規則 {#managing-typology-rules}

## 關於類型學規則 {#about-typology-rules}

類型學規則是商業規則，可讓您在傳送訊息前先對訊息執行檢查和篩選。 可用的類型學規則類型有：

* **篩選規則** : 此類型的規則允許您根據查詢中定義的條件排除郵件目標的一部分，如已發送一定數量電子郵件的隔離配置檔案或配置檔案。 如需詳細資訊，請參閱[本章節](../../sending/using/filtering-rules.md)。

* **疲勞規則** : 此類型的規則可讓您定義每個描述檔的訊息數目上限，以避免過度索取。 如需詳細資訊，請參閱[本章節](../../sending/using/fatigue-rules.md)。

* **控制規則** : 此類規則可讓使用者在傳送訊息之前檢查訊息的有效性和品質，例如字元顯示、SMS訊息大小、位址格式等。 如需詳細資訊，請參閱[本章節](../../sending/using/control-rules.md)。

「 > > > >」功能表 **[!UICONTROL Administration]** 下方 **[!UICONTROL Channels]** 提供 **[!UICONTROL Typologies]** 排版規 **[!UICONTROL Typology rules]** 則。

依預設，有數種現成可用的篩 **選****和控制** 排版規則。 這些規則在篩選規則和 [控制規則](../../sending/using/fatigue-rules.md)[各節中詳細說明](../../sending/using/control-rules.md) 。

您可以根據需要修改現有的排版規則或建立新規則（規則除外）, **[!UICONTROL Control]** 這些規則是唯讀的且無法修改。

## 建立排版規則 {#creating-a-typology-rule}

建立排版規則的主要步驟如下：

1. 存取 **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Typologies]** / **[!UICONTROL Typology rules]** menu，然後按一下 **[!UICONTROL Create]**。

   ![](assets/typology_create-rule.png)

1. 輸入類型 **[!UICONTROL Label]**&#x200B;學，然後指 **[!UICONTROL Channel]** 定應套用規則的項目。

   ![](assets/typology-rule-label.png)

1. 指定排版規 **[!UICONTROL Type]**&#x200B;則，然後根據您的需求進行設定。 請注意，排版規則設定視其類型而異。 如需詳細資訊，請參閱「篩選 **[規則](../../sending/using/filtering-rules.md)**」**[&#x200B;和「疲乏規則](../../sending/using/fatigue-rules.md)** 」區段。

1. 選擇要包含新規則的類型。 若要這麼做，請選取標 **[!UICONTROL Typologies]** 簽，然後按一下 **[!UICONTROL Create element]** 按鈕。

   ![](assets/typology-typologies-tab.png)

1. 選取所要的排版，然後按一下 **[!UICONTROL Confirm]**。

   ![](assets/typology-link.png)

1. 在選取所有類型後，按一下以 **[!UICONTROL Create]** 確認類型規則的建立。

## 排版規則執行順序 {#typology-rules-execution-order}

排版規則會依定位、分析和訊息個人化階段期間指定的順序執行。

在標準操作模式下，規則按以下順序應用：

1. 控制規則（如果規則是在定位開始時套用）。
1. 篩選規則:

   * 地址限定的原生應用程式規則： 塊清單上的已定義地址／未驗證地址／地址／隔離地址／地址質量。
   * 篩選由使用者定義的規則。

1. 控制規則（如果規則在定位結束時套用）。
1. 控制規則（如果這些規則在個人化開始時套用）。
1. 控制規則（如果這些規則在個人化結束時套用）。

不過，您可以調整每個類型學中相同類型規則的執行順序。 事實上，當在相同的訊息處理階段執行多個規則時，您可以選擇套用規則的順序。

例如，執行順序位於20的篩選規則將在執行順序位於30的篩選規則之前執行。

在類型 **[!UICONTROL Properties]** 學規則中，您可以設定其執行順序。 當必須套用數個規則時，每個規則的執行順序會決定要先處理的規則。 有關詳細資訊，請參閱「類 [型規則執行順序](#typology-rules-execution-order) 」部分。

![](assets/typology_rule-active.png)

如果您不想在分析規則所關 **[!UICONTROL Properties]** 注的訊息時套用規則，則可透過其停用分類規則。

![](assets/typology_rule-order.png)