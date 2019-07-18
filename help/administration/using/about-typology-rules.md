---
title: 關於打字規則
seo-title: 關於打字規則
description: 關於打字規則
seo-description: 瞭解類文規則如何在Adobe Campaign中運作。
page-status-flag: 從未啓動
uuid: a98ebc36-172d-4f46-b6 ee-b2636 a1007 c9
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 使用typology規則
discoiquuid: 2590d94c-51ef-4c0f-b1 ec-c2837 e94 da40
context-tags: typolology，概觀；TypologyRule，main；Typology規則，概述
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# About typology rules{#about-typology-rules}

字型是一組規則，在訊息分析階段中執行，可讓目標、內容和設定進行驗證：主旨、URL、影像、取消訂閱連結、校對大小等。

在Adobe Campaign中，每個訊息都包含字型的連結。This link is defined in the advanced parameters of the delivery template's properties (for more on this, refer to the [Preparation](../../administration/using/configuring-email-channel.md#preparation) section).

>[!NOTE]
>
>每個訊息只能被指派一個字元。

For each typology, the **[!UICONTROL Typology rules]** section lists the set of rules for this typology.

![](assets/typology_typo-rule-list.png)

## Managing typologies {#managing-typologies}

應用程式中預設會顯示數個字體。根據您的需求，您可以建立自己的字體或修改現有的字體。

1. Access the **[!UICONTROL List of typologies]** from the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** menu.
1. 選取字型來修改其內容和屬性，或建立新屬性。

   ![](assets/typology_list.png)

1. 定義類型的類型。Typologes可以是標準或篩選類型。
1. Add the typology rules you need using the **[!UICONTROL Add an element]** button or remove the ones you do not want to use.

   您可以修改規則套用至給定印刷符號的順序。若要這麼做，請移動元素來修改顯示在畫面上的順序。然後會自動重新計算對應至執行順序的數字。The rule application mode is presented in the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

   顯示在此畫面上的規則可透過唯讀模式存取。

您的印刷樣式已準備好使用。您可以在訊息屬性或訊息範本屬性中選取它。

>[!NOTE]
>
>**[!UICONTROL IP affinity]** 欄位可讓您根據設定來管理相關性。這些定義在例項的設定檔案中。如果您想要使用相關性，請聯絡管理員。

## Typology rules {#typology-rules}

Typology規則是在訊息準備期間套用的業務規則。它們可用來檢查訊息是否有效並符合您的品質標準。他們也會檢查目標讀者是否有資格收到訊息。

Typology rules are available under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]** menu.

規則有兩種類型：

* **篩選** 規則：允許您根據查詢中定義的條件排除訊息目標的一部分，例如已傳送特定數目電子郵件的隔離設定檔或描述檔。See [Filtering rules](../../administration/using/filtering-rules.md).
* **疲勞** 規則：可讓您定義每個描述檔的最大訊息數，以避免過度吸引他們。See [Fatigue rules](../../administration/using/fatigue-rules.md).
* **控制** 規則：允許使用者在傳送訊息之前檢查其有效性和品質，例如字元顯示、SMS訊息大小、地址格式等。See [Control rules](../../administration/using/control-rules.md).

類文規則只能套用到一個渠道或所有渠道。

![](assets/typology_channel.png)

In the **[!UICONTROL Properties]** of a typology rule, you can set its execution order. 必須套用幾個規則時，每個規則的執行順序決定要先處理的規則。For more on this, refer to the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

![](assets/typology_rule-active.png)

A typology rule can be deactivated through its **[!UICONTROL Properties]** if you do not want the rule to be applied at the moment that the messages concerned by the rule are analyzed.

![](assets/typology_rule-order.png)

**[!UICONTROL Targeting context]** 在類別中，您可以選取 **定位維度** 和 **篩選維度** ，視您要定位的資料而定。

By default, filtering is carried out on the **[!UICONTROL Profiles]**. For example, if the rule is aimed at a mobile application, the **[!UICONTROL Filtering dimension]** can be changed to **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

>[!NOTE]
>
>無法修改控制規則的內容，它們基本上是使用的篩選規則。

## Typology rules execution order {#typology-rules-execution-order}

類文規則是按照定位、分析和訊息個人化階段中指定的順序執行。

在標準作業模式中，規則會套用至下列順序：

1. 控制規則(如果在定位開始時套用)。
1. 篩選規則：

   * 解決方案資格的原生應用程式規則：已定義地址/未驗證位址/黑名單位址/四分化位址/地址品質。
   * 篩選使用者定義的規則。

1. 控制規則(如果在定位結束時套用)。
1. 控制規則(如果在個人化開始時套用)。
1. 控制規則(如果在個人化結束時套用)。

不過，您可以調整每個印刷項目中相同類型規則的執行順序。的確，當同一個訊息處理階段中執行多個規則時，您可以選擇套用它們的順序。

例如，將執行順序定位在數字20的篩選規則將在執行順序設為編號30的篩選規則之前執行。
