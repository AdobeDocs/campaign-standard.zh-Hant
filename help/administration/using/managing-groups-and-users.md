---
title: 管理群組和使用者
seo-title: 管理群組和使用者
description: 管理群組和使用者
seo-description: 瞭解如何建立安全性群組及管理使用者。
page-status-flag: 從未啓動
uuid: b3a3a2e3-9d69-431-b724-8f37419 f7 a61
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 使用者與安全性
discoiquuid: 12f896ab-ee79-4d96-976d-cf3464391 b4
context-tags: user，overview；user，main；安全性，總覽；安全性，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Managing groups and users{#managing-groups-and-users}

## About security groups {#about-security-groups}

安全群組是在組織內共用相同角色和權限的使用者集合。

使用者必須隨時連結至安全群組。這可讓您指派特定角色和組織單位。

For more information on roles, the tables in the following page present the different operations available according to a user's role(s): [Adobe Campaign Standard authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

預設安全性群組為：

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

如果使用者未連結至任何安全群組，則無法存取Adobe Campaign。

To restrict a user's access, do not add the user to the Campaign Standard users group as this is linked to **[!UICONTROL All]** organizational unit.

## Creating a security group and assigning users {#creating-a-security-group-and-assigning-users}

>[!CAUTION]
>
>請注意，在Admin Console中，安全性群組會被視為描述檔。

如果已立即可用的群組不足以管理使用者，您可以建立自己的安全群組。管理員可以管理可存取Adobe Campaign管理功能表和Admin Console的管理員。For more information on the Admin console, refer to this [documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

在這裡，我們首先需要指派兩個現成可用的群組標準使用者和管理員給我們的使用者。這些安全性群組將限制Adobe Campaign的某些功能：標準使用者具有Adobe Campaign的基本存取權，而管理員可以存取管理功能表。

請注意，當使用者登入Adobe Campaign時，管理控制台上對安全性群組所做的任何變更都會立即同步。

然後，我們想要建立一組安全性群組Geometrixx和Geometrixx服裝，這會限制根據標準使用者和管理員的組織單位存取部分存取權。

![](assets/ootb_security_group_1.png)

您首先需要指派一個現成可用的安全性群組給您的使用者：

1. In the Admin console, select your instance then the **Users** tab.

   ![](assets/manage_security_group_2.png)

1. Click the **[!UICONTROL Add user]** button and enter your user's email address.
1. **[!UICONTROL Assign Products]** 在標籤中，選取您的執行個體，然後從下拉式清單中選擇 **[!UICONTROL Administrators]** 立即可用的保全群組。這可讓使用者存取管理功能表，並建立下一個安全性群組。

   ![](assets/ootb_security_group_2.png)

1. Click **[!UICONTROL Save]** and follow the same procedures to assign the **[!UICONTROL Standard Users]** out-of-the-box security group to your new user.

   ![](assets/ootb_security_group_3.png)

Once your two users are attached to the **[!UICONTROL Administrators]** and **[!UICONTROL Standard users]** out-of-the-box security groups which assign roles to our users, the Administrator user can now create the two security groups **Geometrixx** and **Geometrixx Clothes** that will assign organizational units to our users in addition to the out-of-the-box security groups.

1. In the Admin console, select your instance then the **Products** tab.
1. Click the **New Profile** button to create the **Geometrixx** security group.

   ![](assets/create_security_1.png)

1. Type the **[!UICONTROL Profile name]** by following this exact syntax: **[!UICONTROL Campaign Standard- instance name - ID of the security group]** and click **[!UICONTROL Done]**.

   然後在Adobe Campaign中建立安全群組時，就會使用所選的ID。

   >[!NOTE]
   >
   >If the above syntax doesn't seem to work with an older instance, it needs to be replaced by **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Then, follow the same procedures to create the **Geometrixx Clothes** security group.
1. Assign your security group to your user by selecting the **[!UICONTROL Users]** tab.

   ![](assets/manage_security_group_2.png)

1. Click your previously created user then the ![](assets/managing_security_group_10.png) icon in the **[!UICONTROL Products]** category.

   Select **[!UICONTROL Edit products assigned directly]** to start assigning new security group to your user.

   ![](assets/manage_security_group_8.png)

1. **[!UICONTROL Assign Products]** 在標籤中，選取您的例項，然後從下拉式清單中建立先前建立的安全性群組Geometrixx，將其指派給您的管理員使用者。

   Click **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   如果使用者位於數個群組：

   * 不同群組的角色已累積。在這裡，使用者分成兩種不同的群組：一個對角色起作用的角色。
   * It is the unit that is the highest in the hierarchy that will be used (see example in the [Organizational units](../../administration/using/organizational-units.md) section).
   * 如果單位具有相同等級且階層中的平行分支，使用者將無法再連線。

1. 請依照相同的程序，將Geometrixx服裝安全性群組指派給您的Standard使用者。

   ![](assets/manage_security_group_9.png)

新建立的安全性群組現在會在管理控制台中建立。如果要完全同步，您也需要在Adobe Campaign中建立它們。

管理員使用者必須建立用於指派組織單位的安全群組集合：Geometrixx和Geometrixx服裝。To learn how to create organizational units, see [Creating and managing units](../../administration/using/organizational-units.md#creating-and-managing-units) .

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Create your new security group and specify its **[!UICONTROL Label]** and **[!UICONTROL ID]**.

   ID必須與管理控制台中所選的相同。

1. In the **[!UICONTROL User access]** field, assign organizational unit. Here, the Geometrixx security group is assigned the **[!UICONTROL All]** organizational unit.

   ![](assets/manage_security_group_6.png)

1. 您也可以指派角色給安全性群組。In our case, this step is not needed since the out-of-the-box security groups **[!UICONTROL Administrators]** and **[!UICONTROL Standard users]** are used to assign roles.
1. 請依照相同的程序建立最後一個安全性Geometrixx服裝，並指派Geometrixx服裝組織單位。

   ![](assets/manage_security_group_7.png)

您的使用者現在已指派給安全性群組，並且可以連線至Adobe Campaign。

>[!CAUTION]
>
>如果使用者從Admin Console中的安全性群組移除，則仍屬於Adobe Campaign安全性群組的一部分，將無法再登入Adobe Campaign。在此情況下，移除Admin Console中的使用者電子郵件地址，以防止他們接收敏感資訊。

