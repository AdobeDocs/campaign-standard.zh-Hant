---
title: 以行動應用程式資料為基礎建立和更新設定檔資訊
description: 瞭解如何根據移動應用程式資料建立和更新配置檔案資訊。
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

本頁介紹了開發工作流的步驟，該工作流在Mobile Application按計畫發送收集PII資料後建立/更新配置檔案資料。

* **PII** 代表「個人身份資訊」。 它可以是任何資料，包括未出現在市場活動資料庫（例如， Analytics for Mobile）的Profile表中的資訊 [興趣點](../../integrating/using/about-campaign-points-of-interest-data-integration.md)。 PII由Mobile App Developer定義，通常與Marketer一起定義。
* **收集PII** 是從移動應用對Adobe Campaign Standard的Rest API的HTTPPOST操作。

此使用案例的目標是建立或更新Campaign Standard配置檔案，如果Mobile應用程式返回的PII資料包含與配置檔案相關的資料。

## 必要條件

在基於Mobile App訂閱資料建立或更新配置檔案之前，要啟用Campaign Standard中的推送通知，需要執行以下幾個配置步驟：

1. [建立移動應用程式](../../administration/using/configuring-a-mobile-application.md)
1. [將Adobe移動SDK與移動應用程式整合](../../administration/using/supported-mobile-use-cases.md)。
1. [配置Adobe Campaign以發送推送通知](../../administration/using/configuring-a-mobile-application.md)。

## 步驟1 — 擴展推送通知/訂閱的配置檔案資源

要能夠使用PII資料建立或更新Profile資源，必須首先使用所需欄位擴展Profile資源。 操作步驟：

* 確定由Mobile應用程式發送的PII欄位。
* 確定用於協調的欄位，以將PII資料與配置檔案資料關聯。

![](assets/update_profile1.png)

在此示例中， **[!UICONTROL Fields]** 部分反映Mobile應用程式發送的PII資料。 的 **[!UICONTROL Link to profiles]** 部分指示用於將PII與配置檔案資料關聯的欄位，其中 **自定義電子郵件** 映射到 **@email**。

在擴展 **[!UICONTROL Subscriptions to an Application]** 資源為只讀。 它用於協調。 必須將配置檔案輸入到系統中，並且必須提供必要的資料，以便將配置檔案與PII資料協調起來。 在我們的情況下，配置檔案的電子郵件地址必須與「收集PII」中的電子郵件匹配，以便進行協調：

* 收集PII是從Mobile App中為其名為「Jane」、「Last Name」且電子郵件地址為janedoe@doe.com的用戶接收的。
* 另外，配置檔案資料必須存在（例如，資料必須手動輸入或已來自其他資源），其中配置檔案的電子郵件地址為janedoe@doe.com。

**相關主題：**

