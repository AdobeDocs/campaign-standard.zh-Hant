---
title: 角色清單
description: 瞭解您可指派給使用者的角色清單。
page-status-flag: 從未激活
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 參考
topic-tags: 使用者與安全性
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: 角色，概述；角色，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 角色清單{#list-of-roles}

依預設，Adobe Campaign提供一組角色，可讓您定義指派給使用者和使用者群組的統一授權。 結合組織單位，角色可讓使用者檢視介面的篩選檢視，並定義其對不同功能的存取權。 有關詳細資訊，請參閱「角 [色和權限」表](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

[![影像](/help/administration/using/assets/user_management_3.png)](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

您可從功能表管理 **[!UICONTROL Administration > Users & Security > Roles]** 角色。

預設權限為：

* **[!UICONTROL Administration]**:一般管理權限。
* **[!UICONTROL Datamodel]**:直接執行出版品和建立自訂資源。
* **[!UICONTROL Export]**:匯出資料的權利。
* **[!UICONTROL Generic import]**:對資料執行一般匯入的權限。 要使此功能發揮作用，您需要將角色 **[!UICONTROL Generic import]** 連結到角 **[!UICONTROL Workflow]** 色。
* **[!UICONTROL Prepare deliveries]**:建立、修改、準備和刪除傳送的權利。 具有此角色的使用者可以準備傳送，但無法傳送。
* **[!UICONTROL Start deliveries]**:建立、修改、準備、傳送和刪除傳送的權限。
* **[!UICONTROL Workflow]**:建立、修改、啟動和刪除工作流程的權限。 具有此角色的使用者即使在工作流程中，也無法傳送傳送。

>[!CAUTION]
>
>這些 **[!UICONTROL Deliverability]**、 **[!UICONTROL Command execution]**、 **[!UICONTROL Export]****[!UICONTROL File access]****[!UICONTROL Message Center push]** 和角色僅供Adobe管理員內部使用。 不應授予使用者這些權限。

**相關主題：**

* [關於存取管理](../../administration/using/about-access-management.md)
* [管理群組和使用者](../../administration/using/managing-groups-and-users.md)

