---
title: 管理群組和使用者
description: 瞭解如何建立安全組和管理用戶
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 4b9834ab-0f7c-419e-a210-77a018ba874d
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '933'
ht-degree: 72%

---

# 管理群組和使用者{#managing-groups-and-users}

## 關於安全性群組 {#about-security-groups}

>[!IMPORTANT]
>
>的 **[!UICONTROL Access to the deliverability parameters (Deliverability)]** 和 **[!UICONTROL Message Center agents (mcExec)]** 安全組僅Adobe內部，不應分配給任何用戶。

安全性群組是一組使用者，在您的組織內共用相同的角色和權限。

使用者必須始終連結到安全性群組。這可讓您指派他們特定的角色和組織單位。要限制用戶的訪問權限，請勿將用戶添加到市場活動 **[!UICONTROL Standard Users]** 組，因為此連結 **[!UICONTROL All]** 組織單位。

有關角色的詳細資訊，以下頁中的表顯示了根據用戶角色可用的可能操作： [Adobe Campaign Standard授權](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)。

預設安全性群組為：

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

請注意，這些內置安全組是只讀的，無法修改。 要使用一組特定角色建立您自己的安全組，請參閱下面的部分。

## 建立安全性群組並指派使用者 {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>請注意，在Admin Console中，安全組稱為配置檔案。

如果現成的群組不足以管理您的使用者，您可以建立自己的安全性群組。可以由同時訪問Adobe Campaign管理菜單和Admin Console的管理員管理。 有關Admin Console的詳細資訊，請參閱 [文檔](https://helpx.adobe.com/tw/enterprise/managing/user-guide.html)。

首先，我們需要將兩個現成的群組（Standard User 和 Administrator）指派給使用者。這些安全性群組將限制 Adobe Campaign 的某些功能：舉例來說，Standard User 可以存取 Adobe Campaign 的基本存取權限，而 Administrator 可以存取管理功能表。

請注意，使用者登入 Adobe Campaign 時，Admin Console 對安全性群組所進行的任何變更都會同步化。

然後，我們想要建立一組安全性群組（Geometrixx 及 Geometrixx Chattes），這些群組會根據　Standard 使用者和 Administrator　的組織單位來限制部分存取權限。

![](assets/ootb_security_group_1.png)

首先，您需要將一個現成的安全性群組指派給使用者：

1. 在Admin Console中，選擇實例，然後 **用戶** 頁籤。

   ![](assets/manage_security_group_2.png)

1. 按一下 **[!UICONTROL Add user]** 按鈕，然後輸入使用者的電子郵件地址。
1. 在 **[!UICONTROL Assign Products]** 索引標籤中，從下拉式清單依序選取您的執行個體以及　**[!UICONTROL Administrators]**　現成安全性群組。這可讓使用者存取管理功能表，並建立下一個安全性群組。

   ![](assets/ootb_security_group_2.png)

1. 按一下　**[!UICONTROL Save]**　並依照相同的程序，將　**[!UICONTROL Standard Users]**　現成安全性群組指派給新使用者。

   ![](assets/ootb_security_group_3.png)

將您的兩個使用者附加至 **[!UICONTROL Administrators]** 及 **[!UICONTROL Standard users]** 現成安全性群組（會將角色指派給我們的使用者）之後，Administrator 使用者現在可已建立兩個安全性群組（**Geometrixx** 及 **Geometrixx Clothes**），除了現成安全性群組之外，還會將組織單位指派給我們的使用者。

1. 在Admin Console中，選擇實例，然後 **產品** 頁籤。
1. 按一下 **New Profile** 按鈕以建立 **Geometrixx** 安全性群組。

   ![](assets/create_security_1.png)

1. 請依照此確切語法輸入 **[!UICONTROL Profile name]**：**[!UICONTROL Campaign Standard- instance name - ID of the security group]** 並按一下 **[!UICONTROL Done]**。

   之後，在　Adobe Campaign　中建立安全性群組時，將會使用所選取的　ID。

   >[!NOTE]
   >
   >如如果上述語法不適用於舊版執行個體，則需要以&#x200B;**[!UICONTROL Campaign - instance name - ID of the security group]**　取代。

   ![](assets/manage_security_group_1.png)

1. 之後，請依照相同的程序建立 **Geometrixx Chatters** 安全性群組。
1. 選取　**[!UICONTROL Users]**　索引標籤，將您的安全性群組指派給使用者。

   ![](assets/manage_security_group_2.png)

1. 按一下之前建立的使用者，然後再按　**[!UICONTROL Products]**　類別中的 ![](assets/managing_security_group_10.png) 圖示。

   選取 **[!UICONTROL Edit products assigned directly]**，開始為使用者指派新的安全性群組。

   ![](assets/manage_security_group_8.png)

1. 在 **[!UICONTROL Assign Products]** 索引標籤中，選取您的執行個體並從下拉式清單中選取之前建立的安全性群組　Geometrixx，然後將之指派給您的　Administrator　使用者。

   按一下 **[!UICONTROL Save]**。

   ![](assets/manage_security_group_3.png)

   如果使用者位於數個群組中：

   * 會累積不同群組中的角色。此處的使用者會分為兩個不同的群組：一個群組會擔任角色，另一個群組則會擔任單位。
   * 這是將會使用的最高階層單位（請參閱[組織單位](../../administration/using/organizational-units.md)區段中的範例）。
   * 如果單位具有相同的對等層級，而且位於階層中的平行分支，則無法再連接該使用者。

1. 請依照相同的程序，將 Geometrixx Chates 安全性群組指派給您的 Standard 使用者。

   ![](assets/manage_security_group_9.png)

新建立的安全組現在在Admin Console中建立。 您也需要在 Adobe Campaign 中建立這些檔案，才能完全同步化。

Administrator 使用者必須建立一組用於指派組織單位的安全性群組：Geometrixx 及 Geometrixx Chattes。若要瞭解如何建立組織單位，請參閱[建立和管理單位](../../administration/using/organizational-units.md#creating-and-managing-units)。

1. 按一下 **Adobe** 徽標，在左上角，然後選擇 **[!UICONTROL Administration > Users & Security > Security groups]**。
1. 建立新的安全性群組並指定其 **[!UICONTROL Label]** 及 **[!UICONTROL ID]**。

   ID必須與Admin Console中選擇的ID相同。

1. 在 **[!UICONTROL User access]** 欄位中，指派組織單位。在此處，會為 Geometrixx 安全性群組指派 **[!UICONTROL All]** 組織單位。

   >[!NOTE]
   >
   >如果您正在為用戶分配現成的安全組，則需要重置組織單位。

   ![](assets/manage_security_group_6.png)

1. 您也可以將角色指派給安全性群組。在此情況下，不需要執行此步驟，因為會使用現成的安全性群組 **[!UICONTROL Administrators]** 及 **[!UICONTROL Standard users]** 來指派角色。
1. 請依照相同的程序建立最後一個安全性 Geometrixxx Chates，並指派 Geometrixx Chates 組織單位。

   ![](assets/manage_security_group_7.png)

現在已將您的使用者指派給安全性群組，而且可以連線至 Adobe Campaign。

>[!IMPORTANT]
>
>如果用戶從Admin Console中的安全組中刪除，他們將繼續是Adobe Campaign安全組的一部分，並且將無法再登錄Adobe Campaign。 在此情況下，請在 Admin Console 中移除該使用者的電子郵件地址，以防止他們收到敏感資訊。