* [將訂閱擴充到應用程式資源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [建立或擴展現有資源](../../developing/using/key-steps-to-add-a-resource.md)。

## 步驟2 — 建立工作流

使用Campaign Standard中的工作流允許管理員在AppSubscription（訂閱伺服器）資料和配置檔案或收件人資料之間唯一地標識和同步資料。 雖然基於工作流的更新不會即時同步配置檔案資料，但它不應造成任何不適當的資料庫鎖定或開銷。

構建工作流的主要步驟是：

1. 使用 **[!UICONTROL Query]** 或 **[!UICONTROL Incremental query]** 活動，以獲取最新訂閱的清單。
1. 使用 **[!UICONTROL Reconciliation]** 活動，將PII資料與配置檔案映射。
1. 添加一些驗證過程。
1. 使用 **[!UICONTROL Update data]** 更新或建立具有PII資料的配置檔案。

在此工作流中假定了以下要求：

* 已擴展的任何/所有欄位應可用於建立/更新配置檔案表。
* 「配置檔案」(Profile)表可以擴展到支援本機不支援的欄位（例如，T恤衫尺寸）。
* AppSubscription表中空的任何欄位都不應在配置檔案表中更新。
* 在AppSubscription表中更新的任何記錄都應包括在工作流的下一運行中。

要構建工作流，請將以下活動拖放到工作區中並將它們連結在一起： **[!UICONTROL Start]**。 **[!UICONTROL Scheduler]**。 **[!UICONTROL Incremental query]**。 **[!UICONTROL Update data]**。

![](assets/update_profile0.png)

然後按照以下步驟配置每個活動。

### 配置 **[!UICONTROL Scheduler]** 活動

在 **[!UICONTROL General]** 頁籤 **[!UICONTROL Execution frequency]** （例如，「每日」）, **[!UICONTROL Time]** (例如，&quot;1&quot;:00:00 AM」), **[!UICONTROL Start]** （例如，「今天」日期）。

![](assets/update_profile2.png)

### 配置 **[!UICONTROL Incremental query]** 的子菜單。

1. 在 **[!UICONTROL Properties]** 頁籤 **[!UICONTROL Select an element]** 表徵圖 **[!UICONTROL Resource]** ，然後選擇 **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 的子菜單。

   ![](assets/update_profile3.png)

1. 在 **[!UICONTROL Target]** 按鈕 **[!UICONTROL Mobile application]** ，然後選擇移動應用程式名稱。

   ![](assets/update_profile4.png)

1. 在 **[!UICONTROL Processed data]** 頁籤 **[!UICONTROL Use a date field]**，然後添加 **[!UICONTROL Last modified (lastModified)]**  欄位 **[!UICONTROL Path to the date field]**。

   ![](assets/update_profile5.png)

### 配置 **[!UICONTROL Update data]** 的子菜單。

1. 在 **[!UICONTROL Identification]** 頁籤，確保 **[!UICONTROL Dimension to update]** 欄位設定為「配置式（配置式）」，然後按一下 **[!UICONTROL Create element]** 按鈕，將欄位添加為協調條件。

   ![](assets/update_profile_createelement.png)

1. 在 **[!UICONTROL Source]** 欄位，從appSubscriptionRcp表中選擇一個欄位作為協調欄位。 它可以是配置檔案的電子郵件、 crmId 、 marketingCloudId等。 在本示例中，使用「電子郵件(cusEmail)」欄位。

1. 在 **[!UICONTROL Destination]** 欄位，從配置檔案表中選擇一個欄位以協調appSubscriptionRcp表中的資料。 它可以是配置檔案的電子郵件，也可以是任何擴展欄位，如crmId、marketingCloudId等。 在本示例中，我們需要選擇「電子郵件（電子郵件）」欄位，以將其與appSubscriptionRcp表中的「電子郵件(cusEmail)」欄位進行映射。

   ![](assets/update_profile7.png)

1. 在 **[!UICONTROL Fields to update]** 頁籤 **[!UICONTROL Create element]** 按鈕，然後映射來自appSubscriptionRcp表的欄位(**[!UICONTROL Source]** 欄位)中的值(**[!UICONTROL Destination]** )。

1. 在 **[!UICONTROL Enabled if]** 欄位中，添加一個表達式，以確保只有源欄位包含值時才更新「配置檔案」表中的相應欄位。 為此，請從清單中選擇欄位，然後添加「！」=&quot;&quot;表達式(如果源欄位為 `[target/@cusEmail]` 在表達式編輯器中確保鍵入 `[target/@cusEmail] != ''"`)。

   ![](assets/update_profile8.png)

>[!NOTE]
>
>在這種情況下，工作流執行UPSERT，但是它基於 **[!UICONTROL Incremental query]** 只插入資料。 更改查詢會影響插入或更新的資料。
>此外，「要更新的欄位」(Fields to update)頁籤中的設定將確定在特定條件下插入或更新哪些欄位。 這些設定對於每個應用程式或客戶可以是唯一的。
>配置這些設定時要小心，因為基於appSubscriptionRcp資料更新配置檔案中的記錄可以更改用戶個人資訊而無需驗證。

在「配置檔案」中插入/更新的所有欄位都已添加後，按一下 **[!UICONTROL Confirm]**。

![](assets/update_profile9.png)

保存工作流，然後按一下 **[!UICONTROL Start]** 的子菜單。

![](assets/update_profile10.png)
