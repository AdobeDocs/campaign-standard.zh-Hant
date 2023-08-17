---
title: 角色清單
description: 瞭解您可指派給使用者的角色清單
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 75%

---

# 角色清單{#list-of-roles}

依預設，Adobe Campaign 提供一組角色，可讓您定義指派給使用者和使用者群組的統一授權。

與組織單位結合之後，角色可讓使用者檢視介面的篩選檢視，並定義其對不同功能的存取權限。

您可從 **[!UICONTROL Administration > Users & Security > Roles]** 功能表管理角色。

預設權限為：

* **[!UICONTROL Administration]**：一般管理權限。

  >[!NOTE]
  >
  >如果您使用Experience Cloud觸發程式，您需要 **[!UICONTROL Administration]** 有權存取Experience Cloud觸發器功能表。 如需Experience Cloud觸發器的詳細資訊，請參閱本 [頁面](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**：直接執行出版品和建立自訂資源。
* **[!UICONTROL Generic import]**：對資料執行一般匯入的權限。若要讓此功能發揮作用，您必須連結 **[!UICONTROL Generic import]** 角色至 **[!UICONTROL Workflow]** 角色。
* **[!UICONTROL Prepare deliveries]**：建立、修改、準備和刪除傳送的權利。具有此角色的使用者可以準備傳送，但無法傳送。
* **[!UICONTROL Start deliveries]**：建立、修改、準備、傳送和刪除傳送的權限。
* **[!UICONTROL Workflow]**：管理工作流程的執行（開始、停止、暫停等）。具有此角色的使用者即使在工作流程中，也無法傳送傳送。

有關詳細資訊，請參閱[角色和權限表格](/help/administration/using/assets/acs_rights.pdf)，該表根據所選授權詳細說明了介面中可用的功能。

[![影像](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

**相關主題：**

* [關於存取管理](../../administration/using/about-access-management.md)
* [管理群組和使用者](../../administration/using/managing-groups-and-users.md)
