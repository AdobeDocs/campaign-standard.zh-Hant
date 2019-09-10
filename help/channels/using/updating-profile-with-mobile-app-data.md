---
title: 根據行動應用程式資料建立和更新描述檔資訊
seo-title: 根據行動應用程式資料建立和更新描述檔資訊
description: 根據行動應用程式資料建立和更新描述檔資訊
seo-description: 瞭解如何根據行動應用程式資料建立和更新描述檔資訊。
page-status-flag: 從未啓動
uuid: 8cf74adp-b1 ba-4aad-83bd-7289cb22 d5 f
contentOwner: lemaitre
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 推播通知
discoiquuid: dc944c85-2059-46df-b396-676Fe3617 dd1
context-tags: delivery，MobileAppContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2b514387a803de25c6ddcc41bdf0e56692cfa446

---


# 根據行動應用程式資料建立和更新描述檔資訊

## 概觀

本頁面說明開發/更新行動應用程式之後，在行動應用程式傳送PII資料時建立/更新描述檔資料的步驟。

* **PII** 代表「個人識別資訊」。它可以是任何資料，包括不會出現在「促銷活動」資料庫中的資訊(例如「行動 [點」](../../integrating/using/about-campaign-points-of-interest-data-integration.md)的Analytics)。PII由行動應用程式開發人員定義，通常是行銷人員。
* **收集PII** 是對Adobe Campaign Standard中Adobe Campaign Standard中的REST API的HTTP-POST作業。

此使用案例的目標在於建立或更新促銷活動標準描述檔，如果行動應用程式傳回的PII資料包含與描述檔相關的資料。

## 必要條件

在「Campaign Standard」(促銷活動標準)中啓用推播通知之前，必須先執行幾個設定步驟，才能根據行動應用程式訂閱資料建立或更新「描述檔」：

