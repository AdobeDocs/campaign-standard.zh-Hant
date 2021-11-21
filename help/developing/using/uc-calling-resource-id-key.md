---
title: 使用複合識別鍵呼叫資源
description: 了解如何使用複合識別鍵呼叫資源
feature: Data Model
role: Developer
level: Experienced
exl-id: c7aca0c3-525d-4195-8c04-2fad32ca43b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 7%

---

# 使用複合識別鍵呼叫資源{#calling-a-resource-using-a-composite-identification-key}

在某些情況下，您可能需要為資源定義由兩個欄位組成的識別索引鍵。 在設定識別金鑰後，您需要設定篩選定義，才能透過此識別金鑰(從Campaign Standard介面或API)呼叫資源。

在此使用案例中， **設定檔** 已使用自訂擴充資源 **&quot;CRM ID&quot;** 和 **&quot;category&quot;** 欄位。 我們將為設定檔資源建立識別索引鍵，由這兩個欄位組成。 之後，我們會設定篩選器定義，以便使用識別索引鍵存取設定檔資源。

此使用案例的主要步驟為：

1. 根據兩個欄位，設定設定檔資源的識別金鑰。
1. 設定篩選定義，以便使用其識別索引鍵呼叫設定檔資源。
1. 從介面或從AP呼叫設定檔資源。

相關主題：

* [建立或擴充資源](../../developing/using/creating-or-extending-the-resource.md)
* [定義標識鍵](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign StandardREST API](../../api/using/get-started-apis.md)

## 步驟1:配置標識密鑰{#step-1-configure-the-identification-key}

>[!NOTE]
> 配置標識鍵時的全局概念在 [本節](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. 在設定識別金鑰之前，請確定資源已擴充至所需的欄位，且已發佈。 如需詳細資訊，請參閱[本章節](../../developing/using/creating-or-extending-the-resource.md)。

1. 前往 **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]** ，然後開啟 **[!UICONTROL Profile]** 資源。

   ![](assets/uc_idkey1.png)

1. 在 **[!UICONTROL Identification keys]** 區段，按一下 **[!UICONTROL Create element]** 按鈕。

   ![](assets/uc_idkey2.png)

1. 新增兩個自訂「CRM ID」和「類別」欄位，然後按一下 **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > 如果您想在設定檔的介面中顯示兩個自訂欄位，請設定 **[!UICONTROL Screen definition]** 標籤。 如需詳細資訊，請參閱[本章節](../../developing/using/configuring-the-screen-definition.md)。

1. 您現在可以設定篩選定義，以使用其識別索引鍵呼叫資源。

## 步驟2:設定篩選定義{#step-2-configure-the-filter-definition}

>[!NOTE]
> 設定篩選器定義時的全域概念在 [本節](../../developing/using/configuring-filter-definition.md).

1. 在 **[!UICONTROL Filter definition]** 按一下 **[!UICONTROL Add an element]**，然後輸入篩選定義的標籤和ID。

1. 編輯篩選器定義的屬性以設定其規則。

   ![](assets/uc_idkey4.png)

1. 將包含標識鍵中所用欄位的表拖放到工作區中。

   ![](assets/uc_idkey5.png)

1. 選取識別金鑰(「CRM ID」)中使用的第一個欄位，然後啟用 **[!UICONTROL Switch to parameters]** 選項。

   ![](assets/uc_idkey6.png)

1. 在 **[!UICONTROL Filter conditions]** 區段，保留 **[!UICONTROL Equal]** 運算子，然後定義參數的名稱，然後按一下加號以建立它。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 按一下 **+** 按鈕，則會自動產生參數的名稱。 請注意，因為您需要此資訊才能使用API的篩選器。

1. 對構成識別索引鍵(「category」)的所有欄位重複上述步驟，然後儲存您的變更。

   ![](assets/uc_idkey8.png)

1. 篩選器定義現在已設定。 您可以發佈資源，讓篩選器可供使用。

## 步驟3:根據其識別鍵呼叫資源{#step-3-call-the-resource-based-on-its-identification-key}

在設定識別金鑰及其篩選定義後，您就可以使用這些金鑰，從Campaign標準介面或REST API呼叫資源。

若要從介面使用篩選定義，請使用 **[!UICONTROL Query]** 工作流程中的活動(請參閱 [本節](../../automating/using/query.md))。 篩選器便可在左窗格中使用。

![](assets/uc_idkey9.png)

若要使用Campaign StandardREST API的篩選器定義，請使用下列語法：

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>若要呼叫自訂篩選，請在設定篩選器定義時，使用「by」首碼，後接定義的篩選器名稱(在 [步驟2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

在本例中，使用「123456」CRM ID從「spring」類別擷取設定檔的語法為：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

如需詳細資訊，請參閱 [Campaign StandardREST API檔案](../../api/using/filtering.md).
