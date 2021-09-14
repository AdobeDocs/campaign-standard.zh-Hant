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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 4%

---

# 以行動應用程式資料為基礎建立和更新設定檔資訊

## 概覽

本頁說明在行動應用程式依排程傳送收集PII資料後，建立/更新設定檔資料的工作流程所需的步驟。

* **** PII代表「個人識別資訊」。它可以是任何資料，包括未出現在Campaign資料庫之「設定檔」表格中的資訊，例如Analytics for Mobile [Points of Interest](../../integrating/using/about-campaign-points-of-interest-data-integration.md)。 PII由行動應用程式開發人員定義，通常由行銷人員定義。
* **收集** PII是從行動應用程式對Adobe Campaign Standard中的Rest API進行HTTPPOST作業。

如果行動應用程式傳回的PII資料包含與設定檔相關的資料，此使用案例的目的就是建立或更新Campaign Standard設定檔。

## 先決條件

若要在Campaign Standard中啟用推播通知，您必須先執行數個設定步驟，才能根據行動應用程式訂閱資料建立或更新設定檔：

1. [建立行動應用程式](../../administration/using/configuring-a-mobile-application.md)
1. [將Adobe行動SDK與您的行動應用程式整合](https://helpx.adobe.com/tw/campaign/kb/integrate-mobile-sdk.html)。
1. [設定Adobe Campaign以傳送推播通知](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html)。

## 步驟1 — 擴充推播通知/訂閱的設定檔資源

若要使用PII資料建立或更新設定檔資源，您必須先使用所需欄位擴充設定檔資源。 操作步驟：

* 識別行動應用程式傳送的PII欄位。
* 識別要用於調解的欄位，以將PII資料與設定檔資料建立關聯。

![](assets/update_profile1.png)

在此範例中，**[!UICONTROL Fields]**&#x200B;區段反映行動應用程式傳送的PII資料。 **[!UICONTROL Link to profiles]**&#x200B;區段指出用來將PII與設定檔資料建立關聯的欄位，其中&#x200B;**cusEmail**&#x200B;對應至&#x200B;**@email**。

擴展&#x200B;**[!UICONTROL Subscriptions to an Application]**&#x200B;資源時的「配置檔案資料」映射為「只讀」。 用於調解。 必須將設定檔輸入系統中，並附上必要的資料，以便將設定檔與PII資料調解。 在此情況下，設定檔的電子郵件地址必須符合來自收集PII的電子郵件，才能進行調解：

* 從行動應用程式收集PII，若使用者的名字為「Jane」、姓氏為「Doe」，且電子郵件地址為janedoe@doe.com，系統便會收到該使用者的資訊。
* 另外，設定檔資料必須存在（例如，必須手動輸入資料，或已來自其他資源），其中設定檔的電子郵件地址為janedoe@doe.com。

**相關主題：**

* [將訂閱擴充到應用程式資源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [建立或擴充現有資源](../../developing/using/key-steps-to-add-a-resource.md)。

## 步驟2 — 建立工作流程

在Campaign Standard中使用工作流程可讓管理員唯一識別並同步AppSubscription（訂閱者）資料與設定檔或收件者資料之間的資料。 雖然基於工作流的更新不會即時同步配置檔案資料，但它不應造成任何不必要的資料庫鎖定或開銷。

建立工作流程的主要步驟為：

1. 使用&#x200B;**[!UICONTROL Query]**&#x200B;或&#x200B;**[!UICONTROL Incremental query]**&#x200B;活動來取得最新訂閱的清單。
1. 使用&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動將PII資料與設定檔對應。
1. 添加一些驗證過程。
1. 使用&#x200B;**[!UICONTROL Update data]**&#x200B;更新或建立包含PII資料的設定檔。

此工作流程會採用下列要求：

* 已擴充的任何/所有欄位都應可用來建立/更新設定檔表格。
* 「設定檔」表格可擴充至不支援原生欄位（例如T恤大小）。
* AppSubscription表格中任何空白的欄位都不應在設定檔表格中更新。
* AppSubscription表格中已更新的任何記錄都應包含在工作流的下次運行中。

若要建立工作流程，請將下列活動拖放至工作區中，並將它們連結在一起：**[!UICONTROL Start]**、**[!UICONTROL Scheduler]**、**[!UICONTROL Incremental query]**、**[!UICONTROL Update data]**。

![](assets/update_profile0.png)

然後，請依照下列步驟設定每個活動。

### 配置&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動

在&#x200B;**[!UICONTROL General]**&#x200B;標籤中，設定&#x200B;**[!UICONTROL Execution frequency]**（例如&quot;Daily&quot;）、**[!UICONTROL Time]**（例如&quot;1:00:00 AM&quot;）和&#x200B;**[!UICONTROL Start]**（例如，Today的日期）。

![](assets/update_profile2.png)

### 配置&#x200B;**[!UICONTROL Incremental query]**&#x200B;活動。

1. 在&#x200B;**[!UICONTROL Properties]**&#x200B;標籤中，按一下&#x200B;**[!UICONTROL Resource]**&#x200B;欄位的&#x200B;**[!UICONTROL Select an element]**&#x200B;圖示，然後選取&#x200B;**[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]**&#x200B;元素。

   ![](assets/update_profile3.png)

1. 在&#x200B;**[!UICONTROL Target]**&#x200B;標籤中，拖曳&#x200B;**[!UICONTROL Mobile application]**&#x200B;篩選器，然後選取行動應用程式名稱。

   ![](assets/update_profile4.png)

1. 在&#x200B;**[!UICONTROL Processed data]**&#x200B;標籤中，選擇&#x200B;**[!UICONTROL Use a date field]**，然後將&#x200B;**[!UICONTROL Last modified (lastModified)]**&#x200B;欄位添加為&#x200B;**[!UICONTROL Path to the date field]**。

   ![](assets/update_profile5.png)

### 配置&#x200B;**[!UICONTROL Update data]**&#x200B;活動。

1. 在&#x200B;**[!UICONTROL Identification]**&#x200B;索引標籤中，確認&#x200B;**[!UICONTROL Dimension to update]**&#x200B;欄位已設為「Profiles(profile)」，然後按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕以新增欄位作為調解標準。

   ![](assets/update_profile_createelement.png)

1. 在&#x200B;**[!UICONTROL Source]**&#x200B;欄位中，從appSubscriptionRcp表格選取欄位作為調解欄位。 可以是設定檔的電子郵件、crmId、marketingCloudId等。 在此範例中，我們將使用「電子郵件(cusEmail)」欄位。

1. 在&#x200B;**[!UICONTROL Destination]**&#x200B;欄位中，從設定檔表格選取欄位，以調解appSubscriptionRcp表格中的資料。 這可以是設定檔的電子郵件，或任何延伸欄位，例如crmId、marketingCloudId等。 在此範例中，我們需要選取「電子郵件（電子郵件）」欄位，以與appSubscriptionRcp表格中的「電子郵件(cusEmail)」欄位對應。

   ![](assets/update_profile7.png)

1. 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;標籤中，按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕，然後將appSubscriptionRcp表格（**[!UICONTROL Source]**&#x200B;欄位）中的欄位與您要在「設定檔」表格（**[!UICONTROL Destination]**&#x200B;欄位）中更新的欄位對應。

1. 在&#x200B;**[!UICONTROL Enabled if]**&#x200B;欄位中，新增運算式，以確保只有在來源欄位包含值時，才會更新Profile表格中的對應欄位。 要執行此操作，請從清單中選取欄位，然後新增「！=&quot;&quot;表達式（如果表達式編輯器中的「源」欄位為`[target/@cusEmail]`，請確保鍵入`[target/@cusEmail] != ''"`）。

   ![](assets/update_profile8.png)

>[!NOTE]
>
>在這種情況下，工作流將執行UPSERT，但因為它基於&#x200B;**[!UICONTROL Incremental query]**資料只插入。 更改查詢會影響插入或更新的資料。
>此外，「要更新的欄位」索引標籤中的設定會決定要在特定條件下插入或更新哪些欄位。 這些設定對於每個應用程式或客戶可以是唯一的。
>設定這些設定時請務必小心，因為根據appSubscriptionRcp資料更新設定檔中的記錄可能會變更使用者的個人資訊，而不經驗證。

新增要在「設定檔」中插入/更新的所有欄位時，按一下「**[!UICONTROL Confirm]**」。

![](assets/update_profile9.png)

保存工作流，然後按一下&#x200B;**[!UICONTROL Start]**&#x200B;以執行工作流。

![](assets/update_profile10.png)
