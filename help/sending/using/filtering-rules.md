---
title: 篩選規則
description: 使用篩選規則來調整訊息的讀者。
page-status-flag: never-activated
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7f5bc442b1dae467a6b6de3e048531940f75031f
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 1%

---


# 篩選規則 {#filtering-rules}

篩選規則允許您根據查詢中定義的條件排除郵件目標的一部分，如已發送一定數量電子郵件的隔離配置檔案或配置檔案。

## 預設篩選排版規則 {#default-filtering-typology-rules}

下表提供現成可用篩選規則及其相關渠道的相關資訊。

| 標籤 | 頻道 | 說明 |
---------|----------|---------
| **[!UICONTROL Address not specified]** | 全部 | 排除沒有指定地址（電子郵件、郵遞區號等）的目標人口。 )。 |
| **[!UICONTROL Blocklisted address]** | 全部 | 排除塊清單中的地址。 |
| **[!UICONTROL Duplicate]** | 全部 | 根據目標人口欄位排除復 **[!UICONTROL Address]** 本。 |
| **[!UICONTROL Exclude mobile applications]** | 行動應用程式 | 排除不符合訊息中定義之行動應用程式的應用程式訂閱。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | 應用程式內 | 排除不符合訊息（應用程式內範本）中定義之行動應用程式的應用程式訂閱。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | 應用程式內 | 排除不符合訊息中定義之行動應用程式的應用程式訂閱（應用程式內廣播範本） |
| **[!UICONTROL Exclude mobile applications for Push]** | 行動應用程式 | 排除不符合訊息中定義之行動應用程式的應用程式訂閱（針對推播） |
| **[!UICONTROL Quarantined address]** | 全部 | 排除隔離地址。 |
| **[!UICONTROL Target limited in size]** | 全部 | 檢查是否達到目標的最大傳送大小。 套用至啟用「傳送限制」選項的直接郵件傳送。 |

除了這些預設篩選規則外，還有兩個排除規則可供使用：

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

在電子郵件分析期間，這些規則會比較收件者電子郵件地址與傳送能力例項中管理之加密全域隱藏清單中所包含之禁止地址或網域名稱。 如果有相符項目，則不會傳送訊息給該收件者。

這是為了避免由於惡意活動（尤其是使用Spamtrap）而添加到阻止清單。 例如，如果使用Spamtrap來透過您的其中一個Web表單訂閱，系統會自動傳送確認電子郵件給該Spamtrap，如此會自動將您的位址新增至封鎖清單。

>[!NOTE]
>
>全局隱藏清單中包含的地址和域名將被隱藏。 傳送分析記錄中只會指出已排除的收件者數目。

## 建立篩選規則 {#creating-a-filtering-rule}

您可以根據自己的需求建立自己的篩選規則。 例如，您可以篩選電子報的目標人口，讓18歲以下的訂閱者永遠無法收到通訊。

若要建立篩選排版規則，請遵循下列步驟：

1. 建立新的排版規則。 本節將詳細說明建立排版規則的 [主要步驟](../../sending/using/managing-typology-rules.md)。

1. 選取規 **[!UICONTROL Filtering]** 則類型，然後指定所要的渠道。

1. 在標籤 **[!UICONTROL Filtering criteria]** 中，選擇類別中的訂 **[!UICONTROL Subscription]** 閱。

   ![](assets/typology_create-rule-subscription.png)

1. 在查 **[!UICONTROL Explorer]** 詢編輯器的頁籤中，將節 **[!UICONTROL Subscriber]** 點拖放到螢幕的主部分。

   ![](assets/typology_create-rule-subscriber.png)

1. 選取 **[!UICONTROL Age]** 欄位並定義篩選條件，讓訂閱者的年齡在18歲或以上。

   ![](assets/typology_create-rule-age.png)

1. 在標籤 **[!UICONTROL Typologies]** 中，將此規則連結至類型學。

   ![](assets/typology_create-rule-typology.png)

1. 請務必在您要使用的傳送或傳送範本中選取印刷樣式。 如需詳細資訊，請參閱[本章節](../../sending/using/managing-typologies.md#applying-typologies-to-messages)。

   ![](assets/typology_template.png)

每當在訊息中使用此規則時，會自動排除被視為未成年者的訂閱者。

## 設定篩選規則的定位內容 {#configuring-filtering-rules-targeting-context}

「促銷活動標準」可讓您設 **定「定位** 」和「篩 **** 選」維度，以根據您要定位的資料而使用。

若要這麼做，請開啟排版規則的屬性，然後存取該 **[!UICONTROL Advanced information]** 區段。

依預設，會對進行篩選 **[!UICONTROL Profiles]**。 例如，如果規則針對行動應用程式，則 **[!UICONTROL Filtering dimension]** 可變更為 **[!UICONTROL Subscriptions to an application]**。

![](assets/typology_rule-order_2.png)

## 限制篩選規則的適用性 {#restricting-the-applicability-of-a-filtering-rule}

您可以根據要傳送的訊息限制篩選規則的適用性。

1. 在排版規則的標 **[!UICONTROL Application criteria]** 簽中，取消選 **[!UICONTROL Apply the rule on all deliveries]** 中選項，該選項預設啟用。

   ![](assets/typology_limit.png)

1. 使用查詢編輯器來定義篩選器。 例如，您只能對標籤以指定字詞開頭或其ID包含特定字母的訊息套用規則。

   ![](assets/typology_limit-rule.png)

在此情況下，規則只會套用至對應於已定義准則的訊息。
