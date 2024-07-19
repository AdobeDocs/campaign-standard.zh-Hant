---
title: 使用複合識別鍵呼叫資源
description: 瞭解如何使用複合識別鍵呼叫資源
feature: Data Model
role: Developer
level: Experienced
exl-id: c7aca0c3-525d-4195-8c04-2fad32ca43b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 6%

---

# 使用複合識別鍵呼叫資源{#calling-a-resource-using-a-composite-identification-key}

在某些情況下，您可能需要為資源定義由兩個欄位組成的識別索引鍵。 在設定識別金鑰後，您需要設定篩選器定義，以便能夠從Campaign Standard介面或API使用此識別金鑰呼叫資源。

在此使用案例中，**設定檔**&#x200B;資源已使用自訂&#x200B;**&quot;CRM ID&quot;**&#x200B;和&#x200B;**&quot;category&quot;**&#x200B;欄位擴充。 我們將為設定檔資源建立識別金鑰，該金鑰將由這兩個欄位組成。 然後，我們將設定篩選定義，以便可以使用識別鍵存取設定檔資源。

此使用案例的主要步驟為：

1. 根據兩個欄位，設定設定檔資源的識別碼。
1. 設定篩選定義，以便能夠使用設定檔資源的識別鍵進行呼叫。
1. 從介面或API呼叫設定檔資源。

相關主題：

* [建立或擴充資源](../../developing/using/creating-or-extending-the-resource.md)
* [定義識別鍵](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [CAMPAIGN STANDARDREST API](../../api/using/get-started-apis.md)

## 步驟1：設定識別鍵{#step-1-configure-the-identification-key}

>[!NOTE]
> 設定識別金鑰時的全域概念在[本節](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)中有詳細說明。

1. 在設定識別金鑰之前，請確定資源已使用所需欄位擴展，並且已發佈。 如需詳細資訊，請參閱[本章節](../../developing/using/creating-or-extending-the-resource.md)。

1. 前往&#x200B;**[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]**&#x200B;功能表，然後開啟&#x200B;**[!UICONTROL Profile]**&#x200B;資源。

   ![](assets/uc_idkey1.png)

1. 在&#x200B;**[!UICONTROL Identification keys]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕。

   ![](assets/uc_idkey2.png)

1. 新增兩個自訂「CRM ID」和「類別」欄位，然後按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > 如果您想要在設定檔介面中顯示兩個自訂欄位，請設定&#x200B;**[!UICONTROL Screen definition]**&#x200B;標籤。 如需詳細資訊，請參閱[本章節](../../developing/using/configuring-the-screen-definition.md)。

1. 您現在可以設定篩選定義，以便能夠使用資源的識別鍵呼叫資源。

## 步驟2：設定篩選定義{#step-2-configure-the-filter-definition}

>[!NOTE]
> 設定篩選定義時的全域概念在[本節](../../developing/using/configuring-filter-definition.md)中有詳細說明。

1. 在&#x200B;**[!UICONTROL Filter definition]**&#x200B;索引標籤中，按一下&#x200B;**[!UICONTROL Add an element]**，然後輸入篩選器定義的標籤和ID。

1. 編輯篩選器定義的屬性以設定其規則。

   ![](assets/uc_idkey4.png)

1. 將包含識別鍵中所用欄位的表格拖放到工作區中。

   ![](assets/uc_idkey5.png)

1. 選取識別碼(「CRM ID」)中使用的第一個欄位，然後啟用&#x200B;**[!UICONTROL Switch to parameters]**&#x200B;選項。

   ![](assets/uc_idkey6.png)

1. 在&#x200B;**[!UICONTROL Filter conditions]**&#x200B;區段中，保留&#x200B;**[!UICONTROL Equal]**&#x200B;運運算元，然後定義引數的名稱並按一下加號以建立它。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 按一下&#x200B;**+**&#x200B;按鈕後，引數名稱會自動產生。 請記下這些資訊，因為您需要這些資訊才能使用API的篩選器。

1. 對組成識別索引鍵（「類別」）的所有欄位重複上述步驟，然後儲存變更。

   ![](assets/uc_idkey8.png)

1. 現在已設定篩選器定義。 您可以發佈資源，讓篩選器可供使用。

## 步驟3：根據其識別鍵呼叫資源{#step-3-call-the-resource-based-on-its-identification-key}

設定識別鍵及其篩選定義後，您就可以從Campaign標準介面或REST API使用它們來呼叫資源。

若要使用介面的篩選定義，請在工作流程中使用&#x200B;**[!UICONTROL Query]**&#x200B;活動（請參閱[此區段](../../automating/using/query.md)）。 然後，即可在左窗格中使用篩選器。

![](assets/uc_idkey9.png)

若要使用Campaign StandardREST API的篩選定義，請使用下列語法：

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>若要呼叫自訂篩選器，請在[步驟2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition)中設定篩選器定義時，使用「by」前置詞，後接定義的篩選器名稱。

在我們的案例中，以「123456」CRM ID從「spring」類別中擷取設定檔的語法為：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

如需詳細資訊，請參閱[Campaign StandardREST API檔案](../../api/using/filtering.md)。
