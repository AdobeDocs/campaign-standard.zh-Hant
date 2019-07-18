---
title: 篩選規則
seo-title: 篩選規則
description: 篩選規則
seo-description: 使用篩選規則來調整訊息的對象。
page-status-flag: 從未啓動
uuid: ed eea62-3a47-4318-ae22-d82 aa857448 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 使用typology規則
discoiquuid: 7ddaf36c-74e6-4501-b3 b-3d03 f005 aa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Filtering rules{#filtering-rules}

篩選規則可讓您根據查詢中定義的條件(例如已傳送特定數目電子郵件的隔離設定檔或描述檔)排除訊息目標的一部分。

例如，您可以篩選電子報訂閱者，讓低於18歲的訂閱者不會收到通訊。

## Creating a filtering rule {#creating-a-filtering-rule}

1. Create a **Filtering** typology rule, one that can be applied on all communication channels.

   ![](assets/typology_create-rule.png)

1. **[!UICONTROL Filtering criteria]** 在標籤中，選取 **[!UICONTROL Subscription]** 類別中的訂閱。

   ![](assets/typology_create-rule-subscription.png)

1. In the **[!UICONTROL Explorer]** tab of the query editor, drag and drop the **[!UICONTROL Subscriber]** node into the main part of the screen.

   ![](assets/typology_create-rule-subscriber.png)

1. Select the **[!UICONTROL Age]** field and define the filtering conditions so that the age of the subscribers is 18 or above.

   ![](assets/typology_create-rule-age.png)

1. **[!UICONTROL Typologies]** 在標籤中，將此規則連結至打字。

   ![](assets/typology_create-rule-typology.png)

1. 請確定您要使用的傳送範本中選取相關的印刷文字。

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >To access the delivery templates, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** in the navigation menu, which can be accessed via the Adobe Campaign logo.

每當訊息中使用此規則時，被視為未成年人的訂閱者將自動被排除在外。

## Restricting the applicability of a filtering rule {#restricting-the-applicability-of-a-filtering-rule}

您可以根據訊息的傳送限制篩選規則的適用性。

1. In the typology rule's **[!UICONTROL Application criteria]** tab, uncheck the **[!UICONTROL Apply the rule on all deliveries]** option, which is enabled by default.

   ![](assets/typology_limit.png)

1. 使用查詢編輯器來定義篩選。例如，您只能在標籤以指定字詞開頭或ID包含特定字母的訊息上套用規則。

   ![](assets/typology_limit-rule.png)

在此情況下，規則只會套用至對應於定義標準的訊息。

## Default deliverability exclusion rules {#default-deliverability-exclusion-rules}

Two filtering rules are available by default: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) and **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). 在電子郵件分析期間，這些規則會比較收件者電子郵件地址，其中包含在傳送能力例項管理之加密全域抑制清單中所包含的隱含位址或網域名稱。如果有相符項目，則訊息不會傳送給該收件者。

這是為了避免因為惡意活動(尤其是使用Spamtrap)而列入黑名單。例如，如果使用Spamatch訂閱您的其中一個Web表格，確認電子郵件會自動傳送至該Spamatch，而這會導致您的地址自動列入黑名單。

>[!NOTE]
>
>全域抑制清單中包含的位址和網域名稱會隱藏。傳送分析記錄檔中只會指出已排除收件者的數目。

