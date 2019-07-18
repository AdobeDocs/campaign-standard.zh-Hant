---
title: 設定篩選定義
seo-title: 設定篩選定義
description: 設定篩選定義
seo-description: 探索篩選功能以管理大型資料集。
page-status-flag: 從未啓動
uuid: c9db95Fe-e9 aa-40f8-9c0 a-e74 bb21 ac14 b
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 開發
content-type: reference
topic-tags: 新增或延伸-資源
discoiquuid: 993ab bd-e05 f-468e-9ef8-a603761247 f
context-tags: CusResource，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring filter definition{#configuring-filter-definition}

**[!UICONTROL Filter definition]** 在標籤中，您可以建立進階篩選，讓使用者在建立複雜查詢時直接存取，例如定義觀眾時。

此步驟不是強制性的，因為您仍可透過工作流程、觀眾和REST API填入資源並存取資料。

![](assets/custom_resource_filter-definition.png)

這些篩選器會以預先設定規則的形式用於查詢編輯器中。它們允許您限制取得所需設定所需的步驟數，這對重復的區段提及特別有用。

例如，您可以建立篩選器，讓您在過去三個月內選取大於特定金額的所有交易。

To do this, you need to extend the **[!UICONTROL Profiles]** resource and define a filter linking to a transaction table (that you have previously created) with a rule indicating that the transaction price must be greater than or equal to a given parameter and that the transaction date must fall within a range corresponding to the last three months.

1. 確定您建立並發佈交易表格。See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >此程序使用自訂交易表格的範例。為符合您的業務需求，請加以調整。

1. Before defining a filter related to the transaction table in the **[!UICONTROL Profiles]** resource, make sure you define the link to this table and publish your changes. See [Defining links with other resources](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) and [Updating the database structure](../../developing/using/updating-the-database-structure.md).
1. In the **[!UICONTROL Definition]** tab of your new filter's definition screen, select the transaction table.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. **[!UICONTROL Add a rule - Profiles/Transactions]** 在視窗中，將交易表格拖放至工作區。在顯示的下一個視窗中，選取您要使用的欄位。

   ![](assets/custom_resource_filter-definition_example-field.png)

1. In the **[!UICONTROL Optional parameter settings]** of the **[!UICONTROL Add a rule - Transactions]** window, check the **[!UICONTROL Switch to parameters]** box.

   In the **[!UICONTROL Filter conditions]**, select the **[!UICONTROL Greater than or equal to]** operator. **[!UICONTROL Parameters]** 在欄位中輸入名稱，然後按一下加號以建立新參數。

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. 確認您的變更。此定義對應至可設定欄位，使用者必須稍後填寫才能執行查詢。

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. 將此規則與另一個規則結合，指定交易日期必須落在與過去三個月對應的範圍內。

   ![](assets/custom_resource_filter-definition_example.png)

1. 選擇將顯示篩選的類別。

   ![](assets/custom_resource_filter-definition_category.png)

1. In the **[!UICONTROL Parameters]** tab of the filter definition screen, modify the description and the label to clearly indicate the subject of your filter to the users. 此資訊將會出現在查詢編輯器中。

   ![](assets/custom_resource_filter-definition_parameters.png)

   如果定義多個可設定欄位，您可以修改其出現在介面中的順序。

1. 儲存變更並發佈資源。For more on this, refer to the [Updating the database structure](../../developing/using/updating-the-database-structure.md) section.

Once the **[!UICONTROL Profiles]** resource extension is published, the users will see this filter under the shortcuts tab in the [query editor](../../automating/using/editing-queries.md) interface.

這可讓使用者在建立電子郵件時輕鬆定義其對象，以傳送給在過去三個月內花費超過一筆金額的所有客戶。

![](assets/custom_resource_filter-definition_email-audience.png)

他們只需要在出現的對話方塊中輸入所要的數量，而不需自行設定。

![](assets/custom_resource_filter-definition_email-audience_filter.png)