1. [建立行動應用程式](../../administration/using/configuring-a-mobile-application.md)
1. [將Adobe Mobile SDK與行動應用程式整合](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html)。
1. [設定Adobe Campaign以傳送推播通知](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

## 步驟-延伸推送通知/訂閱的描述檔資源

若要使用PII資料建立或更新描述檔資源，您必須先將描述檔資源與所需欄位搭配使用。若要這麼做：

* 識別行動應用程式所傳送的PII欄位。
* 識別用於協調的欄位，以便將PII資料與描述檔資料建立關聯。

![](assets/update_profile1.png)

在此範例中， **[!UICONTROL Fields]** 區段反映行動應用程式所傳送的PII資料。**[!UICONTROL Link to profiles]** 區段指出用來將PII與Profile Data關聯的欄位，其中 **CuseMail** 地圖會對應 **至@ email**。

設定「描述檔資料」的對應同時將 **[!UICONTROL Subscriptions to an Application]** 資源延伸為唯讀。用於協調。您必須使用必要資料輸入描述檔，以協調描述檔與PII資料。在本公司案例中，設定檔的電子郵件地址必須與「Collect PII」中的電子郵件相符，以便協調發生：

* 從行動應用程式收集PII，適用於使用者，其名字為「Jane」，「姓氏」為「Doe」，電子郵件地址為janedoe@doe.com。
* 另外，描述檔資料必須存在(例如，必須手動輸入資料，或已來自其他資源)，該資料的電子郵件地址是janedoe@doe.com的。

**相關主題：**

* [將訂閱延伸至應用程式資源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)。
* [建立或擴充現有資源](../../developing/using/key-steps-to-add-a-resource.md)。

## 步驟-建立工作流程

在Campaign Standard中使用工作流程可讓管理員在AppSubscription(訂閱者)資料和描述檔或收件者資料之間唯一識別和同步資料。雖然工作流程更新不會即時同步描述檔資料，但不會造成任何未到期的資料庫鎖定或負荷。

建立工作流程的主要步驟為：

1. 使用 **[!UICONTROL Query]** 或 **[!UICONTROL Incremental query]** 活動取得最新訂閱的清單。
1. 使用 **[!UICONTROL Reconciliation]** 活動將PII資料與描述檔對應。
1. 新增驗證程序。
1. 使用更新 **[!UICONTROL Update data]** 或使用PII資料來建立描述檔。

此工作流程中假設有下列需求：

* 您可以使用任何已擴充的欄位來建立/更新描述檔表格。
* 「描述檔」表格可延伸至不支援原生支援的欄位(例如T恤大小)。
* 「設定檔表格」中不應更新AppSubscription表格中的任何欄位。
* 在AppSubscription表格中更新的任何記錄都應包含在下次執行的工作流程中。

若要建立工作流程，請遵循下列步驟：

1. 將下列活動拖放至工作區並將它們連結在一起：
   1. **[!UICONTROL Start]**
   1. **[!UICONTROL Scheduler]**
   1. **[!UICONTROL Incremental query]**
   1. **[!UICONTROL Update data]**
   ![](assets/update_profile0.png)

1. 設定 **[!UICONTROL Scheduler]** 活動。**[!UICONTROL General]** 在標籤中，設定( **[!UICONTROL Execution frequency]** 例如「每日」)、( **[!UICONTROL Time]** 例如「1：00：00AM」)和 **[!UICONTROL Start]** (例如今天的日期)。

   ![](assets/update_profile2.png)

1. 設定 **[!UICONTROL Incremental query]** 活動。
   1. 在 **[!UICONTROL Properties]** 標籤中按一下 **[!UICONTROL Select an element]****[!UICONTROL Resource]** 欄位的圖示，然後選取 **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 元素。

      ![](assets/update_profile3.png)

   1. **[!UICONTROL Target]** 在標籤中，拖曳 **[!UICONTROL Mobile application]** 篩選，然後選取行動應用程式名稱。

      ![](assets/update_profile4.png)

   1. 在 **[!UICONTROL Processed data]** 標籤中選取 **[!UICONTROL Use a date field]**，然後將 **[!UICONTROL Last modified (lastModified)]** 欄位新增為 **[!UICONTROL Path to the date field]**。

      ![](assets/update_profile5.png)

1. 設定 **[!UICONTROL Update data]** 活動。
   1. **[!UICONTROL Identification]** 在標籤中，確定 **[UICONHTROL維度更新]** 欄位設為「描述檔(描述檔)」，然後按一下 **[!UICONTROL Create element]** 按鈕以新增欄位做為協調標準。

      ![](assets/update_profile_createelement.png)

   1. **[!UICONTROL Source]** 在欄位中，選取AppsubscriptionRCP表格中的欄位做為協調欄位。它可以是描述檔的電子郵件、CRM、MarketingCloudID等。在此範例中，我們將使用「電子郵件(Cusemail)」欄位。
   1. **[!UICONTROL Destination]** 在欄位中，從描述檔表格中選取欄位，以協調appsubscriptionRCP表格中的資料。它可以是描述檔的電子郵件，或任何擴充欄位，例如CRM、MarketingCloudID等。在此範例中，我們需要選取「電子郵件(電子郵件)」欄位，將它與AppsubscriptionRCP表格中的「電子郵件(Cusemail)」欄位對應。

      ![](assets/update_profile7.png)

   1. **[!UICONTROL Fields to update]** 在標籤中按一下 **[!UICONTROL Create element]** 按鈕，然後將來自appsubscriptionRCP表格(**[!UICONTROL Source]** 欄位)的欄位對應至您要在描述檔表格&#x200B;**[!UICONTROL Destination]** (欄位)中更新的欄位。
   1. 在 **[!UICONTROL Enabled if]** 欄位中新增運算式，以確保只有當來源欄位包含值時，才會更新「描述檔」表格中的對應欄位。若要這麼做，請從清單中選取欄位，然後新增「！=運算式(如果「Source[」欄位是「運算式」編輯器中的「目標/@ CuseMail]」，請確實輸入「[target/@ CuseMail] ！」=」)。

      ![](assets/update_profile8.png)

      >[!NOTE]
      >
      >在這種情況下，「工作流程」會執行UPESLT，但因為它是以「增量查詢」資料為基礎才會插入。變更查詢會影響插入或更新的資料。
      >此外，「欄位要更新」標籤中的設定會決定在特定條件下插入或更新哪些欄位。這些設定對每個應用程式或客戶而言都是獨一無二的。設定這些設定時請小心謹慎，因為可能會有不預期的結果，因為在AppsubscriptionRCP資料中更新記錄可變更使用者的個人資訊而無需驗證。

   1. 新增「描述檔」中要插入/更新的所有欄位時，請按一 **[!UICONTROL Confirm]**&#x200B;下。

      ![](assets/update_profile9.png)

1. 儲存工作流程，然後按一下「開始」以啓動工作流程程序。

   ![](assets/update_profile10.png)
