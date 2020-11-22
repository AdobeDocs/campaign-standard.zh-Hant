---
solution: Campaign Standard
product: campaign
title: 基於行動應用程式資料來建立和更新設定檔資訊
description: 瞭解如何根據行動應用程式資料建立和更新個人檔案資訊。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 4%

---


# 基於行動應用程式資料來建立和更新設定檔資訊

## 概觀

本頁說明在Mobile Application以排程方式傳送Collect PII資料後，建立／更新描述檔資料的工作流程的步驟。

* **PII** 代表「個人識別資訊」。 它可以是任何資料，包括未出現在促銷活動資料庫「設定檔」表格中的資訊，例如「行動地標 [分析」](../../integrating/using/about-campaign-points-of-interest-data-integration.md)。 PII由行動應用程式開發人員（通常與行銷人員）定義。
* **Collect PII** 是從行動應用程式對Adobe Campaign Standard中的Rest API進行HTTP-POST作業。

此使用案例的目的是建立或更新Campaign Standard描述檔（如果行動應用程式傳回的PII資料包含描述檔相關資料）。

## 必要條件

在「行動應用程式訂閱」資料建立或更新「設定檔」之前，請先執行數個設定步驟，以在「促銷活動標準」中啟用推播通知：

1. [建立行動應用程式](../../administration/using/configuring-a-mobile-application.md)
1. [將Adobe Mobile SDK與您的行動應用程式整合](https://helpx.adobe.com/tw/campaign/kb/integrate-mobile-sdk.html)。
1. [設定Adobe Campaign以傳送推播通知](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html)。

## 步驟1 —— 擴充推播通知／訂閱的描述檔資源

若要能夠使用PII資料建立或更新描述檔資源，您必須先將描述檔資源擴充至所需欄位。 操作步驟：

* 識別行動應用程式所傳送的PII欄位。
* 確定用於協調的欄位，以將PII資料與配置檔案資料關聯。

![](assets/update_profile1.png)

在此範例中，此 **[!UICONTROL Fields]** 區段反映行動應用程式傳送的PII資料。 該 **[!UICONTROL Link to profiles]** 區段指出用於將PII與描述檔資料關聯的欄位，其中 **cusEmail** 對應 **至@email**。

擴展資源時的配置檔案數 **[!UICONTROL Subscriptions to an Application]** 據映射為只讀。 用於協調。 必須將配置檔案輸入到系統中，並使用必要的資料來協調配置檔案與PII資料。 在我們的情況下，描述檔的電子郵件地址必須符合來自Collect PII的電子郵件，才能進行協調：

* 收集PII會從行動應用程式收到，其名字為「Jane」、「Last Name」（姓氏）為「Doe」且電子郵件地址為janedoe@doe.com的使用者。
* 另外，描述檔資料必須存在（例如，資料必須手動輸入或已來自其他資源），其中描述檔的電子郵件位址為janedoe@doe.com。

**相關主題：**

* [將訂閱擴充到應用程式資源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [建立或擴展現有資源](../../developing/using/key-steps-to-add-a-resource.md)。

## 步驟2 —— 建立工作流程

使用Campaign Standard中的「工作流程」可讓管理員在AppSubscription（訂閱者）資料和描述檔或收件者資料之間唯一識別並同步資料。 雖然基於工作流的更新不會即時同步描述檔資料，但不應造成任何不當的資料庫鎖定或開銷。

建立工作流程的主要步驟為：

1. 使用或 **[!UICONTROL Query]** 活 **[!UICONTROL Incremental query]** 動來取得最新訂閱的清單。
1. 使用活 **[!UICONTROL Reconciliation]** 動將PII資料與描述檔對應。
1. 新增一些驗證程式。
1. 使用 **[!UICONTROL Update data]** 更新或建立包含PII資料的描述檔。

此工作流程會採用下列要求：

* 已擴展的任何／所有欄位都可用於建立／更新配置檔案表。
* 「描述檔」表格可以延伸，以支援不支援的欄位（例如T恤衫大小）。
* AppSubscription表格中空白的任何欄位都不應更新至描述檔表格中。
* AppSubscription表格中已更新的任何記錄都應包含在下次執行的工作流程中。

若要建立工作流程，請將下列活動拖放至工作區，並將它們連結在一起： **[!UICONTROL Start]**, **[!UICONTROL Scheduler]**, **[!UICONTROL Incremental query]**, **[!UICONTROL Update data]**。

![](assets/update_profile0.png)

然後，請依照下列步驟來設定每個活動。

### 設定活 **[!UICONTROL Scheduler]** 動

在標 **[!UICONTROL General]** 簽中，設定 **[!UICONTROL Execution frequency]** （例如「每日」）、 **[!UICONTROL Time]** （例如「1:00:00 AM」）和 **[!UICONTROL Start]** （例如「今天的日期」）。

![](assets/update_profile2.png)

### 設定活 **[!UICONTROL Incremental query]** 動。

1. 在標 **[!UICONTROL Properties]** 簽中，按一下 **[!UICONTROL Select an element]** 欄位的圖 **[!UICONTROL Resource]** 示，然後選取元 **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 素。

   ![](assets/update_profile3.png)

1. 在標籤 **[!UICONTROL Target]** 中，拖曳篩選 **[!UICONTROL Mobile application]** 器，然後選取行動應用程式名稱。

   ![](assets/update_profile4.png)

1. 在標籤 **[!UICONTROL Processed data]** 中，選 **[!UICONTROL Use a date field]**&#x200B;擇，然後將字 **[!UICONTROL Last modified (lastModified)]** 段添加為 **[!UICONTROL Path to the date field]**。

   ![](assets/update_profile5.png)

### 設定活 **[!UICONTROL Update data]** 動。

1. 在標 **[!UICONTROL Identification]** 簽中，請確定欄位已設 **[!UICONTROL Dimension to update]** 為「描述檔（描述檔）」，然後按一下 **[!UICONTROL Create element]** 按鈕以新增欄位作為協調標準。

   ![](assets/update_profile_createelement.png)

1. 在欄位 **[!UICONTROL Source]** 中，從appSubscriptionRcp表格選取欄位作為協調欄位。 可以是描述檔的電子郵件、crmId、marketingCloudId等。 在此範例中，我們將使用「電子郵件(cusEmail)」欄位。

1. 在欄位 **[!UICONTROL Destination]** 中，從描述檔表格中選取欄位，以協調appSubscriptionRcp表格中的資料。 它可以是描述檔的電子郵件，或任何延伸欄位，例如crmId、marketingCloudId等。 在此範例中，我們需要選取「電子郵件（電子郵件）」欄位，以從appSubscriptionRcp表格中將其對應至「電子郵件(cusEmail)」欄位。

   ![](assets/update_profile7.png)

1. 在標 **[!UICONTROL Fields to update]** 簽中，按一下按 **[!UICONTROL Create element]** 鈕，然後將appSubscriptionRcp表格（欄位）中的欄位與您要在「描述檔」表格（欄位）中更新的欄位對應&#x200B;**[!UICONTROL Source]****[!UICONTROL Destination]** 。

1. 在欄位 **[!UICONTROL Enabled if]** 中，添加表達式以確保只有在源欄位包含值時才更新配置檔案表中的相應欄位。 若要這麼做，請從清單中選取欄位，然後新增「!=&quot;&quot;運算式(如果「來源」欄位位於「運 `[target/@cusEmail]` 算式」編輯器中，請務必輸入 `[target/@cusEmail] != ''"`)。

   ![](assets/update_profile8.png)

>[!NOTE]
>
>在這種情況下，工作流將執行UPSERT，但因為它基於數 **[!UICONTROL Incremental query]** 據只插入。 變更查詢會影響插入或更新的資料。
>此外，「要更新的欄位」標籤中的設定會決定在特定條件下插入或更新哪些欄位。 這些設定對於每個應用程式或客戶而言都是唯一的。
>設定這些設定時請務必小心，因為根據appSubscriptionRcp資料更新描述檔中的記錄可能會變更使用者的個人資訊，而不需驗證。

新增要插入／更新至描述檔的所有欄位後，按一下 **[!UICONTROL Confirm]**。

![](assets/update_profile9.png)

儲存工作流程，然後按一 **[!UICONTROL Start]** 下以執行工作流程。

![](assets/update_profile10.png)
