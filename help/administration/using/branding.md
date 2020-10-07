---
title: 品牌推廣
description: 探索所有可用來管理品牌識別的工具。
page-status-flag: never-activated
uuid: d66ac5a2-2ae1-4870-b48e-7f276744ffdd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: cbb1dcec-3bc6-4013-87fa-27d0e5d32bf8
context-tags: branding,overview;branding,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 品牌推廣{#branding}

## 關於品牌識別 {#about-brand-identity}

每家公司都有品牌視覺化與技術準則。有了 Adobe Campaign，您可以定義一組規格，為客戶從標誌到技術層面呈現一致的品牌，例如電子郵件寄件者、URL 或網域。

技術管理員可定義一或多個品牌，以集中輸入影響品牌識別的參數。這包括品牌標誌、登錄頁面存取 URL 之網域或訊息追蹤設定。有了 Adobe Campaign，您可以建立這些品牌，並將其連結至訊息或登錄頁面。此設定在範本中管理。

## 設定與使用品牌 {#configuring-and-using-brands}

設定與使用品牌的主要原則為：

1. 建立與設定品牌操作需要特定權限，並由 Adobe Campaign 技術管理員執行。在Campaign中取得新品牌的步驟，請參閱 [本節](#creating-a-brand)。
1. 為此品牌建立一或多個傳遞與登錄頁面範本。請參閱[建立範本](../../start/using/marketing-activity-templates.md)區段。
1. 根據此範本建立訊息與登錄頁面。請參閱[建立電子郵件](../../channels/using/creating-an-email.md)及[建立登錄頁面](../../channels/using/designing-a-landing-page.md)區段。

>[!IMPORTANT]
>
>一般使用者不能建立或修改品牌：這些操作必須由 Adobe Campaign 技術管理員執行。如需任何請求，請與 Adobe 客戶服務聯繫。
>
>無法在交易式訊息的內容中使用多品牌推廣。如需詳細資訊，請參閱[交易式訊息與品牌推廣](../../channels/using/transactional-messaging-limitations.md#permissions-and-branding)。

可以在 **[!UICONTROL Administration > Instance settings > Brand configuration]** 功能表中找到品牌。

依照預設，新建立的品牌僅對管理員指派具有相對應權限的使用者可見。

**品牌**&#x200B;由以下特性所定義：

* **身分識別**&#x200B;可以定義並個人化您的品牌。本章節包含以下欄位：

   ![](assets/branding_01.png)

   * **標籤** 在此介面中可見
   * **品牌名稱**
   * 品牌的&#x200B;**網站 URL** 與&#x200B;**網站標籤**
   * **品牌標誌**

* **[!UICONTROL Header parameters of sent emails]** 可以個人化行銷活動的收件者所看到之內容。本章節包含以下欄位：

   ![](assets/branding_04_header.png)

   * 使用品牌電子郵件的&#x200B;**寄件者（電子郵件）**。
   * 使用品牌名稱的&#x200B;**寄件者（姓名）**。
   * 使用客戶可回覆的電子郵件地址&#x200B;**回覆（電子郵件地址）**。
   * 使用品牌名稱&#x200B;**回覆（姓名）**。
   * 使用的電子郵件有錯誤&#x200B;**的錯誤（電子郵件地址）**。

   >[!IMPORTANT]
   >
   >更新電子郵件的標題參數後，如果在範本建立的電子郵件中寄件者的姓名與電子郵件地址未更改時，請檢查範本的進階設定。

* **網際網路上公開的伺服器** 定義用於追蹤及登錄頁面存取的伺服器。本章節包含以下欄位：

   ![](assets/configure_branding_04.png)

   * **應用程式伺服器的外部 URL** 用於託管及存取您建立的不同登錄頁面 ，
   * **追蹤伺服器的外部 URL** 在傳遞期間為追蹤的 URL。
   * **鏡像頁面伺服器的外部 URL** 在傳遞期間為預設鏡像頁面。

   >[!NOTE]
   >
   >若要在 Campaign 使用者介面中顯示登入頁面預覽與鏡像頁面呈現，應用程式伺服器和鏡像頁面伺服器 URL 必須是安全的。在此情況下，在設定這些 URL 時，請使用 https://，而不是 http://。

* **[!UICONTROL Tracking URL configuration (Web Analytics)]**，定義您品牌的 URL 追蹤的設定。

   此處定義了允許在外部系統（例如，Adobe Analytics 或 Google Analytics 等 Web Analytics 之工具）上追蹤連結的其他參數。

   ![](assets/branding_05.png)

## Creating a new brand {#creating-a-brand}

您可以在Campaign中新增組織實體，或建立新類型的電子郵件，您需要在不同的子網域下傳送。 若要執行此動作，請依照下列步驟：

1. **委派新子網域** -對於Adobe要使用的任何新子網域，第一步是委派它。 您可以透過「促銷活 [動控制面板](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/subdomains-and-certificates/subdomains-branding.html) 」執行此動作，或聯絡Adobe技術聯絡人。 在本文中進一步瞭解子 [網域委派](https://helpx.adobe.com/tw/campaign/kb/domain-name-delegation.html)。

1. **建立票證** -一旦委派子網域後，Adobe就需要在您的生產環境中進行設定。 若要要求此 [項，請建立Client Care的票證](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html) ，並包含下列資訊：

   * 主旨：ACS新品牌設定

   * 內容：Adobe已委派新網域，我們希望在Campaign平台中設定它

   * 網域：XXX

   * 生產URL:XXX.campaign.adobe.com

1. **建立傳送範本** -新品牌推出後，最佳實務是建立至少一個參考此新品牌的新空白傳送範本。 [進一步瞭解](#linking-a-brand-to-a-template)。

1. **檢查傳遞性准則** -在開始使用新網域之前，應先與Adobe Deliverability團隊討論該策略。 例如，如果應建立新的相似性以在網域之間分割IP，以及／或應定義加速計畫，這些特性將有助於定義最佳實務。 在本節中進一步瞭解傳遞 [能力最佳實務](../../sending/using/about-deliverability.md)。

## 為電子郵件指派品牌 {#assigning-a-brand-to-an-email}

### 將品牌連結至範本 {#linking-a-brand-to-a-template}

必須將其連結至傳遞範本或登錄頁面範本，才能使用為品牌定義的參數。您必須建立或編輯範本，才能執行此操作。

>[!NOTE]
>
>如需建立範本的詳細資訊，請參閱「[建立範本](../../start/using/marketing-activity-templates.md)」一節。

建立範本後，您就可以將其連結至品牌。操作步驟：

1. 按一下 **[!UICONTROL Edit properties]** 按鈕以存取範本屬性。

   ![](assets/branding_04.png)

1. 使用下拉式清單來選取您要連結至範本的品牌。

   >[!NOTE]
   >
   >依照預設，會選取 **[!UICONTROL Default brand (branding)]**。

   ![](assets/branding_05.png)

   要檢視所選品牌的設定方式，請按 **[!UICONTROL Navigate to the detail of the element selected]** 圖示。

   ![](assets/branding_06.png)

1. 確認您所選的項目並儲存範本。

您的範本已連結至品牌。在電子郵件編輯工具中，「 **預設寄件者的電子郵件地址**」、「 **預設寄件者名稱**」或「 **Logo** 」等元素將使用已設定的品牌資料。

### 品牌推廣使用案例 {#branding-use-case}

在此範例中，我們將建立新的旅遊相關品牌，並在電子郵件中使用它。

#### 設定新品牌 {#configure-a-new-brand}

>[!IMPORTANT]
>
>品牌設定僅由 Adobe 管理，因為需要特定的權限與技術設定。

1. Adobe Campaign 管理員會在 **[!UICONTROL Administration > Instance settings > Brand configuration]** 中建立品牌。他從進階功能表新增 **Vacations in the Tropics** 元素，並設定 **[!UICONTROL ID]** 與品牌的 **[!UICONTROL Header parameters of sent emails]**。

   ![](assets/branding_07.png)

1. 然後，管理員會設定&#x200B;**在網際網路上公開之伺服器的 URL**，以便使用登錄頁面，並接著使用追蹤 URL。

   在此範例中，使用的 **Web Analytics** 工具是 **Google Analytics**。管理員會依以下方式設定追蹤 URL：

   ![](assets/branding_12.png)

已正確建立與設定該品牌。行銷團隊現在可以使用它了。

#### 實施新品牌 {#implement-a-new-brand}

身為傳遞經理，您負責使用新品牌建立傳遞範本。請遵循以下步驟完成此項目：

1. 在進階功能表 **[!UICONTROL Resources > Templates > Delivery templates]** 中，複製內建範本以設定新的傳遞範本。

   ![](assets/branding_08.png)

1. 若要將此範本連結至 **Vacations in the Tropics** 品牌，請編輯範本屬性，並從下拉式清單中選取品牌。

   ![](assets/branding_09.png)

1. 設定此電子郵件範本以反映此品牌識別。
1. 當範本完成後，您即可儲存。

   ![](assets/branding_10.png)

   現在可以使用傳遞範本建立將傳送給對象的電子郵件。

#### 在傳送中使用新品牌 {#use-the-new-brand-in-a-delivery}

若要建立連結至品牌的電子郵件，請遵循以下步驟：

1. 按一下 **[!UICONTROL Create]** 功能表中的 **[!UICONTROL Marketing activities]** 按鈕。

   ![](assets/branding_14.png)

1. 選取 **[!UICONTROL Email]** 活動，然後選取連結至新品牌的範本。

   ![](assets/branding_15.png)

1. 您的電子郵件已設定好。您可以先檢查資訊，再使用測試設定檔進行測試，然後將其傳送給您的對象。

   ![](assets/branding_16.png)

