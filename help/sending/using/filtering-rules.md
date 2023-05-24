---
title: 篩選規則
description: 使用篩選規則來細化郵件的受眾。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 43e97f3c-ed82-4fcc-ac0d-fcee6a22da35
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 3%

---

# 篩選規則 {#filtering-rules}

過濾規則允許您根據查詢中定義的條件排除郵件目標的一部分，例如已發送一定數量電子郵件的隔離配置檔案或配置檔案。

## 預設篩選類型規則 {#default-filtering-typology-rules}

下表提供了有關出廠設定過濾規則及其相關通道的資訊。

| 標籤 | 通道 | 說明 |
| ---------|----------|---------|
| **[!UICONTROL Address not specified]** | 全部 | 排除沒有指定地址（電子郵件、郵政地址等）的目標人口。 根據所選頻道)。 |
| **[!UICONTROL Address on denylist]** | 全部 | 排除denylist上的地址。 |
| **[!UICONTROL Duplicate]** | 全部 | 根據目標人口排除重複項 **[!UICONTROL Address]** 的子菜單。 |
| **[!UICONTROL Exclude mobile applications]** | 行動應用程式 | 排除與消息中定義的移動應用程式不匹配的應用程式訂閱。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | 應用程式內 | 排除與消息（In-App模板）中定義的移動應用程式不匹配的應用程式訂閱。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | 應用程式內 | 排除與消息中定義的移動應用程式不匹配的應用程式訂閱（In-App廣播模板） |
| **[!UICONTROL Exclude mobile applications for Push]** | 行動應用程式 | 排除與消息中定義的移動應用程式不匹配的應用程式訂閱（用於推送） |
| **[!UICONTROL Quarantined address]** | 全部 | 排除隔離的地址。 |
| **[!UICONTROL Target limited in size]** | 全部 | 檢查是否達到目標的最大傳遞大小。 應用於已激活「交貨限制」選項的直接郵件交付。 |

除這些預設過濾規則外，還有兩個排除規則：

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

在電子郵件分析期間，這些規則將收件人電子郵件地址與包含在可傳送性實例中管理的加密全局禁止清單中的禁止地址或域名進行比較。 如果存在匹配項，則不會將消息發送到該收件人。

這是為了避免由於惡意活動而被添加到密鑰清單，特別是使用垃圾郵件陷阱。 例如，如果使用Spamtrap通過您的一個Web表單訂閱，則會自動向該Spamtrap發送確認電子郵件，這將導致您的地址被自動添加到密鑰清單中。

>[!NOTE]
>
>全局隱藏清單中包含的地址和域名將被隱藏。 在傳遞分析日誌中只指示排除的收件人數。

## 建立篩選規則 {#creating-a-filtering-rule}

您可以根據需要建立自己的過濾規則。 例如，您可以過濾新聞通訊的目標人數，使18歲以下的訂閱者永遠不會收到通信。

要建立篩選類型規則，請執行以下步驟：

1. 建立新類型規則。 建立類型規則的主要步驟在中詳細介紹 [此部分](../../sending/using/managing-typology-rules.md)。

1. 選擇 **[!UICONTROL Filtering]** 規則類型，然後指定所需的通道。

1. 在 **[!UICONTROL Filtering criteria]** 頁籤，選擇 **[!UICONTROL Subscription]** 的子菜單。

   ![](assets/typology_create-rule-subscription.png)

1. 在 **[!UICONTROL Explorer]** 頁籤，拖放 **[!UICONTROL Subscriber]** 節點進入螢幕的主部。

   ![](assets/typology_create-rule-subscriber.png)

1. 選擇 **[!UICONTROL Age]** 定義過濾條件，使用戶的年齡小於18。

   ![](assets/typology_create-rule-age.png)

1. 在 **[!UICONTROL Typologies]** 頁籤，將此規則連結到類型。

   ![](assets/typology_create-rule-typology.png)

1. 確保在要使用的交貨或交貨模板中選擇了該類型。 如需詳細資訊，請參閱[本章節](../../sending/using/managing-typologies.md#applying-typologies-to-messages)。

   ![](assets/typology_template.png)

無論何時在消息中使用此規則，被視為未成年人的訂閱者都將自動被排除。

## 配置篩選規則的目標上下文 {#configuring-filtering-rules-targeting-context}

Campaign Standard允許您配置  **目標** 和 **篩選** 要使用的維，具體取決於要瞄準的資料。

為此，請開啟類型規則的屬性，然後訪問 **[!UICONTROL Advanced information]** 的子菜單。

預設情況下，對 **[!UICONTROL Profiles]**。 例如，如果規則針對移動應用程式， **[!UICONTROL Filtering dimension]** 可以更改為 **[!UICONTROL Subscriptions to an application]**。

![](assets/typology_rule-order_2.png)

## 限制篩選規則的適用性 {#restricting-the-applicability-of-a-filtering-rule}

可以根據要發送的消息限制過濾規則的適用性。

1. 在類型規則中 **[!UICONTROL Application criteria]** 頁籤 **[!UICONTROL Apply the rule on all deliveries]** 的子菜單。

   ![](assets/typology_limit.png)

1. 使用查詢編輯器定義篩選器。 例如，您只能對標籤以給定單詞開頭或其ID包含某些字母的消息應用規則。

   ![](assets/typology_limit-rule.png)

在這種情況下，該規則僅應用於與定義的條件對應的消息。
