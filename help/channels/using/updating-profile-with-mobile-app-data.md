---
title: 以行動應用程式資料為基礎建立和更新設定檔資訊
description: 了解如何根據行動應用程式資料建立和更新設定檔資訊。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 1b48456e-9aae-485c-a7c4-7e3e2f53cbca
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# 以行動應用程式資料為基礎建立和更新設定檔資訊

## 概覽

本頁說明在行動應用程式依排程傳送收集PII資料後，建立/更新設定檔資料的工作流程所需的步驟。

* **PII** 代表「個人識別資訊」。 可以是任何資料，包括未出現在Campaign資料庫之類「設定檔」表格中的資訊，例如Analytics for Mobile [地標](../../integrating/using/about-campaign-points-of-interest-data-integration.md). PII由行動應用程式開發人員定義，通常由行銷人員定義。
* **收集PII** 是從行動應用程式對Adobe Campaign Standard中的Rest API進行HTTPPOST作業。

如果行動應用程式傳回的PII資料包含與設定檔相關的資料，此使用案例的目的就是建立或更新Campaign Standard設定檔。

## 先決條件

若要在Campaign Standard中啟用推播通知，您必須先執行數個設定步驟，才能根據行動應用程式訂閱資料建立或更新設定檔：

1. [建立行動應用程式](../../administration/using/configuring-a-mobile-application.md)
1. [將Adobe行動SDK與您的行動應用程式整合](../../administration/using/supported-mobile-use-cases.md).
1. [設定Adobe Campaign以傳送推播通知](../../administration/using/configuring-a-mobile-application.md).

## 步驟1 — 擴充推播通知/訂閱的設定檔資源

若要使用PII資料建立或更新設定檔資源，您必須先使用所需欄位擴充設定檔資源。 操作步驟：

* 識別行動應用程式傳送的PII欄位。
* 識別要用於調解的欄位，以將PII資料與設定檔資料建立關聯。

![](assets/update_profile1.png)

在此範例中， **[!UICONTROL Fields]** 區段會反映行動應用程式傳送的PII資料。 此 **[!UICONTROL Link to profiles]** section指示用於將PII與設定檔資料關聯的欄位，其中 **cusEmail** 映射至 **@email**.

擴充「設定檔資料」的對應 **[!UICONTROL Subscriptions to an Application]** 資源為只讀。 用於調解。 必須將設定檔輸入系統中，並附上必要的資料，以便將設定檔與PII資料調解。 在此情況下，設定檔的電子郵件地址必須符合來自收集PII的電子郵件，才能進行調解：

* 收集PII會從行動應用程式接收，且使用者的名字為「Jane」、姓氏為「Doe」，而電子郵件地址為janedoe@doe.com。
* 另外，設定檔資料必須存在（例如，必須手動輸入資料，或已來自其他資源），其中設定檔的電子郵件地址為janedoe@doe.com。

**相關主題：**

