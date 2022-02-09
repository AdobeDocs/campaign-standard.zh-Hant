---
title: 組織單位
description: 使用組織單位定義用戶的訪問級別
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: fbab695a-2672-4183-8c3b-78af7aefd5b1
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 4%

---

# 組織單位{#organizational-units}

## 關於單位 {#about-units}

平台的每個對象和用戶被連結到組織單元。 此單元允許定義分層結構以向用戶提供過濾的視圖。 用戶單元為不同的平台對象定義其訪問級別。

>[!IMPORTANT]
>
>如果用戶未連結到任何設備，則該用戶將無法連接到Adobe Campaign。 如果要限制特定用戶或用戶組的訪問，請不要將其連結到 **[!UICONTROL All]** 的下界。 我們建議添加選項 **訪問授權管理欄位** 導入任何配置檔案之前。 如需詳細資訊，請參閱本[區段](../../administration/using/organizational-units.md#partitioning-profiles)。
>
>依預設，將 **[!UICONTROL All (all)]** 組織單位指派給 **[!UICONTROL Administrators]** 安全性群組。其為唯讀狀態且無法修改。

用戶對父單元中的所有對象都具有只讀訪問權限。 這種用戶對其單元和子單元的所有對象具有讀寫權限。 用戶無權訪問並行分支中的對象。

預設情況下，僅 **[!UICONTROL All]** 單位可用。

為用戶分配組織單位時，此單位將始終應用於用戶建立的對象。

![](assets/user_management_2.png)

>[!NOTE]
>
>當用戶位於多個連結到不同單元的組中時，將應用某些規則。 有關詳細資訊，請參閱 [管理組和用戶](../../administration/using/managing-groups-and-users.md) 的子菜單。

## 建立和管理單元 {#creating-and-managing-units}

組織單位允許您根據用戶連結到的組織來篩選實例。 在您的實例中，此單元可以表示區域、國家或甚至品牌。

在此，我們以前建立了兩個不同角色的安全組：一個用戶被分配了安全組管理員和Geometrixx，另一個用戶屬於安全組標準用戶和Geometrixx服裝請參閱 [建立安全組並分配用戶](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) 的下界。

現在，我們需要為Geometrixx服裝和Geometrixx安全組建立組織單位：

1. 從Adobe市場活動高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**。
1. 按一下 **[!UICONTROL Create]** 開始配置組織單位。

   ![](assets/manage_units_1.png)

1. 更改預設值 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** Geometrixx。
1. 然後，將此設備連結到父設備。 我們選擇 **[!UICONTROL All]**。

   ![](assets/manage_units_2.png)

1. 最後，按一下 **[!UICONTROL Create]** 開始將新組織單位分配給安全組。
1. 對「Geometrixx服裝」單元執行相同的步驟，但其父單元必須是先前建立的單元「Geometrixx」。

   ![](assets/manage_units_3.png)

要查看將不同設備分配給不同安全組的影響，分配給管理員和Geometrixx組的用戶將建立兩個電子郵件模板，以查看分配給標準用戶和Geometrixx服裝的其他用戶可以訪問或無法訪問的內容。

1. 從高級菜單中，選擇 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**。
1. 複製現有模板並根據需要對其進行個性化設定。 有關詳細資訊，請參閱 [關於模板](../../start/using/marketing-activity-templates.md) 的子菜單。
1. 建立模板時，選擇 **[!UICONTROL Edit properties]** 表徵圖，將設備分配給模板。

   ![](assets/manage_units_6.png)

1. 在 **[!UICONTROL Access authorization]** 下拉菜單，選擇組織單位。

   這裡，我們將使用先前建立的組織單位Geometrixx建立一個模板。

   ![](assets/manage_units_5.png)

1. 按照相同的步驟建立分配給先前建立的Geometrixx服裝組織單位的第二個模板。

分配給 **標準用戶** 和 **Geometrixx服** 組將能夠查看這兩個模板。 由於組織單位的分層結構，它們將具有對連結到Geometrixx服裝單位的模板的讀寫權限，並且只對連結到Geometrixx單位的模板具有只讀權限。

![](assets/manage_units_7.png)

由於Geometrixx服裝單元是Geometrixx的子單元，因此當用戶嘗試修改Geometrixx模板時，將顯示以下消息：

![](assets/manage_units_8.png)

組織單位可以限制對配置檔案等不同功能的訪問。 例如，如果我們的Geometrixx服裝用戶 **[!UICONTROL Profiles]** 頁籤，他們將能夠使用「Geometrixx服裝」組織單位完全訪問和修改配置檔案。

雖然具有Geometrixx組織單位的配置檔案將是只讀的，但如果用戶嘗試修改一個配置檔案，則會出現以下錯誤： **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**。

![](assets/manage_units_10.png)

## 對配置檔案進行分區 {#partitioning-profiles}

>[!IMPORTANT]
>
>我們建議在導入任何配置檔案之前添加此選項，因為用戶無法訪問沒有組織單位的配置檔案。
>
>如果已導入客戶資料庫，則需要更新才能在已導入的配置檔案上設定組織單位值。

如果您的組織需要隔離每個不同品牌聯繫的配置檔案，則可以按其組織單位對配置檔案進行分區。

預設情況下，配置檔案上不提供組織單位欄位，需要添加。

1. 從高級菜單中，通過Adobe Campaign徽標選擇 **管理>開發>自定義資源**。
1. 選擇 **配置檔案** 或建立新的自定義資源以擴展配置檔案。 有關如何擴展配置檔案的詳細資訊，請參閱此 [頁](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource)。
1. 檢查 **添加訪問授權管理欄位** 框，以在 **配置檔案** 擴展。

   ![](assets/user_management_9.png)

1. 按一下&#x200B;**[!UICONTROL Save]**。
1. 通過重新發佈自定義資源來更新結構。 有關發佈過程的詳細資訊，請參閱 [更新結構](../../developing/using/updating-the-database-structure.md) 的子菜單。

組織單位欄位將添加到您的配置檔案中 **[!UICONTROL Access authorization]** 的子菜單。

![](assets/user_management_10.png)

**相關主題**：

* [關於單位](../../administration/using/organizational-units.md#about-units)
* [關於存取管理](../../administration/using/about-access-management.md)
