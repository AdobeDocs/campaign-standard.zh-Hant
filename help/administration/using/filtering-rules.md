---
title: 篩選規則
description: 使用篩選規則來調整訊息的讀者。
page-status-flag: 從未激活
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 參考
topic-tags: 使用類型學規則
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 篩選規則{#filtering-rules}

篩選規則允許您根據查詢中定義的條件排除郵件目標的一部分，如已發送一定數量電子郵件的隔離配置檔案或配置檔案。

例如，您可以篩選電子報訂閱者，讓18歲以下的訂閱者永遠無法收到通訊。

## 建立篩選規則 {#creating-a-filtering-rule}

1. 建立可 **套用至** 所有通訊管道的篩選類型規則。

   ![](assets/typology_create-rule.png)

1. 在標籤 **[!UICONTROL Filtering criteria]** 中，選擇類別中的訂 **[!UICONTROL Subscription]** 閱。

   ![](assets/typology_create-rule-subscription.png)

1. 在查 **[!UICONTROL Explorer]** 詢編輯器的頁籤中，將節 **[!UICONTROL Subscriber]** 點拖放到螢幕的主部分。

   ![](assets/typology_create-rule-subscriber.png)

1. 選取 **[!UICONTROL Age]** 欄位並定義篩選條件，讓訂閱者的年齡在18歲或以上。

   ![](assets/typology_create-rule-age.png)

1. 在標籤 **[!UICONTROL Typologies]** 中，將此規則連結至類型學。

   ![](assets/typology_create-rule-typology.png)

1. 請務必在您要使用的傳送範本中選取相關的類型。

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >若要存取傳送範本，請在導覽功 **[!UICONTROL Resources]** 能表 **[!UICONTROL Templates]** 中選取&gt;，此導覽功能表可透過Adobe Campaign標誌存取。

每當在訊息中使用此規則時，會自動排除被視為未成年者的訂閱者。

## 限制篩選規則的適用性 {#restricting-the-applicability-of-a-filtering-rule}

您可以根據要傳送的訊息限制篩選規則的適用性。

1. 在排版規則的標 **[!UICONTROL Application criteria]** 簽中，取消選 **[!UICONTROL Apply the rule on all deliveries]** 中選項，該選項預設啟用。

   ![](assets/typology_limit.png)

1. 使用查詢編輯器來定義篩選器。 例如，您只能對標籤以指定字詞開頭或其ID包含特定字母的訊息套用規則。

   ![](assets/typology_limit-rule.png)

在此情況下，規則只會套用至對應於已定義准則的訊息。

## 預設可傳遞性排除規則 {#default-deliverability-exclusion-rules}

預設提供兩個篩選規則： **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) **[!UICONTROL Exclusion of domains]** 和( **[!UICONTROL domainExclusions]** )。 在電子郵件分析期間，這些規則會比較收件者電子郵件地址與傳送能力例項中管理之加密全域隱藏清單中所包含之禁止地址或網域名稱。 如果有相符項目，則不會傳送訊息給該收件者。

這是為了避免因惡意活動而列入黑名單，尤其是使用Spamtrap。 例如，如果使用Spamtrap來透過您的其中一個Web表單進行訂閱，系統會自動傳送確認電子郵件給該Spamtrap，這會自動將您的位址列入黑名單。

>[!NOTE]
>
>全局隱藏清單中包含的地址和域名將被隱藏。 傳送分析記錄中只會指出已排除的收件者數目。

