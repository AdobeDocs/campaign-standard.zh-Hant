---
title: 以行動應用程式資料為基礎建立和更新設定檔資訊
description: 瞭解如何根據行動應用程式資料建立和更新設定檔資訊。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 1b48456e-9aae-485c-a7c4-7e3e2f53cbca
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 2%

---

# 以行動應用程式資料為基礎建立和更新設定檔資訊

## 概覽

本頁說明開發工作流程的步驟，此工作流程會在行動應用程式傳送收集PII資料後，依排程建立/更新設定檔資料。

* **PII**&#x200B;代表「個人識別資訊」。 可以是任何資料，包括不會出現在促銷活動資料庫之設定檔表格的資訊，例如，行動裝置[地標](../../integrating/using/about-campaign-points-of-interest-data-integration.md)的分析。 PII由行動應用程式開發人員定義，通常與行銷人員合作。
* **收集PII**&#x200B;是從行動應用程式對Adobe Campaign Standard中的Rest API執行HTTPPOST作業。

如果行動應用程式傳回的PII資料包含設定檔相關資料，則此使用案例的目標是建立或更新Campaign Standard設定檔。

## 先決條件

必須先完成數個設定步驟，才能在Campaign Standard中啟用推播通知，之後才能根據行動應用程式訂閱資料建立或更新設定檔：

1. [建立行動應用程式](../../administration/using/configuring-a-mobile-application.md)
1. [將Adobe行動SDK與您的行動應用程式整合](../../administration/using/supported-mobile-use-cases.md)。
1. [設定Adobe Campaign以傳送推播通知](../../administration/using/configuring-a-mobile-application.md)。

## 步驟1 — 擴充推播通知/訂閱的設定檔資源

若要能夠使用PII資料建立或更新設定檔資源，您必須先使用所需欄位擴充設定檔資源。 操作步驟：

* 識別行動應用程式傳送的PII欄位。
* 識別要用於調解，以將PII資料與設定檔資料關聯的欄位。

![](assets/update_profile1.png)

在此範例中，**[!UICONTROL Fields]**&#x200B;區段反映行動應用程式傳送的PII資料。 **[!UICONTROL Link to profiles]**&#x200B;區段指出用來關聯PII與設定檔資料的欄位，其中&#x200B;**cusEmail**&#x200B;對應至&#x200B;**@email**。

擴充&#x200B;**[!UICONTROL Subscriptions to an Application]**&#x200B;資源時，設定檔資料的對映是唯讀的。 它用於調解。 必須將設定檔輸入到系統中，並輸入必要資料，才能將設定檔與PII資料調解。 在我們的案例中，設定檔的電子郵件地址必須與收集PII的電子郵件相符，才能進行調解：

* 系統會從行動應用程式接收使用者的收集PII，使用者的名字為「Jane，姓氏為「Doe」，電子郵件地址為janedoe@doe.com。
* 單獨的設定檔資料必須存在（例如，資料必須手動輸入或已來自其他資源），其中設定檔的電子郵件地址為janedoe@doe.com。

**相關主題：**

* [將訂閱擴充至應用程式資源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)。
* [正在建立或擴充現有資源](../../developing/using/key-steps-to-add-a-resource.md)。

## 步驟2 — 建立工作流程

在Campaign Standard中使用工作流程，可讓管理員唯一識別AppSubscription （訂閱者）資料與設定檔或收件者資料之間的資料並加以同步。 雖然工作流程式更新不會即時同步設定檔資料，但不應造成任何不必要的資料庫鎖定或額外負荷。

建立工作流程的主要步驟如下：

1. 使用&#x200B;**[!UICONTROL Query]**&#x200B;或&#x200B;**[!UICONTROL Incremental query]**&#x200B;活動取得最新訂閱的清單。
1. 使用&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動將PII資料與設定檔對應。
1. 新增一些驗證程式。
1. 使用&#x200B;**[!UICONTROL Update data]**&#x200B;更新或建立具有PII資料的設定檔。

此工作流程會假設下列需求：

* 已擴充的任何/所有欄位應該可用於建立/更新設定檔表格。
* 設定檔表格可延伸以支援原生不支援的欄位（例如T恤尺寸）。
* AppSubscription表格中任何空白的欄位都不應在設定檔表格中更新。
* 在AppSubscription表格中更新的任何記錄，都應包含在下一次執行的工作流程中。

若要建置工作流程，請將下列活動拖放至工作區，並將它們連結在一起： **[!UICONTROL Start]**、**[!UICONTROL Scheduler]**、**[!UICONTROL Incremental query]**、**[!UICONTROL Update data]**。

