---
title: 篩選規則
description: 使用篩選規則來調整訊息的對象。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 43e97f3c-ed82-4fcc-ac0d-fcee6a22da35
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 3%

---

# 篩選規則 {#filtering-rules}

篩選規則可讓您根據查詢中定義的條件排除訊息目標的一部分，例如已隔離的設定檔，或已傳送特定數量之電子郵件的設定檔。

## 預設篩選型別規則 {#default-filtering-typology-rules}

下表提供有關現成可用篩選規則及其相關管道的資訊。

| 標籤 | 管道 | 說明 |
| ---------|----------|---------|
| **[!UICONTROL Address not specified]** | 全部 | 排除未指定地址（電子郵件、郵寄地址等）的目標母體。 （根據選取的管道）。 |
| **[!UICONTROL Address on denylist]** | 全部 | 排除封鎖清單上的地址。 |
| **[!UICONTROL Duplicate]** | 全部 | 根據目標母體&#x200B;**[!UICONTROL Address]**&#x200B;欄位排除重複專案。 |
| **[!UICONTROL Exclude mobile applications]** | 行動應用程式 | 排除與訊息中定義的行動應用程式不符的應用程式訂閱。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | 應用程式內 | 排除與訊息（應用程式內範本）中定義的行動應用程式不符的應用程式訂閱。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | 應用程式內 | 排除與訊息中定義的行動應用程式不符的應用程式訂閱（應用程式內廣播範本） |
| **[!UICONTROL Exclude mobile applications for Push]** | 行動應用程式 | 排除與訊息中定義的行動應用程式不符的應用程式訂閱（針對推播） |
| **[!UICONTROL Quarantined address]** | 全部 | 排除隔離的地址。 |
| **[!UICONTROL Target limited in size]** | 全部 | 檢查是否已達到目標的傳遞大小上限。 套用至啟用「傳遞限制」選項的直接郵件傳遞。 |

除了這些預設篩選規則外，還提供兩個排除規則：

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** )。

在電子郵件分析期間，這些規則會將收件者電子郵件地址與包含在加密全域隱藏清單（在傳遞能力執行個體中管理）中的禁止地址或網域名稱進行比較。 如果有相符專案，則不會傳送訊息給該收件者。

這是為了避免因惡意活動（尤其是使用Spamtrap）而加入封鎖清單。 例如，如果使用Spamtrap透過您的網路表單進行訂閱，則會自動傳送確認電子郵件給該Spamtrap，而您的地址會自動新增至封鎖清單中。

>[!NOTE]
>
>全域隱藏清單中包含的位址和網域名稱會隱藏。 傳遞分析記錄中只會指出已排除的收件者數量。

## 建立篩選規則 {#creating-a-filtering-rule}

您可以視需要建立自己的篩選規則。 例如，您可以篩選電子報的目標母體，這樣18歲以下的訂閱者就不會收到通訊。

若要建立篩選型別規則，請遵循下列步驟：

1. 建立新的型別規則。 建立型別規則的主要步驟在[本節](../../sending/using/managing-typology-rules.md)中有詳細說明。

1. 選取&#x200B;**[!UICONTROL Filtering]**&#x200B;規則型別，然後指定所要的管道。

1. 在&#x200B;**[!UICONTROL Filtering criteria]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Subscription]**&#x200B;類別中的訂閱。

   ![](assets/typology_create-rule-subscription.png)

1. 在查詢編輯器的&#x200B;**[!UICONTROL Explorer]**&#x200B;索引標籤中，將&#x200B;**[!UICONTROL Subscriber]**&#x200B;節點拖放到畫面的主要部分。

   ![](assets/typology_create-rule-subscriber.png)

1. 選取&#x200B;**[!UICONTROL Age]**&#x200B;欄位並定義篩選條件，讓訂閱者的年齡少於18歲。

   ![](assets/typology_create-rule-age.png)

1. 在&#x200B;**[!UICONTROL Typologies]**&#x200B;標籤中，將此規則連結至型別。

   ![](assets/typology_create-rule-typology.png)

1. 確保在您要使用的傳遞或傳遞範本中選取型別。 如需詳細資訊，請參閱[本章節](../../sending/using/managing-typologies.md#applying-typologies-to-messages)。

   ![](assets/typology_template.png)

每當在訊息中使用此規則時，系統都會自動排除被視為次要的訂閱者。

## 設定篩選規則的目標內容 {#configuring-filtering-rules-targeting-context}

Campaign Standard可讓您設定&#x200B;**目標定位**&#x200B;和&#x200B;**篩選**&#x200B;維度，以根據您要鎖定的資料使用。

若要這麼做，請開啟型別規則的屬性，然後存取&#x200B;**[!UICONTROL Advanced information]**&#x200B;區段。

依預設，會對&#x200B;**[!UICONTROL Profiles]**&#x200B;執行篩選。 例如，如果規則是針對行動應用程式，則&#x200B;**[!UICONTROL Filtering dimension]**&#x200B;可以變更為&#x200B;**[!UICONTROL Subscriptions to an application]**。

![](assets/typology_rule-order_2.png)

## 限制篩選規則的適用性 {#restricting-the-applicability-of-a-filtering-rule}

您可以根據要傳送的消息限制篩選規則的適用性。

1. 在型別規則的&#x200B;**[!UICONTROL Application criteria]**&#x200B;標籤中，取消勾選&#x200B;**[!UICONTROL Apply the rule on all deliveries]**&#x200B;選項，該選項預設為啟用。

   ![](assets/typology_limit.png)

1. 使用查詢編輯器來定義篩選器。 例如，您只能對標籤以特定字詞開頭或ID包含特定字母的訊息套用規則。

   ![](assets/typology_limit-rule.png)

在此情況下，規則只會套用至對應已定義條件的訊息。
