---
title: 關於類型學規則
description: 瞭解Adobe Campaign中的排版規則如何運作。
page-status-flag: 從未激活
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 參考
topic-tags: 使用類型學規則
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: 類型學，概述；類型學規則，主要；類型學規則，概述
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 關於類型學規則{#about-typology-rules}

類型學是一組規則，在消息分析階段執行，允許驗證以下元素的目標、內容和配置：主題、URL、影像、取消訂閱連結、校樣大小等。

在Adobe Campaign中，每則訊息都包含一個類型的連結。 此連結在交付模板屬性的高級參數中定義(有關詳細資訊，請參閱「準 [備](../../administration/using/configuring-email-channel.md#preparation) 」部分)。

>[!NOTE]
>
>每個訊息只能指派單一類型學。

對於每種類型學，本 **[!UICONTROL Typology rules]** 節列出此類型學的規則集。

![](assets/typology_typo-rule-list.png)

## 管理類型 {#managing-typologies}

應用程式預設會顯示幾種類型。 您可以根據自己的需求建立自己的類型或修改現有的類型。

1. 從&gt; **[!UICONTROL List of typologies]** &gt;功能表 **[!UICONTROL Administration]** 存 **[!UICONTROL Channels]** 取 **[!UICONTROL Typologies]** 。
1. 選擇一種類型學以修改其內容和屬性，或者建立新類型學。

   ![](assets/typology_list.png)

1. 定義類型學。 類型可以是「標準」或「篩選」類型。
1. 使用按鈕新增您需要的排 **[!UICONTROL Add an element]** 版規則，或移除您不想使用的規則。

   您可以修改規則在指定類型學中套用的順序。 若要這麼做，請移動元素，以修改元素在畫面上的顯示順序。 然後自動重新計算與執行順序相對應的數字。 規則應用模式顯示在「類型學 [規則」執行順序部分](#typology-rules-execution-order) 。

   此螢幕上顯示的規則可以以只讀模式訪問。

您的排版已準備好使用。 可以在消息屬性或消息模板屬性中選擇它。

>[!NOTE]
>
>欄位 **[!UICONTROL IP affinity]** 可讓您根據您的設定來管理相關性。 這些定義在實例的配置檔案中。 如果您想要使用相關性，請連絡您的管理員。

## 類型學規則 {#typology-rules}

類型學規則是在準備訊息時套用的業務規則。 它們用來檢查訊息是否有效，以及是否符合您的品質標準。 他們也會檢查目標對象的每個成員是否符合接收訊息的資格。

「 &gt; &gt; &gt; &gt;」功能表 **[!UICONTROL Administration]** 下方 **[!UICONTROL Channels]** 提供 **[!UICONTROL Typologies]** 排版規 **[!UICONTROL Typology rules]** 則。

規則有兩種類型：

* **篩選規則** :允許您根據查詢中定義的條件排除郵件目標的一部分，例如已發送一定數量電子郵件的隔離配置檔案或配置檔案。 請參閱 [篩選規則](../../administration/using/filtering-rules.md)。
* **疲勞規則** :允許您定義每個描述檔的訊息數量上限，以避免過度索取。 請參 [閱疲勞規則](../../administration/using/fatigue-rules.md)。
* **控制規則** :允許用戶在發送前檢查消息的有效性和質量，如字元顯示、SMS消息大小、地址格式等。 請參閱 [控制規則](../../administration/using/control-rules.md)。

排版規則只能套用至一個渠道或所有渠道。

![](assets/typology_channel.png)

在類型 **[!UICONTROL Properties]** 學規則中，您可以設定其執行順序。 當必須套用數個規則時，每個規則的執行順序會決定要先處理的規則。 有關詳細資訊，請參閱「類 [型規則執行順序](#typology-rules-execution-order) 」部分。

![](assets/typology_rule-active.png)

如果您不想在分析規則所關 **[!UICONTROL Properties]** 注的訊息時套用規則，則可透過其停用分類規則。

![](assets/typology_rule-order.png)

在類 **[!UICONTROL Targeting context]** 別中，您可以選取「定 **位」維度和** 「篩選」維度 **** ，視您要定位的資料而定。

依預設，會對進行篩選 **[!UICONTROL Profiles]**。 例如，如果規則針對行動應用程式，則 **[!UICONTROL Filtering dimension]** 可變更為 **[!UICONTROL Subscriptions to an application]**。

![](assets/typology_rule-order_2.png)

## 排版規則執行順序 {#typology-rules-execution-order}

排版規則會依定位、分析和訊息個人化階段期間指定的順序執行。

在標準操作模式下，規則按以下順序應用：

1. 控制規則（如果規則是在定位開始時套用）。
1. 篩選規則:

   * 地址限定的原生應用程式規則：定義地址／未驗證地址／黑名單地址／隔離地址／地址質量。
   * 篩選由使用者定義的規則。

1. 控制規則（如果規則在定位結束時套用）。
1. 控制規則（如果這些規則在個人化開始時套用）。
1. 控制規則（如果這些規則在個人化結束時套用）。

不過，您可以調整每個類型學中相同類型規則的執行順序。 事實上，當在相同的訊息處理階段執行多個規則時，您可以選擇套用規則的順序。

例如，執行順序位於20的篩選規則將在執行順序位於30的篩選規則之前執行。