![](assets/update_profile0.png)

然後依照下列步驟設定每個活動。

### 設定&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動

在&#x200B;**[!UICONTROL General]**&#x200B;索引標籤中，設定&#x200B;**[!UICONTROL Execution frequency]** （例如「每日」）、**[!UICONTROL Time]** （例如「1:00:00 AM」）及&#x200B;**[!UICONTROL Start]** （例如「今天的日期」）。

![](assets/update_profile2.png)

### 設定&#x200B;**[!UICONTROL Incremental query]**&#x200B;活動。

1. 在&#x200B;**[!UICONTROL Properties]**&#x200B;索引標籤中，按一下&#x200B;**[!UICONTROL Resource]**&#x200B;欄位的&#x200B;**[!UICONTROL Select an element]**&#x200B;圖示，然後選取&#x200B;**[!UICONTROL Subscriptions to an application (`nms:appSubscriptionRcp:appSubscriptionRcpDetail`)]**&#x200B;元素。

   ![](assets/update_profile3.png)

1. 在&#x200B;**[!UICONTROL Target]**&#x200B;索引標籤中，拖曳&#x200B;**[!UICONTROL Mobile application]**&#x200B;篩選器，然後選取行動應用程式名稱。

   ![](assets/update_profile4.png)

1. 在&#x200B;**[!UICONTROL Processed data]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Use a date field]**，然後將&#x200B;**[!UICONTROL Last modified (lastModified)]**&#x200B;欄位新增為&#x200B;**[!UICONTROL Path to the date field]**。

   ![](assets/update_profile5.png)

### 設定&#x200B;**[!UICONTROL Update data]**&#x200B;活動。

1. 在&#x200B;**[!UICONTROL Identification]**&#x200B;索引標籤中，確定&#x200B;**[!UICONTROL Dimension to update]**&#x200B;欄位已設定為「設定檔（設定檔）」，然後按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕，新增欄位作為調解條件。

   ![](assets/update_profile_createelement.png)

1. 在&#x200B;**[!UICONTROL Source]**&#x200B;欄位中，從appSubscriptionRcp表格中選取欄位作為調解欄位。 可以是設定檔的電子郵件、crmId、marketingCloudId等。 在此範例中，使用「電子郵件(cusEmail)」欄位。

1. 在&#x200B;**[!UICONTROL Destination]**&#x200B;欄位中，從設定檔表格中選取欄位以調解appSubscriptionRcp表格中的資料。 它可以是設定檔的電子郵件，或任何擴充欄位，例如crmId、marketingCloudId等。 在此範例中，我們需要選取「電子郵件（電子郵件）」欄位，以與appSubscriptionRcp表格中的「電子郵件(cusEmail)」欄位對應。

   ![](assets/update_profile7.png)

1. 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;索引標籤中，按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕，然後將來自appSubscriptionRcp資料表的欄位（**[!UICONTROL Source]**&#x200B;欄位）與您要在設定檔資料表中更新的欄位（**[!UICONTROL Destination]**&#x200B;欄位）對應。

1. 在&#x200B;**[!UICONTROL Enabled if]**&#x200B;欄位中新增運算式，以確保只有在來源欄位包含值時，才能更新設定檔表格中的對應欄位。 若要這麼做，請從清單中選取欄位，然後新增「！=&quot;&quot;運算式(如果Source欄位在運算式編輯器中為`[target/@cusEmail]`，請務必輸入`[target/@cusEmail] != ''"`)。

   ![](assets/update_profile8.png)

>[!NOTE]
>
>在此情況下，工作流程會執行UPSERT，但因為它是以&#x200B;**[!UICONTROL Incremental query]**&#x200B;資料為基礎，所以只會插入。 變更查詢可能會影響要插入或更新哪些資料。
>此外，要更新欄位索引標籤中的設定會決定在特定條件下插入或更新哪些欄位。 這些設定對每個應用程式或客戶可能都是唯一的。
>在設定這些設定時請小心，可能會產生非預期的後果，因為根據appSubscriptionRcp資料更新設定檔中的記錄可能會變更使用者的個人資訊，而不需要驗證。

在設定檔中新增要插入/更新的所有欄位後，按一下&#x200B;**[!UICONTROL Confirm]**。

![](assets/update_profile9.png)

儲存工作流程，然後按一下&#x200B;**[!UICONTROL Start]**&#x200B;以執行工作流程。

![](assets/update_profile10.png)
