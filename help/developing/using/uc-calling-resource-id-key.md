---
title: 使用複合識別鍵呼叫資源
description: 瞭解如何使用組合標識鍵調用資源
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

在某些情況下，您可能需要為資源定義由兩個欄位組成的標識鍵。 一旦配置了標識密鑰，您需要配置篩選器定義，以便能夠通過Campaign Standard介面或API使用此標識密鑰調用資源。

在此使用情況下， **配置檔案** 已使用自定義擴展資源 **&quot;CRM ID&quot;** 和 **&quot;類別&quot;** 的子菜單。 我們將為Profile資源建立一個標識鍵，該標識鍵將由這兩個欄位組成。 然後，我們將配置篩選器定義，以便我們能夠使用標識鍵訪問配置檔案資源。

此用例的主要步驟是：

1. 根據這兩個欄位配置配置檔案資源的標識鍵。
1. 配置篩選器定義，以便能夠使用其標識鍵調用配置檔案資源。
1. 從介面或從AP調用配置檔案資源。

相關主題：

* [建立或擴充資源](../../developing/using/creating-or-extending-the-resource.md)
* [定義標識鍵](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign StandardREST API](../../api/using/get-started-apis.md)

## 步驟1:配置標識密鑰{#step-1-configure-the-identification-key}

>[!NOTE]
> 配置標識鍵時的全局概念在中詳細介紹 [此部分](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

1. 在配置標識密鑰之前，請確保資源已擴展到所需欄位，並且已發佈。 如需詳細資訊，請參閱[本章節](../../developing/using/creating-or-extending-the-resource.md)。

1. 轉到 **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]** ，然後開啟 **[!UICONTROL Profile]** 資源。

   ![](assets/uc_idkey1.png)

1. 在 **[!UICONTROL Identification keys]** 的 **[!UICONTROL Create element]** 按鈕

   ![](assets/uc_idkey2.png)

1. 添加兩個自定義「CRM ID」和「類別」欄位，然後按一下 **[!UICONTROL Confirm]**。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > 如果要在配置檔案的介面中顯示兩個自定義欄位，請配置 **[!UICONTROL Screen definition]** 頁籤。 如需詳細資訊，請參閱[本章節](../../developing/using/configuring-the-screen-definition.md)。

1. 現在，您可以配置篩選器定義，以便能夠使用其標識鍵調用資源。

## 步驟2:配置篩選器定義{#step-2-configure-the-filter-definition}

>[!NOTE]
> 配置篩選器定義時的全局概念在中詳細介紹 [此部分](../../developing/using/configuring-filter-definition.md)。

1. 在 **[!UICONTROL Filter definition]** 按鈕 **[!UICONTROL Add an element]**，然後輸入篩選器定義的標籤和ID。

1. 編輯篩選器定義的屬性以配置其規則。

   ![](assets/uc_idkey4.png)

1. 將包含標識鍵中使用的欄位的表拖放到工作區中。

   ![](assets/uc_idkey5.png)

1. 選擇標識鍵(「CRM ID」)中使用的第一個欄位，然後激活 **[!UICONTROL Switch to parameters]** 的雙曲餘切值。

   ![](assets/uc_idkey6.png)

1. 在 **[!UICONTROL Filter conditions]** 部分，保留 **[!UICONTROL Equal]** 運算子，然後定義參數的名稱，然後按一下加號建立它。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 一旦按一下 **+** 按鈕，將自動生成參數的名稱。 請注意此資訊，因為您需要它使用API中的篩選器。

1. 對構成標識鍵（「類別」）的所有欄位重複上述步驟，然後保存更改。

   ![](assets/uc_idkey8.png)

1. 現在已配置篩選器定義。 您可以發佈資源，以便篩選器可用。

## 第3步：根據資源的標識鍵調用資源{#step-3-call-the-resource-based-on-its-identification-key}

一旦配置了標識鍵及其篩選器定義，您就可以使用它們從市場活動標準介面或REST API調用資源。

要使用介面中的篩選器定義，請使用 **[!UICONTROL Query]** 工作流中的活動(請參閱 [此部分](../../automating/using/query.md))。 然後，該過濾器在左窗格中可用。

![](assets/uc_idkey9.png)

要使用Campaign StandardREST API中的篩選器定義，請使用以下語法：

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>要調用自定義篩選器，請在中配置篩選器定義時使用「by」前置詞，後跟定義的篩選器名稱 [步驟2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition)。

在本例中，從「spring」類別中檢索具有「123456」 CRM ID的配置檔案的語法為：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

有關詳細資訊，請參閱 [Campaign StandardREST API文檔](../../api/using/filtering.md)。
