---
title: 角色清單
seo-title: 角色清單
description: 角色清單
seo-description: 找出可指派給使用者的角色清單。
page-status-flag: 從未啓動
uuid: 128aab9b-9b7d-49f3-9e1f-72e79a29ba0
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 使用者與安全性
discoiquuid: ceaa3c94-9e1a-4271-b443-b00 b4068929 f
context-tags: 角色，概觀；角色，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# List of roles{#list-of-roles}

根據預設，Adobe Campaign提供一組角色，可讓您定義指派給使用者和使用者群組的整體授權。透過組織單位，角色可為使用者提供介面的篩選檢視，並定義其對不同功能的存取權。For more on this, refer to the [Roles and permissions table](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

![](assets/user_management_3.png)

Roles can be managed from the **[!UICONTROL Administration > Users & Security > Roles]** menu.

預設權限為：

* **[!UICONTROL Administration]**：通用管理權限。
* **[!UICONTROL Datamodel]**：執行出版品及建立自訂資源的權利。
* **[!UICONTROL Export]**：匯出資料的權利。
* **[!UICONTROL Generic import]**：在資料上執行一般匯入的權限。For this to work, you need to link the **[!UICONTROL Generic import]** role to the **[!UICONTROL Workflow]** role.
* **[!UICONTROL Prepare deliveries]**：建立、編輯、開始傳送準備及傳送校樣的權利。
* **[!UICONTROL Start deliveries]**：驗證先前準備之傳送的權限。
* **[!UICONTROL Workflow]**：使用工作流程的權利。

>[!CAUTION]
>
>「傳遞能力」角色僅供Adobe管理員內部使用。不能授予使用者。

**相關主題：**

* [關於存取管理](../../administration/using/about-access-management.md)
* [管理群組和使用者](../../administration/using/managing-groups-and-users.md)

