---
title: 組織單位
seo-title: 組織單位
description: 組織單位
seo-description: 使用組織單位定義使用者的存取層級。
page-status-flag: 從未啓動
uuid: 8c82ffea-cef4-4a89-b823-d8 b7 bae1 db4 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 使用者與安全性
discoiquuid: 6f60c653-1d12-4d27-9bc8-ce8 c19 bca466
context-tags: orgUnit，概觀；orgUnit，main；GeOnIT，概觀；GeOnIT，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Organizational units{#organizational-units}

## About units {#about-units}

平台的每個物件和使用者都連結到組織單位。此單位允許定義階層式結構，以提供使用者篩選檢視。使用者的單位定義不同平台物件的存取層級。

>[!CAUTION]
>
>如果使用者未連結至任何單位，則該使用者將無法連線至Adobe Campaign。If you would like to restrict access for a particular user or group of users, do not link it to the **[!UICONTROL All]** unit.

使用者擁有父台中所有物件的唯讀存取權。他已閱讀並寫入對其單元和子系的所有物件的存取權。使用者無法存取平行分支中的物件。

By default, only the **[!UICONTROL All]** units are available.

當使用者獲指派組織單位時，此單位將一律套用至使用者建立的物件。

![](assets/user_management_2.png)

>[!NOTE]
>
>當使用者在連結到不同單位的數個群組中時，會套用某些規則。For more information, refer to the [Managing groups and users](../../administration/using/managing-groups-and-users.md) section.

## Creating and managing units {#creating-and-managing-units}

組織單位可讓您依據您的使用者所連結的組織來篩選您的例項。此單位可代表您實例中的地區、國家或甚至品牌。

Here, we previously created security groups with different roles to two users: one user is assigned the security groups Administrators and Geometrixx, the other user belongs to the security groups Standard user and Geometrixx Clothes See [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) for the full example.

我們現在必須為Geometrixx服裝和Geometrixx安全性群組建立組織單位：

1. From Adobe campaign advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Users & security]** &gt; **[!UICONTROL Organizational units]**.
1. Click **[!UICONTROL Create]** to start configuring your organizational unit.

   ![](assets/manage_units_1.png)

1. Change the default **[!UICONTROL Label]** and **[!UICONTROL ID]** to Geometrixx.
1. 然後，將此單位連結至父單位。Here, we chose **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Finally, click **[!UICONTROL Create]** to start assigning your new organizational unit to security group.
1. 請遵循與Geometrixx服裝單元相同的程序，但其父單位必須是先前建立的單位，Geometrixx。

   ![](assets/manage_units_3.png)

為查看指派不同件數給不同安全性群組的影響，指派給管理員和Geometrixx群組的使用者會建立兩個電子郵件範本，以查看其他指派給Standard User和Geometrixx服裝的使用者可以或無法存取。

1. From the advanced menu, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery Templates]**.
1. 複製現有範本並視需要加以個人化。For more on this, refer to the [About templates](../../start/using/about-templates.md) section.
1. When the template is created, select the **[!UICONTROL Edit properties]** icon to assign units to your template.

   ![](assets/manage_units_6.png)

1. In the **[!UICONTROL Access authorization]** drop down menu, select the organizational unit.

   我們將在此處建立一個範本，其中包含先前建立的組織單元Geometrixx。

   ![](assets/manage_units_5.png)

1. 依照相同的程序建立指派給先前建立Geometrixx服裝組織單位的第二個範本。

指派給Standard User and Geometrixx服裝群組的使用者可以看到這兩個範本。由於組織單位的階層結構，他可以讀取和寫入連結至Geometrixx服裝單元的範本，並且只讀取連結至Geometrixx單元之範本的範本存取權。

![](assets/manage_units_7.png)

由於Geometrixx服裝單元是Geometrixx的子單位，當使用者嘗試修改Geometrixx範本時，會出現下列訊息：

![](assets/manage_units_8.png)

組織單位可限制存取不同功能，例如設定檔。For example, if our Geometrixx Clothes user access the **[!UICONTROL Profiles]** tab, he will be able to fully access and modify the profiles with the Geometrixx Clothes organizational unit.

Whereas the profiles with the Geometrixx organizational unit will be read only, the following error will appear if our user tries to modify one profile: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partitioning profiles {#partitioning-profiles}

如果您的組織需要隔離各個不同品牌的個人檔案，您可以依組織單位劃分個人檔案。

依預設，組織單位欄位不適用於您的個人檔案，必須新增。

使用者無法存取具有組織單位的個人檔案。

>[!CAUTION]
>
>建議您先新增此選項，然後再匯入任何描述檔。如果您已匯入客戶資料庫，則必須進行更新，才能設定已匯入描述檔上的組織單位值。

1. From the advanced menu, via the Adobe Campaign logo, select **Administration &gt; Development &gt; Custom resources**.
1. Select **Profile** or create a new custom resource to extend the profiles.
1. Check the **Add access authorization management fields** box to add the organizational units in the **Profile** extension.

   ![](assets/user_management_9.png)

1. Click **[!UICONTROL Save]**.
1. 重新發佈自訂資源以更新結構。For more information about the publication process, refer to [Updating the structure](../../developing/using/data-model-concepts.md) section.

The organizational unit field is added to your profiles in the **[!UICONTROL Access authorization]** section.

![](assets/user_management_10.png)

**相關主題**：

* [關於單位](../../administration/using/organizational-units.md#about-units)
* [關於存取管理](../../administration/using/about-access-management.md)

