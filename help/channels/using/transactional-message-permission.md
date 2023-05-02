---
title: 交易式訊息權限
description: 了解連結至交易事件的權限。
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
ht-degree: 0%

---

# 異動事件改善 {#transactional-event-improvements}

>[!AVAILABILITY]
>
>這些功能目前僅適用於一組組織（有限可用性）。 如需詳細資訊，請連絡您的Adobe代表。

目前，在Adobe Campaign Standard中，沒有管理員安全性群組的使用者無法存取、建立或發佈交易事件，造成業務使用者需要設定和發佈事件但缺少管理員權限的問題。 此外，無法複製交易式事件。

我們已對交易式訊息存取控制實作下列改善：

* 新 **[!UICONTROL Role]**，呼叫 **MC用戶**，可讓非管理員使用者管理交易式事件設定。 此 **MC用戶** 角色可授予這些使用者存取、建立、發佈和取消發佈交易式事件和訊息的能力。

* 執行傳送（即每次編輯和重新發佈交易式訊息時所建立的技術訊息，或依預設每月一次）現在設為 **[!UICONTROL Organizational unit]** 建立事件的使用者所屬的安全性群組，而非限制為 **[!UICONTROL Organizational unit]** 的 **消息中心代理(mcExec)** 安全組。

* **管理員** 現在可以複製已發佈的交易式事件，以及使用者 **MC用戶** 角色(條件是它們位於相同 **組織單位** 階層：建立事件的使用者。

## 分配MC用戶角色 {#assign-role}

若要指派 **MC用戶** 角色至您的安全組：

1. 建立新 **[!UICONTROL Security group]** 或更新現有的。 [了解更多資訊](../../administration/using/managing-groups-and-users.md)。

1. 按一下 **[!UICONTROL Create element]** 將角色指派給安全性群組。

   ![](assets/event_access_1.png)

1. 選擇MC用戶 **[!UICONTROL Role]** 按一下 **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > 將MC用戶角色分配給操作員時，請小心操作，因為這授予他們取消發佈事件的能力。

   ![](assets/event_access_2.png)

1. 設定後，按一下 **[!UICONTROL Save]**.

連結到此 **[!UICONTROL Security group]** 現在可以存取、建立和發佈交易式事件和訊息。

## 分配MC用戶安全組 {#assign-group}

1. 在Admin Console中，選取 **產品** 標籤。

1. 選擇 **Adobe Campaign Standard** 然後選擇您的執行個體。

1. 從 **產品設定檔** 清單，選擇 **MC用戶** 群組。

1. 按一下 **新增使用者** 並輸入您要新增至此產品設定檔之設定檔的名稱、使用者群組或電子郵件地址。

1. 新增後，按一下 **儲存**.

新增至此 **[!UICONTROL Security group]** 現在可以存取、建立和發佈交易式事件和訊息。

## 重複交易事件 {#duplicate-transactional-events}

使用 **管理員** 安全組<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> 現在可以複製事件設定(如果事件已 **已發佈**.

此外，非管理員使用者 **MC用戶** 角色現在可以存取事件設定，但其複製權限由 **組織單位** 他們屬於。 如果目前使用者和建立事件的使用者屬於相同的組織單位階層，則允許複製。

例如，如果屬於「法國銷售」組織單位的用戶建立了事件配置：

* 組織單位為「巴黎銷售」的另一個用戶將能夠複製此事件，因為「巴黎銷售」是「法國銷售」組織單位的一部分。

* 但是，組織單位為「舊金山銷售」的使用者將無法這麼做，因為「舊金山銷售」位於「美國銷售」組織單位下，與「法國銷售」組織單位分開。

若要複製事件設定，請遵循下列步驟。

1. 按一下 **Adobe** 徽標，在左上角，然後選擇 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.

1. 將滑鼠移至您所選取的已發佈事件設定上，然後選取 **[!UICONTROL Duplicate element]** 按鈕。

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >無法複製未發佈的事件配置。 [了解更多](publishing-transactional-event.md)

1. 會自動顯示重複的事件。 它包含您為原始事件定義的相同設定，但具有 **[!UICONTROL Draft]** 狀態。

   ![](assets/message-center_duplicated-draft-event.png)

1. 會自動建立對應的交易式訊息。 若要存取，請前往 **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_duplicated-message.png)

1. 開啟新複製的訊息。 它包含您為原始訊息定義的相同設計，但具有 **[!UICONTROL Draft]** 狀態，即使原始交易式訊息已發佈亦然。

   ![](assets/message-center_duplicated-draft-message.png)

1. 您現在可以編輯並個人化此訊息。 請參閱 [編輯交易式訊息](../../channels/using/editing-transactional-message.md).

## 影響 {#impacts}

下表概述這些改進的影響：

| 物件 | 此變更前 | 此變更後 |
|:-: | :--: | :-:|
| 交易事件 | 僅限 **管理員** 安全性群組可以建立和發佈事件。 | 此 **MC用戶** 角色可讓使用者建立和發佈事件。 |
| 交易式訊息 | 交易式訊息會設為 **組織單位** 的 **消息中心代理(mcExec)** 安全組。 | 交易式訊息會設為 **組織單位** 建立交易式事件/訊息所屬之安全性群組的。 |
| 執行傳送 | 執行傳送會設為 **組織單位** 的 **消息中心代理(mcExec)** 安全組。 | 執行傳送會設為 **組織單位** 建立交易式事件/訊息所屬之安全性群組的。 |
| 已發佈的交易式事件 | 任何用戶都無法複製。 | <ul><li>具有 **管理員** 安全性群組可以複製已發佈的事件。</li> <li>具有 **MC用戶** 角色可以複製已發佈事件(前提是它們位於相同的 **組織單位** 階層：建立事件的使用者。</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->