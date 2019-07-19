---
title: 使用復合識別金鑰來呼叫資源
seo-title: 使用復合識別金鑰來呼叫資源
description: 使用復合識別金鑰來呼叫資源
seo-description: 瞭解如何使用復合識別金鑰來呼叫資源
translation-type: tm+mt
source-git-commit: 8aea0483bcb1b104e5bd2b13426a1ac590c8efaf

---


# 使用復合識別金鑰來呼叫資源

在某些情況下，您可能需要為資源定義由兩個欄位組成的識別索引鍵。在設定識別金鑰後，您必須設定篩選定義，以便使用此識別金鑰來呼叫資源(來自Campaign Standard介面或API)。

In this use case, the **Profile** resource has been extended with custom **"CRM ID"** and **"category"** field. 我們將為描述檔資源建立一個識別金鑰，由這兩個欄位組成。然後，我們將設定篩選定義，以便使用識別金鑰存取描述檔資源。

此使用案例的主要步驟為：

1. 根據這兩個欄位，設定描述檔資源的識別索引鍵。
1. 設定篩選定義，以便使用其識別金鑰呼叫描述檔資源。
1. 從介面或API呼叫描述檔資源。

相關主題：

* [建立或擴充資源](../../developing/using/creating-or-extending-the-resource.md)
* [定義識別金鑰](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign Standard REST API](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## 步驟1：設定識別金鑰

>[!NOTE]
> Global concepts when configuring identification keys are detailed in [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. 在設定識別金鑰之前，請確定資源已與所需欄位一起延伸，並已發佈。For more on this, refer to [this section](../../developing/using/creating-or-extending-the-resource.md).

1. Go to the **[!UICONTROL Administration]** / **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** menu, then open the **[!UICONTROL Profile]** resource.

   ![](assets/uc_idkey1.png)

1. In the **[!UICONTROL Identification keys]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/uc_idkey2.png)

1. Add the two custom "CRM ID" and "Category" fields, then click **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > If you want to display the two custom fields in the profile's interface, configure the **[!UICONTROL Screen definition]** tab. For more on this, refer to [this section](../../developing/using/configuring-the-screen-definition.md).

1. 您現在可以設定篩選定義，以便使用其識別金鑰呼叫資源。

## 步驟2：設定篩選定義

>[!NOTE]
> Global concepts when configuring filter definitions are detailed in [this section](../../developing/using/configuring-filter-definition.md).

1. **[!UICONTROL Filter definition]** 在標籤中，按一下 **[!UICONTROL Add an element]**，然後輸入篩選定義的標籤和ID。

1. 編輯篩選定義的屬性以設定其規則。

   ![](assets/uc_idkey4.png)

1. 將表格拖放至工作區，表格包含識別索引鍵中使用的欄位。

   ![](assets/uc_idkey5.png)

1. Select the first field used in the identification key ("CRM ID"), then activate the **[!UICONTROL Switch to parameters]** option.

   ![](assets/uc_idkey6.png)

1. In the **[!UICONTROL Filter conditions]** section, keep the **[!UICONTROL Equal]** operator, then define the parameter's name and click the plus sign to create it.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 按一下加號按鈕後，參數的名稱就會自動產生。請注意此資訊，因為您需要使用API中的篩選。

1. 請重復上述步驟，連同所有可編譯識別金鑰(「類別」)的欄位，然後儲存您的變更。

   ![](assets/uc_idkey8.png)

1. 篩選定義現在已設定。您可以發佈資源，以便使用篩選。

## 步驟3：根據識別碼來呼叫資源

一旦設定識別金鑰及其篩選定義後，您可以使用促銷活動標準介面或REST API來呼叫資源。

To use the filter definition from the interface, use a **[!UICONTROL Query]** activity in a workflow (see [this section](../../automating/using/query.md)). 然後，該篩選器便可在左側窗格中使用。

![](assets/uc_idkey9.png)

若要使用Campaign Standard REST API的篩選定義，請使用下列語法：

```
GET /profileAndServicesExt/&lt;resourceName&gt;&lt;filterName&gt;?&lt;param1_parameter&gt;=&lt;value&gt;&&lt;param2_parameter&gt;=&lt;value&gt;
```

在我們的案例中，從「Spring」類別擷取描述檔的語法，以及「123456」CRM ID會是：

```
GET https://mc.adobe.io/&lt;ORGANIZATION&gt;/campaign/profileAndServicesExt/profile/identification_key?category_parameter=spring&crm_id_parameter=123456
```

For more details, refer to [Campaign Standard REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering).