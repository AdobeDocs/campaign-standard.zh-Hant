---
title: 交易式訊息權限
description: 了解連結至交易事件的權限。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
hide: true
hidefromtoc: true
feature: Transactional Messaging
role: User
level: Intermediate
source-git-commit: d7e0912dd7d19a1f5dd2172235f28a40e130cac1
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# 交易式訊息權限 {#transactional-message-permission}

目前，在Adobe Campaign Standard中，沒有管理員安全性群組的使用者無法存取、建立或發佈事件，造成業務使用者需要設定和發佈事件但缺少管理員權限的問題。

我們已對交易式訊息存取控制實作下列改善：

* 新 **[!UICONTROL Role]**，呼叫 **MC用戶**，可讓非管理員使用者管理交易事件。 此 **MC用戶** 角色可授予這些使用者存取、建立、發佈和取消發佈交易式事件和訊息的能力。

* 子傳遞現在設為 **[!UICONTROL Organizational unit]** 建立訊息範本的使用者所屬的安全性群組，而非限制為 **[!UICONTROL Organizational unit]** 的 **消息中心代理(mcExec)** 安全組。

* 預設 **消息中心執行(mcExec)** campaign會收集交易式訊息子傳送，現在已設為組織單位 **全部** 允許所有使用者檢視子傳遞的報表。

若要指派 **MC用戶** 角色：

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

下表概述此功能對訪問控制的影響：

| 物件 | 此變更前 | 此變更後 |
|:-: | :--: | :-:|
| 訊息中心執行(mcExec)行銷活動 | **消息中心執行(mcExec)** 促銷活動已設為 **消息中心代理(mcExec)** 安全組。 | **消息中心執行(mcExec)** 促銷活動已設為「組織」單位 **全部** 允許所有子傳遞與此促銷活動相關聯。</br> 所有使用者都能檢視子傳送的報表，但只能以唯讀方式存取傳送內容。 |
| 子傳遞 | 子傳遞設為 **組織單位** 的 **消息中心代理(mcExec)** 安全組。 | 子傳遞將設為 **組織單位** 建立訊息範本的使用者所屬的安全性群組。 |
| 訊息範本 | 訊息範本設為 **組織單位** 的&#x200B;**消息中心代理(mcExec)** 安全組。 | 訊息範本將設為 **組織單位** 建立訊息範本的使用者所屬的安全性群組。 |
| 交易事件 | 僅限 **管理員** 安全性群組可以建立和發佈事件。 | 此 **MC用戶** 角色可讓使用者建立和發佈事件。 |
| 交易式訊息範本 | 交易式訊息範本會設為組織單位 **全部**. | 交易訊息範本將設為 **組織單位** 建立訊息範本的使用者所屬的安全性群組。 |