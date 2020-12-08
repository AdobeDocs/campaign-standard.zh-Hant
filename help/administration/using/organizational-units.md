---
solution: Campaign Standard
product: campaign
title: 組織單位
description: 使用組織單位定義使用者的存取層級。
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
translation-type: tm+mt
source-git-commit: 824c91669bd717e5bf31dab9005e4c3b9e497edf
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 組織單位{#organizational-units}

## 關於設備{#about-units}

平台的每個對象和用戶都與組織單元連結。 該單元允許定義分層結構，以便給用戶提供過濾視圖。 用戶單元為不同平台對象定義其訪問級別。

>[!IMPORTANT]
>
>如果使用者未連結至任何單位，該使用者將無法連結至Adobe Campaign。 如果您想要限制特定使用者或使用者群組的存取權，請勿將其連結至&#x200B;**[!UICONTROL All]**&#x200B;裝置。 建議在導入任何配置檔案之前添加&#x200B;**訪問授權管理欄位**&#x200B;選項。 如需詳細資訊，請參閱本[區段](../../administration/using/organizational-units.md#partitioning-profiles)。
>
>依預設，將 **[!UICONTROL All (all)]** 組織單位指派給 **[!UICONTROL Administrators]** 安全性群組。其為唯讀狀態且無法修改。

用戶對父單元中的所有對象都具有只讀訪問權限。 他可以讀取和寫入其單位和子單位的所有對象。 用戶無法訪問並行分支中的對象。

預設情況下，僅&#x200B;**[!UICONTROL All]**&#x200B;設備可用。

在為用戶分配組織單位時，此單位將始終應用於用戶建立的對象。

![](assets/user_management_2.png)

>[!NOTE]
>
>當使用者位於連結至不同單位的數個群組時，會套用特定規則。 有關詳細資訊，請參閱[管理組和用戶](../../administration/using/managing-groups-and-users.md)部分。

## 建立和管理單元{#creating-and-managing-units}

組織單位可讓您根據使用者所連結的組織來篩選例項。 在您的例項中，此單位可代表地區、國家或甚至品牌。

在此，我們先前已建立對兩個使用者具有不同角色的安全性群組：一個用戶被分配給安全組Administrators和Geometrixx，另一個用戶屬於安全組Standard用戶和Geometrixx Chastes。請參閱[建立安全組並為完整示例分配用戶](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users)。

我們現在需要為Geometrixx Chates和Geometrixx安全性群組建立組織單位：

1. 從Adobe促銷活動進階功能表，選擇&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**。
1. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;開始配置組織單元。

   ![](assets/manage_units_1.png)

1. 將預設的&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL ID]**&#x200B;變更為Geometrixx。
1. 然後，將此設備連結到父設備。 這裡，我們選擇了&#x200B;**[!UICONTROL All]**。

   ![](assets/manage_units_2.png)

1. 最後，按一下&#x200B;**[!UICONTROL Create]**&#x200B;開始將新組織單元分配給安全組。
1. 請依照與Geometrixx Chattes單元相同的程式進行，只不過其父單位必須是先前建立的單位Geometrixx。

   ![](assets/manage_units_3.png)

若要查看指派不同單位給不同安全性群組的影響，指派給管理員和Geometrixx群組的使用者將建立兩個電子郵件範本，以查看指派給標準使用者和Geometrixxx Chastes的其他使用者可以或無法存取的項目。

1. 從高級菜單中，選擇&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**。
1. 複製現有範本，並視需要加以個人化。 有關詳細資訊，請參閱[關於templates](../../start/using/marketing-activity-templates.md)部分。
1. 建立模板時，選擇&#x200B;**[!UICONTROL Edit properties]**&#x200B;表徵圖為模板分配設備。

   ![](assets/manage_units_6.png)

1. 在&#x200B;**[!UICONTROL Access authorization]**&#x200B;下拉菜單中，選擇組織單位。

   在此，我們將使用先前建立的組織單位Geometrixx建立一個範本。

   ![](assets/manage_units_5.png)

1. 依照相同的程式建立指派給先前建立之Geometrixx Chates組織單位的第二個範本。

指派給「標準使用者」和「Geometrixx服裝」群組的使用者將能夠檢視這兩個範本。 由於組織單位的階層結構，他將擁有連結至Geometrixx Chats單位之範本的讀取和寫入存取權，並僅擁有連結至Geometrixx單位之範本的唯讀存取權。

![](assets/manage_units_7.png)

由於Geometrixx Chattes單位是Geometrixx的子單位，當使用者嘗試修改Geometrixx範本時，會出現下列訊息：

![](assets/manage_units_8.png)

組織單位可以限制對不同功能（例如描述檔）的存取。 例如，如果我們的Geometrixx Chates使用者存取&#x200B;**[!UICONTROL Profiles]**&#x200B;標籤，他將能夠完整存取並修改Geometrixx Chates組織單位的描述檔。

具有Geometrixx組織單位的描述檔將只讀，但若我們的使用者嘗試修改一個描述檔，則會出現下列錯誤：**[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**。

![](assets/manage_units_10.png)

## 分區配置檔案{#partitioning-profiles}

>[!IMPORTANT]
>
>我們建議在匯入任何描述檔之前新增此選項，因為使用者無法存取沒有組織單位的描述檔。
>
>如果您已匯入客戶資料庫，則必須進行更新，才能在已匯入的個人檔案上設定組織單位值。

如果您的組織需要隔離每個不同品牌所聯絡的個人檔案，您可以依組織單位來劃分個人檔案。

依預設，您的設定檔中無法使用組織單位欄位，因此需要新增。

1. 從進階功能表，透過Adobe Campaign標誌，選取「**管理>開發>自訂資源**」。
1. 選擇&#x200B;**配置式**&#x200B;或建立新的自定義資源以擴展配置式。 有關如何擴展配置檔案的詳細資訊，請參閱此[頁](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource)。
1. 選中&#x200B;**添加訪問授權管理欄位**&#x200B;框，以在&#x200B;**配置檔案**&#x200B;擴展中添加組織單位。

   ![](assets/user_management_9.png)

1. 按一下 **[!UICONTROL Save]**。
1. 重新發佈自訂資源以更新結構。 有關發佈過程的詳細資訊，請參閱[更新結構](../../developing/using/updating-the-database-structure.md)部分。

組織單位欄位將添加到&#x200B;**[!UICONTROL Access authorization]**&#x200B;部分的配置檔案中。

![](assets/user_management_10.png)

**相關主題**：

* [關於單位](../../administration/using/organizational-units.md#about-units)
* [關於存取管理](../../administration/using/about-access-management.md)

