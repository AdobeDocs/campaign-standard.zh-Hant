---
solution: Campaign Standard
product: campaign
title: 使用複合識別鍵呼叫資源
description: 瞭解如何使用複合識別碼呼叫資源
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 7%

---


# 使用複合識別鍵呼叫資源{#calling-a-resource-using-a-composite-identification-key}

在某些情況下，您可能需要為資源定義由兩個欄位組成的標識鍵。 在設定識別金鑰後，您必須設定篩選定義，才能使用此識別金鑰（從Campaign Standard介面或API）呼叫資源。

在此使用案例中，**Profile**&#x200B;資源已擴展為自定義&#x200B;**&quot;CRM ID&quot;**&#x200B;和&#x200B;**&quot;category&quot;**&#x200B;欄位。 我們將為Profile資源建立一個標識鍵，該標識鍵將由這兩個欄位組成。 然後，我們將設定篩選定義，以便我們能夠使用識別碼存取描述檔資源。

此使用案例的主要步驟為：

1. 根據這兩個欄位，設定描述檔資源的識別碼。
1. 設定篩選定義，以便能夠使用其識別金鑰呼叫描述檔資源。
1. 從介面或從APi調用Profile資源。

相關主題：

* [建立或擴充資源](../../developing/using/creating-or-extending-the-resource.md)
* [定義標識鍵](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign Standard REST API](../../api/using/get-started-apis.md)

## 步驟1:配置標識鍵{#step-1-configure-the-identification-key}

>[!NOTE]
> 配置標識鍵時的全局概念在[本節](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)中有詳細說明。

1. 在設定識別金鑰之前，請確定資源已擴充至所需欄位，且已發佈。 如需詳細資訊，請參閱[本章節](../../developing/using/creating-or-extending-the-resource.md)。

1. 前往&#x200B;**[!UICONTROL Administration]** / **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]**&#x200B;功能表，然後開啟&#x200B;**[!UICONTROL Profile]**&#x200B;資源。

   ![](assets/uc_idkey1.png)

1. 在&#x200B;**[!UICONTROL Identification keys]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕。

   ![](assets/uc_idkey2.png)

1. 新增兩個自訂「CRM ID」和「類別」欄位，然後按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > 如果要在配置檔案的介面中顯示兩個自定義欄位，請配置&#x200B;**[!UICONTROL Screen definition]**&#x200B;頁籤。 如需詳細資訊，請參閱[本章節](../../developing/using/configuring-the-screen-definition.md)。

1. 您現在可以設定篩選定義，以便能夠使用其識別碼呼叫資源。

## 步驟2:設定篩選定義{#step-2-configure-the-filter-definition}

>[!NOTE]
> 設定篩選器定義時的全域概念，請參閱[本節](../../developing/using/configuring-filter-definition.md)。

1. 在&#x200B;**[!UICONTROL Filter definition]**&#x200B;標籤中，按一下&#x200B;**[!UICONTROL Add an element]**，然後輸入篩選定義的標籤和ID。

1. 編輯篩選定義的屬性以設定其規則。

   ![](assets/uc_idkey4.png)

1. 將包含標識鍵中使用的欄位的表拖放到工作區中。

   ![](assets/uc_idkey5.png)

1. 選取識別碼中使用的第一個欄位(「CRM ID」)，然後啟動&#x200B;**[!UICONTROL Switch to parameters]**&#x200B;選項。

   ![](assets/uc_idkey6.png)

1. 在&#x200B;**[!UICONTROL Filter conditions]**&#x200B;區段中，保留&#x200B;**[!UICONTROL Equal]**&#x200B;運算子，然後定義參數的名稱，然後按一下加號以建立它。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 按一下&#x200B;**+**&#x200B;按鈕後，就會自動產生參數的名稱。 請注意，因為您需要此項資訊才能使用API的篩選。

1. 使用構成識別碼的所有欄位（「類別」）重複上述步驟，然後儲存變更。

   ![](assets/uc_idkey8.png)

1. 現在已設定篩選定義。 您可以發佈資源，以便篩選器可用。

## 步驟3:基於其標識鍵調用資源{#step-3-call-the-resource-based-on-its-identification-key}

一旦設定識別金鑰及其篩選定義後，您就可使用它們來呼叫資源，不論是從Campaign標準介面或REST API。

若要使用介面中的篩選定義，請在工作流程中使用&#x200B;**[!UICONTROL Query]**&#x200B;活動（請參閱[本節](../../automating/using/query.md)）。 然後，篩選器便可在左窗格中使用。

![](assets/uc_idkey9.png)

若要使用Campaign Standard REST API的篩選定義，請使用下列語法：

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>若要呼叫自訂篩選，請在[步驟2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition)中設定篩選定義時，使用&quot;by&quot;字首，後面接著定義的篩選器名稱。

在本例中，從&quot;spring&quot;類別擷取具有&quot;123456&quot; CRM ID的描述檔的語法為：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

如需詳細資訊，請參閱[Campaign Standard REST APIs檔案](../../api/using/filtering.md)。