* [將訂閱擴充到應用程式資源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [建立或擴充現有資源](../../developing/using/key-steps-to-add-a-resource.md).

## 步驟2 — 建立工作流程

在Campaign Standard中使用工作流程可讓管理員唯一識別並同步AppSubscription（訂閱者）資料與設定檔或收件者資料之間的資料。 雖然基於工作流的更新不會即時同步配置檔案資料，但它不應造成任何不必要的資料庫鎖定或開銷。

建立工作流程的主要步驟為：

1. 使用 **[!UICONTROL Query]** 或 **[!UICONTROL Incremental query]** 活動以取得最新訂閱的清單。
1. 使用 **[!UICONTROL Reconciliation]** 活動將PII資料與設定檔對應。
1. 添加一些驗證過程。
1. 使用 **[!UICONTROL Update data]** 更新或建立包含PII資料的設定檔。

此工作流程會採用下列要求：

* 已擴充的任何/所有欄位都應可用來建立/更新設定檔表格。
* 「設定檔」表格可擴充至不支援原生欄位（例如T恤大小）。
* AppSubscription表格中任何空白的欄位都不應在設定檔表格中更新。
* AppSubscription表格中已更新的任何記錄都應包含在工作流的下次運行中。

若要建立工作流程，請將下列活動拖放至工作區中，並將它們連結在一起： **[!UICONTROL Start]**, **[!UICONTROL Scheduler]**, **[!UICONTROL Incremental query]**, **[!UICONTROL Update data]**.

![](assets/update_profile0.png)

然後，請依照下列步驟設定每個活動。

### 設定 **[!UICONTROL Scheduler]** 活動

在 **[!UICONTROL General]** 頁簽，設定 **[!UICONTROL Execution frequency]** （例如「每日」）、 **[!UICONTROL Time]** (例如，「1」:00:00 AM」), **[!UICONTROL Start]** （例如，今天的日期）。

![](assets/update_profile2.png)

### 設定 **[!UICONTROL Incremental query]** 活動。

1. 在 **[!UICONTROL Properties]** ，按一下 **[!UICONTROL Select an element]** 表徵圖 **[!UICONTROL Resource]** 欄位，然後選取 **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 元素。

   ![](assets/update_profile3.png)

1. 在 **[!UICONTROL Target]** 標籤，拖曳 **[!UICONTROL Mobile application]** 篩選，然後選取行動應用程式名稱。

   ![](assets/update_profile4.png)

1. 在 **[!UICONTROL Processed data]** 索引標籤，選取 **[!UICONTROL Use a date field]**，然後新增 **[!UICONTROL Last modified (lastModified)]**  欄位 **[!UICONTROL Path to the date field]**.

   ![](assets/update_profile5.png)

### 設定 **[!UICONTROL Update data]** 活動。

1. 在 **[!UICONTROL Identification]** 標籤，確定 **[!UICONTROL Dimension to update]** 欄位設為「設定檔（設定檔）」，然後按一下 **[!UICONTROL Create element]** 按鈕以新增欄位作為調解標準。

   ![](assets/update_profile_createelement.png)

1. 在 **[!UICONTROL Source]** 欄位中，從appSubscriptionRcp表格中選取欄位作為調解欄位。 可以是設定檔的電子郵件、crmId、marketingCloudId等。 在此範例中，使用「電子郵件(cusEmail)」欄位。

1. 在 **[!UICONTROL Destination]** 欄位中，從設定檔表格中選取欄位以調解appSubscriptionRcp表格中的資料。 這可以是設定檔的電子郵件，或任何延伸欄位，例如crmId、marketingCloudId等。 在此範例中，我們需要選取「電子郵件（電子郵件）」欄位，以與appSubscriptionRcp表格中的「電子郵件(cusEmail)」欄位對應。

   ![](assets/update_profile7.png)

1. 在 **[!UICONTROL Fields to update]** ，按一下 **[!UICONTROL Create element]** 按鈕，然後映射來自appSubscriptionRcp表格的欄位(**[!UICONTROL Source]** 欄位)，以及您要在設定檔表格中更新的欄位(**[!UICONTROL Destination]** 欄位)。

1. 在 **[!UICONTROL Enabled if]** 欄位中，新增運算式，以確保只有在來源欄位包含值時，才會更新設定檔表格中的對應欄位。 要執行此操作，請從清單中選取欄位，然後新增「！=&quot;&quot;表達式(如果源欄位為 `[target/@cusEmail]` 在運算式編輯器中，請務必輸入 `[target/@cusEmail] != ''"`)。

   ![](assets/update_profile8.png)

>[!NOTE]
>
>在此情況下，工作流程會執行UPSERT，但因為它以 **[!UICONTROL Incremental query]** 僅插入資料。 更改查詢會影響插入或更新的資料。
>此外，「要更新的欄位」索引標籤中的設定會決定要在特定條件下插入或更新哪些欄位。 這些設定對於每個應用程式或客戶可以是唯一的。
>設定這些設定時請務必小心，因為根據appSubscriptionRcp資料更新設定檔中的記錄可能會變更使用者的個人資訊，而不經驗證。

新增要在「設定檔」中插入/更新的所有欄位時，按一下 **[!UICONTROL Confirm]**.

![](assets/update_profile9.png)

儲存工作流程，然後按一下 **[!UICONTROL Start]** 執行工作流程。

![](assets/update_profile10.png)
