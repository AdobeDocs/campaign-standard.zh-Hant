---
title: 異動訊息傳送許可權
description: 瞭解連結至交易式事件的許可權。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 995da330-6c86-444b-86b2-61d887f37db4
source-git-commit: 7247fe596494690ac0676196fbb72c6139aeb0c7
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---

# 異動事件改善 {#transactional-event-improvements}

>[!AVAILABILITY]
>
>這些功能目前僅適用於一組組織（可用性限制）。 如需詳細資訊，請聯絡您的 Adobe 代表。

目前，在Adobe Campaign Standard中，沒有Administrator安全性群組的使用者無法存取、建立或發佈交易式事件，導致需要設定和發佈事件但缺少Administrator許可權的業務使用者出現問題。 此外，也不可能重複異動事件。

我們已對異動訊息存取控制實施下列改善：

* 已新增名為&#x200B;**MC使用者**&#x200B;的新&#x200B;**[!UICONTROL Role]**，以允許非管理員使用者管理異動事件設定。 **MC使用者**&#x200B;角色授予這些使用者存取、建立、發佈和取消發佈交易事件和訊息的能力。

* 執行傳送（亦即每次編輯並再次發佈交易式訊息時所建立的技術訊息，或預設為每月一次）現在已設定為建立事件之使用者所屬的安全性群組的&#x200B;**[!UICONTROL Organizational unit]**，而非限製為&#x200B;**訊息中心代理程式(mcExec)**&#x200B;安全性群組的&#x200B;**[!UICONTROL Organizational unit]**。

* **管理員**&#x200B;現在可以複製已發佈的交易事件，以及具有&#x200B;**MC使用者**&#x200B;角色的使用者，前提是他們與建立事件的使用者屬於相同的&#x200B;**組織單位**&#x200B;階層。

## 指派MC使用者角色 {#assign-role}

若要將&#x200B;**MC使用者**&#x200B;角色指派給您的安全性群組：

1. 建立新的&#x200B;**[!UICONTROL Security group]**&#x200B;或更新現有的。 [了解更多](../../administration/using/managing-groups-and-users.md)。

1. 按一下&#x200B;**[!UICONTROL Create element]**&#x200B;指派角色給您的安全性群組。

   ![](assets/event_access_1.png)

1. 選取MC使用者&#x200B;**[!UICONTROL Role]**&#x200B;並按一下&#x200B;**[!UICONTROL Confirm]**。

   >[!IMPORTANT]
   >
   > 在指派MC使用者角色給操作員時，請務必謹慎，因為這樣可讓操作員取消發佈事件。

   ![](assets/event_access_2.png)

1. 設定之後，按一下&#x200B;**[!UICONTROL Save]**。

連結至此&#x200B;**[!UICONTROL Security group]**&#x200B;的使用者現在可以存取、建立及發佈異動事件和訊息。

## 指派MC使用者安全性群組 {#assign-group}

1. 在Admin Console中，選取&#x200B;**產品**&#x200B;索引標籤。

1. 選取&#x200B;**Adobe Campaign Standard**，然後選擇您的執行個體。

1. 從&#x200B;**產品設定檔**&#x200B;清單中，選取&#x200B;**MC使用者**&#x200B;群組。

1. 按一下&#x200B;**新增使用者**，然後輸入要新增至此產品設定檔的設定檔名稱、使用者群組或電子郵件地址。

1. 新增後，按一下&#x200B;**儲存**。

新增至此&#x200B;**[!UICONTROL Security group]**&#x200B;的使用者現在可以存取、建立及發佈異動事件和訊息。

## 重複的交易式事件 {#duplicate-transactional-events}

如果事件已&#x200B;**發佈**，具有&#x200B;**系統管理員**&#x200B;安全性群組<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)-->的使用者現在可以複製事件設定。

此外，具有&#x200B;**MC使用者**&#x200B;角色的非管理員使用者現在可以存取事件設定，但其複製許可權由所屬的&#x200B;**組織單位**&#x200B;決定。 如果目前使用者和建立事件的使用者屬於相同的組織單位階層，則允許複製。

例如，如果屬於「France Sales」組織單位的使用者建立了事件組態：

* 組織單位為「Paris Sales」的另一個使用者將能夠複製此事件，因為「Paris Sales」是「France Sales」組織單位的一部分。

* 但是，組織單位為「San Francisco Sales」的使用者將無法這麼做，因為「San Francisco Sales」在「US Sales」組織單位底下，該組織單位與「France Sales」組織單位不同。

若要複製事件設定，請遵循下列步驟。

1. 按一下左上角的&#x200B;**Adobe**&#x200B;標誌，然後選取&#x200B;**[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。

1. 將滑鼠停留在您選取的已發佈事件設定上，並選取&#x200B;**[!UICONTROL Duplicate element]**&#x200B;按鈕。

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >您無法複製未發佈的事件設定。 [了解更多](publishing-transactional-event.md)

1. 系統會自動顯示重複的事件。 它包含您為原始事件定義的相同組態，但具有&#x200B;**[!UICONTROL Draft]**&#x200B;狀態。

   ![](assets/message-center_duplicated-draft-event.png)

1. 對應的交易式訊息會自動建立。 若要存取它，請移至&#x200B;**[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**。

   ![](assets/message-center_duplicated-message.png)

1. 開啟新複製的訊息。 它包含您為原始訊息定義的相同設計，但即使原始交易式訊息已發佈，它仍具有&#x200B;**[!UICONTROL Draft]**&#x200B;狀態。

   ![](assets/message-center_duplicated-draft-message.png)

1. 您現在可以編輯和個人化此訊息。 請參閱[編輯異動訊息](../../channels/using/editing-transactional-message.md)。

## 影響 {#impacts}

下表概述這些改善專案的影響：

| 物件 | 在此變更之前 | 在此變更之後 |
|:-: | :--: | :-:|
| 異動事件 | 只有&#x200B;**Administrator**&#x200B;安全性群組中的使用者可以建立和發佈事件。 | **MC使用者**&#x200B;角色可讓使用者建立和發佈事件。 |
| 交易型訊息 | 交易式訊息已設定為&#x200B;**訊息中心代理程式(mcExec)**&#x200B;安全性群組的&#x200B;**組織單位**。 | 交易式訊息設定為建立交易式事件/訊息的使用者所屬之安全性群組的&#x200B;**組織單位**。 |
| 執行傳送 | 執行傳遞設定為&#x200B;**訊息中心代理程式(mcExec)**&#x200B;安全性群組的&#x200B;**組織單位**。 | 執行傳遞設定為建立交易事件/訊息的使用者所屬之安全性群組的&#x200B;**組織單位**。 |
| 已發佈的交易式事件 | 任何使用者都不能複製。 | <ul><li>具有&#x200B;**Administrator**&#x200B;安全性群組的使用者可以複製已發佈的事件。</li> <li>具有&#x200B;**MC使用者**&#x200B;角色的使用者可以複製已發佈的事件，前提是他們與建立事件的使用者位於相同的&#x200B;**組織單位**&#x200B;階層。</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->